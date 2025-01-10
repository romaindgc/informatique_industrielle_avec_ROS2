##################################
Utilisation des moteurs dynamixel
##################################

*************************************
Informations sur les moteurs
*************************************

Dans ce projet, nous utilisons les `moteurs AX-12 <https://emanual.robotis.com/docs/en/dxl/ax/ax-12a/>`_ de chez Dynamixel.   

Pour les piloter, nous utilisons le convertisseur de communication USB `U2D2 <https://emanual.robotis.com/docs/en/parts/interface/u2d2/>`_ pour contrôler les moteurs avec l'ordinateur.

*************************************
Exemple d'utilisation
*************************************

Dans cette partie, nous allons réaliser un exemple très simple pour prendre en main le contrôle des moteurs avec ROS2. Pour cela, nous allons nous appuyer sur un exemple de Dynamxiel.  

Dans un premier temps, suivre le tutoriel suivant **jusqu'à 1.13 min**  : `tutoriel <https://www.youtube.com/watch?v=E8XPqDjof4U&ab_channel=ROBOTISOpenSourceTeam>`_  

À travers cette partie du tutoriel, nous avons pu réaliser les branchements et préparer le dossier d'accueil.  

Clone le projet de l'exemple et le build
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Si vous possédez **ROS2 Humble**, vous pouvez suivre le tutoriel **jusqu'à 1.47min**.  
En cas d'une autre version de ROS2 ou d'erreurs, entrez la commande suivante pour cloner le projet github :  

.. code-block:: bash

   cd ~/robotis_ws/src && git clone -b humble-devel https://github.com/ROBOTIS-GIT/DynmaxielSDK

Une fois le projet cloné, entrez la commande suivante pour le build :

.. code-block:: bash
   cd ~/robotis_ws && colcon build --symlink-install


Le projet devrait se build sans erreur.  

Sourcer ROS2 
~~~~~~~~~~~~~

Dans le tutoriel, vous voyez la commande suivante :   

.. code-block:: bash

   source /opt/ros/VERSIONROS2/setup.bash


*NB : Dans la vidéo la version ROS2 est foxy*  

Pour éviter de le faire dans chaque terminal, nous allons l'ajouter au fichier bash.rc.   
Ainsi, ajoutez la commande précédente à la fin de votre bashrc.  
Pour modifier votre bashrc, entrez la commande suivante :  

.. code-block:: bash

   sudo nano ~/.bashrc


Ajoutez la commande puis faites Ctrl+S puis Ctrl+X, pour sauvegarder et quitter.  

Le groupe *dialout*
~~~~~~~~~~~~~~~~~~~~~

La partie s'arrête avec la commande suivante :  

.. code-block:: bash

   sudo usermod -aG dialout <linux_account>


Pour communiquer avec les moteurs, nous utilisons l'USB. Via la commande précédente dans le tutoriel, nous avons vu que nous communiquons via le port **ttyUSB0**.   
Pour pouvoir utiliser ce port, nous devons être inscrits dans le groupe **dialout** et la commande décrite précédemment nous permet de nous inscrire justement dans ce groupe.  

**NB :** Si vous ne connaissez pas votre *linux_account* vous pouvez utiliser la commande suivante pour l'afficher :  

.. code-block:: bash

   whoami

Une fois que vous vous êtes ajouté au groupe, redémarrez votre ordinateur (*il s'agit ici d'une sécurité d'Ubuntu* ). 

Pour vérifier que vous êtes bien inscrit au groupe, vous pouvez effectuer la commande suivante :  

.. code-block:: bash

   groups

Le groupe *dialout* devrait apparaître.  


Adaptation du code
~~~~~~~~~~~~~~~~~~~~

L'exemple que nous sommes en train de suivre est en réalité adapté aux moteurs XL430-W250. Ainsi, nous devons légèrement l'adapter pour qu'il fonctionne avec nos moteurs. Dans un premier temps, nous devons modifier les adresses.  

Changement des adresses
^^^^^^^^^^^^^^^^^^^^^^^^^

Dans l'exemple actuel, nous écrivons les données aux mauvais endroits dans les moteurs. Pour corriger cela, nous devons ajuster les adresses. Pour cela, rendez-vous dans le code de l'exemple, le fichier **read_write_node.cpp**. Si vous avez suivi la même nomenclature que dans l'exemple, la commande suivante devrait l'ouvrir : 

.. code-block:: bash

   cd ~/robotis_ws/src/DynamixelSDK/dynamixel_sdk_examples/src && code .

Changez les lignes 42 à 46 par le code suivant : 

.. code-block:: cpp

   // Control table address for X series (except XL-320)
   #define ADDR_OPERATING_MODE 255
   #define ADDR_TORQUE_ENABLE 24
   #define ADDR_GOAL_POSITION 30
   #define ADDR_PRESENT_POSITION 36

Pour connaitre les adresses à mettre, se référer à la `datasheet AX-12 <https://emanual.robotis.com/docs/en/dxl/ax/ax-12a/>`_  du moteur dans le tableau *Control Table of RAM Area*.  

*NB : le moteur AX-12 n'a pas de registre pour OPERATING_MODE, nous avons donc mis la valeur 255 pour être sûr de ne pas écrire dans un registre existant important.*  

Changement du protocole de communication
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Dans la documentation technique du moteur, nous pouvons également trouver qu'il communique en utilisant le protocole 1.0 et non 2.0 comme il est configuré dans le code. Pour changer cela, remplacez la ligne 49 par la ligne suivante : 

.. code-block:: cpp

   #define PROTOCOL_VERSION 1.0


Connaître le baudrate
^^^^^^^^^^^^^^^^^^^^^^^^^

Enfin, nous devons connaître le **baudrate** de nos moteurs pour pouvoir communiquer avec eux. En effet, nous devons parler et écouter à la même vitesse pour pouvoir se comprendre. Pour connaître le **baudrate** des moteurs, nous pouvons utiliser le logiciel `Wizard 2.0 <https://emanual.robotis.com/docs/en/software/dynamixel/dynamixel_wizard2/>`_ de chez Dynamixel. En scannant les moteurs, le logiciel va trouver le baudrate.    

Si vous rencontrez des difficultés à installer le logiciel, testez la valeur de bauderate suivante : 115200.  

Une fois la valeur du baudrate trouvée, modifiez la valeur dans le code à la **ligne 52**.  


De plus, ce logiciel permet également de contrôler les moteurs basiquement pour voir si ces derniers fonctionnent bien.  

Finir le tutoriel
~~~~~~~~~~~~~~~~~~~~

Une fois ces étapes réalisées, vous pouvez enfin terminer le `tutoriel <https://www.youtube.com/watch?v=E8XPqDjof4U&ab_channel=ROBOTISOpenSourceTeam>`_  .  
Les moteurs devraient tourner. 

**N'oubliez pas de sourcer votre environnement pour pouvoir lancer les nodes !** 

.. code-block:: bash

   cd ~/robotis_ws && source install/setup.bash


