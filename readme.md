## Guia básico dos meus aprendizados com o JavaScript.

O JavaScript(JS) é uma linguagem de programação dinâmica que nos fornece diversas funcionalidades, juntamente com o HTML e CSS.
No editor de códigos de sua preferência (irei usar como base o Visual Studio Code), você irá conseguir utilizar o JS de 2 maneiras:

1ª- No arquivo _index.html_, basta criar dentro da tag _body_, uma tag _script_, dessa maneira:
```javascript
<body>
    <script>
        código vai aqui!
    </script>
</body>
```

![script no head](imgs\scriptDentroDoBody.png)

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

Agora, aperte F12 para abrir o DevTools. E vamos inserir uma mensagem para ver se ambos arquivos estão conectados corretamente:

```javascript
console.log('testando...')
```

![console browser](imgs/consoleBrowser.png)

Como podemos ver, o teste retornou certinho. 