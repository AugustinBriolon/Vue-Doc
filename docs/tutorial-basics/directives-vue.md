---
sidebar_position: 3
---


# Les directives Vue

Les directives Vue.js sont des attributs HTML qui peuvent être insérés dans votre page afin de modifier le rendu de votre application Vue.

Voici la liste des directives disponible:

### v-bind

Permet d'assigner une expression à un attribut. Vue va remplacer l'expression par sa valeur

```js
<img v-bind:src="image_url" />

// ou syntaxe raccourcie
<img :src="image_url" />

```

### v-once

Avec la directive v-once Vue va interpolé l'expression seulement une fois. L'expression sera donc ignorée pour tous les autres rafraîchissements

```js
<div v-once>
   {{ title }}
</div>

```

### v-model

Permet de lier la valeur d'un champ de saisie avec une variable. Si vous modifiez l'un ou l'autre Vue mettra à jour automatiquement l'autre. Du coup, la variable et le champ de saisie auront toujours la même valeur.

```js
<input v-model="name" type="text" />
<div>
    Nom : {{ name }}
</div>

```

### v-if, v-else-if et v-else

Rend un élément visible ou invisible selon la valeur vrai ou faux de l'expression. Lorsque non visible l'élément n'est pas rendu dans le html

```js
<div v-if="montant > 100">
    Livraison gratuite!
<div>
<div v-else-if="montant > 50">
    Livraison 9.95$
</div>
<div v-else>
    Livraison 19.95$
</div>

```

### v-for

Permet d'afficher une liste d'élément

```js

<ul>
    <li v-for="item in items" :key="item.id">
        {{ item.name }}
    </li>
</ul>

```
À noter le mot-clé "key" est nécessaire pour permettre à Vue d'identifier uniquement l'élément
create-a-page.md
6 Ko