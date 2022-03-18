---
sidebar_position: 1
---

# Rendu déclaratif 

Au cœur de Vue.js, il y a un système qui va nous permettre de faire le rendu des données déclarativement dans le DOM en utilisant simplement cette syntaxe de template :

```html

<div id="app">
  {{ message }}
</div>

```
```js

var app = new Vue({
  el: '#app',
  data: {
    message: 'Hello Vue !'
  }
})

```

## Résultat
| Hello World                                                                         |
| ----------------------------------------------------------------------------------- |
Nous venons tout juste de créer notre première application Vue ! Ça ressemble à un simple rendu de template en chaine de caractères, mais sous le capot, Vue effectue un réel travail. Les données et le DOM sont maintenant couplés, et tout est à présent réactif. Comment s’en rendre compte ? Ouvrez juste la console JavaScript de votre navigateur (là maintenant, sur cette page) et attribuez à app.message différentes valeurs. Vous devriez voir le rendu de l’exemple en cours se mettre à jour en concordance.

Notez que nous n’avons plus besoin d’interagir directement avec le HTML. Une application Vue s’attache à un seul élément DOM (#app dans notre cas) puis le contrôle entièrement. Le HTML est notre point d’entrée, mais tout le reste se passe au sein de la nouvelle instance Vue.

En plus de l’interpolation de texte, nous pouvons également lier les attributs d’un élément comme ceci :

```html
<div id="app-2">
  <span v-bind:title="message">
    Passez votre souris sur moi pendant quelques secondes
    pour voir mon titre lié dynamiquement !
  </span>
</div>

```
```js
var app2 = new Vue({
  el: '#app-2',
  data: {
    message: 'Vous avez affiché cette page le ' + new Date().toLocaleString()
  }
})

```
## Résultat

| Passez votre souris sur moi pendant quelques secondes pour voir mon titre lié dynamiquement ! |                                                                     |
| ----------------------------------------------------------------------------------- |

Ici nous venons de rencontrer quelque chose de nouveau. L’attribut v-bind que vous voyez est appelé une directive. Les directives sont préfixées par v- pour indiquer que ce sont des attributs spéciaux fournis par Vue, et comme vous l’avez peut-être deviné, elles appliquent un comportement réactif spécifique au DOM après rendu. Ici cela veut tout simplement dire : « garde l’attribut title de cet élément à jour avec la propriété message de l’instance de Vue ».