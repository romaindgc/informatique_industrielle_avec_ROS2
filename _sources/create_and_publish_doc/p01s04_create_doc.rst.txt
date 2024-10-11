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

   touch ~/info_indus/info_indus_tutorial/doc/sphinx/requirements.txt

Ajouter les dépendances suivantes dans le fichier ``requirements.txt`` avec vscode:

.. literalinclude:: ../../requirements.txt

Installer les dépendances:

.. code-block:: bash

   cd ~/info_indus/info_indus_tutorial/doc/sphinx
   python3 -m venv .venv
   source .venv/bin/activate
   pip install -r requirements.txt


============================
Configurer la documentation
============================

Initialiser la documentation avec les outils sphinx:

.. code-block:: bash

   cd ~/info_indus/info_indus_tutorial/doc
   sphinx-quickstart sphinx

Répondre aux questions posées par sphinx-quickstart, pour le nom du projet mettez les initiales des personnes de votre groupe suivi de ``info_indus_tutorial``. Par exemple, pour le groupe d' Amélie POULAIN, Jean DUPONT et Nikita TESTU, le nom du projet sera ``PaDjTn_info_indus_tutorial``.

Regarder avec git les nouveaux fichiers créés:

.. code-block:: bash

   git status

Modifier le fichier ``conf.py``:

1. mettre-à-jour les extensions,
2. mettre-à-jour le theme html de la documentation (:code:`html_theme`),
3. donner les options pour l'extension copybutton,
4. donner le chemin du fichier css

.. literalinclude:: ../conf.py
   :language: python
   :caption: Fichier de configuration de Sphinx (et oui! c'est du python)
   :linenos:
   :emphasize-lines: 33-41,65,67-69,76-78

Ajouter les fichiers créés par sphinx-quickstart:

Ajouter le fichier ``custom.css``

.. literalinclude:: ../_static/css/custom.css
   :language: css
   :caption: Fichier css custom.css
   :linenos:


=======================
Créer la documentation
=======================

Depuis le répertoire ``sphinx`` faire:

.. code-block:: bash

   cd ~/info_indus/info_indus_tutorial/doc/sphinx
   make html

La documentation est un site statique html qui se trouve dans le répertoire ``build/html``.
Le fichier ``index.html`` est la page d'accueil de la documentation.
Ouvrir la documentation avec un navigateur web, par exemple firefox:

.. code-block:: bash

   firefox ~/info_indus/info_indus_tutorial/doc/sphinx/build/html/index.html

=======================================
Sauvegarder la documentation avec git
=======================================

Voir l'état de votre dépôt git:

.. code-block:: bash

   git status

Ajouter les fichiers de la documentation:

.. code-block:: bash

   cd ~/info_indus/info_indus_tutorial/doc/sphinx
   git add source
   git add Makefile make.bat requirements.txt

Fair le commit des modifications:

.. code-block:: bash

   git commit -m "First commit of the documentation"
   