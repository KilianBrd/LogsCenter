# LogsCenterWeb appli
Lien github : https://github.com/KilianBrd/LogsCenterWeb


# LogsCenter
 1  sudo mkdir .ssh/
    2  ls
    3  ls -la
    4  cd .ssh/
    5  sudo touch authorized_keys
    6  sudo nano authorized_keys
    7  exit
    8  docker run hello-world
    9  sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
   10  sudo chmod +x /usr/local/bin/docker-compose
   11  docker-compose --version
   12  su - user0
   13  docker --version
   14  ls
   15  sudo systemctl status rsyslog
   16  exit
   17  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   18  clear
   19  for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done
   20  sudo apt-get update
   21  sudo apt-get install ca-certificates curl
   22  sudo install -m 0755 -d /etc/apt/keyrings
   23  sudo curl -fsSL https://download.docker.com/linux/debian/gpg -o /etc/apt/keyrings/docker.asc
   24  sudo chmod a+r /etc/apt/keyrings/docker.asc
   25  echo   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
   26    $(. /etc/os-release && echo "$VERSION_CODENAME") stable" |   sudo tee /etc/apt/sources
   27  sudo apt-get update
   28  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   29  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   30  echo   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/debian \
   31    $(. /etc/os-release && echo "$VERSION_CODENAME") stable" |   sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   32  sudo apt-get update
   33  sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   34  sudo docker run hello-world
   35  sudo apt update && sudo apt upgrade -y
   36  sudo apt install ca-certificates curl gnupg lsb-release -y
   37  sudo mkdir -p /etc/apt/keyrings
   38  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
   39  echo   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
   40    https://download.docker.com/linux/ubuntu \
   41    $(lsb_release -cs) stable" |   sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   42  sudo apt update
   43  sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
   44  docker --version
   45  docker run hello-world
   46  sudo usermod -aG docker $USER
   47  newgrp docker
   48  ssh log
   49  exit
   50  ls
   51  ls -la
   52  sudo systemctl status rsyslog*
   53  sudo systemctl status rsyslog
   54  zcat /usr/share/dbconfig-common/data/rsyslog-mysql/install/mysql | mysql -u root -p Syslog
   55  zcat /usr/share/dbconfig-common/data/rsyslog-mysql/install/mysql | mysql -u rsyslog -p Syslog
   56  clear
   57  mysql -u rsyslog -p -e "USE Syslog; SHOW TABLES;"
   58  sudo systemctl restart rsyslog
   59  sudo systemctl status rsyslog
   60  sudo journalctl -u rsyslog -f
   61  sudo apt update
   62  sudo apt install rsyslog-mysql
   63  sudo mysql
   64  zcat /usr/share/dbconfig-common/data/rsyslog-mysql/install/mysql | mysql -u root -p Syslog
   65  mysql -u root -p -e "USE Syslog; SHOW TABLES LIKE 'SystemEvents';"
   66  sudo systemctl restart rsyslog
   67  sudo journalctl -u rsyslog -f
   68  sudo zcat /usr/share/dbconfig-common/data/rsyslog-mysql/install/mysql.gz | mysql -u root -p Syslog
   69  sudo mysql
   70  sudo -u root -p
   71  mysql -u root -p
   72  ls /usr/share/dbconfig-common/data/rsyslog-mysql/install
   73  mysql -u root -p -e "USE Syslog; SHOW TABLES LIKE 'SystemEvents';"
   74  sudo mysql
   75  mysql -u root -p
   76  sudo systemctl restart mysql
   77  sudo systemctl restart rsyslog
   78  sudo systemctl status rsyslog
   79  logger "TEST"
   80  mysql -u root -p



#Commandes dans mysql 

show\040databases;
use\040Syslog;
show\040tables;
exit
use\040Syslog;
CREATE\040TABLE\040SystemEvents\040(
\040\040ID\040INT\040UNSIGNED\040NOT\040NULL\040AUTO_INCREMENT\040PRIMARY\040KEY,
\040\040ReceivedAt\040DATETIME,
\040\040DeviceReportedTime\040DATETIME,
\040\040Facility\040SMALLINT,
\040\040Priority\040SMALLINT,
\040\040FromHost\040VARCHAR(60),
\040\040Message\040TEXT,
\040\040InfoUnitID\040INT,
\040\040SysLogTag\040VARCHAR(60)
);
CREATE\040TABLE\040SystemEvents\040(\040\040\040ID\040INT\040UNSIGNED\040NOT\040NULL\040AUTO_INCREMENT\040PRIMARY\040KEY,\040\040\040ReceivedAt\040DATETIME,\040\040\040DeviceReportedTime\040DATETIME,\040\040\040Facility\040SMALLINT,\040\040\040Priority\040SMALLINT,\040\040\040FromHost\040VARCHAR(60),\040\040\040Message\040TEXT,\040\040\040InfoUnitID\040INT,\040\040\040SysLogTag\040VARCHAR(60)\040);
exit
use\040Syslog;
select\040*\040from\040SystemEvents\040where\040message\040like\040'%TEST%';
exit
