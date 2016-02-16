#MongoDB

##Installation de MongoDB

>Ajouter les keys MongoDB pour que le système reconnaisse les packages signés par MongoDB et leur fasse confiance.

```bash
	sudo apt-key adv --keyserver keyserver.ubuntu.com --recv 7F0CEB10  
```

>Ajout de leur dépot aux sources du système.

```bash
	echo "deb http://repo.mongodb.org/apt/debian wheezy/mongodb-org/3.2 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.0.list
```

> mise à jour de la liste des packages puis Installation de MongoDB avec apt-get

```bash
	sudo apt-get update
	sudo apt-get install mongodb-org -y
```
Installation en utilisant le dépot apt MongoDB.

Cette méthode permet au système de recevoir la dernière version de MongoDB considérée stable par la team MongoDB.

Si vous voulez supprimer le dépot Mongo DB des sources de votre système par la suite, supprimer simplement le fichier suivant :
`/etc/apt/sources.list.d/mongodb-org-3.0.list`