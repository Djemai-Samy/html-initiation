# HTML: INITIATION

Plusieurs cours et tutoriels pour apprendre à structurer vos pages web en utilisant le HTML. Vous trouverez ici un ensemble d'exemples pour vous familiariser avec les éléments HTML.

[Suivre tous les tutoriels sur mon site:](https://djemai-samy.com/blog/0.html-initiation)

- [HTML: Introduction](https://djemai-samy.com/blog/1.html-introduction.article)
- [HTML: Les textes](https://djemai-samy.com/blog/2.html-texts.article)
- [HTML: Les médias](https://djemai-samy.com/blog/3.html-medias.article)

---

[Suivre tous les tutoriels sur GITHUB:](https://github.com/Djemai-Samy/html-initiation)

- [HTML: Introduction](https://github.com/Djemai-Samy/html-initiation/tree/main/1.html-introduction)
- [HTML: Les textes](https://github.com/Djemai-Samy/html-initiation/tree/main/2.html-texts)
- [HTML: Les médias](https://github.com/Djemai-Samy/html-initiation/tree/main/2.html-texts)

---

## Multimédia et Intégration

Ce tutoriel explore l'utilisation du HTML pour inclure du contenu multimedia dans vos pages web.

Cela comprend les différentes manières d'ajouter des images, d'intégrer de la video, de l'audio et même des pages web entières.

---

## 1/ Les images

Pour mettre une image simple sur une page web, nous utiliserons l'élément `<img>`.

C'est un élément vide (ce qui signifie qu'il ne contient ni texte ni balise de fermeture) qui demande au moins un attribut pour fonctionner — src (souvent appelé par son nom entier: source).

L'attribut src contient un chemin pointant vers l'image que vous voulez intégrer, qui peut être une URL absolue ou relative.

Donc, par exemple, dans un page html basique, si votre image s'appelle logo-html.png, et qu'elle est située dans le même répertoire que votre page HTML, vous pouvez intégrer cette image comme ceci (URL relative) :

```bash
📦html-medias
┣ 📜index.html
┗ 📜html-logo.png
```

```html
<img src="./logo-html.png" />
```

Et si cette image se trouve dans un sous-répertoire images situé dans le même dossier que la page HTML (ce que Google recommande pour SEO/dans un but d'indexation et d'optimisation de la recherche) :

```bash
📦html-medias
┣ 📂images
┃  ┗ 📜logo-html.png
┗ 📜index.html
```

Alors vous l'intégrerez comme ceci:

```html
<img src="./images/logo-html.png" />
```

Vous pouvez intégrer l'image en utilisant son URL absolue, par exemple :

```html
<img src="https://cdn-icons-png.flaticon.com/512/888/888909.png" />
```

Ce n'est pas trés efficace, cela fait travailler le navigateur plus qu'il ne devrait, il cherche l'adresse IP depuis le serveur DNS à chaque fois etc...

---

### 1.1/ L'attribut alt

La balise `<img>` peut prendre un attribut `alt`, un descriptif sous forme de texte de l'image, à utiliser dans les cas où l'image ne peut être affichée:

```html
<img
  src="images/inexistant.jpg"
  alt="Logo HTML5 de couleur orange en forme de bouclier, avec un 5 blanc au millieu."
/>
```

Pourquoi vous verrez partout du texte alt ? Vous en aurez besoin car c'est très pratique:

- L'utilisateur est déficient visuel qui utilise un lecteur d'écran qui s'en sert pour "lire" le web.

- Comme nous l'avons vu au-dessus, vous pourriez avoir mal épelé le nom ou le chemin du fichier.

- Le navigateur ne gère pas ce type d'image. Certains utilisent encore des navigateurs en terminal, affichant seulement du texte.

- Vous pouvez avoir envie de fournir du texte que pourraient utiliser les moteurs de recherche. Par exemple, ils mettront en relation le texte alt avec des requêtes de recherche.

- L'utilisateur a supprimé les images pour économiser le volume du transfert de données ou pour ne pas être distrait. C'est très commun sur les téléphones mobiles et dans les pays où la bande passante est limitée ou coûte cher.

---

### 1.2/ Hauteur et largeur

Vous pouvez vous servir des attributs `width` et `height` pour spécifier la largeur et la hauteur de votre image.

```html
<img
  src="images/logo-html.png"
  alt="Logo HTML5 de couleur orange sou forme de bouclier, avec un 5 blanc au millieu."
  width="256"
  height="256"
/>
```

### 1.3/ Titre d'images

Vous pouvez aussi ajouter un attribut `title` aux images, pour fournir un supplément d'information si nécessaire:

Cela donne une info-bulle avec le texte entré quand l'utilisateur survole li'mage avec la souris:

```html
<img
  src="images/logo-html.png"
  alt="Logo HTML5 de couleur orange sou forme de bouclier, avec un 5 blanc au millieu."
  width="256"
  height="256"
  title="Le logo officiel de language HTML."
/>
```

---

### 1.4/ Légender les images

Les éléments HTML5 `<figure>` et `<figcaption>` ont été conçus pour fournir un conteneur sémantique aux objets et lier clairement cet objet à sa légende:

```html
<figure>
  <img
    src="images/logo-html.png"
    alt="Logo HTML5 de couleur orange sou forme de bouclier, avec un 5 blanc au millieu."
    width="256"
    height="256"
    title="Le logo officiel de language HTML."
  />

  <figcaption>Le logo officiel de language HTML.</figcaption>
</figure>
```

---

## 2/ Contenu vidéo

L'élément `<video>` vous permet d'intégrer de la vidéo très facilement. En voici un exemple :

```bash
📦html-medias
 ┣ 📂images
 ┃  ┗ 📜logo-html.png
 ┣ 📂videos
 ┃  ┗ 📜video.mp4
 ┗ 📜index.html
```

```html
<video src="./videos/video.mp4" controls>
  <p>Votre navigateur ne prend pas en charge les vidéos HTML5.</p>
</video>
```

Les fonctionnalités de ce code sont :

- `src`: De la même manière que pour l'élément `<img>`, l'attribut src (source) contient le chemin vers la vidéo.

- `controls`: Les utilisateurs doivent avoir un contrôle sur la lecture de la vidéo. Vous devez vous servir de l'attribut controls pour appeler l'interface de contrôle du navigateur.

- Le paragraphe dans la balise `<video>`: Cela peut s'appeler solution de repli (fallback content) — si le navigateur accédant à la page ne supporte pas l'élément `<video>`, cela offre un texte alternatif qui peut être ce que vous voulez.

Les vidéos peuvent prendre plus d'attributs:

- ```width``` et ```height```: Il est possible de contrôler la taille de la vidéo soit avec ces attributs.

- ```autoplay```: Cet attribut permet de lancer immédiatement la lecture de l'audio ou de la vidéo pendant que le reste de la page se charge.

- ```loop```: Cet attribut permet de relancer en boucle la lecture de la vidéo (ou de l'audio).

- ```muted```: Cet attribut coupe le son de la vidéo par défaut.

- ```poster```: Cet attribut prend comme valeur l'URL d'une image affichée avant la lecture de la vidéo.

- ```preload```: Cet attribut s'utilise pour mettre en tampon les gros fichiers. Il peut prendre 3 valeurs:
  - ```"none"``` : ne pas mettre le fichier dans un tampon.
  - ```"auto"``` : mettre le fichier média dans un tampon.
  - ```"metadata"``` : ne mettre que les métadonnées dans le tampon.

---

## 3/ Contenu audio

L'élément ```<audio>``` fonctionne exactement de la même manière que l'élément ```<video>```, mais avec quelques différences:

```bash
📦html-medias
 ┣ 📂images
 ┃  ┗ 📜logo-html.png
 ┣ 📂videos
 ┃  ┗ 📜video.mp4
 ┣ 📂audios
 ┃  ┗ 📜audio.mp3
 ┗ 📜index.html
```

```html
<audio src="./audios/audio.mp3" controls>
  <p>Votre navigateur ne prend pas en charge l'audio' HTML5.</p>
</audio>
```

---

## 4/ SVG: Images vectorielles

 **SVG**: **S**calable **V**ector **G**raphic est un langage basé sur XML qui permet de décrire des images vectorielles, des images adaptatives par excellence : légères et redimensionnables.

Certaines images (appelées images « matricielles ») sont en fait des tableaux de carrés colorés (appelés pixels). Si on agrandit une image de ce type, à un moment, on arrive à distinguer ces carrés.

Au contraire, les images vectorielles décrivent des lignes et des formes. On obtient donc une image qui est toujours nette, quelle que soit la résolution de l'écran ou l'agrandissement effectué sur l'image.

Il est possible de coder le SVG à la main grâce à un éditeur de texte. En revanche, pour réaliser des images complexes, il est préférable d'utiliser un éditeur graphique dédié, comme [Inkscape](https://inkscape.org/). 

Voici un exemple simple:

```html
<svg width="300" height="200">
    <rect width="100%" height="100%" fill="green" />
    <ellipse cx="50%" cy="50%" rx="50" ry="30" fill="red"/>
</svg>
```

<svg width="300" height="200">
    <rect width="100%" height="100%" fill="green" />
    <ellipse cx="50%" cy="50%" rx="50" ry="30" fill="red"/>
</svg>

### Avantages

- Rapide à mettre en œuvre.
- Syntaxe très proche avec les images matricielles,
- Texte alternatif disponible.

### Inconvénients

- Il est impossible de manipuler l'image avec JavaScript.

---

il est possible d'utiliser la balise ```<ìmg>``` pour afficher un SVG:

```bash
📦html-medias
 ┣ 📂images
 ┃  ┣ 📜image.svg
 ┃  ┗ 📜logo-html.png
 ┣ 📂videos
 ┃  ┗ 📜video.mp4
 ┣ 📂audios
 ┃  ┗ 📜audio.mp3
 ┗ 📜index.html
```

```html
<img src="./images/image.svg">
```

Ou bien ouvrir le fichier dans un éditeur de texte, et copier le code pour le coller directement dans votre page HTML:

```html
<svg width="512" height="288" viewBox="0 0 512 288">
  
  <!--Background/Couleur de Fond-->
  <rect width="100%" height="100%" fill="#212121" />

  <!--Le texte: HTML-->
  <path
    d="M254 155.4V142.8H284.6V155.4H254ZM278.6 185V113H295.2V185H278.6ZM248 185V113H264.6V185H248ZM304.18 125.6V113H353.18V125.6H304.18ZM320.38 185V113H336.98V185H320.38ZM387.707 185L403.307 113H415.307L399.707 185H387.707ZM387.307 185L371.707 113H383.707L399.307 185H387.307ZM362.207 185V113H378.807V185H362.207ZM408.207 185V113H424.807V185H408.207ZM451.416 185V172.4H474.816V185H451.416ZM437.816 185V113H454.416V185H437.816Z"
    fill="#EF652A"
  />

  <!--Le logo HTML-->
  <g>
    <path
      d="M53.43 230.424L37.333 48.2666H214.4L198.303 230.424L125.67 251.015"
      fill="#E34F26"
    />
    <path
      d="M126.063 235.176L184.561 218.94L198.303 62.9184H126.063"
      fill="#EF652A"
    />
    <path
      d="M126.063 130.633H96.617L94.654 107.666H126.063V85.49H70.3122L76.2014 153.205H126.063V130.633ZM125.67 188.844L100.936 182.112L99.3653 164.293H77.3792L80.1275 199.536L125.67 212.208V188.844Z"
      fill="#EBEBEB"
    />
    <path
      d="M125.67 130.633V153.205H153.153L150.404 182.112L125.67 188.844V212.208L171.213 199.536L177.494 130.633H125.67ZM125.67 85.49V107.666H179.457L181.42 85.49H125.67Z"
      fill="white"
    />
  </g>
</svg>
```

<svg width="100%" height="288" viewBox="0 0 512 288">
  <rect width="100%" height="100%" fill="#212121" />
  <path
    d="M254 155.4V142.8H284.6V155.4H254ZM278.6 185V113H295.2V185H278.6ZM248 185V113H264.6V185H248ZM304.18 125.6V113H353.18V125.6H304.18ZM320.38 185V113H336.98V185H320.38ZM387.707 185L403.307 113H415.307L399.707 185H387.707ZM387.307 185L371.707 113H383.707L399.307 185H387.307ZM362.207 185V113H378.807V185H362.207ZM408.207 185V113H424.807V185H408.207ZM451.416 185V172.4H474.816V185H451.416ZM437.816 185V113H454.416V185H437.816Z"
    fill="#EF652A"
  />
  <g>
    <path
      d="M53.43 230.424L37.333 48.2666H214.4L198.303 230.424L125.67 251.015"
      fill="#E34F26"
    />
    <path
      d="M126.063 235.176L184.561 218.94L198.303 62.9184H126.063"
      fill="#EF652A"
    />
    <path
      d="M126.063 130.633H96.617L94.654 107.666H126.063V85.49H70.3122L76.2014 153.205H126.063V130.633ZM125.67 188.844L100.936 182.112L99.3653 164.293H77.3792L80.1275 199.536L125.67 212.208V188.844Z"
      fill="#EBEBEB"
    />
    <path
      d="M125.67 130.633V153.205H153.153L150.404 182.112L125.67 188.844V212.208L171.213 199.536L177.494 130.633H125.67ZM125.67 85.49V107.666H179.457L181.42 85.49H125.67Z"
      fill="white"
    />
  </g>
</svg>

### Avantages

- Placer le SVG à même le document permet d'économiser une requête HTTP, ce qui peut permettre de réduire le temps de chargement de la page.

- Vous pouvez ajouter des attributs class et id aux éléments SVG pour les mettre en forme grâce à CSS.

- Cette approche est la seule qui permet d'utiliser des interactions CSS (telles que :focus) et des animations.

### Inconvénients

- Cette méthode n'est utilisable que si le SVG n'est utilisé qu'à un seul endroit. S'il faut le dupliquer, cela compliquera la maintenance et gaspillera de la mémoire.

- Chaque image SVG augmente la taille du fichier HTML.

- Le navigateur ne peut pas placer ces images SVG en cache comme il pourrait le faire avec d'autres ressources.

## Aller plus loin

[Précédent: HTML: Les textes](https://djemai-samy.com/2.html-texts.article)

[Suivant: HTML: Les formulaires](https://djemai-samy.com/1.html-forms.article)
