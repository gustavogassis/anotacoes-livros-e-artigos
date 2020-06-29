# BEM(Block, Element and Modifier)

## O que é?
É uma metodologia que visa ajudar o desenvolvedor a criar pedaços reutilizáveis de código, tornando o processo de nomeação de classes no HTML & CSS mais prático, lógico e rápido.

A ideia é dividir a interface em componentes independentes, reutilizáveis e de fácil entendimento de hierarquia e ação, criando um padrão de nomeação de classes que acelera o processo de desenvolvimento do HTML&CSS.

### Bloco
* É único e independente
* Não deve haver dois ou mais blocos com mesmo nome
* É o primeiro componente a ser idealizado e construído, carregando consigo os comportamentos e estilos mais genéricos
* O bloco pode conter elementos ou outros blocos
* Pensando no CSS, a classe de um bloco **descreve o seu propósito nessa interface** (“O que é isso?” Menu, Navbar, Form, etc), e **não como é o seu estilo ou estado** (“Como ele é?” branco, com margin-left: 10px, etc).

```md
1. <div class="error"></div>
Correto: Representa de forma semântica o que aquele bloco é/contém

2. <div class="red-text"></div>
Errado: Descreve a aparência do bloco. Não se sabe qual seu propósito ou o que ele faz
```

### Elemento
* Está diretamente atrelado a um Bloco
* **Não** pode ser utilizado sem um Bloco
* **Depende** de outras estruturas no código para “*existir*”
  * Ex `<li></li>` que depende de um bloco `<ul></ul>` para existir
* **A classe dada a um elemento descreve o seu propósito** (“O que é isso? text, input, label”)

#### Nomenclatura
* `nome-do-bloco__nome-do-elemento`. **O bloco e o elemento são separados por dois underlines** (__).

```html
<form class= "search-form">
    <input class="search-form__input">

    <button class="search-form__button">Pesquisar</button>
</form>
```

### Modificador
* É **Opcional**
* Pode estar atrelado tanto a um **Bloco** como a um **Elemento**
* Carrega caraterísticas específicas de aparência, estado ou comportamento (“Como esse bloco é? O que esse elemento faz?”)
* Um de seus principais usos é quando temos **blocos ou elementos com estruturas iguais**, mas com **estilos ou estados diferentes**.
* O modificador é separado do Elemento ou do Bloco com um underline
```css
.header__navigation { }
  .header__navigation_secondary { }
  .header__navigation_primary { }
```