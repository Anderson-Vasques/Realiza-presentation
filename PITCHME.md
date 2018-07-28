@title[FrontEnd jQuery]
# FrontEnd
# jQuery

---
@title[jQuery ???]

###### jQuery é uma biblioteca que torna a manipulação de elementos, adição/remoção de eventos, animação e ajax muito mais simples. Tem uma API simples e funciona nos mais variados browsers.

![Press Down Key](assets/down-arrow.png)

+++
@title[javascritp x jQuery]


```javascript
var hiddenBox = document.getElementById("banner-message");
var button = document.querySelector("#button-container button");
button.addEventListener( "click", function( event ) {
  hiddenBox.style.display = "";
});
```

```javascript
var hiddenBox = $( "#banner-message" );
$( "#button-container button" ).on( "click", function( event ) {
  hiddenBox.show();
});
```

+++

### O jQuery permite o encadeamento de métodos para o mesmo alvo:

```javascript
$("#p1").css("color", "red")
    .slideUp(2000)
    .css("height", "auto")
    .show();
```
#### Os métodos **css**, **slideUp** e **show** - ainda veremos o que cada um faz, são aplicados todos no elemento com o id **p1**


---

### Efeitos

![Press Down Key](assets/down-arrow.png)

+++
@title[hide/show efect]

###### Escondendo elementos com o método **hide()**

```javascript
var paragraphs = $('p');
paragraphs.hide();
```

@[1](Selecionar todos as tags **p** do documento)
@[2](Esconder todas as tags **p**. O jQuery modifica o estilo do elemento adicionando um atributo **style** e adiciona o valor **none** para a propriedade **display**)

+++
@title[hide/show efect with time - explained]
###### O método hide (asssim como o método show e o método toggle) aceita dois parâmetros. O primeiro é o tempo (em milesegundos - 1000, por exemplo - ou uma string com 'slow' ou 'fast') que a animação vai durar. O segundo é uma função que vai ser chamada assim que a animação terminar.

+++
@title[hide/show efect with time]

```javascript
var container = $('#container');
container.hide(1000, function() {
    console.log('O efeito terminou!!!');
});
```

@[1](Selecionar o elemento com id **container**)
@[2-4](Esconder o elemento com id **container**. O jQuery modificará a opacidade do elemento atual - o valor é 1 por padrão -, o width atual será decrescido até 0 - ou min-width, se aplicável - e o height atual será decrescido até 0 - ou min-height, se aplicável. Após isso, o jQuery adicionará o valor **none** para a propriedade **display** do elemento e em seguida executará a função de callback. O tempo percorrido do inicio ao fim do efeito será de 1 segundo.)

+++
@title[show efect]
###### Mostrando elementos com o método **show()**

```javascript
var paragraphs = $('p');
paragraphs.show();
```
@[1](Selecionar todos as tags **p** do documento)
@[2](Mostrar todas as tags **p**. O jQuery modifica o estilo do elemento removendo o valor da propriedade **display** caso ela esteja com o valor **none** no atributo **style**. Caso o elemento esteja com o estilo **display: none** no css, o jQuery exibe o elemento adicionando o atributo **style="display: block;"**.)

+++
@title[show efect with time - explained]
###### O método show aceita dois parâmetros. O primeiro é o tempo (em milesegundos - 1000, por exemplo - ou uma string com 'slow' ou 'fast') que a animação vai durar. O segundo é uma função que vai ser chamada assim que a animação terminar.


+++
@title[show efect with time]

```javascript
var container = $('#container');
container.show(1000, function() {
    console.log('O efeito terminou!!!');
});
```

@[1](Selecionar o elemento com id **container**)
@[2-4](Mostrar o elemento com id **container**. O jQuery exibirá o elemento com width:0, height:0 e opacity:0, e aumentará esses valores progressivamente em 1 segundo. Ao final do efeito a mensagem **O efeito terminou!!!** será exibida no console.)

+++
@title[toggle efect with or without time explained]
###### O método toggle serve para alternar entre os estados de show e hide. Assim como os métodos já comentados, toggle aceita dois parâmetros (que são opcionais): um tempo e uma função para ser chamada ao final do efeito


+++
@title[toggle efect without time ]

```javascript
var container = $('#container');
container.toggle();
```

@[1](Selecionar o elemento com id **container**)
@[2-4](Troca entre show e hide. Se o elemento estiver sendo exibido ele será escondido. Se o elemento não estiver visível ele será exibido. Como o paramâetro de tempo não foi definido, a troca entre os estados ocorrerá instantaneamente)


+++
@title[toggle efect without time ]

```javascript
var container = $('#container');
container.toggle(1000, function() {
    console.log('O efeito terminou!!!');
});
```

@[1](Selecionar o elemento com id **container**.)
@[2-4](Alterar entre o estado **hide** e **show** aplicando o respectivo efeito. Ao final do efeito a mensagem **O efeito terminou!!!** deve ser exibida no console.)

+++
@title[fadeIn fadeOut fadeToggle ]
### fadeIn, fadeOut e fadeToggle

+++
@title[fadeIn fadeOut fadeToggle explained ]
###### A familia de métodos fade aplica um efeito de 'esvanecer' e tem a mesma assinatura dos metodos show/hide/toggle.
###### Nessa animação apenas a opacidade e o display do elemento mudam.

+++
@title[fadeOut example ]

```javascript
var container = $('#container');
container.fadeOut();
```
@[2](O elemento com id **container** terá sua opacidade reduzida a 0 em 400 milesegundos - tempo padrão caso nenhum outro valor seja especificado. Após 400 milesegundos, quando o elemento estiver com a **opacidade** igual a 0, o valor da propriedade **display** é modificado para **none** em um atributo **style**.)

+++
@title[fadeIn example ]

```javascript
var container = $('#container');
container.fadeIn(1000, function() {
    console.log('O efeito terminou!!!');
});
```
@[2-4](O **display** do elemento será modificado da mesma maneira que no método **show**. Após isso a **opacidade** será aumentada progressivamente do valor atual até 1 em 1 segundo, e então a mensagem **O efeito terminou!!!'** será exibida no console.)

+++
@title[fadeToggle example ]

```javascript
var container = $('#container');
container.fadeToggle(1000, function() {
    console.log('O efeito terminou!!!');
});
```
@[2-4](O estado irá alternar entre fadeIn e fadeOut, com animação de 1 segundo. Após o termino da animação a mensagem **O efeito terminou!!!'** será exibida no console.)

+++
@title[slideUp slideDown slideToggle ]
### slideUp, slideDown e slideToggle

+++
@title[slideUp slideDown slideToggle explained ]
###### A familia de métodos slide aplica um efeito de expandir ou recolher e tem a mesma assinatura dos metodos show/hide/toggle.
###### Nessa animação apenas a altura e o display do elemento mudam. A altura é modificada progressivamente durante a animação.

+++
@title[slideUp example ]

```javascript
var container = $('#container');
container.slideUp();
```
@[2](O elemento com id **container** terá sua altura reduzida a 0 em 400 milesegundos - tempo padrão caso nenhum outro valor seja especificado. Após 400 milesegundos, o valor da propriedade **display** é modificado para **none** em um atributo **style**.)

+++
@title[slideDown example ]

```javascript
var container = $('#container');
container.slideDown(1000, function() {
    console.log('O efeito terminou!!!');
});
```
@[2-4](O **display** do elemento será modificado da mesma maneira que no método **show**. Após isso a **altura** será aumentada progressivamente do valor atual até o valor máximo em 1 segundo, e então a mensagem **O efeito terminou!!!'** será exibida no console.)

+++
@title[slideToggle example ]

```javascript
var container = $('#container');
container.slideToggle(1000, function() {
    console.log('O efeito terminou!!!');
});
```
@[2-4](O estado irá alternar entre slideUp e slideDown, com animação de 1 segundo. Após o termino da animação a mensagem **O efeito terminou!!!'** será exibida no console.)

+++
@title[animate ]
### Animate
##### Com o método animate podemos criar animções ao fazer uma transição entre valores de várias propriedades css.

+++
@title[animate explained]
###### Uma das formas mais simples do método animate recebe 3 parametros. O primeiro é um objeto com as propridades css e seus respectivos valores que a animação irá efetuar,o segundo é um numero ou uma string informando a duração da animação e o terceiro parametro é uma função que vai ser executada quando a animação terminar.

+++
@title[animate example]
```javascript
var box = $('#box');
box.animate(
    {
        left: 140,
        width: '200px',
        opacity: .5
    },
    2000,
    function() {
        console.log('Animação concluída');
    }
);
```
@[3-7](Objeto com as propriedades css que devem ser modificadas até o fim da animação.)
@[8](Tempo de duração da animação.)
@[9-11](Função que vai ser executada quando a animação terminar.)

+++
@title[animate chain]
Diferentente dos outros efeitos vistos até agora, o método animate pode ser encadeado.

```javascript
var box = $(".box");
        box.animate({height: '300px',opacity: '0.4'}, "slow", function() {
            console.log('primeira fase completa')
        });
        box.animate({width: '300px', opacity: '0.8'}, 800, function() {
            console.log('segunda fase completa')
        });
        box.animate({height: '100px', opacity: '0.4'}, "slow",function() {
            console.log('terceira fase completa')
        });
        box.animate({width: '100px', opacity: '0.8'}, "slow",function() {
            console.log('quarta fase completa')
        });
```

+++
@title[animate chain explained]
###### Quando a primeira fase da animação for concluída, a segunda fase começará. Ao final da segunda fase, a terceira fase será iniciada...


+++
@title[stop]
#### O método stop serve para parar um efeito ou animação em um ou mais elementos. A animação do elemento selecionado encerrará no momento em o método stop for executado.
###### Esse método funciona com todos efeitos vistos até agora.

+++
@title[stop example html]

```html
    <div id="container"></div>
    <button id="stop-efect">Interromper efeito</button>
```
+++
@title[stop example javascript]

```javascript
    var container = $('#container');
    var button = $('#stop-efect');
    container.fadeOut(10000);
    button.on('click', function() {
        container.stop();
    });
```
@[3](Disparando efeito de fadeOut no elemento de id **container**.)
@[4-6](Adicionando evento de click no elemento de id **stop-efect**. Dessa maneira o efeito será encerrado no momento em que o button for clicado.)
@[5](Parando o efeito de fadeOut.)

+++
@title[stop animation example html]
```html
    <div id="container"></div>
    <button id="stop-animation">Interromper animação</button>
```

+++
@title[stop animation example javascript]

```javascript
    var container = $('#container');
    var button = $('#stop-animation');
    container.animate({left: '400px'}, 10000);
    button.on('click', function() {
        container.stop();
    });
```
@[3](Disparando animação no elemento de id **container**.)
@[4-6](Adicionando evento de click no elemento de id **stop-animation**. Dessa maneira animação será encerrada no momento em que o button for clicado.)
@[5](Parando animação. O elemento vai ficar no estado que estava quando o button foi clicado.)

---
### HTML

![Press Down Key](assets/down-arrow.png)


+++
@title[text html append prepend ... methods]
##### o jQuery possui métodos para interagir com o DOM. Com jQuery é possivel adicionar, editar e remover texto, elementos e atributos.

+++
@title[text method]
###### Para adicionar ou pegar o texto de um elemento podemos utilizar o método text.

+++
@title[text method get mode html]
```html
...
<p id="paragraph">Hello World</p>
...
```
+++
@title[text method get mode javascript]
```javascript
var paragraph = $('#paragraph');
console.log(paragraph.text());
```
@[1](Selecioar o elemento com id **paragraph**.)
@[2](O texto **Hello World** será exibido no console.)

+++
@title[text method get mode 2 html]
```html
...
<p id="paragraph">
    Hello World
    <a target="_blank" href="http://wwww.google.com"> Acesse o google</a>
</p>
...
```

+++
@title[text method get mode 2 javascript]

```javascript
var paragraph = $('#paragraph');
console.log(paragraph.text());
```
@[1](Selecioar o elemento com id **paragraph**.)
@[2](O texto **Hello World Acesse o google** será exibido no console.)

+++
@title[text method set mode]
### Também é possível adicionar texto em um elemento com o método text, basta passarmos o uma string como parâmetro


+++
@title[text method set mode example]

```html
...
<p id="paragraph">Hello World</p>
...
```

```javascript
var paragraph = $('#paragraph');
paragraph.text("Esse texto foi adicionado via javascript");
```

+++
@title[text method set mode example continued]
###### Resultará no seguinte: 

```html
...
<p id="paragraph">Esse texto foi adicionado via javascript</p>
...
```

+++
@title[text method set mode example 2]

```html
...
<p id="paragraph">
    Hello World
    <a target="_blank" href="http://wwww.google.com">Acesse o google</a>
</p>
...
```

```javascript
var paragraph = $('#paragraph');
paragraph.text("Esse texto foi adicionado via javascript");
```

+++
@title[text method set mode example 2 continued]
###### Resultará no seguinte: 

```html
...
<p id="paragraph">Esse texto foi adicionado via javascript</p>
...
```

+++
@title[html method]
###### Sem quiser pegar o html de dentro de um elemento, basta usar o método html. Também é possivel passar um parâmetro se quiser adicionar conteúdo html para uma página.

+++

@title[html method get mode html]
```html
...
<p id="paragraph">
    Hello World
    <a target="_blank" href="http://wwww.google.com">Acesse o google</a>
</p>
...
```

+++
@title[html method get mode javascript]

```javascript
var paragraph = $('#paragraph');
console.log(paragraph.html());
```
@[2](A seguinte mensagem deve aparecer no console: **Hello World <a target="_blank" href="http://wwww.google.com">Acesse o google</a>**)


+++
@title[html method set html]
```html
...
<p id="paragraph">
    Hello World
    <a target="_blank" href="http://wwww.google.com">Acesse o google</a>
</p>
...
```

+++
@title[html method set mode javascript]

```javascript
var paragraph = $('#paragraph');
console.log(paragraph.text('<span>Esse texto foi adicionado via javascript<span>'));
```
@[2](O conteúdo do elemento selecionado será substituido por **<span>Esse texto foi adicionado via javascript<span>**.)

+++
@title[html method set mode html result]

```html
...
<p id="paragraph">
    <span>Esse texto foi adicionado via javascript<span>
</p>
...


---
### Code-Blocks
##### Using
#### Code-Presenting
#### **With Annotations**

![Press Down Key](assets/down-arrow.png)

+++
@title[Sample With Annotations]

```python
from time import localtime

activities = {8: 'Sleeping', 9: 'Commuting', 17: 'Working',
              18: 'Commuting', 20: 'Eating', 22: 'Resting' }

time_now = localtime()
hour = time_now.tm_hour

for activity_time in sorted(activities.keys()):
    if hour < activity_time:
        print activities[activity_time]
        break
else:
    print 'Unknown, AFK or sleeping!'
```

@[1](Python from..import statement)
@[3-4](Python dictionary initialization block)
@[6-7](Python working with time)
@[9-14](Python for..else statement)

---
@title[Working with Source Files]

### Naturally
### Code-Presenting
### works in exactly the same way on [Code-Delimiter Slides](https://github.com/gitpitch/gitpitch/wiki/Code-Delimiter-Slides) as it does on [Code-Blocks](https://github.com/gitpitch/gitpitch/wiki/Code-Slides).

---
@title[Code Delimiter Syntax]

### Code-Delimiter Slides

```
                  ---?code=path/to/source.file
```

#### The Basics

![Press Down Key](assets/down-arrow.png)

+++?code=src/python/time.py&lang=python
@title[Sample Source File]

###### Code delimiters let you present any <p> **code file** with auto-syntax highlighting

---
@title[Code-Delimiter Slides]

### Code-Delimiter Slides
##### Using
#### **Code-Presenting**

![Press Down Key](assets/down-arrow.png)

+++?code=src/javascript/config.js&lang=javascript
@title[Sample Code Presenting]

@[1-3]
@[5-8]
@[10-16]
@[18-24]

###### Use code-presenting to **step-thru** code <p> from directly within your presentation 

---

### Code-Delimiter Slides
##### Using
#### Code-Presenting
#### **With Annotations**

![Press Down Key](assets/down-arrow.png)

+++?code=src/elixir/monitor.ex&lang=elixir
@title[Sample With Annotations]

@[11-14](Elixir module-attributes as constants)
@[22-28](Elixir with-statement for conciseness)
@[171-177](Elixir case-statement pattern matching)
@[179-185](Elixir pipe-mechanism for composing functions)

---

### Learn By Example
#### View The [Presentation Markdown](https://github.com/gitpitch/code-presenting/blob/master/PITCHME.md)