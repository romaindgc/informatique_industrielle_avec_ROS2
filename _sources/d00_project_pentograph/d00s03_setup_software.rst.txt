##################
Setup du software
##################

*************************************
Installer Ubuntu sur la Raspberry Pi 5
*************************************

Dans cette section, nous allons installer Ubuntu sur la Raspberry Pi 5.  
Nous disposons d’une carte SD pré-programmée avec l’OS Raspberry Pi. La première étape consiste à insérer cette carte SD dans la Raspberry Pi, comme indiqué sur l'image ci-dessous :

.. figure:: resources/img/sd_rasberry.jpg
   :align: center
   :width: 30%

   Insertion de la carte SD dans la Raspberry Pi.

Ensuite, branchez une souris et un clavier aux ports USB de la Raspberry Pi. Connectez également un écran via le port HDMI, puis alimentez la Raspberry Pi 5 à l'aide de l'alimentation fournie.

.. figure:: resources/img/branchement_rpi.jpg
   :align: center
   :width: 30%

   Connexion des périphériques à la Raspberry Pi.

Une fois la Raspberry Pi allumée et connectée à Internet, rendez-vous sur le site suivant : `Ubuntu.com <https://ubuntu.com/download/raspberry-pi>`_.  
Sur ce site, vous trouverez les instructions pour installer le logiciel *rpi-imager*, qui permet de flasher un périphérique de stockage (disque dur, carte SD, etc.).  

Dans notre cas, nous allons flasher un disque dur avec l'image d'Ubuntu 24.04.1. Téléchargez la version indiquée sur l'image ci-dessous (bouton vert), disponible sur la même page :

.. figure:: resources/img/ubuntu2401LTS.png
   :align: center
   :width: 30%

   Téléchargement de l’image Ubuntu 24.04.1 LTS.

Après avoir téléchargé le fichier, lancez le logiciel *rpi-imager*.

.. figure:: resources/img/rpi-imager.png
   :align: center
   :width: 30%

   Interface du logiciel rpi-imager.

Dans le logiciel, procédez comme suit :

#. **Device** : Sélectionnez la Raspberry Pi 5.  
#. **OS** : Choisissez le fichier Ubuntu 24.04.1 que vous venez de télécharger.  
#. **Storage** : Sélectionnez le disque dur.  


Le disque dur sera ensuite flashé avec l’image d’Ubuntu.
