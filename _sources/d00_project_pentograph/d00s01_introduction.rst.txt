#############
Introduction
#############

*************************************
Objectif du tutoriel
*************************************
Notre objectif est d'ajouter un disque SSD à une Raspberry Pi 5 à l'aide d'une base NVMe. Cela nous permettra d'avoir un ordinateur performant à portée de main.

Cette fonctionnalité est rendue possible grâce à la nouvelle interface PCIe du Raspberry Pi 5, qui offre la possibilité d'ajouter un stockage rapide et de grande capacité. Le PCIe (Peripheral Component Interconnect Express) est une norme d'interface permettant de connecter des composants haute vitesse, tels que des dispositifs de stockage externes, des cartes graphiques ou des hubs USB.

La base NVMe de Pimoroni permet de connecter un SSD NVMe au connecteur PCIe en ruban du Pi 5, transformant ainsi le Raspberry Pi en un ordinateur de bureau réactif, un lecteur multimédia performant, un serveur de fichiers pour vos photos, musiques et documents, ou encore un serveur de sauvegarde pour votre PC.

*************************************
Liste du matériel 
*************************************

#. `Raspberry PI 5 <https://www.raspberrypi.com/products/raspberry-pi-5/>`_ ~ RPI5
#. 27W Power supply
#. micro SD card pre-programmed with Raspberry Pi OS
#. `Active cooler <https://www.raspberrypi.com/products/active-cooler/>`_ (Raspberry PI 5 offical)
#. `NVMe Base <https://shop.pimoroni.com/products/nvme-base?variant=41219587178579>`_  
#. `SSD <https://www.adata.com/fr/consumer/category/ssds/solid-state-drives-legend-700/?tab=description>`_  (storage)

*****************
Spécification RPI5
*****************

Voici quelques caractéristiques techniques  de la Raspberry PI 5 : 
 * Dual 4Kp60 HDMI® display output with HDR support  
 * LPDDR4X-4267 SDRAM (8GB)
 * Bluetooth 5.0 / Bluetooth Low Energy (BLE)
 * microSD card slot, with support for high-speed SDR104 mode
 * 2 × USB 3.0 ports, supporting simultaneous 5Gbps operation
 * 2 × USB 2.0 ports
 * Gigabit Ethernet, with PoE+ support (requires separate PoE+ HAT)
 * 5V/5A DC power via USB-C, with Power Delivery support
 * Real-time clock (RTC), powered from external battery
 * Power button

 Voir le site de `Raspberry <https://www.raspberrypi.com/products/raspberry-pi-5/>`_ pour plus de détails.

*******************
Spécification strorage
*******************

Voici quelques caractéristiques techniques  du Solid State Drive : 
 * Capacité : 256GB 
 * Mémoire flash NAND : 3D NAND 
 * Lecture séquentielle (max) : Jusqu’à 2 000 Mo/s
 * Ecriture séquentielle (max) : Jusqu’à 1 600 Mo/s

Voir le site de `SSD <https://www.adata.com/fr/consumer/category/ssds/solid-state-drives-legend-700/?tab=description>`_ pour plus de détails.
La base NVMe permet d'acceuillir le SSD afin de le lier à la RPI5.