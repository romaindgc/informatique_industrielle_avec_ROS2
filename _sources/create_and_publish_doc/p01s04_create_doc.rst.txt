**********************************************
Création d'une première documentation sphinx
**********************************************

=======================
Installer sphinx
=======================

.. code-block:: bash

   sudo apt-get install python3-sphinx

Créer un répertoire pour la documentation:

.. code-block:: bash

   mkdir doc

Créer un fichier requirments.txt pour les dépendances de la documentation:

.. code-block:: bash

   touch ~/info_indus/info_indus_tutorial/doc/requirements.txt

Ajouter les dépendances suivantes dans le fichier ``requirements.txt`` avec vscode:

.. literalinclude:: ../../../requirements.txt

Installer les dépendances:

.. code-block:: bash
   cd ~/info_indus/info_indus_tutorial/doc/sphinx
   python3 -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt


=======================
Créer la documentation
=======================

Initialiser la documentation avec les outils sphinx:

.. code-block:: bash

   cd ~/info_indus/info_indus_tutorial/doc
   sphinx-quickstart sphinx

Répondre aux questions posées par sphinx-quickstart, pour le nom du projet mettez les initiales des personnes de votre groupe suivi de ``info_indus_tutorial``. Par exemple, pour le groupe d' Amélie POULAIN, Jean DUPONT et Nikita TESTU, le nom du projet sera ``PaDjTn_info_indus_tutorial``.

Regarder avec git les nouveaux fichiers créés:

.. code-block:: bash

   git status

