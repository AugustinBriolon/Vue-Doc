---
sidebar_position: 2
---
# Conditions et boucles

Il est assez simple de permuter la présence d’un élément :

```html

<div id="app-3">
  <p v-if="seen">Maintenant vous me voyez</p>
</div>

```

```js

<div id="app-3">
var app3 = new Vue({
  el: '#app-3',
  data: {
    seen: true
  }
})

```
Côté console entrez app3.seen = false. Vous devriez voir le message disparaitre.

Cet exemple démontre que nous pouvons lier des données non seulement aux textes et attributs, mais également à la structure du DOM. De plus, Vue fournit un puissant système d’effets de transition qui peut automatiquement appliquer des effets de transition quand des éléments sont insérés/mis à jour/enlevés par Vue.

Il existe quelques autres directives, chacune avec leur propre fonction spécifique. Par exemple, la directive v-for peut être utilisée pour afficher une liste d’éléments en provenance d’un tableau de données

```html
<div id="app-4">
  <ol>
    <li v-for="todo in todos">
      {{ todo.text }}
    </li>
  </ol>
</div>

```

```js
var app4 = new Vue({
  el: '#app-4',
  data: {
    todos: [
      { text: 'Apprendre JavaScript' },
      { text: 'Apprendre Vue' },
      { text: 'Créer quelque chose de génial' }
    ]
  }
})

```
| - Apprendre JavaScript             |
|----------------------------------------------------------------------------------- |

| - Apprendre Vue    |         
|----------------------------------------------------------------------------------- |

| - Créer quelque chose de génial  |          
|----------------------------------------------------------------------------------- |

Dans la console, entrez app4.todos.push({ text: 'Nouvel élément' }). Vous devriez le voir ajouté à la liste.
