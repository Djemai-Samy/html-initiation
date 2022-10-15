# HTML: INITIATION

Plusieurs cours et tutoriels pour apprendre à structurer vos pages web en utilisant le HTML. Vous trouverez ici un ensemble d'exemples pour vous familiariser avec les éléments HTML.

[Suivre tous les tutoriels sur mon site:](https://djemai-samy.com/blog/0.html-initiation)

- [HTML: Introduction](https://djemai-samy.com/blog/1.html-introduction.article)
- [HTML: Les textes](https://djemai-samy.com/blog/2.html-texts.article)
- [HTML: Les médias](https://djemai-samy.com/blog/3.html-medias.article)
- [HTML: Les formulaires](https://djemai-samy.com/blog/4.html-forms.article)

---

[Suivre tous les tutoriels sur GITHUB:](https://github.com/Djemai-Samy/html-initiation)

- [HTML: Introduction](https://github.com/Djemai-Samy/html-initiation/tree/main/1.html-introduction)
- [HTML: Les textes](https://github.com/Djemai-Samy/html-initiation/tree/main/2.html-texts)
- [HTML: Les médias](https://github.com/Djemai-Samy/html-initiation/tree/main/3.html-texts)
- [HTML: Les formulaires](https://github.com/Djemai-Samy/html-initiation/tree/main/4.html-forms)

---

## 1/ Le formulaire

Les formulaires HTML sont un des vecteurs principaux d'interaction entre un utilisateur et un site web ou une application.

Ils permettent à l'utilisateur d'envoyer des données au site web. La plupart du temps, ces données sont envoyées à des serveurs web.

Tous les formulaires HTML débutent par un élément `<form>` comme celui-ci :

```html
<form action="/ma-page-de-traitement" method="post"></form>
```

C'est un élément conteneur, il accepte aussi quelques attributs spécifiques afin de contrôler la manière dont il se comporte.

Tous ses attributs sont optionnels mais définir au moins les attributs action et method est considéré comme de bonne pratique.

- L'attribut `action` définit l'emplacement (une URL) où doivent être envoyées les données collectées par le formulaire. Si omis les données seront envoyé sur la meme URL que la page html.

- L'attribut `method` définit la méthode HTTP utilisée pour envoyer les données (cela peut être « get » ou « post »). La methode par défaut est `get`.

---

## 2/ Les entrées de l'utilisateur

L'élément HTML `<input>` est utilisé pour créer un contrôle interactif dans un formulaire web qui permet à l'utilisateur de saisir des données.

Pour commencer, ajoutons a notre page un simple formulaire avec un champs texte (`input`) pour le nom et son étiquette (`label`). Ainsi qu'un bouton pour valider le formulaire:

```html
<form action="/ma-page-de-traitement" method="post">
  <label for="name">Nom: </label>
  <input type="text" id="name" name="user_name" placeholder="Entrez votre nom..." />
  <button>Valider</button>
</form>
```

- L'attribut ```for``` sur tous les éléments ```<label>```, est une manière formelle de lier un libellé à un élément du formulaire. Cet attribut fait référence à l'id de l'élément correspondant.
- Dans l'éléments ```<input>```:
  - ```type```: Dans notre exemple nous n'utilisons que la valeur text et représente un champ de texte basique sur une seule ligne acceptant n'importe quel type de texte.
  - ```placeholder```: Permet d'afficher du texte quand le champs est vide.

Il est possible de renseigner une valeur au champ en utilisant l'attribut ```value```:

```html
<form action="/ma-page-de-traitement" method="post">
  
  <label for="name">Nom: </label>
  
  <input type="text"  
          name="user_name" 
          placeholder="Entrez votre nom..." 
          id="name"
          value="Doe" />
  
  <button>Valider</button>

</form>
```

---

## 3/ Les différents types de champs

La façon dont un élément ```<input>``` fonctionne dépend grandement de la valeur de son attribut type.

### 3.1/ Le type email

Un champ qui permet de saisir une adresse électronique, il ressemble à un champ de type text, mais possède des fonctionnalités de validation et l'adaptation du clavier pour les navigateurs et appareils qui ont des claviers dynamiques.

```html
<label for="email">Email: </label>

<input type="email"  
    name="email" 
    id="email"
    placeholder="exemple@exemple.com" />
```

---

### 3.2/ Le type password

Un champ qui permet de saisir une adresse électronique, il ressemble à un champ de type text, mais possède des fonctionnalités de validation et l'adaptation du clavier pour les navigateurs et appareils qui ont des claviers dynamiques.

Un champ texte sur une seule ligne dont la valeur est masquée et qui affichera une alerte si le site n'est pas sécurisé.

```html
<label for="password">Mot de passe: </label>

<input type="password"  
    name="password" 
    id="password"
    placeholder="Entrez un mot de passe" />
```

---

### 3.3/ Le type date

Un contrôle qui permet de saisir une date (composé d'un jour, d'un mois et d'une année mais sans heure).

Cela ouvre un sélecteur de date ou des roues numériques pour la sélection du jour/mois/année dans les navigateurs qui le prennent en charge.

```html
<label for="date">Date: </label>

<input type="date"  
    name="date" 
    id="date"/>
```

---

### 3.4/ Le type checkbox

Une case à cocher qui permet de sélectionner/désélectionner une valeur.

```html
<fieldset>
    <legend>Sélectionnez des cours:</legend>

    <input type="checkbox" id="html" name="html" value="html" checked/>
    <label for="html">HTML</label>

    <br/>

    <input type="checkbox" id="css" name="css" value="css"/>
    <label for="css">CSS</label>
        
    <br/>
        
    <input type="checkbox" id="javascript" name="javascript" value="javascript"/>
    <label for="javascript">Javascript</label>
</fieldset>
```

---

- ```checked```: Un attribut booléen qui indique si la case est cochée. Cet attribut n'indique pas si la case est actuellement cochée : si l'état a été modifié, l'attribut dans le document ne reflètera pas cette modification.
  
  À la différence des autres champs, les valeurs des cases à cocher ne sont envoyées au serveur que lorsqu'elles sont cochées. Lorsque c'est le cas, c'est la valeur de l'attribut value qui est envoyé.

- ```value```: L'attribut value est partagé par l'ensemble des éléments ```<input>``` mais il a un rôle spécifique pour les champs de type checkbox:
  
  lorsqu'un formulaire est envoyé, seules les cases à cocher qui sont cochées sont envoyées. Si l'attribut value n'est pas renseigné, ce sera la chaîne de caractères "on" qui sera envoyée par défaut.

---

### 3.5/ Le type radio

Les éléments ```<input>``` dont l'attribut type vaut radio sont généralement utilisés pour construire des groupes d'options parmi lesquelles on ne peut choisir qu'une valeur.

Les « boutons radio » sont représentés par des cercles remplis lorsqu'ils sont sélectionnés.

```html
<fieldset>
    <legend>Sélectionnez votre cours préféré:</legend>

    <input type="radio" id="html" name="cours" value="html" />
    <label for="html">HTML</label>

    <br/>

    <input type="radio" id="css" name="cours" value="css"/>
    <label for="css">CSS</label>
        
    <br/>
        
    <input type="radio" id="javascript" name="cours" value="javascript"/>
    <label for="javascript">Javascript</label>
</fieldset>
```

Il est possible d'avoir autant de groupes que nécessaire, il suffit que chaque groupe ait un nom (l'attribut name) unique.

Lorsqu'on envoie le formulaire précédent avec une option sélectionnée, les données du formulaire contiendront une valeur sous la forme ```cours=valeur```.

---

### 3.6/ Le type file

Les éléments ```<input>``` dont l'attribut type vaut "file" permettent à un utilisateur de sélectionner un ou plusieurs fichiers depuis leur appareil et de les uploader vers un serveur via un formulaire ou grâce à du code JavaScript.

```html
<label for="avatar">Choisissez une image:</label>

<input type="file"
        id="avatar" name="avatar"
        accept="image/png, image/jpeg">
```

- ```value```: L'attribut contient une chaîne de caractères (DOMString) qui représente le chemin du/des fichier(s) sélectionné(s).
- ```accept```: Un ou plusieurs identifiants de type de fichier décrivants les types de fichier autorisés.

---

### 3.7/ Le type range

Les éléments ```<input>``` dont l'attribut type vaut range permettent à l'utilisatrice ou l'utilisateur d'indiquer une valeur numérique comprise entre deux bornes.

```html
<label for="volume">Volume:</label>

<input type="range"
        id="volume"
        name="volume"
        min="0" 
        max="10"/>
```

- ```min```: La plus petite valeur autorisée sur l'intervalle. Si la valeur saisie dans le champ (représentée par l'attribut value) est inférieure à ce seuil, la validation échouera (en-US).
- ```max```: La plus grande valeur autorisée sur l'intervalle. Si la valeur saisie dans le champ (représentée par l'attribut value) dépasse ce seuil, la validation échouera (en-US).

Autres attributs:

- ```step```: L'attribut step est un nombre qui définit la granularité à laquelle la valeur doit obéir.

---

## Conclusion

Dans cet article, nous avons vu les champs utilisateurs es plus utilisés, ainsi que les attributs les plus intéressants.

Il existe beaucoup plus de types, ici, vous trouverez une documentation plus approfondie:

[Documentation MDN sur les inputs.](https://developer.mozilla.org/fr/docs/Web/HTML/Element/input)

## Aller plus loin

[Précédent: HTML: Les médias](https://djemai-samy.com/2.html-medias.article)

[Suivant: HTML: Strcture d'un page web](https://djemai-samy.com/1.html-page.article)
