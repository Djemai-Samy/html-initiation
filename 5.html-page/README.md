# HTML: Structurer une page

Plusieurs cours et tutoriels pour apprendre à structurer vos pages web en utilisant le HTML. Vous trouverez ici un ensemble d'exemples pour vous familiariser avec les éléments HTML.

[Suivre tous les tutoriels sur mon site:](https://djemai-samy.com/blog/0.html-initiation)

- [HTML: Introduction](https://djemai-samy.com/blog/1.html-introduction.article)
- [HTML: Les textes](https://djemai-samy.com/blog/2.html-texts.article)
- [HTML: Les médias](https://djemai-samy.com/blog/3.html-medias.article)
- [HTML: Les formulaires](https://djemai-samy.com/blog/4.html-forms.article)
- [HTML: Structurer une page](https://djemai-samy.com/blog/5.html-page.article)

---

[Suivre tous les tutoriels sur GITHUB:](https://github.com/Djemai-Samy/html-initiation)

- [HTML: Introduction](https://github.com/Djemai-Samy/html-initiation/tree/main/1.html-introduction)
- [HTML: Les textes](https://github.com/Djemai-Samy/html-initiation/tree/main/2.html-texts)
- [HTML: Les médias](https://github.com/Djemai-Samy/html-initiation/tree/main/3.html-texts)
- [HTML: Les formulaires](https://github.com/Djemai-Samy/html-initiation/tree/main/4.html-forms)
- [HTML: Structurer une page](https://github.com/Djemai-Samy/html-initiation/tree/main/5.html-page)

---

## Structure du projet

  ```bash
  📦html-page
  ┣ 📂images
  ┃ ┣ 📜JohnDoe.png
  ┃ ┣ 📜LoremIpsum.png
  ┃ ┗ 📜logo.svg
  ┣ 📜favicon.ico
  ┗ 📜index.html
  ```

- Un dossier images avec le logo, et des images pour les articles.
- Une page ```index.html``` représentant la page d'accueil.
- ```favicon.ico```: icône affichée dans l'onglet du navigateur.

---

## 1/ Principales parties d'une page

Les pages web peuvent sembler assez différentes les unes des autres, mais elles ont toutes tendance à partager des composants standard similaires.

Dans cette dernière partie du tutoriel, nous allons voir comment construire une page web basique.

### 1.1/ l'élément (head)

l'élément ```<head>```que nous avons vu dans la partie [Introduction](https://djemai-samy.com/1.html-introduction), est utilisé comme un container pour toutes les choses qui font partie de la page HTML mais qui ne sont pas du contenu affiché:

```html
<head>
  <meta charset="utf-8" />
    
  <!--Image afficher dans la barre d'onglet-->
  <link rel="icon" href="./favicon.ico">

  <!--Titre du site affiché dans la barre d'onglet-->
  <title>BRAND: Acceuil</title>

  <!--Description du site-->
  <meta name = "description" content= "Déscription de votre site en quelques mots" >
    
  <!-- Image du site-->
  <meta property="og:image"  content="./images/logo.svg">

  <!--Instructions sur la taille et l’échelle du viewport-->
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
</head>
```

- La balise ```<link>``` avec ```rel="icon"``` permet d'ajouter un Favicon. C'est une image/logo qui répresente son site dans la barre d'onglet.
- La balise ```<title>``` quand a elle est sûrement la plus importante, c'est le titre visible par les moteurs de recherches. Elle apparaît aussi dans la barre des onglets, elle sert pour le référencement du site.
- La balise ```<meta>``` avec ```name= "description"```: Définit une description qui incorpore des mots-clés relatifs au contenu de la page. Très est utile car aidera votre page a apparaître plus haut dans la liste de recherches par pertinence créée par un moteur de recherches.
- La balise ```<meta>``` avec ```name= "viewport"``` va permettre de donner des instructions relatives à la taille et à l’échelle du viewport aux navigateurs mobiles afin que les différents éléments d’une page s’affichent au mieux. 

  Nous allons pouvoir passer plusieurs propriétés à l’attribut content:
  - Les propriétés width et height vont nous permettre de contrôler la taille du viewport dans lequel notre page doit s’afficher.
  - La propriété initial-scale permet de définir de niveau de zoom initial du viewport, c’est-à-dire son échelle. Nous allons également pouvoir lui passer un nombre entre 0 et 10.

---

### 1.2/ L'élément body

La balise ```body``` est divisée en cinq parties:

![Structure de l'élément body](https://djemai-samy.com/blog/2.programmation/1.web/1.html/1.html-initiation/5.html-page/1-html-page-wireframe.png)

---

#### 1.2.1 En-tête

Le ```header``` est une en-tête pour une page web, en général elle est constituée d'une image en bandeau et d'un titre.

  ```html
  <header>
    <!-- Titre visible de la page -->
    <h1>Bienvenue sur BRAND!</h1>

    <!-- Image visible de la page -->
    <img src="./images/logo.svg" alt="Lettre B en bleu et orange." width="100%"/>
      
    <!-- Déscription visible de la page -->
    <p>
      Lorem ipsum, dolor sit amet consectetur adipisicing elit. 
      Obcaecati soluta rerum quam perspiciatis repudiandae eveniet 
      vero molestiae maxime.
    </p>
  </header>
  ```

---

#### 1.2.2/ Barre de navigation

La barre de navigation ```<nav>```, fait le lien vers les principales parties du site (pages, sections, liens externes...).

Comme l'en‑tête, la barre de navigation reste souvent cohérente d'une page à l'autre:


```html
<nav>
  <!-- Un contenant pour le logo et la marque. -->
  <div>
    <img src="./images/logo.svg" alt="Lettre B en bleu et orange." width="30px"/>
    <span>BRAND</span>
  </div>

  <!-- Une liste de liens vers d'autre page ou sections. -->
  <ul>
    <li><a href="./index.html">Accueil</a></li>
    <li><a href="#articles">Articles</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>

  <!-- Un formulaire de recherche est une autre façon de naviguer. -->
  <form>
    <input type="search" name="q" placeholder="Rechercher" />
    <input type="submit" value="Lancer !" />
  </form>
</nav>
```

- La balise ```<div>``` ou division, est un conteneur générique. Il n'a aucun effet sur le contenu ou la mise en page. Il permet de regrouper des éléments, le logo et le nom de la marque dans notre cas.

  Il sera utile plus tard, quand nous passerons a la mise en forme en CSS.

- la balise ```<ul>```: En général les menus sont des listes de liens, ce qui explique la structure en listes. Question de sémantique et d'accessiblité.
- La balise ```<form>```: Un formulaire de recherche est une autre façon de naviguer de façon non‑linéaire dans un site.

---

#### 1.2.3/ Contenu principal

Le **```main```** est une grande zone au centre contenant la majeure partie du contenu unique de la dite page web, par ex. la vidéo à regarder, le corps de l'article à parcourir, la carte à lire, les dernières nouvelles etc. 

C'est la partie du site variable de page en page.

```html
<main>
    <!--Contenu principale de la page.-->
</main>
```

Nous ajouterons du contenu plus tard en deuxième partie.

---

#### 1.2.4/ Barre latérale

Dans la balise ```aside```, on met souvent quelques informations autour du sujet, liens, citations, annonces, etc.

Habituellement c'est contextuel au contenu principal (par exemple sur une page d'informations, la barre latérale peut contenir la biographie de l'auteur, ou des liens vers des articles connexes).

Mais il y a aussi des cas où vous trouverez des éléments récurrents comme un système de navigation secondaire.

```html
<aside>
  <h2>En relation:</h2>

  <!-- Liste ordonnées des articles de la page-->
  <ol>
    <!-- En relation avec l'article 1-->
    <li>
      <!-- Lien interne vers l'article 1-->
      <a href="#article1">Lorem Ipsum, c'est quoi?</a>

    <!-- Liste de liens externes en relation avec l'article 1-->
      <ul>
        <li>
          <a href="https://fr.wikipedia.org/wiki/Lorem_ipsum" target="_blank">
            Lorem ipsum sur Wikipedia
          </a>
        </li>
        <li>
          <a href="https://loremipsum.io/" target="_blank">
            Générateur de texte Lorem Ipsum
          </a>
        </li>
      </ul>
    </li>

    <!-- En relation avec l'article 2-->
    <li>
      <!-- Lien interne vers l'article 2-->
      <a href="#article2">
        Qui est John Doe ?
      </a>

      <!-- Liste de liens externes en relation avec l'article 2-->
      <ul>
        <li>
          <a href="https://fr.wikipedia.org/wiki/John_Doe" target="_blank">
            John Doe sur Wikipedia
          </a>
        </li>
        <li>
          <a href="https://ui-avatars.com/" target="_blank">
            API générateur d'avatars
          </a>
        </li>
      </ul>
    </li>
  </ol>
</aside>
```

---

### 1.2.5/ Pied de page

Une bande au bas de la page qui contient généralement, en petits caractères, des avis de droit d'auteur ou des coordonnées de contact.

C'est un endroit pour mettre de l'information commune (comme l'en-tête), mais il s'agit dans ce cas d'informations non‑critiques, voire secondaires par rapport au site Web lui-même.

Le pied de page est aussi parfois utilisé à des fins de SEO, en fournissant des liens pour un accès rapide à des contenus prisés.

```html
<footer>
  <p>©Copyright 2050. Tous droits reversés.</p>
</footer>
```

---

## 2/ Le contenu principal

Le contenu de la page est mis dans la balise ```main```, directement à l'intérieur de l'élement ```<body>```. Idéalement, il ne devrait pas être imbriqué dans d'autres éléments.

Il existe la balise ```<section>```,  qui sert à contenir une partie isolée de la page constituant un élément de fonctionnalité en soi (par ex. une petite carte ou un ensemble d'intitulés d'article ou de résumés). 

Il est considéré de bonne pratique de commencer chaque section par un heading.

---

### 2.1/ Section articles

Dans cette section, nous metterons plusieurs articles. 

Pour cela, nous allons utilisé la balise ```article```, une balise qui entoure un bloc de contenu en relation constituant en soi une unité de sens pris isolément par rapport au reste de la page 

(par ex. un unique billet de blog.)

```html
<section id="articles">
  <!-- Titre de la section des articles -->
  <h2>Les articles</h2>

  <!-- Un article -->
  <article id="article1">
    <h3>Lorem Ipsum, c'est quoi?</h2>
    <img src="./images/LoremIpsum.png" width="100%" alt="Icon d'une image sur fond gris">
    <p>
      La phrase latine "<i>Lorem ipsum dolor sit amet consectetur</i>" 
      est utilisée depuis le XVIe siècle par des typographes puis par des graphistes pour 
      visualiser l'espace occupé par un texte et tester les différentes polices de caractères.
    </p>
    <p>
      L'extrait complet
        
      <blockquote cite="https://loremipsum.io/fr/">
        "Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, 
        consectetur, adipisci velit."
      </blockquote>
        
      siginfie

      <blockquote cite="https://fr.wikipedia.org/wiki/Lorem_ipsum">
        "Personne n'aime la douleur en elle-même, 
        ne la recherche et ne la souhaite, 
        tout simplement parce qu'il s'agit de la douleur."
      </blockquote>
    </p>
  </article>

  <!--Balise pour ajouter un ligne de séparation -->
  <hr>

  <!-- Un deuxiemme article -->
  <article id="article2">
    <h3>Qui est John Doe ?</h2>
      <img src="./images/JohnDoe.png" width="100%" alt="Icon d'une image sur fond gris">
    <p>
      En anglais, <strong>John Doe</strong> (version féminine : Jane Doe) est une expression 
      qui désigne <strong>une personne non identifiée</strong> ou un homme de la rue : 
      « Monsieur X », « Monsieur Tout-le-monde ». 
      Pour les très jeunes enfants, l'équivalent est « Baby Doe », 
      ou encore « Jonnie Doe » ou « Janie Doe ».
  </article>
</section>
```

Dans notre section d'articles (2 dans notre exemple), chacque article possede un titre ```<h3>``` et du contenu sous forme de paragraphe, citations...

---

### 2.2/ Section contact

Dans cette section, nous metterons un formulaire permettant aux utlisateurs de nous envoyer des messages en précisant leur email, et le sujet:

```html
<section id="contact">
  <!-- Titre de la section contact -->
  <h2>Contactez nous</h2>

  <!-- Formulaire de contact -->
  <form action="post">
    <!-- Label et champ pour l'email -->
    <label for="email">Votre adresse mail: </label>
    <input id="email" type="email" name="email" placeholder="exemple@exemple.com" />

    <!-- Groupes de choix du sujet-->
    <fieldset>
      <!--Legende du groupe de champs -->
      <legend>Sujet:</legend>
      
      <!-- Label et choix pourposer une question -->
      <input type="radio" id="question" name="sujet" value="question" />
      <label for="question">Vous avez une question?</label>

      <br />    

      <!-- Label et choix pour émettre une réclamation -->
      <input type="radio" id="reclamation" name="sujet" value="reclamation" />
      <label for="reclamation">Vous avez une réclamation?</label>

      <br />
      
      <!-- Label et choix pour autre sujet -->
      <input type="radio" id="autre" name="sujet" value="autre" />
      <label for="autre">Autre chose?</label>
    </fieldset>

    <!--Champs de texte de plusieurs lignes -->
    <label for="message">Votre message</label>
    <br />
    <textarea name="message" id="message" cols="30" rows="10"></textarea>

    <br />
  
    <!--Bouton pour valider le formulaire -->
    <button>Envoyer !</button>
  </form>
</section>
```

---

## 3/ Resultat

### 3.1/ Code complet

Le code complet de la page ressemble a ceci:

```html
<!DOCTYPE html>
<html lang="fr">
  <head>
    <meta charset="utf-8" />
    <meta charset="utf-8" />
            
    <!--Image afficher dans la barre d'onglet-->
    <link rel="icon" href="./favicon.ico">

    <!--Titre du site affiché dans la barre d'onglet-->
    <title>BRAND: Acceuil</title>

    <!--Description du site-->
    <meta name = "description" content= "Déscription de votre site en quelques mots" >
    
    <!-- Image du site-->
    <meta property="og:image"  content="./images/logo.svg">

    <!--Instructions sur la taille et l’échelle du viewport-->
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  </head>

  <body>
    <!-- Voici notre en‑tête principale-->
    <header>
      <!-- Titre visible de la page -->
      <h1>Bienvenue sur BRAND!</h1>

      <!-- Image visible de la page -->
      <img src="./images/logo.svg" alt="Lettre B en bleu et orange." width="100%"/>
    
      <!-- Déscription visible de la page -->
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. 
        Obcaecati soluta rerum quam perspiciatis repudiandae eveniet vero.
      </p>
    </header>

    <!-- La barre de navigation. -->
    <nav>
      <!-- Un contenant pour le logo et la marque. -->
      <div>
        <img src="./images/logo.svg" alt="Lettre B en bleu et orange." width="30px"/>
        <span>BRAND</span>
      </div>

      <!-- Une liste de liens vers d'autre page ou sections. -->
      <ul>
        <li><a href="#">Accueil</a></li>
        <li><a href="#articles">Articles</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>

      <!-- Un formulaire de recherche afin de naviguer de façon non‑linéaire.-->
      <form>
        <input type="search" name="q" placeholder="Rechercher" />
        <input type="submit" value="Lancer !" />
      </form>
    </nav>

    <!-- Ici nous mettons le contenu de la page -->
    <main>
      <!-- La section des articles -->
      <section id="articles">
        <!-- Titre de la section des articles -->
        <h2>Les articles</h2>

        <!-- Un article -->
        <article id="article1">
          <h3>Lorem Ipsum, c'est quoi?</h2>
          <img src="./images/LoremIpsum.png" width="100%" alt="Icon d'une image sur fond gris">
          <p>
            La phrase latine "<i>Lorem ipsum dolor sit amet consectetur</i>" est 
            utilisée depuis le XVIe siècle par des typographes puis par des graphistes 
            pour visualiser l'espace occupé par un texte et tester les différentes
            polices de caractères.
          </p>
          <p>
            L'extrait complet
            
            <blockquote cite="https://loremipsum.io/fr/">
            "Neque porro quisquam est qui dolorem ipsum quia dolor sit amet, 
            consectetur, adipisci velit."
            </blockquote>
            
            siginfie
            <blockquote cite="https://fr.wikipedia.org/wiki/Lorem_ipsum">
            "Personne n'aime la douleur en elle-même, 
            ne la recherche et ne la souhaite, 
            tout simplement parce qu'il s'agit de la douleur."
            </blockquote>
        
          </p>
        </article>
        
        <!--Balise pour ajouter un ligne de séparation -->
        <hr>

        <!-- Un deuxiemme article -->
        <article id="article2">
          <h3>Qui est John Doe ?</h2>
          <img src="./images/JohnDoe.png" width="100%" alt="Icon d'une image sur fond gris">
          <p>
            En anglais, <strong>John Doe</strong> (version féminine : Jane Doe) est 
            une expression qui désigne <strong>une personne non identifiée</strong>:
            « Monsieur X », « Monsieur Tout-le-monde ». 
            Pour les très jeunes enfants, l'équivalent est « Baby Doe », 
            ou encore « Jonnie Doe » ou « Janie Doe ».
          </p>
        </article>
      </section>
    
      <hr>

      <!-- Section contact -->
      <section id="contact">
        <!-- Titre de la section contact -->
        <h2>Contactez nous</h2>

        <!-- Formulaire de contact -->
        <form action="post">
          <!-- Label et champ pour l'email -->
          <label for="email">Votre adresse mail: </label>
          <input id="email" type="email" name="email" placeholder="exemple@exemple.com" />

          <!-- Groupes de choix du sujet-->
          <fieldset>
            <!--Legende du groupe de champs -->
            <legend>Sujet:</legend>
            
            <!-- Label et choix pour pour poser une question -->
            <input type="radio" id="question" name="sujet" value="question" />
            <label for="question">Vous avez une question?</label>

            <br />    

            <!-- Label et choix pour émettre une réclamation -->
            <input type="radio" id="reclamation" name="sujet" value="reclamation" />
            <label for="reclamation">Vous avez une réclamation?</label>

            <br />

            <!-- Label et choix pour un autre sujet -->
            <input type="radio" id="autre" name="sujet" value="autre" />
            <label for="autre">Autre chose?</label>
          </fieldset>

            <!-- Label et champ a plusieur ligne pour le message -->
            <label for="message">Votre message</label>
            <br />
            <textarea name="message" id="message" cols="30" rows="10"></textarea>

            <br />
            
            <!-- Bouton pour valider le formulaire -->
            <button>Envoyer !</button>
        </form>
      </section>
    </main>

    <!-- Le contenu « à côté »-->
    <aside>
      <h2>En relation:</h2>
      <!-- Liste ordonnés des articles de la page-->
      <ol>
        
        <!-- En relation avec l'article 1-->
        <li>
          <!-- Lien vers interne l'article 1-->
          <a href="#article1">Lorem Ipsum, c'est quoi?</a>
          
          <!-- Liste de liens externes en relation avec l'article 1-->
          <ul>
            <li>
              <a href="https://fr.wikipedia.org/wiki/Lorem_ipsum" target="_blank">
                Lorem ipsum sur Wikipedia
              </a>
            </li>
            
            <li>
              <a href="https://loremipsum.io/" target="_blank">
                Générateur de texte Lorem Ipsum
              </a>
            </li>
          </ul>
        </li>
        
        <!-- En relation avec l'article 2-->
        <li>
          <!-- Lien interne vers l'article 2-->
          <a href="#article2">
            Qui est John Doe ?
          </a>
          
          <!-- Liste de liens externes en relation avec l'article 2-->
          <ul>
            <li>
              <a href="https://fr.wikipedia.org/wiki/John_Doe" target="_blank">
                John Doe sur Wikipedia
              </a>
            </li>
            
            <li>
              <a href="https://ui-avatars.com/" target="_blank">
                API générateur d'avatars
              </a>
            </li>
          </ul>
        </li>
      </ol>
    </aside>

    <!-- Le pied de page utilisé sur toutes les pages -->
    <footer>
      <p>©Copyright 2050 par personne. Tous droits reversés.</p>
    </footer>
  </body>
</html>
```

---

### 3.2/ La page

![Image du resultat de la page](https://djemai-samy.com/blog/2.programmation/1.web/1.html/1.html-initiation/5.html-page/3-html-page.png)

## Conclusion

Vous devriez avoir maintenant une meilleure idée de la façon de structurer une page web ou un site web. 

Il est temps de passer à l'étape suivante, et apprendre à styliser les pages web en utilisant le CSS, afin de rendre nos sites web plus lisible et moderne.

## Aller plus loin

[Précédent: HTML: Les formulaires](https://djemai-samy.com/4.html-forms.article)

[Suivant: CSS: Initiation](https://djemai-samy.com/1.css-initation)
