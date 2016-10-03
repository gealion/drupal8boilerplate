# Mise en Place d'un Projet Drupal 8

## Machine Local de développement

La machine de développement est basé sur la box Vagrant [DrupalVM](www.drupalvm.com).
Les choix techniques des services dépendent de la stack choisit pour l'hébérgement.


## Installation de drupal et de ces dépendances

## Strucure des fichiers
### Séparation de la box et du site
Pour éviter les problème de versionning et de déployment, les fichiers de la box Vagrant et de Drupal ne doivent pas se situer dans un seul chemin.

 - Vagrant/NomDuProjet  
 - Sites/NomDuProjet 


### Configuration locale
Le fichier `settings.php`doit être commun et versionné. La configuration locale doit être déporté dans un fichier `settings.local.php` en décommentant le snipet de code suivant en fin du fichier `settings.php`

```
if (file_exists(__DIR__ . '/settings.local.php')) {
   include __DIR__ . '/settings.local.php';
 } 
```

### Fichier de configuration 
Les fichier YAML de la configuration drupal doivent être déporté à l'exterrieur du docroot drupal dans un dossier config :

```
$config_directories = array(
  CONFIG_SYNC_DIRECTORY => '../config/sync',
);
```



## Versionning 

## Configuration de Drupal
