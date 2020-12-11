# MMI x JEKYLL

## Static Site Generator

https://jamstack.org/

https://jekyllrb.com/



## Prise en main 

1. Installer jekyll :

- https://jekyllrb.com/docs/installation/windows/ (pc)
- https://jekyllrb.com/docs/installation/macos/ (mac)
- https://jekyllrb.com/docs/installation/ubuntu/ (linux)


2. Naviguer jusqu'au dossier de votre choix (où vous voulez que vos fichiers soient sur votre ordinateur) via le terminal : utiliser la commande ```cd``` et ```pwd``` pour vous aider.


3. Générer son premier siteweb avec jekyll : 
```

jekyll new my-website-name/ --blank

```

3. Entrer dans le dossier généré "cd my-website-name"

4. Lancer le serveur jekyll avec la commande : 

```

jekyll serve

```

À partir de là, vous êtes prêt à développer !


> Utilisez l'argument "--livereload" pour un rafraichissement automatique de la page
> ```
> jekyll serve --livereload
> ```


## Setup du projet

Une personne du groupe va créer le repository sur github. 

Il va y inviter les membres de son groupe.

Cette même personne va préparer le site jekyll pour le projet : 

1. Cloner le repository sur son ordi (en ayant bien vérifier où est-ce qu'on voulait cloner les fichiers): ```git clone URL_DU_REPO```

3. Générer le projet jekyll : 
```

jekyll new NOM_DU_DOSSIER_DU_REPO --blank

```

4. Créer un fichier ".gitignore" à la racine du dossier contenant les dossiers et fichiers à ignorer :

```
_site/
.sass-cache/
.jekyll-cache/
.jekyll-metadata
.DS_Store
.DS_Store?
.Spotlight-V100
.Trashes
```

> ou vous pouvez le trouver ici : https://github.com/alexisben/mmi-jekyll/blob/master/.gitignore


5. Versionner le code : 

```
git add . 

git commit -m "Setup du projet Jekyll"

git push
```

6. Les autres membres peuvent cloner ou pull s'ils ont déjà cloné le repo.

7. Se repartir les parties du site à intégrer entre chaque développeur.

8. Créer ensemble (en partage d'écran) les dossiers et fichiers des parties que vous pourrez ensuite vous attribuer.

9. Bravo vous êtes prêts à coder !

## Pré-processeur CSS

https://sass-lang.com/guide

https://www.youtube.com/watch?v=aOccUzHD_MQ&ab_channel=Grafikart.fr


## Organisation des fichiers du site

- _includes : C'est ici que l'on va mettre nos "partials" / nos "morceaux" de html.

- _layouts : C'est ce qui va venir "encapsuler" le contenu de notre html, il contient généralement les balises essentielles : html / head / body / header / footer

- _sass : C'est ici que l'on va écrire notre SASS, nos fichiers .scss, les fichiers .scss sont prefixé par un underscore "_", sauf le fichier main.scss. C'est dans main.scss que l'on va importer toutes les autres feuilles de styles.

- _site : Ici on ne modifie rien ! C'est dans ce dossier que Jekyll va compiler nos fichiers et générer le site web.

- assets : Ici on va appeler notre feuille main.scss, et y écrire notre JS. / ! \ on ne va pas styliser notre site dans ce dossier, mais c'est ici qu'on va écrire notre javascript.

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

Et last but not least, la plupart des projets comportent un dossier vendors/ qui regroupe tous les fichiers CSS provenant de bibliothèques et frameworks externes — Normalize, Bootstrap, jQueryUI, FancyCarouselSliderjQueryPowered, etc. Le fait de les mettre ainsi de côté dans un dossier séparé est une bonne façon d’indiquer qu’ils ne sont pas de vous et ne relèvent pas de votre responsabilité.


## DOCS du 9 décembre 

Pour les includes jekyll

https://jekyllrb.com/docs/includes/

Pour flexbox : 

https://css-tricks.com/snippets/css/a-guide-to-flexbox/

https://flexboxfroggy.com/#fr

https://developer.mozilla.org/fr/docs/Web/CSS/CSS_Flexible_Box_Layout/Concepts_de_base_flexbox

Vidéo sur Sass : 

https://www.youtube.com/watch?v=aOccUzHD_MQ&ab_channel=Grafikart.fr

https://www.sassmeister.com/

https://codepen.io/

https://codepen.io/alexisben (code pens de l'atelier Design Interactif)


Media Query :

https://developer.mozilla.org/fr/docs/Web/CSS/Requ%C3%AAtes_m%C3%A9dia/Utiliser_les_Media_queries

https://css-tricks.com/snippets/css/media-queries-for-standard-devices/

https://itnext.io/writing-media-queries-with-sass-mixins-3ea591ea3ea4



# Mettre en ligne sur Netlify : 

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

> Branch to deploy : master
>
> Build command : jekyll build
>
> Publish directoy : _site/

8. Validez en cliquant sur "Deploy site"

9. Attendez que le site soit bien déployé (le premier déploiement peut prendre du temps), puis modifiez le sous-domaine par défaut en cliquant sur "Site settings" > "Change site name".

10. Désormais, à chaque "git push", le site sera mis à jour, plus besoin d'intervenir !


