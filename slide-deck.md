---
marp: true
theme: gaia
markdown.marp.enableHtml: true
paginate: true
class: invert
header: 'Découvrir Vim'
footer: "[Site de l'auteur](https://thebidouilleur.xyz)"
---

<style>

video {
  display: block;
  margin: auto;
}

img[alt~="center"] {
  display: block;
  margin: 0 auto;
}
blockquote {
  background: #ffedcc;
  border-left: 10px solid #d1bf9d;
  margin: 1.5em 10px;
  padding: 0.5em 10px;
}
blockquote:before{
  content: unset;
}
blockquote:after{
  content: unset;
}
video::-webkit-media-controls {
    will-change: transform;
  }
</style>

<!-- _class: lead invert -->
<!-- transition: cover -->

CyberPrez #03 - VIM
# Découvrir Vim 

![width:250](./img/vimlogo.png)

---

<!-- transition: fade -->
<!-- _class: lead invert -->

# Qu'est-ce que Vim ?

Vim est un utilitaire en ligne de commande permettant de modifier des fichiers texte. Celui-ci est un dérivé de l'éditeur `vi`, qui est intégré dans la plupart des systèmes Unix-like.

---

Vim est connu pour être complexe à prendre en main, mais une fois que l'on a compris les bases, il est très puissant et permet de gagner beaucoup de temps.

Si vous avez trouvé cette présentation parce que **vous êtes bloqué dans vim** depuis plusieurs heures : *Respirez un bon coup*, pressez la touche `echap` et tapez `:q!` pour quitter sans sauvegarder.

![contain](./img/key-echap---_q_.png)

---
<!-- _class: lead invert -->

*Et maintenant que j'ai perdu 90% de mon audience, je peux commencer la réelle présentation.*

---
<!-- _class: lead invert -->

… mais avant ça, un peu d'histoire.

---
<!-- _class: lead invert -->

# 1. Histoire de vim

---
<!-- _header: '1. Histoire de Vim' -->


Vim, qui signifie **"Vi Improved"** *(Vi amélioré)*, est l'editeur de texte le plus utilisé en ligne de commande. Son histoire remonte aux années 1970 avec l'apparition d'un éditeur de texte appelé Vi *(Visual Editor)* développé par *Bill Joy* pour le système d'exploitation Unix.

Vi est devenu populaire parmi les programmeurs et les administrateurs système grâce à sa puissance et à sa simplicité d'utilisation en mode texte. Au fil des années, de nombreux utilisateurs ont contribué au développement de Vi en créant des versions personnalisées, chacune avec ses améliorations et fonctionnalités spécifiques.

---
<!-- _class: lead invert -->
<!-- _header: '1. Histoire de Vim' -->

En *1991*, *Bram Moolenaar* a créé Vim en se basant sur le code source de Vi. Vim était destiné à être une version améliorée de Vi, incorporant de nouvelles fonctionnalités et offrant une plus grande flexibilité.

![auto](./img/Bram-Moolenaar.png)

---
<!-- _class: lead invert -->
<!-- _header: '1. Histoire de Vim' -->

Parmi les améliorations, on peut retrouver la coloration syntaxique, l'édition multifenêtres, le support des plugins et la possibilité d'étendre les fonctionnalités grâce à un langage de script interne.

![contain](./img/vim-features-.png)

<!-- Source : https://null-byte.wonderhowto.com/how-to/intro-vim-unix-text-editor-every-hacker-should-be-familiar-with-0174674/ -->
---

<!-- _class: lead invert -->
<!-- _header: '1. Histoire de Vim' -->

Aujourd'hui, Vim continue d'évoluer grâce à une communauté active qui propose des mises à jour, des corrections de bugs et des fonctionnalités supplémentaires.

Il reste un outil essentiel pour les développeurs et les utilisateurs expérimentés qui apprécient sa puissance et sa capacité à optimiser leur flux de travail.

---
<!-- _class: lead invert -->
<!-- transition: explode -->

Maintenant que le cours d'histoire est terminé, passons à la pratique.

---
<!-- _class: lead invert -->
<!-- transition: fade -->

# 2. La base de vim

---
<!-- _header: '2. La base de vim' -->

# 2. La base de vim

N'oubliez pas que VIM s'apprend avant-tout par la pratique. Il est donc conseillé de suivre cette présentation en même temps que vous lisez les slides.

Ne désespérez pas si vous oubliez certains raccourcis, Vim se maitrise par la pratique et l'habitude.

![center h:200](./img/vim-curve.jpeg)

<!-- Source : https://www.freecodecamp.org/news/learn-linux-vim-basic-features-19134461ab85/ -->

---
<!-- _header: '2.1. Les modes' -->

## 2.1. Les modes

Vim possède plusieurs modes, chacun ayant un rôle différent. Il est important de comprendre comment fonctionne les modes pour pouvoir utiliser Vim correctement.

Nous utiliserons principalement 3 modes : le mode **normal**, le mode **insertion** et le mode **visuel**.

Le mode normal est celui par défaut, il permet de lancer les 'macros'. Le mode **insertion** peut se lancer en pressant '**i**', et le mode **visuel** en pressant '**v**'.

---
<!-- _header: '2.1. Les modes' -->
<!-- _footer: '' -->

Le mode dans lequel nous nous trouvons est indiqué en bas à gauche de l'écran. Si vous êtes en mode **insertion**, vous devriez voir `-- INSERT --` en bas à gauche de l'écran.

![center h:200](./img/mode-vim.png)

Le mode **visuel** sera affiché de la même manière, avec `-- VISUAL --`.

Vous pouvez **toujours** revenir au mode `normal` en pressant la touche `echap`.

---

Téléchargez maintenant le fichier exemple `cigale-et-la-fourmi.txt` [ici](./exercices/cigale-et-la-fourmi.txt).

Pour l'ouvrir avec vim, tapez `vim cigale-et-la-fourmi.txt` dans votre terminal ou tapez `vim` puis écrivez `:open cigale-et-la-fourmi.txt`.

![center h:350](./img/fenetre-vim.png)

---
<!-- _header: '2.2. Les déplacements' -->

À l'origine, les touches directionnelles n'existaient pas. Pour se déplacer dans le texte, il fallait utiliser les touches `h`, `j`, `k` et `l` pour se déplacer respectivement à gauche, en bas, en haut et à droite.

![center h:250 opacity:.5](./img/./hjkl.png)

Vim a gardé cette logique, mais il est *(heureusement)* possible d'utiliser les touches directionnelles pour se déplacer.

--- 
<!-- _header: '2.3. Mise en pratique - Insertion' -->

Dans le fichier `cigale-et-la-fourmi.txt`, placez votre curseur sur la première ligne du texte, entrez en mode **insertion** en pressant `i` et écrivez `La Cigale et la Fourmi` puis appuyez sur `echap` pour revenir en mode **normal**. L'objectif est d'ajouter le titre en début de fichier.

<video style="center" src="videos/mode-i.mp4" controls width="60%"></video>

---
<!-- _header: '2.3. Mise en pratique - Insertion' -->

Simple ? Une fois de retour en mode **normal**, enregistrez le fichier en pressant `:w` puis `entrée`.

<video style="center" src="videos/save.mp4" controls width="30%"></video>

Pour quitter vim, `:q` puis `entrée`.

Pour enregistrer  **et** quitter, combinez les deux raccourcis précédents : `:wq` puis `entrée`.



