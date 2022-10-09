# html-initiation

Plusieurs cours et tutoriels pour apprendre à structurer vos pages web en utilisant le HTML. Vous trouverez ici un ensemble d'exemples pour vous familiariser avec les éléments HTML.

## Prérequis

Il n'y a pas besoin de connaissances préalables en HTML.

Vous devriez avoir un environnement de travail en place:

- Un ordinateur.
- Un éditeur de texte (ex :[Visual Studio Code]("https://code.visualstudio.com/"), [Atom]('https://atom.io/'), [Sublime Text]('https://www.sublimetext.com/')...). - Un navigateur web.

et comprendre comment créer et gérer des fichiers sur votre ordinateur.

## Qu'est-ce que le HTML ?

**HTML:** (**H**yper**T**ext **M**arkup **L**anguage) n'est pas un langage de programmation : c'est un langage de balisage qui sert à indiquer au navigateur comment structurer les pages web visitées.

Le HTML se compose d'une série d'éléments avec lesquels vous pouvez encadrer, envelopper ou baliser différentes parties du contenu pour les faire apparaître ou agir d'une certaine manière.

Des balises encadrantes peuvent transformer une petite partie de contenu en un lien vers une autre page sur le Web, mettre des mots en italique, etc.

---

Les documents HTML sont donc des fichiers possédant l'extension .html, pouvant être ouverts et lus sur le navigateur.

Par exemple, créez un fichier ```index.html``` puis ouvrez le fichier avec votre éditeur de texte, et ajoutez du texte à l'intérieur:

```html
Un titre intéressant!
Un paragraphe avec du contenu de qualité.
```

Sauvegarder le fichier, et ouvrez le sur votre navigateur (double clique sur le fichier dans l'explorateur de dossiers):

![Du texte dans du HTML](https://djemai-samt.com/blog/2.programmation/1.web/1.html/1.html-initiation/1.html-introduction/1.html-page.png)

## 1/ Les éléments HTML

### 1.1/ Premiers éléments

Dans l'exemple précédent, le texte était bien affiché, mais la mise en forme n'était pas respectée. (pas de retour à la ligne).

Pour y remédier nous allons introduire deux nouvelles balises/élément HTML très utilisées:

- La balise ```<h1>```: Indique au navigateur et moteurs de recherche que cela représente le titre principal de la page. (Très important pour le référencement.)
- La balise ```<p>```: Permet d'indiquer qu'il s'agit d'un paragraphe.

```html
<h1>Un titre intéressant!</h1>
<p>Un paragraphe avec du contenu de qualité.</p>
```

![Premiers éléments](https://djemai-samt.com/blog/2.programmation/1.web/1.html/1.html-initiation/1.html-introduction/2.html-page.png)

### 1.2/ Anatomie des élements

Regardons notre élément titre d'un peu plus près :

![Anatomie des élements](https://djemai-samt.com/blog/2.programmation/1.web/1.html/1.html-initiation/1.html-introduction/4.elements-anatomy.png)

es principales parties de notre élément sont :

- La balise ouvrante : il s'agit du nom de l'élément (dans ce cas, h1), encadré par un chevron ouvrant ```<``` et un chevron fermant ```>```.
- Le contenu : il s'agit du contenu de l'élément. Dans notre cas, c'est simplement du texte.
- La balise fermante : la même que la balise ouvrante, sauf qu'elle comprend une barre oblique (/) avant le nom de l'élément. Elle indique la fin de l'élément. Ne pas inclure une balise de fermeture est une erreur fréquente chez les débutants, et peut amener des résultats étranges.

### 1.3/ Imbrication des éléments

Vous pouvez mettre des éléments à l'intérieur d'autres éléments — cela s'appelle l'imbrication. Cela permet par exemple de mettre en gras un mot de votre paragraphe:

```html
<h1>Un titre intéressant!</h1>
<p>Un paragraphe avec du contenu de <strong>qualité.</strong></p>
```

![Imbrication des éléments page](https://djemai-samt.com/blog/2.programmation/1.web/1.html/1.html-initiation/1.html-introduction/3.html-page.png)

![Imbrication des éléments anatomie](https://djemai-samt.com/blog/2.programmation/1.web/1.html/1.html-initiation/1.html-introduction/5.html-imbrication.png)

## 1.4/ Les attributs

Les éléments peuvent aussi avoir des attributs, pour cela nous allons introduire une nouvelle balise très importante, permettant de naviguer et de lier les pages d'internet.

- la balise ```<a>```: permet de diriger l'utilisateur vers d'autres pages, pour cela elle prend l'attribut:
- ```href```: L'URL de la page à ouvrir quand l'utilisateur clique sur le lien.
- ```target```: permet d'ouvrir la page dans un nouvel onglet (si omis la page s'ouvrira dans l'onglet actif)

```html
<a href="https://google.com" target="_blank">Lien vers Google</a>
```

Pour créer un attribut, il faut :

- Insérer un espace entre cet attribut et le nom de l'élément (ou l'attribut précédent).
- Donner un nom à l'attribut, puis ajouter un signe égal.
- Donner une valeur à l'attribut, entourée par des guillemets d'ouverture et de fermeture.

![Les attributs](https://djemai-samt.com/blog/2.programmation/1.web/1.html/1.html-initiation/1.html-introduction/6.html-attributs.png)

## 2/ Première page HTML

Voici l'exemple d'une page html basique:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset='utf-8' />
    <title>Ma page test</title>
</head>
<body>
    <h1>Votre site web</h1>
</body>
</html>
````

1. ```<!DOCTYPE html>```: Avant, les doctypes étaient censés agir comme des liens vers un ensemble de règles que la page HTML devait suivre pour être considérée comme un bon HTML.

2. ```<html>```: Cet élément est le contenant de tout le code de la page et est parfois connu comme l'élément racine.

3. ```<head>```: Cet élément a le rôle de conteneur pour toute chose que vous souhaitez inclure dans la page HTML qui ne soit pas du contenu à afficher: mots clés, description...
    - ```<meta>```: Cet élément définit que le jeu de caractères à utiliser pour votre document est UTF-8. Ce jeu comporte la quasi‑totalité des caractères de toutes les écritures de langues humaines connues.

    - ```<title>```: Il définit le titre de la page, celui qui s'affiche dans l'onglet du navigateur

4. ```<head>```: Il contient tout le contenu que vous souhaitez afficher aux internautes lorsqu'ils visitent votre page, que ce soit du texte, des images, des vidéos...

5. ```<body>``` : Il contient tout le contenu que vous souhaitez afficher aux internautes lorsqu'ils visitent votre page, que ce soit du texte, des images, des vidéos, des jeux, des pistes audio jouables ou autre.

## Conclusion

Les pages web sont composées de texte brut, parfaitement lisible avec le moindre
éditeur de texte, dans lequel on retrouvera donc les balises.

Ces balises fonctionnent
le plus souvent par paire, car comme nous l’avons dit, elles servent à encadrer un
élément.

Il existe donc une balise ouvrante pour signifier le début d’un élément et
une balise fermante pour en signifier la fin.
