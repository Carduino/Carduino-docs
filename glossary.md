# Prérequis

Cette section détaille l'ensemble des technologies/librairies utilisées. La suite de la documentation

## Système d'exploitation

<img class="logo" src='images/debian-logo.png' alt='Logo Debian' />

L'ensemble du système informatique à été développé pour une utilisation optimale sur des systèmes Linux (Debian pour le serveur et Raspian pour les concentrateurs).
Néanmoins,

Il est possible, sans portage particulier, de lancer le serveur sur la plus part des système Linux (Debian, Ubuntu, Fedora, etc), ainsi que d'autres systèmes UNIX comme Mac-OSX ou FreeBSD. Il est théoriquement possible de lancer le serveur sur des plateformes Windows, mais certaines dépendances et parties de code spécifiques devront êtres portés.

Concernant les concentrateurs, Il est possible d'utiliser différentes distributions de Linux, mais la partie concernant l'acquisition des données (les communications via le GPIO du Raspberry Pi) devra certainement être adaptée.

À l'heure actuel, Raspbian se base sur la dernière version de Debian (version 8 / Debian Jessie). Les OS de tous le système carduino font donc preuve d'une certaine unité qui facilite le travail.



## terminal SSH

> Connexion SSH vers un serveur :

```bash
	ssh -p 'port du serveur' 'utilisateur'@'IP ou ndd'
```

> Déconnexion : **`Ctrl + d`**

<img class="logo" src='images/ssh-logo.png' alt='Logo Iterm' />

L'installation/configuration/lancement de tout le système se fait quasi-systématiquement via SSH.

Il faut donc disposer d'un terminal permettant d'établir une connexion SSH sur la machine utilisée pour installer/configurer/lancer le système Cardiuno. C'est le cas de tous les Linux et de Mac-OSX. Pour windows, il faudra passer par un logiciel comme `PuTTY`, ou d'une machine virtuelle Linux pour disposer d'un terminal performant.



## Node.JS - Javascript ES-2016

<img class="logo" src='images/nodejs-logo.png' alt='Logo Javascript' />

Javascript est le language principal du système. Sa compréhension est indispensable pour comprendre/modifier le système carduino. Il à l'avantage de ne pas nécessiter de compilation, d'être cross-platform, facile à apprendre, multi-paradigme, de plus en plus populaire, de disposer nativement de fonctionnalités réseau avancées, de fédérer une grande communauté de programmeurs, et d'être un des languages de script les plus rapides.

La partie Client du système fait également un usage intensif de Javascript, on peut donc parler de système full-stack Javascript.



## MongoDB - Mongoose ORM

<img class="logo" src='images/mongodb-logo.png' alt='Logo MongoDB' />

L'ensemble des données amassées par le réseau de capteur est stocké sur une base de donnée No-SQL MongoDB.
Cette base de donnée est :
Orientée documents
Rapide
Manipule des Objets JSON/BSON
Hautement scalable
Souple d'utilisation
Adaptée aux infrastuctures complexes (Clouds, Shards, Replica-sets, etc.)
Adaptée a de grandes quantitées de données.

L'accès à cette base de donnée au sein du serveur sera fait via l'ORM Mongoose, permettant d'établir des modèles et de structurer les données.
Pour un accès direct à la base de donnée, il est recommandé d'utiliser des clients comme MongoChef, MongoHub ou RoboMongo.



## Express.js - Connect.js

Express.js, basé sur connect, est le framework de base utilisé par le serveur Carduino.
Il permet de gérer les communications, les routes (urls / API RESTFull) du serveur, l'authentification, etc.
Il fonctionne grâce à un enchainnement de middlewares.


## Feathers.js

<img class="logo" src='images/feathers-logo.png' alt='Logo Feathers' />

Feathers.js est une couche d'abstraction au dessus d'express, qui permet la mise en place de services avec un accès commun via une API REST ainsi qu'une API temps-réel (dans notre cas via socket.io).
Notre api n'est donc déclarée qu'une fois dans le code source, et permet par exemple de réaliser des opérations BDD et de s'authentifier grace a des méchanismes commun, puis de répondre au client via le bon canal de communication automatiquement.



## Socket.IO - Websockets

<img class="logo" src='images/socketio-logo.png' alt='Logo SocketIO' />

En plus de l'API RESTFull, le serveur dispose également d'une API temps réelle réactive (système de Push) via websockets. Socket.IO est la librairie permettant de gérer les websockets, d'établir des rooms, et de gérer les connexions/reconnexion.



## Jade - HTML5

L'interface web se base sur du HTML5. Il sera généré côté serveur grace au pré-processeur/Moteur de template JADE, dont la syntaxe épurée se base sur l'indentation (syntaxe type HAML).



## Stylus - CSS3

La mise en forme de l'interface web se base sur CSS3. Il sera généré coté serveur  grace au pré-processeur Stylus, dont la syntaxe épurée se base sur l'indentation (syntaxe type SASS/SCSS améliorée).