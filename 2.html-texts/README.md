# HTML: INITIATION

Plusieurs cours et tutoriels pour apprendre à structurer vos pages web en utilisant le HTML. Vous trouverez ici un ensemble d'exemples pour vous familiariser avec les éléments HTML.

[Suivre tous les tutoriels sur mon site:](https://djemai-samy.com/blog/0.html-initiation)

- [HTML: Introduction](https://djemai-samy.com/blog/1.html-introduction.article)
- [HTML: Les textes](https://djemai-samy.com/blog/2.html-texts.article)

---

[Suivre tous les tutoriels sur GITHUB:](https://github.com/Djemai-Samy/html-initiation)

- [HTML: Introduction](https://github.com/Djemai-Samy/html-initiation/tree/main/1.html-introduction)
- [HTML: Les textes](https://github.com/Djemai-Samy/html-initiation/tree/main/2.html-texts)

---

## Prérequis

Vous devriez avoir un environnement de travail en place:

- Un ordinateur.
- Un éditeur de texte (ex :[Visual Studio Code]("https://code.visualstudio.com/"), [Atom]('https://atom.io/'), [Sublime Text]('https://www.sublimetext.com/')...). - Un navigateur web.

et comprendre comment créer et gérer des fichiers sur votre ordinateur.

## Principaux buts de HTML

L'un des principaux buts de HTML est de structurer du texte et lui donner du sens (ce que l'on appelle la sémantique) afin que le navigateur puisse l'afficher correctement.

Cet article explique comment HTML peut être utilisé pour structurer une page en ajoutant des titres et des paragraphes, en marquant des emphases, en créant des listes, et bien plus encore.

---

## 1/ Les titres

### 1.1/ Premiers éléments

Il y a 6 éléments de titre — `<h1>`, `<h2>`, `<h3>`, `<h4>`, `<h5>`, et `<h6>`.

Chaque élément représente un niveau de titre différent:

- `<h1>`: représente le titre principal,
- `<h2>`: représente un sous-titre,
- `<h3>`: représente un sous-sous-titre,
- et ainsi de suite jusqu'au niveau de titre le plus bas qui correspond à `<h6>`.

Voici un exemple:

```html
<!DOCTYPE html>
<html lang="fr">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>2/ HTML: Les textes</title>
  </head>
  <body>
    <h1>Ma biographie</h1>
    <p>Par John Doe</p>

    <h2>Chapitre 1:</h2>
    <p>
      Lorem ipsum dolor sit, amet consectetur adipisicing elit. Reiciendis eius in tempore
      incidunt ut dolorum, natus debitis dolores cumque aperiam esse quisquam totam
      repudiandae consequuntur facilis eligendi asperiores sunt beatae.
    </p>

    <h2>Chapitre 2:</h2>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis maiores minima quam.
    </p>

    <h3>Sous chapitre:</h3>
    <p>
      Reiciendis eius in tempore incidunt ut dolorum, natus debitis dolores cumque aperiam
      esse quisquam totam repudiandae consequuntur facilis eligendi asperiores sunt
      beatae.
    </p>

    <h2>Chapitre 3:</h2>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Omnis maiores minima quam.
    </p>
  </body>
</html>
```

![Resultat HTML](https://djemai-samy.com/blog/2.programmation/1.web/1.html/1.html-initiation/2.html-texts/1.html-texts-page.png)

C'est vous qui décidez ce que représentent les éléments utilisés tant que la hiérarchie a du sens. Vous devez cependant garder à l'esprit quelques bonnes pratiques lorsque vous créez de telles structures :

- Il est préférable de n'utiliser qu'un seul `<h1>` par page — c'est le niveau principal, et tous les autres devraient être de niveau inférieur.
- Assurez-vous d'utiliser les balise de titre dans l'ordre correct et logique : `<h1>` puis `<h2>`, puis `<h3>` et ainsi de suite.

---

## 2/ Soulignement et importance

HTML fournit divers éléments de sémantique pour nous permettre de marquer un contenu textuel avec des effets afin de mettre l'accent sur certains mots pour modifier le sens d'une phrase et pour marquer certains mots comme étant importants ou différents.

### 2.1/ Italique ou Emphase

Dans le langage parlé, pour accentuer, nous insistons sur certains mots, modifiant subtilement le sens de ce que nous disons.

De même, dans le langage écrit, nous avons tendance à mettre un certain accent sur des mots en les écrivant en italique. Par exemple, les deux phrases suivantes ont des significations différentes.

« Je suis content que vous n'ayez pas été en retard. »

« Je suis _content_ que vous n'ayez pas été en _retard_. »

En HTML, nous utilisons l'élément `<em>` (emphase) pour mettre du texte en italique:

```html
<h1>Un titre intéressant!</h1>
<p>Un paragraphe avec du contenu de qualité.</p>
```

### 2.1/ Texte en gras

Pour mettre l'accent sur des mots très importants, nous les mettons en caractères gras dans la langue écrite. Par exemple :

Je compte sur vous. **Ne soyez pas en retard !**

En HTML, nous utilisons l'élément `<strong>` (forte importance) comme balise pour mettre le texte en gras:

```html
<p>Je compte sur vous. <strong>Ne soyez pas en retard !</strong></p>
```

Il est possible d'imbriquer `<strong>` et `<em>` :

Ce liquide est **hautement toxique**, si vous en buvez, **vous pourriez en _mourir_.**</p>

```html
<p>
  Ce liquide est <strong>hautement toxique</strong>, si vous en buvez,
  <strong>vous pourriez en <em>mourir</em></strong
  >.
</p>
```

---

## 3/ Les listes

Intéressons-nous maintenant aux listes, très répandues sur le Web, nous allons nous intéresser aux trois différents types.

### 3.1/ Listes non-ordonnées

Les listes non-ordonnées sont utilisées pour représenter des listes d'éléments pour lesquelles l'ordre n'a pas d'importance.

Prenons par exemple une liste de courses :

- Lait
- œufs
- Farine
- Beurre
- Sucre
- Sel

Les listes non-ordonnées débutent par un élément ```<ul>``` (unordered list) qui enveloppe tous les éléments de la liste.

Chaque élément (item) est contenu dans une balise ```<li>``` (list item) :

```html
<ul>
    <li>Lait</li>
    <li>œufs</li>
    <li>Farine</li>
    <li>Beurre</li>
    <li>Sucre</li>
    <li>Sel</li>
</ul>  
```

### 3.2/ Listes ordonnées

Les listes ordonnées permettent de représenter des listes dans lesquelles l'ordre des éléments a de l'importance:

1. Mettez la farine dans un saladier avec le sel et le sucre.

2. Faites un puits au milieu et versez-y les œufs.

3. Commencez à mélanger. Quand le mélange est épais, ajoutez le lait froid petit à petit.

4. Ajoutez ensuite le beurre fondu refroidi, mélangez bien.
Faites cuire les crêpes dans une poêle chaude.

Les listes ordonnées débutent par un élément ```<ol>``` (ordered list) qui enveloppe tous les éléments de la liste :

```html
<ol>
    <li>
        Mettez la farine dans un saladier avec le sel et le sucre.
    </li>
    <li>
        Faites un puits au milieu et versez-y les œufs.
    </li>
    <li>
        Commencez à mélanger. Quand le mélange est épais, ajoutez le lait froid petit à petit.
    </li>
    <li>
        Ajoutez ensuite le beurre fondu refroidi, mélangez bien.
    </li>
    <li>
        Faites cuire les crêpes dans une poêle chaude.
    </li>
</ol>  
```

---

## Conclusion

Cet article doit vous avoir donné une bonne idée de la façon de commencer à baliser le texte en HTML et présenté les éléments les plus importants dans ce domaine.

Il existe énormément d'autres éléments sémantiques à connaître dans ce domaine.

---

## Aller plus loin

[Précédent: HTML: Introduction](https://djemai-samy.com/1.html-introduction.article)

[Suivant: HTML: Les médias](https://djemai-samy.com/1.html-introduction.article)