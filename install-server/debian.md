#Debian

##Procédure d'installation de Debian

1. Télécharger l'image iso de la version 8 de Debian (Debian Jessie)
    * [Debian 8.3.0 amd64.iso (netinst)](http://cdimage.debian.org/debian-cd/8.3.0/amd64/iso-cd/debian-8.3.0-amd64-netinst.iso)
    <br />
    <br />

2. Lancer l'image .iso et suivre le processus d'installation.
    >**Attention:** Penser à bien noter le mot de passe root.



3. Configurer les locales en anglais U.S. encodage UTF-8

    * Lancer l'utilitaire de configuration des locales :
    ```bash
    $ sudo dpkg-reconfigure locales
    ```

        * Sélectionner avec la barre d’espace : en_US.UTF-8 UTF-8
	    * Choisir la locale par défaut : en_US.UTF-8
<br />
<br />
	* Éditer le fichier de configuration des locales :

    ```bash
    $ sudo vim /etc/default/locale
    ```
        * Entrer dans le mode insertion `i` et ajouter la ligne : LC_ALL=en_US.UTF-8 
        * Quitter le mode insertion `esc`, puis enregistrer le fichier `shift`+`z`+`z`
<br />
<br />   
    * Redémarrer le serveur pour prendre les changements en compte :
    ```bash
    $ sudo reboot
    ```

4. Mettre le système à jour.

    ```bash
    $ apt-get update
    ```

5. Installer/Activer SSH si ce n'est pas déjà fait
    >La procédure dépend des cas de figure.









