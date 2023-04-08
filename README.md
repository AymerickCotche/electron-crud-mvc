# Electron.js APP - MVC schema

## Avant propos
Clonez le repo et faites un "npm install" pour installer les modules de node_modules.  

Si vous utilisez MySql, vérifiez les informations de connection du fichier databasemysql.js se trouvant dans /app/databasemysql.js. Tout les fichiers en doubles sont différencié par le mysql à la fin car l'autre fichier est utilisé pour une base postgresql.  

Lancer le projet en faisant "npm start".

## But MVC
J'ai essayé dans ce repo de reproduire une architecture MVC se rapprochant de ce qu'il se fait lors d'un déploiement frontend/backend avec une app web et une API, en un seul serveur tout en respetant le SOC (separation of concerns)
### Explications

- Le fichier d'entré est main.js, il se trouve à la racine du projet.
- Le dossier src contient les fichiers en lien avec l'interface (html + javascript)
- Le dossier app contient les données en lien avec la BDD (modèles et controlleurs)

### Workflow

Les datas circulent de cette façon:
- La page html se charge et appelle le/les scripts JS associés
- Le script JS appelle la méthode de controlleur nécessaire
- Le contolleur fait appelle au modèle afin de lancer une requête à la BDD
- Le modèle retourne la/les données au controlleur
- Le contolleur retourne les données au script JS
- la page HTML affiche les datas issus du script JS