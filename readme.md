# Administration système

## Qu'est-ce qu'un serveur ?

C'est une machine physique (ou non) destinée à être hautement disponible et accessible.

Plusieurs types:
- `Serveurs dédiés` : C'est une machine physique. Vous avez 100% du contrôle sur la machine
- `Serveurs mutualisés` : Vous n'avez pas la main dessus, vous êtes donc restreints. Plusieurs personnes / projets partagent le même serveur.
- `Serveur Virtuel Privé (VPS)` : C'est comme un serveur dédié, sauf qu'il est virtualisé au même titre qu'une VM.

## Choisir son serveur & son hébergeur

### Hébergeurs 

- OVH : https://www.ovhcloud.com/fr/
- Infomaniak : https://www.infomaniak.com/fr
- AWS : https://aws.amazon.com/fr/?nc2=h_home
- GCP : https://cloud.google.com/free

### Serveur

Les points d'attention : 

- Bande passante
- Stockage
- La puissance de calcul (RAM + Cores)
- Le prix
- SAV

## Les 7 travaux de l'adminSys

- Choisir le bon type d'hébergement
- Installer le serveur
- Coniguration du serveur
- Sécurisation du serveur
- Mise en productio du site
- Maintenir et surveiller le serveur
- Faire évoluer et migrer le serveur

## Plan de déploiement

1. Commander le serveur
2. Se connecter en SSH
3. Mettre à jour les paquets
4. Installer NodeJS. (via NVM)
5. Installer la Base de données
6. Créer la base de données
7. Configurer Github
8. Cloner le projet
9. Installer le projet
10. Configurer le projet (.env + BDD)
11. Démarrer l'application
12. Faire tourner l'application en tâche de fond
13. Rendre la chose accessible en ligne via un reverse proxy




