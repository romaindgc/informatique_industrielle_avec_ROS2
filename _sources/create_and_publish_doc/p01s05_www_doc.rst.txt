*************************
Publier la documentation
*************************

Nous allons maintenant publier la documentation sur le web mais aussi sauvegarder notre projet sur un serveur git distant afin de le partager avec d'autres personnes.

.. note::

   Pour pouvoir partager le projet et sa documentation, il faut que le projet soit sur un serveur git distant, accessible par tout utilisateur que vous avez autorisé et tout le temps.
   Dans ce tutoriel nous allons créer un projet publique sur ``github``

Créer un compte sur github
==========================

Si vous avez déjà un compte github, vous pouvez passer à la section suivante et utiliser votre compte.

Pour créer un compte sur github, allez sur le site `github <https://github.com/>`_ et cliquez sur le bouton ``Sign up`` en haut à droite ou cliquez sur le lien: `github signup <https://github.com/signup>`_. Remplissez les informations demandées et cliquez sur le bouton ``Create account``.

Créer un dépôt sur github
=========================

Une fois connecté sur github, vous pouvez créer un nouveau dépôt en cliquant sur le bouton ``New`` en haut à droite ou en cliquant sur le lien: `github new repository <https://github.com/new>`_.

Remplissez les informations demandées:
et appelez votre dépôt ``info_indus_tutorial``.


Créer une clé ssh et l'ajouter à github
---------------------------------------

Pour pouvoir pousser votre projet sur github, il est recommandé d'utiliser une clé ssh. Pour créer une clé ssh, ouvrez un terminal et tapez la commande suivante:

.. code-block:: bash

   ssh-keygen -t ed25519 -C "your_email@example.com" -f ~/.ssh/id_ed25519_info_indus_tutorial

Remplacez ``your_email@example.com`` par votre email.

Maintenant vous allez ajouter la clé ssh à votre compte github. Pour cela, copiez le contenu de la clé publique dans le presse-papier:

.. code-block:: bash

   cat ~/.ssh/id_ed25519_info_indus_tutorial.pub

Allez sur la page de votre compte github et cliquez sur votre photo de profil en haut à droite, puis cliquez sur ``Settings``. Dans la colonne de gauche, cliquez sur ``SSH and GPG keys`` et enfin sur le bouton ``New SSH key``. Collez le contenu de la clé publique dans le champ ``Key`` et cliquez sur le bouton ``Add SSH key``.


Vous pouvez maintenant ajouter votre clé à l'agent ssh, cela vous évitera de taper votre mot de passe à chaque fois que vous poussez sur github:

.. code-block:: bash

   eval "$(ssh-agent -s)"
   ssh-add ~/.ssh/id_ed25519_info_indus_tutorial




Poussez le projet sur github
============================

Pour pousser le projet sur github, il faut ajouter le dépôt distant à votre dépôt local et pousser les modifications.

Pour trouver l'adresse du dépôt distant à utiliser pour pousser votre projet, allez sur la page de votre dépôt github et copiez l'adresse du dépôt.

.. _get_git_remote_project_address:
.. figure:: resources/img/get_git_remote_project_address_01.png
   :align: center
   :width: 30%

.. figure:: resources/img/get_git_remote_project_address_02.png
   :align: center
   :width: 30%

.. figure:: resources/img/get_git_remote_project_address_03.png
   :align: center
   :width: 30%

.. code-block:: bash

   git remote add origin MY_GIT_REMOTE_ADDRESS

Remplacez ``MY_GIT_REMOTE_ADDRESS`` par l'adresse du dépôt distant que vous venez de copier.

Effectuez les commandes suivantes:

.. code-block:: bash
   
   git branch -a
   git branch -M rolling
   git branch -a

The branch commands were to rename the main branch as rolling in accordance with the ROS2 policy.

Now the actual command to push code to github:
.. code-block:: bash

   git push -u origin rolling

Only the first time you push a branch to a remote repository, you need to use the ``-u remote_reopsitory local branch`` option. This option sets the upstream branch for the branch you are pushing. After that, you can use ``git push`` without the ``-u`` option.

Now, you should see the files on github.
