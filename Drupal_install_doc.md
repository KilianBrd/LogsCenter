# Documentation de l'installation drupal

Voici une documentation pour effectuer l'installation du CMS Drupal avec docker compose.

`
mkdir drupal
`
: Ajout du dossier drupal

`
cd drupal
`

`
mkdir nginx-conf
`
: Creation du dossier nginx-conf

`
nano nginx-conf/nginx.conf
`
: Ajout du fichier de config nginx :

```
server {
    listen 80;
    listen [::]:80;

    server_name your_domain www.your_domain;

    index index.php index.html index.htm;

    root /var/www/html;

    location ~ /.well-known/acme-challenge {
        allow all;
        root /var/www/html;
    }

    location / {
        try_files $uri $uri/ /index.php$is_args$args;
    }

    rewrite ^/core/authorize.php/core/authorize.php(.*)$ /core/authorize.php$1;

    location ~ \.php$ {
        try_files $uri =404;
        fastcgi_split_path_info ^(.+\.php)(/.+)$;
        fastcgi_pass drupal:9000;
        fastcgi_index index.php;
        include fastcgi_params;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        fastcgi_param PATH_INFO $fastcgi_path_info;
    }

    location ~ /\.ht {
        deny all;
    }

    location = /favicon.ico { 
        log_not_found off; access_log off; 
    }
    location = /robots.txt { 
        log_not_found off; access_log off; allow all; 
    }
    location ~* \.(css|gif|ico|jpeg|jpg|js|png)$ {
        expires max;
        log_not_found off;
    }
}
```

`
nano .env
`
: Ajout du fichier .env pour ajouter nos variables d'environnement MYSQL : 

```
MYSQL_ROOT_PASSWORD=root_password
MYSQL_DATABASE=drupal
MYSQL_USER=drupal_database_user
MYSQL_PASSWORD=drupal_database_password
```

`
nano .gitignore
`
: Ajout du fichier .gitignore qui permet d'ignore des fichier ou dossier lors d'un commit. Dans notre cas nous allon signoré le fichier : 
`
.env
`

`
nano docker-compose.yml
`
: Ajout du fichier docker-compose.yml pour ajouter nos containers.
```
version: "3"

services:
  mysql:
    image: mysql:8.0
    container_name: mysql
    command: --default-authentication-plugin=mysql_native_password
    restart: unless-stopped
    env_file: .env
    volumes:
      - db-data:/var/lib/mysql
    networks:
      - internal
  
  drupal:
    image: drupal:8.7.8-fpm-alpine
    container_name: drupal
    depends_on:
      - mysql
    restart: unless-stopped
    networks:
      - internal
      - external
    volumes:
      - drupal-data:/var/www/html
  
  webserver:
    image: nginx:1.17.4-alpine
    container_name: webserver
    depends_on:
      - drupal
    restart: unless-stopped
    ports:
      - 80:80
    volumes:
      - drupal-data:/var/www/html
      - ./nginx-conf:/etc/nginx/conf.d
      - certbot-etc:/etc/letsencrypt
    networks:
      - external
  
  certbot:
    depends_on:
      - webserver
    image: certbot/certbot
    container_name: certbot
    volumes:
      - certbot-etc:/etc/letsencrypt
      - drupal-data:/var/www/html
    command: certonly --webroot --webroot-path=/var/www/html --email sammy@your_domain --agree-tos --no-eff-email --staging -d your_domain -d www.your_domain

networks:
  external:
    driver: bridge
  internal:
    driver: bridge

volumes:
  drupal-data:
  db-data:
  certbot-etc:
```

`
docker-compose up -d
`
: pour lancer les containers.

Le Drupal est deployé avec succés.