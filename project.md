# Le projet

## Contributeurs

Le système Carduino a entièrement été développé dans le cadre des Projets de 2ème année de l'ESTIA par une équipe composée de 4 étudiants :
* [Vincent Dauliac](https://www.linkedin.com/in/vincentdauliac)
* Marc Dando
* [Alexandre Marcuzzo](https://www.linkedin.com/in/alexandre-marcuzzo-82a182109)
* [Bruno Caquinaud](https://www.linkedin.com/in/bruno-caquinaud-280354109)

L'équipe a été chapeautée par __Guillaume Terrasson__, Enseignant-chercheur à l'ESTIA, qui a joué le rôle de client et de tuteur, et par [__Patrick Guennec__](https://www.linkedin.com/in/patrick-guennec-1724a343), intervenant extérieur, qui a coaché l'équipe sur l'aspect organisationnel.


## Contexte

Depuis de nombreuses années, le marché des __objets connectés__ ([IoT](https://fr.wikipedia.org/wiki/Internet_des_objets)) ne cesse de croître. Les applications de ce type d'objets au __domaine de la santé__ laissent notamment espérer l'amélioration des conditions de vie des personnes à risque en leur permettant de rester à leur domicile tout en bénéficiant d'une surveillance de leurs constantes vitales à distance. Néanmoins, ce type application de  mesure des signes vitaux nécessite :
* Le développement de __dispositifs d'acquisition miniaturisés, autonomes et fiables__ pouvant être portés temporairement ou de façon permanente sans gêner l'individu.

* Une __architecture réseau__ permettant de collecter des données en __temps réel__ via une liaison sans fil avec les différents dispositifs d'acquisition.

* Un moyen sécurisé et ergonomique de visualiser les données ainsi acquises pour en extraire une valeur ajoutée.

C’est donc dans un contexte **Santé** / **Iot** / **Data-viz** que s’inscrit le projet Carduino.


## Objectifs

Ce projet a pour but l'étude et la réalisation d'un démonstrateur appliqué au monitoring cardiaque composé :
* De **mini-cardiofréquencemètres autonomes** en énergie et portables dont les données seront transmises à un concentrateur local via une liaison sans fil.

* De **concentrateurs locaux** (hubs) permettant de récupérer localement les données transmises par les mini-cardiofréquencemètres.

* D'un **serveur** permettant de centraliser et de traiter l'ensemble des données collectées pour d'offrir aux utilisateurs finaux la possibilité de les visualiser.

Ce "système Carduino" se doit d'être conçu de manière à pouvoir être facilement **ré-utilisé et modifié**, dans le but de prendre part aux futures **activités pédagogiques** (TP, cours) et de **recherche** (capteurs autonomes, énergie, collecte de données) de l'ESTIA.

Ces aspects d'ouverture et d'utilisation future du projet impliquent qu'en plus de fournir un démonstrateur fonctionnel, une documentation complète doit être créée et maintenue à jour, et que l'ensemble du système se base sur du matériel et des logiciels **open-source**.