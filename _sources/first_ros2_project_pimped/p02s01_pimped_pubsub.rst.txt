#########################################
Tutoriel ROS2 épicé
#########################################


*************************************
Rappels : setup ROS2
*************************************

Un projet ROS2 se compile et s'exécute dans ce que l'on appelle un ``workspace`` souvent abrévié en ``ws`` dans lequel se trouve un répertoire ``src`` qui contient les packages ROS2 que vous allez créer ou que vous allez utiliser.

.. code-block:: bash

   cd ~/info_indus/
   mkdir -p ros2_ws/src

Nous allons maintenant utiliser un package ROS2 que nous allons installer dans le répertoire ``src`` de votre workspace ROS2.

.. code-block:: bash

   cd ~/info_indus/ros2_ws/src
   git clone https://github.com/yguel/scara_tutorial_ros2.git

Afin d'accélerer les processus de compilation et d'exécution, nous allons utiliser des macros bash qui facilitent la tâche quand on utilise la suite d'outils ROS2 centrée sur ``colcon``.

Ouvrez votre fichier ``~/.bashrc`` avec vscode:

.. code-block:: bash

   code ~/.bashrc

Ajoutez à la fin du fichier les lignes suivantes:

.. literalinclude:: resources/code/_.bashrc
   :language: bash
   :caption: Addons au fichier .bashrc
   :linenos:

Enregistrez le fichier et fermez vscode.

Rechargez votre fichier ``~/.bashrc`` pour prendre en compte les modifications:

.. code-block:: bash

   source ~/.bashrc

Vous pouvez maintenant utiliser les macros bash que vous venez de définir.

*************************************************
Premiers pas avec le package scara_tutorial_ros2
*************************************************

Nous allons maintenant compiler le package ``scara_tutorial_ros2`` que nous venons de cloner à l'aide des macros bash que nous venons de définir.

.. code-block:: bash

   cd ~/info_indus/ros2_ws
   ros2_humble
   ros2_build

Si tout s'est bien passé, vous devriez voir un message de succès à la fin de la compilation.

.. note::

   ``ros2_humble`` est un alias qui charge l'environnement ROS2 de la distribution humble.
   ``ros2_build`` est un alias qui installe les dépendences et compile tout le workspace ROS2 courant.

===============================================
Créer la description URDF physique d'un robot 
===============================================

Pour créer la description URDF physique d'un robot, suivez dans l'ordre:

#. `tutoriel URDF <https://github.com/yguel/scara_tutorial_ros2/blob/main/resources/urdf_tutorial.md>`_
#. `Comment lancer et intéragir avec le système courant <https://github.com/yguel/scara_tutorial_ros2/blob/main/resources/launch_tutorial.md>`_