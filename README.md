# CSS Order Caker :birthday:

Uma ferramenta __DESKTOP__ desenvolvida para organizar o código __CSS__ em ordem alfabética.

Para acessar a ferramenta, clique no link: __https://css-order-caker.netlify.app/__

## Instalação

### 1. Faça a clonagem do repositório:
```
git clone https://github.com/HeronNepomuceno/css-order-caker.git
```

### 2. Entre na pasta do projeto:
```
cd css-order-caker
```

## Instalando o vuejs, executando o comando abaixo, todos os módulos da lista de dependências vão ser instalados:
```
npm install
```

### Executando o comando abaixo, vai rodar o servidor e no terminal vai ser lançado o link de acesso do projeto
```
npm run serve
```

### Para gerar um arquivo "dist/" (ideal para o deploy), execute o comando abaixo
```
npm run build
```
## Observações sobre a ferramenta:

1. A interface dessa ferramenta tem suporte apenas para telas de computadores. Não há qualquer responsividade no layout do site, isso se deve ao fato de que não consigo imaginar alguém com interesse de utilizar essa ferramenta pelo seu celular ou tablet.

2. Não existe qualquer verificação do que está sendo escrito no textarea habilitato. Ou seja, o que se espera, é um código css formatado na sua sintaxe ideal, mas caso o código não venha dessa forma, ainda haverá um retorno misterioso no textarea de saída.

3. Atualmente, o projeto ainda esta em uma fase beta, mas a ideia é que ele seja extendido e suporte a maioria das tecnologias css, dentre elas: _Stylus, Less, Sass._ E também, que exista outras formas de ordenamento, além de ordem alfabética, dentre elas: _ordem crescente e decrescente de quantidade de caracteres._ Dessa forma, por enquanto, **a sessão do site "Choose your css tecnology:" ainda está completamente estática, e não interfere em nada no funcionamento da ferramenta.**

![Sem título](https://user-images.githubusercontent.com/67935408/156941714-806c1b3f-8d52-482d-b6c9-8ffc107d45e8.png)

## Problemas da Ferramenta

- A ferramenta ainda não tem suporte para organizar **ID's**, então se seu CSS tiver alguma ID, o resultado apresentado na saída pode apresentar problemas.
- A ferramenta ainda não tem suporte para acesso a tags nativas, por ex: "body, li, ul...".
- Utilizar linkagem de url de imagens podem causar problemas na saída do css, pois pode acabar entrando em conflito com os caracteres especiais lançados no replace.
- O conteúdo entre as chaves não tem um tab ou espaço antes de casa item, mas esse problema pode ser facilmente resolvido se você usar o comando "Shift + Alt + F" do vscode para identar o código.
- Items com mais de 1 caracteristica, como "border: 1px solid #000", nesses casos, tudo apos os ":" vai ficar sem espaçamento, ou seja, pode acabar dando erro no css.

___*Estou trabalhando para resolver essas issues do projeto, pelo menos as mais importantes___

## Utilizando a ferramenta

Mesmo com seus problemas, a ferramenta é perfeitamente usável e útil para quem quer ter seu CSS organizado em ordem alfabética, facilitando a procura por items especificos, no final de cada dia programando, fazer essa organização irá melhorar bastante na legibilidade do seu código. Abaixo eu colocarei um link do linkedin dando um exemplo de usabilidade:
