## Guia básico dos meus aprendizados com o JavaScript.

O JavaScript(JS) é uma linguagem de programação dinâmica que nos fornece diversas funcionalidades, juntamente com o HTML e CSS.
No editor de códigos de sua preferência (irei usar como base o Visual Studio Code), você irá conseguir utilizar o JS de 2 maneiras:

1ª- No arquivo _index.html_, basta criar dentro da tag _body_, uma tag _script_, dessa maneira:
```javascript
<body>
    <script>
        // código vai aqui!
    </script>
</body>
```
2ª- Também no arquivo _index.html_, utilizar um link dentro do _head_ direcionado à um novo
arquivo _script.js_, e lá inserindo seus comandos em JavaScript, deixando o código mais organizado e limpo (sendo a maneira mais indicada), por exemplo:
```javascript
<head>
    <script src="script.js"></script>
</head>
```

![js sendo referenciado](imgs/scriptNoHead.png)

> Atalho: Ctrl + click -> clicando no _script.js_, automaticamente irá criar o tipo de arquivo escrito.

## - `Console`
O console é uma ferramenta existente tanto no navegador quanto no editor de código, que nos exibe informações, erros e é bastante utilizada para testes.

* Em falar em console, devemos falar também do _log_, um método que é usado para exibir mensagens. Para isso, copie o caminho do seu arquivo _index.html_ e cole no navegador de sua preferência.

![path do index](imgs/pathIndex.png)

Agora, aperte F12 para abrir o DevTools. E vamos inserir uma mensagem na 1ª linha do _script.js_ para ver se ambos arquivos estão conectados corretamente:

```javascript
console.log('testando...')
```

![console browser](imgs/consoleBrowser.png)

Como podemos ver, o teste retornou certinho.


## Variáveis

Existem 3 tipos de variáveis para a declaração de atribuições no JS. Sendo elas: **var**, **let** e **const**. E para tratarmos desse assunto, devemos falar do _ESCOPO_, que se refere a visibilidade e acessibilidade de variáveis e outros...<br>O escopo define as áreas onde essas entidades são válidas.

### - Escopo Global
É o mais amplo, variáveis declaradas no global são visíveis em todo o código (somente _var_ é também visível no global do navegador).<br>Como exemplo vamos declarar uma variável:

![window variable](imgs/varNoGlobalWindowConsole.png)

Ao abrir o console e digitarmos _window_, podemos ver que o _age = 22_ está lá!

### - Escopo Local
Se refere à um escopo delimitado dentro de uma função, variáveis criadas dentro delas não podem ser acessadas fora desse escopo. O que permite a criação de variáveis com o mesmo nome!

![local escope](imgs/escopoLocalVariaveis.png)

Agora vamos tentar chamar a variável de fora da _function:_

![is not defined error](imgs/isNotDefinedERROR.png)

Percebemos no aviso de erro que a variável aparece como não definida, pois não é possível acessá-los em ambos (_let_ ou _var_) os casos.

### - Escopo em Bloco
É caracterizado quando o pedaço de código está entre chaves `{}`, seja num _else_, num _do_ etc. Vejamos:

> _PS:_ Por algum motivo o JS aceita códigos somente entre chaves.

![bloco escope ok](imgs/letAndVarOkBloco.png)

Agora vamos tentar chamar essas variáveis de fora da função...

![var ok, let error](imgs/letUndefinedVarOk.png)

O _let_ é limitado a ser chamado somente dentro do bloco, já o _var_ é acessível fora dele, pois são içadas (_hoisting_) para o topo do escopo externo do bloco, veremos mais detalhes na descrição da palavra-chave _VAR_ abaixo.

* _LET:_ Tem escopo global _(do arquivo js)_, local e em bloco.<br>- Não são visíveis fora do bloco, podendo ser referenciadas somente dentro dele.<br>- Não são içadas para o topo do escopo onde foram declaradas, podendo ser acessadas somente depois de sua declaração.

---

* _VAR:_ Tem escopo global e local.<br>- Não são limitadas por blocos, podendo ser visiveis em todo o escopo da função em que se encontra ou no objeto global.<br> - São içadas para o topo do escopo onde foram declaradas, tornando a declaração _undefined_, consequentemente, não movendo sua atribuição.

---

* _CONST:_ Depois de declarada sua atribuição não é permitido a alteração da mesma, por isso do nome.

## Operadores

Operadores são símbolos que executam uma operação matemática ou lógica. Para esse módulo, iremos utilizar o terminal do _node.js_, para visualizarmos todo o desenrolar lógico.

Abrir console do node.js _ctrl + '_

```javascript
let x = 5

    x + 2 = 7 (adição)
    x - 2 = 3 (subtração)
    x * 2 = 10 (multiplicação)
    x / 2 = 2.5 (divisão)
    x % 2 = 1 (resto da divisão inteira)
    x ** 2 = 25 (ao quadrado)
```

## Precedência de operações

    ()
    **
    * / %
    + -

## Autoatribuições

    var x = 10

    var x -= 2 subtrai > 8
    var x += 2 adiciona > 12
    var x *= 2 multiplica > 20
    var x /= 2 divide > 5
    var x **= 2 quadrado > 100
    var x %= 2 resto int > 0

## Atalho

    x++ > 11 executa a conta, mas mostra somente depois
    ++x > 11 executa e já mostra a conta
    --x > 9 executa e já mostra a conta
    x-- > 9 executa a conta, mas mostra somente depois

## Operadores Relacionais

    > maior
    < menor
    == igual
    >= maior ou igual
    <= menor ou igual
    != diferente

## Identidade

    5 === '5' false
    5 === 5 true

    var a = 1
    var b = '1'

    a != b false
    a !== b true

## Lógicos

    ! - negação unário
    false > true
    true > false

    && - conjunção binário
    true true > true
    true false > false
    false false > false
    false true > false

    || - disjunção binário
    true true > true
    true false > true
    false false > false
    false true > true

Quando se tem operadores aritméticos, relacionais e lógicos numa mesma expressão, essa é a ordem de calculo:

    1º aritméticos - 2º relacionais - 3º lógicos.
    ex:
    var a = 5
    var b = 8

    a > b && b % 2 == 0
    false

Caso numa mesma expressão houver &&, || e !<br>A ordem correta será: 1º ! - 2º && - 3º ||

## Ternário

    teste ? true : false
    ex: média da disciplina é >= 6 ? "Aprovado" : "Reprovado"

    média = 6
    var aprovacao = média >= 6 ? 'Aprovado' : 'Reprovado'
    aprovacao == 'Aprovado'