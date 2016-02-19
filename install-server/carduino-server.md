# Carduino-server
> Le code source de Carduino-server est hébergé sur le dépot Github [Carduino-server](https://github.com/Carduino/Carduino-server) de l'organisation [Carduino](https://github.com/Carduino).

### La statégie de déploiement de Carduino-server est la suivante :

1. Création d'un dépôt Git nu ainsi que d'un dossier de déploiement/d'exécution pour Carduino-server. 

2. Configuration d'un hook pour déployer automatiquement le contenu de ce dépôt dans le dossier d'exécution lors d'une modification du code (pull ou réception d'un push).

3. Cloner le dépôt GitHub hébergeant le code source en local, puis ajouter le dépôt Git du serveur en tant que dépôt distant.

4. Faire un push à destination du dépôt distant. Lorsque le serveur recevra la le push, le hook post-receive sera déclenché, et déploiera la mise à jour dans le dossier d'exécution.

> Les étapes 1 & 2 se déroulent donc sur le **serveur**, et les étapes 3 & 4 sur la **machine de développement**.


### Sur le serveur

#### 1. Création du dépôt Git et du dossier de déploiement/d'exécution

* ##### pour le dépôt
```bash
$ mkdir -p /var/repo/Carduino-server.git
$ cd /var/repo/Carduino-server.git
#gestion des droits
$ chown -R root:developers .
$ chmod -R g+rwX .
#initialisation d'un dépôt nu   
$ git init --bare --shared=developers
```

* ##### pour le déploiement/l'exécution
```bash
$ mkdir -p /var/www/Carduino-server
$ cd /var/repo/www/Carduino-server
#gestion des droits
$ chown -R root:developers .
$ chmod -R g+rwX .
```


#### 2. Creation du hook post-receive

* ##### création et ouverture du fichier
```bash
$ vim hooks/post-receive
```
* ##### édition du hook 
Entrer en mode insertion en appuyant sur la touche `i`, puis coller le code suivant :
```bash
#!/bin/sh
git --work-tree=/var/www/Carduino-server --git-dir=/var/repo/Carduino-server.git checkout -f
```
Quitter le mode insertion en appuyant sur la touche `esc`, puis enregistrer le fichier et quitter l'éditeur en appuyant sur la touche `shift` + `z` + `z`.
    
* Mettre les bons droits d'accès au fichier :
```bash
$ chmod +x hooks/post-receive
```


---


### Sur la machine de développement

#### 3. Clonage du dépôt Github et ajout du dépôt distant

* ##### Clonage du code source
```bash
$ cd chemin/vers/le/repertoire/parent/du/clone
$ git clone https://github.com/Carduino/Carduino-server.git
```
>Le chemin vers le dossier qui contiendra la copie locale du code source peut être librement choisie.

* ##### Ajout du dépôt distant
```bash
$ cd Carduino-server
$ git remote add production ssh://root@[ip_ou_ndd]/var/repo/neo-creators.git
```


#### 5. Déployer Carduino-serveur
```bash
$ git push production master
```
>`master` représente la branche du dépôt local qui va être poussée jusqu'au serveur. Si vous souhaitez modifier le code source, il serait bon de le faire dans une branche dédiée (par exemple une branche nommée `dev`ou `test`). Il faudra alors adapter la commande ci-dessus en conséquence. 