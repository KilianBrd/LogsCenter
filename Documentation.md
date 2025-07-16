# Résumé du Document sur la Journalisation Sécurisée

## Objectifs

Ce document a pour but de donner des recommandations pour mettre en place un système de journalisation sécurisé.  
L’idée est d’adapter ces conseils en fonction des risques et des besoins spécifiques de chaque système d’information.

## Points Principaux

### Journalisation globale

Il est recommandé de commencer par un ensemble d'élement minimal, donc un ensemble d'événements à journaliser en priorité. Cela inclut :

- Les connexions
- L’accès aux ressources
- Les changements dans la configuration
- Les événements liés au réseau
- Les alertes de sécurité

Il faut faire attention à ne pas collecter trop de données , car certains types d'événements peuvent générer un volume très important.

### La journal doit contenir : 

Pour qu’un événement soit utile, il doit permettre d’identifier clairement la source (machine, utilisateur, processus, etc.).  
Dans certains cas, il peut même être obligatoire légalement de conserver des journaux, surtout pour pouvoir analyser ce qu’il s’est passé après un incident.

### Aspects Techniques

- Il vaut mieux utiliser les fonctionnalités de journalisation déjà intégrées dans les systèmes.
- Tous les événements doivent être horodatés, c’est-à-dire marqués avec la date et l’heure.
- En général, les logs sont stockés en local, souvent compressés, donc il faut prévoir assez d’espace disque.
- Il est important de prévoir une copie des logs vers une autre machine, pour qu’ils soient conservés ailleurs en cas de problème.

### Transfert des Journaux

Voici les deux façon d'envoyé les logs vers une autre machine:

1. En temps réel : C’est rapide, mais ça utilise pas mal de bande passante.
2. En différé : Moins gourmand, mais les journaux arrivent avec du retard et peuvent être perdus entre deux envois si un incident survient.

### Qui Peut Accéder aux Journaux ?

- Les droits d’écriture doivent être très limités, uniquement aux comptes qui en ont besoin.
- La suppression de journaux ne devrait être possible que pour des comptes d’administration spécifiques.
- L’accès en lecture aussi doit être restreint selon les rôles.

### Recommandations Avancées

Pour les organisations qui ont déjà un bon niveau en cybersécurité, des recommandations renforcées existent.  
Elles demandent souvent une réévaluation régulière pour améliorer le dispositif.

### Attaques et Journalisation

Il faut adapter la journalisation aux types d’attaques possibles.  
Pour cela, plusieurs outils sont utiles :

- MITRE ATT&CK : Pour comprendre les techniques utilisées par les attaquants.
- SIGMA : Pour créer des règles de détection.
- DetectionLab et Atomic Red Team : Pour tester la détection dans un environnement simulé.

### Conseils Pratiques

- Toujours partir du principe que le système peut être compromis.
- Chercher les signaux faibles comme une tentative de prise de contrôle, ou des élévations de privilèges.
- Il est conseillé de tester les configurations dans un environnement à part avant de les appliquer en production.

## Conclusion

La journalisation est un élément indispensable pour bien sécuriser un système informatique.  
Il faut y aller progressivement, en commençant petit, puis en complétant.  
Enfin, la collaboration entre les équipes qui s’occupent des logs et celles qui détectent les menaces est très importante pour que tout soit bien coordonné.

---

### Ce qui va être fait : 
- Tous les points de la journalisation globale.
- Va être stocké : le type, la date, l'utilisateur et le message.
- Les droits seront gérés selon un role admin et un role user.

### Ce qui ne va pas être fait :
- La sécurité plus avancée, par manque de temps.