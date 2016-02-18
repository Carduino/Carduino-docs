# Carduino-server



### Sur le serveur

#### Création du dossier du dépot Git :

```bash
$ mkdir -p /var/repo/Carduino-server.git
$ cd /var/repo/Carduino-server.git

$ chown -R root:developers .
$ chmod -R g+rwX .
```

#### Création du dépot :
```bash
$ git init --bare --shared=developers

$ vim hooks/post-receive
    -> remplacer le contenu du fichier par :
        #!/bin/sh
        git --work-tree=/var/www/neo-creators.com --git-dir=/var/repo/neo-creators.git checkout -f

$ chmod +x hooks/post-receive
```

---


### Sur la machine de développement



#### Clonage du dépot Github

>Le code source de Carduino-server est hébergé sur le dépot Github [Carduino-server](https://github.com/Carduino/Carduino-server) de l'organisation [Carduino](https://github.com/Carduino).

```bash
$ git clone https://github.com/Carduino/Carduino-server.git
```