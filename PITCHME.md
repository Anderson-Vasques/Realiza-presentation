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
@title[hide/show efect with time]

###### O método hide (asssim como o método show e o método toggle) aceita dois parâmetros. O primeiro é o tempo (em milesegundos) que a animação vai durar. O segundo é uma função que vai ser chamada assim que a animação terminar.

```javascript
var container = $('#container');
container.hide(1000, function() {
    console.log('O efeito terminou!!!');
});
```

@[1](Selecionar o elemento com id **container**)
@[2](Esconder o elemento com id **container**. O jQuery modificará a opacidade do elemento atual (o valor é 1 por padrão),  o width atual será decrescido até 0 (ou min-width, se aplicável) e o height a atual será decrescido até 0 (ou min-height, se aplicável). Após isso o jQuery adicionaráo valor **none** para a propriedade **display** do elemento e em seguida executará a função

+++
@title[show efect]
###### Mostrando elementos com o método **show()**

```javascript
var paragraphs = $('p');
paragraphs.show();
```

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