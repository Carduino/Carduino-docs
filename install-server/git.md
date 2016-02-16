#Git

## Procédure d'installation de Git

Assurez vous que la liste des packages du système est bien à jour, puis installez Git.

```bash
$ sudo apt-get update
$ sudo apt-get install git-core
```

##Configuration minimale de Git


Git implémente la gestion de version à partir de deux paramètres pricipaux.

Paramètre | Description
--------- | -----------
user.name | Un nom d'utilisateur
user.email | L'email de l'utilisateur

Ces informations se retrouveront dans chaque commit que vous ferez avec Git, qui pourra donc identifier l'auteur de chaque modification.

Définir le username de Git
```bash
$ git config --global user.name "Votre nom"
```

Définir l'email de Git
```bash
$ git config --global user.email sammy@example.com
```