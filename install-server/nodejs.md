#NodeJS

##Installation de NodeJS
Installation de Curl et ajout des sources de NodeJS v5.x :
```bash
$ sudo apt-get install curl
$ sudo curl -sL https://deb.nodesource.com/setup_5.x | bash -
```

Installation de NodeJS :
```bash
$ sudo apt-get install --yes nodejs
$ sudo apt-get install --yes build-essential
```

Vérifier que NodeJS et npm soient bien installés :
```bash
$ node -v
# -> Devrait renvoyer la version de node (5.x)
$ npm -v
# -> Devrait renvoyer la version de npm (3.x)
```