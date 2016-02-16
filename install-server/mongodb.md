#MongoDB

##Installation de MongoDB

>Installation en utilisant le dépot apt MongoDB. Cette méthode permet au système de recevoir la dernière version de MongoDB considérée stable par la team MongoDB.

Ajout des keys MongoDB pour que le système reconnaisse les packages signés par MongoDB :
```bash
$ sudo apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10  
```

Ajout des dépots MongoDB aux sources du système :
```bash
$ echo "deb http://repo.mongodb.org/apt/debian wheezy/mongodb-org/3.2 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.0.list
```

Mise à jour de la liste des packages puis Installation de MongoDB avec apt-get :
```bash
$ sudo apt-get update
$ sudo apt-get install mongodb-org -y
```

Si vous voulez supprimer le dépot Mongo DB des sources de votre système par la suite, supprimez simplement le fichier suivant :
`/etc/apt/sources.list.d/mongodb-org-3.0.list`

##Configuration de MongoDB

>Attention, la configuration de MongoDB est une étape cruciale et très sensible !

Le contenu dce cette section n'est pas encore disponnible...