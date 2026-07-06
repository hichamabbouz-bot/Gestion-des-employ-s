GestionRH est une application desktop Java Swing pour la gestion simple des employes et des departements.
Le projet est concu pour un contexte universitaire : architecture claire, code lisible, et separation simple des responsabilites.
Technologies utilisees
Java 21
Swing pour l'interface graphique
SQLite pour la base de donnees locale
JDBC pour l'acces aux donnees
Projet Java Eclipse classique, sans Maven
Fonctionnalites
Afficher la liste des employes
Ajouter, modifier et supprimer un employe
Rechercher des employes par mot-cle, statut et departement
Afficher la liste des departements
Ajouter, modifier et supprimer un departement
Rechercher un departement par nom
Initialiser automatiquement la base SQLite au demarrage
Architecture du projet
src/
├── model/
│   ├── Employe.java
│   └── Departement.java
├── dao/
│   ├── EmployeDAO.java
│   └── DepartementDAO.java
├── service/
│   ├── EmployeService.java
│   └── DepartementService.java
├── database/
│   ├── DBConnection.java
│   └── DatabaseInitializer.java
├── view/
│   ├── MainFrame.java
│   ├── EmployePanel.java
│   └── DepartementPanel.java
├── util/
│   ├── ValidationUtil.java
│   └── UIStyle.java
└── Main.java
Role des packages
model : contient les objets metier de l'application.
dao : contient les requetes SQL et l'acces a SQLite.
service : contient les validations et la logique metier simple.
database : contient la connexion SQLite et l'initialisation de la base.
view : contient l'interface graphique Swing.
util : contient les outils reutilisables, comme la validation et le style UI.
Base de donnees
L'application utilise une base SQLite locale :
data/gestion_rh.db
Au demarrage, DatabaseInitializer cree automatiquement :
le dossier data/ s'il n'existe pas
la base gestion_rh.db si elle n'existe pas
les tables departements et employes
quelques departements par defaut si la table est vide
Aucun serveur MySQL n'est necessaire.
Aucun mot de passe n'est necessaire.
Dependances
Les bibliotheques necessaires sont dans le dossier lib/ :
lib/sqlite-jdbc.jar
lib/slf4j-api-1.7.36.jar
lib/slf4j-nop-1.7.36.jar
Elles sont referencees dans le fichier .classpath du projet Eclipse.
Lancer le projet dans Eclipse
Ouvrir Eclipse.
Importer le projet GestionRH si necessaire.
Verifier que Java 21 est configure.
Ouvrir src/Main.java.
Clic droit sur Main.java.
Choisir Run As > Java Application.
Explication courte pour le professeur
L'application est separee en plusieurs couches pour garder un code propre.
La couche view gere uniquement l'interface Swing.
La couche service verifie les donnees avant les operations.
La couche dao execute les requetes SQL avec JDBC.
La couche database gere la connexion SQLite et cree la base automatiquement au demarrage.
Pourquoi SQLite ?
SQLite est adapte a une application desktop simple, car il fonctionne avec un fichier local.
Il ne demande pas de serveur, pas de configuration MySQL, et pas de mot de passe.
Cela rend le projet plus facile a lancer sur un autre ordinateur.
Auteur
Projet realise dans le cadre d'un projet Java universitaire.
