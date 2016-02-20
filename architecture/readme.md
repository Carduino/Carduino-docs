#Architecture du système Carduino
Le Système se décompose en 3 sous ensembles indépendants que sont :
* [Le serveur Carduino](server.md)
* [Le(s) Hub(s)](hub.md)
* [Le(s) capteur(s)](sensor.md)

>**Note:** La notion de temps réel dans le projet Carduino ne fait pas référence à garantir une transmission temps réel UDP entre les différents sous-systèmes du réseau (on est obligé d'utiliser un réseau TCP pour garantir la réception des données). Ici, la signification de temps-réel fait référence à la réactivité du système, c'est à dire une gestion  évènementielle et asynchrone des communications réseau qui soit full-duplex entre :
* Serveur &nbsp; &#185;<----------->&#8319; &nbsp; Hub
* Serveur &nbsp; &#185;<----------->&#8319; &nbsp; Client
* Hub &nbsp; &#185;<----------->&#8319; &nbsp; Capteur