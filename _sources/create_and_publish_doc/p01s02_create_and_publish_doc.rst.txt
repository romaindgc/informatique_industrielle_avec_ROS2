*******************
Création du projet
*******************

Ouvrir un terminal sous ubuntu en tapant `Ctrl+Alt+T` ou en recherchant `terminal` dans le menu de recherche ou en cliquant sur l'icone du terminal dans la barre de tâche.

.. _gnome_terminal_icon:
.. figure:: resources/img/gnome_terminal_icon.png
   :align: center
   :width: 30%

   Clickez sur l'icone du terminal

Dans votre home créez un répertoire pour le projet:

.. code-block:: bash

   mkdir -p ~/info_indus/info_indus_tutorial

Nous allons donc appeler ce projet `info_indus_tutorial`. 
Vous pouvez changer ce nom si vous le souhaitez, mais il faudra alors adapter tout le tutorial en conséquence.

À partir de maintenant et sans mention du contraire nous considérerons que vous êtes dans le répertoire du projet:

.. code-block:: bash

   cd ~/info_indus/info_indus_tutorial

Créer un répertoire ''.vscode'' dans le répertoire du projet et créer 2 fichiers vides dedans: ''settings.json'' et ''keybindings.json'':

.. code-block:: bash
   
   mkdir .vscode
   touch .vscode/settings.json
   touch .vscode/keybindings.json

================================================
Premiers pas avec l'éditeur (IDE) de code vscode
================================================

Nous allons maintenant utiliser un bon éditeur de code (très important pour la productivité) qui est `vscode <https://code.visualstudio.com/>`_ de Github.

Ouvrir le répertoire du projet avec vscode:

.. code-block:: bash

   code .

Maintenant vous allez remplir le fichier ''settings.json'' avec le contenu suivant:

.. literalinclude:: resources/code/.vscode/settings.json
   :language: json
   :caption: Fichier settings.json
   :linenos:

Et le fichier ''keybindings.json'' avec le contenu suivant:

.. literalinclude:: resources/code/.vscode/keybindings.json
   :language: json
   :caption: Fichier keybindings.json
   :linenos:

Et vous allez recharger vscode pour prendre en compte ces changements en tapant `Ctrl+Shift+P` puis en tapant `Developer: Reload Window`.


-----------------------------------
Installation des extensions vscode
-----------------------------------

Dans vscode vous allez cliquer sur l'icone 

.. _vscode_extension_icon:
.. figure:: resources/img/vscode_extension.png
   :align: center
   :width: 60%

   Clickez sur l'icone Extensions

Et vous allez installer les extensions suivantes qui seront très utile pour le cours:

Édition de code:
^^^^^^^^^^^^^^^^
#. Gremlins tracker by Nicolas Hoizey

   * ID: nhoizey.gremlins
   * permet de voir tous les charactères invisibles dans le code qui peuvent nous pourrir la vie

git:
^^^^
#. Git Graph by mhutchie

   * ID: mhutchie.git-graph

python:
^^^^^^^
#. Python by microsoft

   * ID: ms-python.python
#. Python Debugger by microsoft

   * ID: ms-python.debugpy

Documentation:
^^^^^^^^^^^^^^
#. Esbonio by Swyddfa

   * ID: swyddfa.Esbonio


c/c++/ embarqué:
^^^^^^^^^^^^^^^^
#. C/C++ by microsoft

   * ID: ms-vscode.cpptools

#. GDB Debugger - Beyond by coolchyni

   * ID: coolchyni.beyond-debug

#. vscode-valgrind by krosf

   * ID: krosf.vscode-valgrind

#. CMake Tools by microsoft

   * ID: ms-vscode.cmake-tools

#. Debug Visualizer by Henning Dieterichs 

   * ID: hediet.debug-visualizer

#. Hex Array Formatter by AloyseTech

   * ID: AloyseTech.hex-array-formatter


ROS2:
^^^^^
#. Uncrustify by Zachary Flower

   * ID: zachflower.uncrustify
   * allows to do good formatting for ROS2

Assistant IA:
^^^^^^^^^^^^^
#. GitHub Copilot by github

   * ID: GitHub.copilot
