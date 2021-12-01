# MMI x JEKYLL

## Static Site Generator

https://jamstack.org/

https://jekyllrb.com/


## Summary
* [Git & Github - Setup](#setup)
* [Démarrer votre projet avec Jekyll](#démarrer-votre-projet-avec-jekyll)
* [Mettre en ligne avec Netlify](#mettre-en-ligne-sur-netlify)
* [Liens utiles](#liens-utiles)


## Git & Github

### Setup 

1. Installer git sur sa machine : https://git-scm.com/downloads
> sur PC : https://youtu.be/4o9qzbssfII?t=188


2. Créer son compte sur https://github.com/

3. Connecter son compte sur sa machine : 

```
git config --global user.name "your_name_here"
git config --global user.email "your_email@email.com"
```

>  3.2 optionnel : changer l'editeur de texte par défaut de git 
>
>  https://docs.github.com/en/get-started/getting-started-with-git/associating-text-editors-with-git


4. Un membre de votre équipe doit créer le repo de votre site web sur github.com

5. Cette personne va ensuite ajouter des collaborateurs au repo :
```https://github.com/USER_NAME/REPO_NAME/settings/access```,
puis cliquer sur "Invite a collaborator".

6. Sur votre machine (pour tous les membres de l'équipe), naviguez et créez un dossier propice où sera placé votre code (exemple : PROJECTS/PROJECT_NAME).

7. Cloner le repo

    a. Sur Mac : 
    - Ouvrez un terminal : spotlight (cmd + espace) puis cherchez "terminal"
    - Naviguer avec la commande ```cd``` (et aidez-vous de la commande ```ls``` jusqu'à entrer dans le dossier que vous avez créé précédement.
    - Un fois à l'intérieur du dossier, taper la commande : ```git clone https://github.com/USER_NAME/REPO_NAME```

    b. Sur PC :
    - Click droit sur le dossier > Git Bash Here
    > https://youtu.be/4o9qzbssfII?t=286

### Tutorial

MAC : https://www.youtube.com/watch?v=hPfgekYUKgk&ab_channel=LaCapsule


PC : 
https://www.youtube.com/watch?v=4o9qzbssfII&ab_channel=getCodingKnowledge

### Pour sauvegarder votre login / password

```
git config credential.helper cache
git push
```


### Usage : 

#### Obtenir la dernière version depuis la remote (le repo sur github)

```
git pull
```
> Vous pouvez avoir un "failed" quand vous voulez pull : c'est surement que vous avez des modifications en local qui ne sont pas "commit", il faut alors créer un commit (sans avoir à le push)

Dans certains cas il peut y avoir des conflits lors du pull. Deux possibilités : 
  - Git résout seul le conflit : dans ce cas il va vous ouvrir une fenêtre pour ajouter un message au commit qu'il créé : soit dans un editeur de texte, soit dans la fenêtre de votre terminal via l'editeur VI. 
  Dans le cas de la fenêtre de l'editeur VI : vous pouvez sauvegarder et quitter l'editeur VI en tapant sur la touche "ESC" - pour quitter le mode édition, puis taper ```:wq``` puis entrée (w - save | q - quit).
  - Sinon vous devez résoudre manuellement le conflit : ouvrir le fichier ou les fichiers en questions, modifier le code en triant les modifications locales (HEAD) VS modifications remote (long identifiant chelou genre ```862638ad1cb8a0d1c30bbb84ab650d5f71bd0cc5```).
  N'oubliez pas de supprimer les balisages git : ```>>>>>> HEAD```, ```=======```, et ```>>>>>>> id du commit distant```

#### Vérifier l'état actuel du projet git en local (sur sa machine)

> Status présente les informations sur l'état actuel du projet en local (suis-je à jour ? Ai-je de nouveaux fichiers non "trackés" - untracked files ? Ai-je des fichiers modifier à commit ?)

```
git status
```

> Log présente l'historique des commits du projet. Tapez "q" pour quitter.

```
git log
```

#### Envoyer ses modifications 

> Ajoute les modifications des fichiers, les suppressions et les créations de nouveaux fichiers :

```
git add .
```

> Créer un nouveau "commit" - ceci passe en "Staged" les modifications, les suppressions et les créations de fichiers :

```
git commit -m 'enter what you did here'
```

> Envoyer votre / vos commits sur la remote (Le repo sur Github) : 

```
git push
```

### CheatSheet

[Cheat sheet](./zt_git_cheat_sheet.pdf)


## Démarrer votre projet avec Jekyll

1. Installer jekyll :

- https://jekyllrb.com/docs/installation/windows/ (pc)
- https://jekyllrb.com/docs/installation/macos/ (mac)
- https://jekyllrb.com/docs/installation/ubuntu/ (linux)


2. Naviguer jusqu'au dossier de votre choix (où vous voulez que vos fichiers soient sur votre ordinateur) via le terminal : utiliser la commande ```cd``` et ```dir``` (pc) ```pwd``` (mac) pour vous aider.


3. Générer son premier siteweb avec jekyll : 
```

jekyll new my-website-name/ --blank

```

3. Entrer dans le dossier généré "cd my-website-name"

4. Lancer le serveur jekyll avec la commande : 

```

jekyll serve

```

ou 


```

jekyll s

```

À partir de là, vous êtes prêt à développer !


> Utilisez l'argument "--livereload" pour un rafraichissement automatique de la page
> ```
> jekyll serve --livereload
> ```


5. Ajouter l'extension Liquid à Visual Code Studio : https://marketplace.visualstudio.com/items?itemName=sissel.shopify-liquid
pour coloriser le code jekyll

## Setup du projet

Une personne du groupe va créer le repository sur github. 

Il va y inviter les membres de son groupe.

Cette même personne va préparer le site jekyll pour le projet : 

1. Cloner le repository sur son ordi (en ayant bien vérifié où est-ce qu'on voulait cloner les fichiers): ```git clone URL_DU_REPO```

2. Télécharger le projet jekyll (https://github.com/alexisben/mmi2024-jekyll) depuis le drive : 


3. Versionner le code : 

```
git add . 

git commit -m "Préparation du site sous jekyll"

git push
```

4. Les autres membres peuvent cloner ou pull s'ils ont déjà cloné le repo.

5. Se repartir les parties du site à intégrer entre chaque développeur.

6. Créer ensemble (en partage d'écran) les dossiers et fichiers des parties que vous pourrez ensuite vous attribuer.

7. Bravo vous êtes prêts à coder !

## Pré-processeur CSS

https://sass-lang.com/guide

https://www.youtube.com/watch?v=aOccUzHD_MQ&ab_channel=Grafikart.fr


## Organisation des fichiers du site

- _includes : C'est ici que l'on va mettre nos "partials" / nos "morceaux" de html.

- _layouts : C'est ce qui va venir "encapsuler" le contenu de notre html, il contient généralement les balises essentielles : html / head / body 

- _sass : C'est ici que l'on va écrire notre SASS, nos fichiers .scss, les fichiers .scss sont prefixé par un underscore "_", sauf le fichier main.scss. C'est dans main.scss que l'on va importer toutes les autres feuilles de styles.

- _site : Ici on ne modifie rien ! C'est dans ce dossier que Jekyll va compiler nos fichiers et générer le site web.

- assets : Ici on va appeler notre feuille main.scss, et y écrire notre JS. / ! \ on ne va pas styliser notre site dans ce dossier, mais c'est ici qu'on va écrire notre javascript. On va aussi déposer les images et médias de notre site dans ce dossier.

Ce qu'on va pour l'instant ignorer :

- .jekyll-cache
- _data
- _drafts
- _posts
- _config.yml

> Pour plus de clareté dans votre arborescence vous pouvez supprimer les dossiers : _data, _drafts et _posts

## Convention Sass :

https://sass-guidelin.es/fr/#architecture

### _sass/base

Le dossier base/ contient ce que nous pourrions appeler le code standard (boilerplate) du projet. On pourrait y trouver par exemple le fichier de reset, quelques règles typographiques, et probablement une feuille de style définissant quelques styles standard pour les éléments HTML les plus employés (que j’ai l’habitude d’appeler _base.scss).


### _sass/layouts

Le dossier layout/ contient tout ce qui concerne la mise en page du site ou de l’application. Ce dossier pourrait intégrer des feuilles de style pour les principales parties du site (header, footer, navigation, sidebar…), pour le système de grille ou même les styles CSS pour tous les formulaires.


### _sass/components

Pour les plus petits composants, il y a le dossier components/. Alors que layout/ est macro (c’est-à-dire qu’il définit l’armature globale), components/ est plus centré sur les widgets. Il contient toutes sortes de modules spécifiques tels qu’un slider, un loader, un widget et toutes ces sortes de choses. Il y a en général de nombreux fichiers dans components/ car l’application tout entière devrait être essentiellement constituée de petits modules.

### _sass/abstracts

Le dossier abstracts/ regroupe les outils et helpers Sass utilisés à travers le projet. Toutes les variables globales, les fonctions, les mixins et les placeholders devraient se retrouver dans ce dossier.

La règle générale concernant ce dossier est qu’il ne devrait pas retourner une seule ligne de CSS s’il était compilé seul. Ce ne sont ici que des helpers Sass.

### _sass/vendors

Et last but not least, la plupart des projets comportent un dossier vendors/ qui regroupe tous les fichiers CSS provenant de bibliothèques et frameworks externes — Normalize, Bootstrap, etc. Le fait de les mettre ainsi de côté dans un dossier séparé est une bonne façon d’indiquer qu’ils ne sont pas de vous et ne relèvent pas de votre responsabilité.


### Jekyll & Sass : liens utiles

Pour les includes jekyll

https://jekyllrb.com/docs/includes/


Vidéo sur Sass : 

https://www.youtube.com/watch?v=aOccUzHD_MQ&ab_channel=Grafikart.fr

https://www.sassmeister.com/

https://codepen.io/


Media Query :

https://developer.mozilla.org/fr/docs/Web/CSS/Requ%C3%AAtes_m%C3%A9dia/Utiliser_les_Media_queries

https://css-tricks.com/snippets/css/media-queries-for-standard-devices/

https://itnext.io/writing-media-queries-with-sass-mixins-3ea591ea3ea4



# Mettre en ligne sur Netlify

1. Depuis Visual Code, à la racine du projet Jekyll, créer un fichier "Gemfile" (pas d'extension, respectez bien la casse).

2. À l'intérieur copier-coller ce contenu :

```
source "https://rubygems.org"

gem 'jekyll'
```

3. Versionnez votre code et pousser le sur le repo :

```
git add .

git commit -m "Setup Jekyll for netlify deployment"

git push
```

4. Créer un compte Netlify en vous connectant via votre compte Github : https://www.netlify.com/

5. Créer un nouveau Site via le bouton "New site from Git"

6. Sélectionnez votre repo github

7. Si tout est OK, Netlify va automatiquement détecter que votre projet est un projet Jekyll. Assurez-vous que les champs suivant soient bien pré-remplis :

> Branch to deploy : master ou main
>
> Build command : jekyll build
>
> Publish directoy : _site/

8. Validez en cliquant sur "Deploy site"

9. Attendez que le site soit bien déployé (le premier déploiement peut prendre du temps), puis modifiez le sous-domaine par défaut en cliquant sur "Site settings" > "Change site name".

10. Désormais, à chaque "git push", le site sera mis à jour, plus besoin d'intervenir !




## Liens utiles

### Exemples sur codepen : 

https://codepen.io/alexisben (des bouts de codes fait en cours qui peuvent vous être utiles)

### Tech:

https://experiments.withgoogle.com/

https://tympanus.net/codrops/

https://developer.mozilla.org/fr/

http://caniuse.com

https://codepen.io/

https://css-tricks.com/


### CSS

#### Bases

https://www.alsacreations.com/article/lire/533-initiation-au-positionnement-en-css-partie-1.html

https://www.alsacreations.com/tuto/lire/530-La-structure-des-balises-bloc-et-en-ligne.html

#### Flexbox : 

https://css-tricks.com/snippets/css/a-guide-to-flexbox/

https://la-cascade.io/flexbox-guide-complet/

#### Liste des propriétés CSS

https://developer.mozilla.org/fr/docs/Web/CSS/Reference

#### RESET CSS

https://gist.github.com/terkel/1360380


#### Slideshows

https://kenwheeler.github.io/slick/

https://owlcarousel2.github.io/OwlCarousel2/

#### Animation

Animer simplement au scroll : https://michalsnik.github.io/aos/



## Veille

#### Créa:

https://dribbble.com/

https://www.behance.net/

http://www.fubiz.net/

#### Les deux : 

https://www.awwwards.com/

https://thefwa.com

https://usepanda.com/app/#/
