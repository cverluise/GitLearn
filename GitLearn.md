[GitHub]: https://github.com

	
###############################################################################

#Git 101

<br>

[toc]

<br>

##A quoi ça sert ?


###Présentation

Git est un logiciel de versioning. Il permet de peut garder la trace de toutes les modifications faites sur un code pour pouvoir s'y retrouver à tout moment. À chaque fois qu'on fait une série de modifications (créer un fichier, supprimer un fichier, modifier un texte dans un fichier, etc.),  on peut enregistrer ces modifs dans un commit.

**Un commit correspond donc à une version du code à un instant t.**

####Modèle distribué vs modèle centralisé

- *Modèle centralisé* : un serveur central contrôle toute la base de code du logiciel. 
- *Modèle distribué* : toutes les machines ont accès à la base de code, pas besoin de passer par un serveur central.  

Git est un modèle distribué, ce qui veut dire : 

* Moins de risque de perdre son code 
* Possibilité de travailler sans être connecté

<br>
##Installation & Prise en Main


###Quelques rappels sur le shell:

`pwd` : obtenir le current working directory
<br>`cd` : se déplacer dans l'arborescence
<br>`mkdir` : créer un dossier
<br>`touch` : créer un fichier
<br>`touch` : supprimer un fichier
<br>`cat`  : lire un fichier
<br>`open` : ouvrir un fichier 
<br> &nbsp;&nbsp; `-a "AppNAme"` : spécifier l'application 
	
###Configuration

`git config --global user.name "nom ou pseudo"`
<br>`git config --global user.email "Votre@email.com"`
	
Pour vérifier que tout va bien, il suffit de relancer le shell
et de taper `git`. Si l’installation a fonctionné, on doit voir du texte en anglais expliquant l’utilisation de Git.

<br>	
##Premiers pas

###Créer un répertoire (*repository*)
`git init` : activation du *repository* dans lequelon s'est préalablement placé.
<br> `git add NomduFichier` : ajout d'un fichier à l'index du Git
<br> &nbsp;&nbsp;`git add .` : ajout de tous les fichiers du dossier dans lequel on est (à utiliser avec modération)

###Faire un commit
`git commit -m "titre modifié"` : enregistrement des modifications de la nouvelle version 

###Lire le log

La commande `git log`affiche toutes les commits effectués.

Ex :

	MacBook-Air-de-Cyril:Python cyrilverluise$ git log

	commit 2c66830a715d0822ab56f11dfea6632271b5d531 (HEAD -> master)
	Author: Cyril Verluise <cyril.verluise@gmail.com>
	Date:   Sun Nov 12 22:41:30 2017 +0100
	   1ere modif

	
On a donc pour chaque commit:

- son SHA : identifiant unique sous forme d'une chaîne de caractères et de nombres.
- son auteur : l'émetteur du commit
- sa date
- sa description 

###Mettre à jour un fichier déjà indexé 

`git commit -a -m "modifXXX"` met à jour tous les fichiers déjà indexés 
`git status` : indique si des modifications ont été faites depuis le dernier commit  

###Se positionner sur un commit donné

- Un commit passé  
`git checkout SHA`

- Le commit le plus récent  
`git checkout master`

###Modifier un commit

`git revert SHA` : n'annule pas le commit mais en fait un nouveau qui fait l'opération inverse du précédent 

`git commit --amend -m "nouveau message"` : modifie le message du dernier commit (tant qu'on ne la pas *pushé* sur l'origine)

`git reset --hard‌` : annule toutes les modifications depuis le dernier commit (tant qu'on n'a pas fait de nouveau commit)


<br>
##Utilisation de Git avec Git-Hub

###GitHub, qu'est-ce que c'est ?

Lorsqu'on a travaillé sur un projet, il est important d'avoir un backup sur une autre machine. Une fois le code et les commits effectués, on les envoie sur un remote :

* interne (si on a plusieurs machines)
* ou externe (ex: [GitHub] ou BitBucket), cela permet notamment de travailler à plusieurs

 
**GitHub est un service en ligne qui permet d'héberger ses repositories de code.**

En plus de cela, Github permet de :

- Communiquer avec d'autres développeurs et de signaler des problèmes de code en déclarant des *issues*
- Partager des morceaux de code en ligne à l'aide de *gists*
- Proposer des modifications de code à d'autres repos en faisant des *pull requests*
- Récupérer du code depuis un autre *repository*


###GitHub, premiers pas

####Cloner un repository

`git clone lienFourniParGitHub` : permet de copier l'intégralité d'un répertoire hebergé par GitHub sur sa propre machie (NB: se placer dans le `wd` souhaité)


 



