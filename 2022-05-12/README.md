# CSS

---

CSS, ou *Cascading Style Sheets*, é uma linguagem que permite que o programador aplique formatação a um determinado conteúdo, tradicionalmente a um arquivo HTML, embora possa se extender a outros tipos de arquivo.
A formatação é aplicada no HTML, a partir dos seguintes métodos:

* Inline CSS
* Internal CSS (ou CSS integrado)
* External CSS

## Uso dos formatadores

CSS pode ser aplicado a:

* Tags
* Classes
* IDs

Seus estilos são definidos com `tipo: formatador;`

```css
background-color: beige; 
width: fit-content; 
font-size: 100px; 
font-weight: bolder; 
```

* Aplicação de estilo em uma tag: `tag { styles }`.
* Aplicação de estilo em uma classe: `.myClass { styles }`.
* Aplicação de estilo em uma ID: `#myID { styles }`.

O uso em uma tag aplicará o estilo para todas as aparições dessa tag em todo o escopo do arquivo.
Classes devem ser usadas para estilos que se repetem, e IDs para alterações locais específicas, já que IDs não devem ser repetidos.

Já que os estilos funcionam em cascata, um elemento pode receber formatação inline, por id, por classe e por elemento, simultaneamente.
Todos os estilos desses caso serão aplicados nessa tag, e estilos repetidos obedecerão a hierarquia.

Múltiplas classes podem ser aplicadas em um mesmo elemento.

```html
<span class="class1, class2"> </span>
```

> O "estilo em cascata" significa que várias formatações diferentes podem se sobrepor, obedecendo a uma hierarquia.

---

### Inline CSS

Esse método trata-se da aplicação do CSS dentro de uma tag html, a partir da propriedade global *"style"*.
Inline é útil apenas para aplicação de poucas formatações em um local específico, devido a falta de reuso.
Limite seu uso sempre para de uma a três formatações, no máximo.

> Estilos inline devem ser evitados para garantir consistência no código, facilidade de leitura e facilitar o entendimento.

**Exemplo:**

```html
<span style="color: darkblue; font-size: 20px"> Oi! </span>
```

**Resultado:**

<span style="color: darkblue; font-size: 20px"> Oi! </span>

---

### Internal CSS

Internal CSS trata-se da aplicação de CSS dentro do arquivo HTML no escopo de uma tag `<style>`.
É o ideal para aplicações simples, permitindo a escrita de formatadores muito mais organizados e bem separados.

**Exemplo:**

```html
<body>
    <span>Texto 1</span>
    
    <p id="identificador">
        Texto 2
    </p>

    <span class="class1">Texto 3</span>
</body>

<style>
    /* Exemplo com tag */
    span {
        font-size: 10px;
        font-family: "Comic Sans MS", cursive, sans-serif;
    }

    /* Exemplo com ID */
    #identificador {
        color: violet;
    }

    /* Exemplo com class */
    .class1 {
        background-color: red;
        opacity: 50%;
    }
</style>
```

---

### External CSS

O CSS externo é, geralmente, o método preferível para aplicação de CSS em projetos grandes.
Trata-se da criação de um arquivo .css externo, que será referenciado dentro do HTML, para a utilização de seus estilos.

Com esse método, múltiplas páginas podem utilizar da mesma stylesheet devido a referência, facilitando o processo de desenvolvimento.

Para refereciar a stylesheet, utilize:

```html
<link rel="stylesheet" type="text/css" href="styles.css">
```

No arquivo CSS, coloque as referências a IDs e classes, juntamente com os estilos a serem aplicados nas tags.

## Considerações

Todos os três métodos, devido a natureza de cascata do CSS, podem ser utilizados simultaneamente.

Para definir o que uma classe deve fazer apenas quando aplicada a um tipo de elemento específico, informe a sua tag, seguida de um ponto, seguida do nome da classe. 

```css
/* Faz com que o texto de todas as tags span que recebem a classe MyClass fiquem em negrito. */
span.myClass{
    font-weight: bold;
}
```
