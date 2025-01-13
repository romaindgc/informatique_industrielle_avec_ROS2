####################
Montage du hardware
####################

La première étape pour construire notre mini-ordinateur consiste à assembler la Raspberry Pi 5 avec un ventilateur et une base NVMe, sur laquelle un disque SSD doit être préalablement installé. Cette section détaille les différentes étapes de l’assemblage.

*************************************
Montage du ventilateur sur la RPI5
*************************************

Nous débutons par l'installation du ventilateur sur la Raspberry Pi 5, en suivant `le tutoriel fourni avec le produit <https://datasheets.raspberrypi.com/cooling/raspberry-pi-active-cooler-product-brief.pdf>`_.

*************************************
Montage du disque
*************************************

Dans cette section, nous chercherons à monter le disque sur la base.  
Le disque que nous avons à disposition se présente comme ci-dessous :

.. figure:: resources/img/SSD.jpg
   :align: center
   :width: 30%

   Le disque SSD et le dissipateur thermique.

Nous identifions deux éléments : le disque SSD proprement dit et un dissipateur thermique (bleu). La première étape consiste à fixer le dissipateur sur le SSD. Pour cela, il suffit de retirer le film protecteur du dissipateur, puis de coller la partie adhésive sur le côté approprié du SSD (face visible du SSD sur la photo précédente).

Voici ci-dessous le SSD avec son dissipateur thermique fixé :

.. figure:: resources/img/carte_ssd.jpg
   :align: center
   :width: 30%

Nous pouvons maintenant commencer `ce tutoriel <https://learn.pimoroni.com/article/getting-started-with-nvme-base>`_ (faire le tutoriel jusqu'à la partie "Putting it Together" comprise), qui expliquera comment monter le disque sur la base, puis la base sur la Raspberry Pi.

.. note::

   Pour insérer le SSD dans la base, il est nécessaire de l’introduire avec un certain angle. Inutile de forcer, il s’insère facilement. L’image ci-dessous illustre cette étape :

   .. figure:: resources/img/base_ssd.jpg
      :align: center
      :width: 30%

      Illustration de l'insertion du SSD dans la base.

   Nous ne souhaitons pas ajouter "un chapeau" sur le RPI5 ainsi les petites vis suffiront.

Une fois le tutoriel réalisé, nous avons fini l'assemblage des différents composants. Il nous reste à présent à nous occuper du software.
