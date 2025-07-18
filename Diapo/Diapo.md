---
marp: true

---
Titre: LogsCenter
Description: Log
Auteur: ~
URL: http://logscenter.fabienmcl.fr
Image: https://marp.app/og-image.jpg
---

---

# Sommaire :
<style>
section {
  font-size: 1.8em;
}
</style>

- Contexte  
- Besoin  
- Objectif  
- Fonctions Principales 
- Critères de Performances  
- Technique de Contraintes  
- Livrables  
- Matériel et Logiciel  
- Diagramme Cas d'utilisation  
- Diagramme de bloc 
- Réseau   
- Maquette

---

# Contexte : 

![alt text](image.png)

![alt text](image-1.png)              ![alt text](image-3.png)

---

# Besoin : 

<style>
section.besoin  {
  font-size: 2.5em;
}
</style>

- Site Web
- Génère des logs 
- Utiliser Rsyslog
- Préconisation de l'Agence National de la sécurité des Systèmes d'Information (ANSSI)



![alt text](image-5.png)

---

# Objectif : 

- Centraliser des Logs sur une Application Web

<img src="image-6.png" alt="Schéma" style="width: 100%;"/>

---

# Fonction Principales  : 

- Affichage des Logs
- Collecte des Logs 
- Charger un utilisateur par email

![alt text](image-10.png)




---

# Critères de Performances :
  
  - Rafraîchissement manuel de la page Web lors de l'ajout de nouveaux Logs

  ![alt text](image-11.png) 



---

# technique de Contraintes : 

- Coder en PHP 
- Utiliser Rsyslog
- Utiliser deux Machines Virtuelles

![alt text](image-7.png)

---

# Livrable :

- Deux Machines Virtuelles(Application et LogsCenter)
- La Documentation du Site Web 
- Les différents Diagrammes
- Repository Github
- Documentation d'Analyse de l'Anssi
- Tests de Validation

---

# Matériel et Logiciel :

- Deux Machines Virtuelles
- Rsyslog7
- Drupal 
- PHP 
- Github
- Mysql
- Visual Studio Code 


--- 

#  Diagramme Cas d'Utilisation :

![alt text](image-8.png)


---

# Diagramme de Bloc :

![alt text](image-9.png)

---

# Réseau :
