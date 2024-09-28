![imagem de código fonte](https://dri.es/files/cache/blog/javascript-close-up-1280w.jpg)

# Bootcamp Ri Happy Frontend do Zero
Repositório de notas, atividades e projetos do bootcamp de Frontend Web Developer com JavaScript oferecidos pela DIO e Ri Happpy


## HTML semântico

Como uma melhor prática de escrita de código, o HTML5 trouxe como uma evolução a substituição de *tags* genéricas como **div** por outras que dão melhor sentido ao código, como a introdução das *tags*:
* **header**
* **aside**
* **main**
* **footer**
* **nav**
* **article**
* **section**.

Esses elementos auxiliam numa melhor compreensão da estrutura do código. Com isso o HTML deixa ter importância para formatação do conteúdo e passa a se preocupar muito mais com a sua estruturação.

## HTML4 X HTML5

A **W3C - World Wide Web Consortium** organização de padronização da internet colocou em desuso as *tags* de formatação do **HTML4**, ficando a formatação a cargo das folhas de estilo (*cascading stile sheet*) **CSS3**.
Algumas da *tags* em desuso:

* basefont
* big
* center
* font
* strike
* tt
* frame
* frameset

Exemplo de código base em HTML5 no ex001:

    <!DOCTYPE html>
    <html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Document</title>
    </head>
    <body>
        <header>
            <nav></nav>
        </header>
        <main>
            <section>
                <article></article>
            </section>
            <section>
                <article></article>
            </section>
        </main>
        <footer></footer>
    </body>
    </html>

## Acessibilidade
Diz respeito as tecnologias e mecanismos que tornem o conteúdo das páginas acessíveis às pessoas que possuam necessidades especiais de visão, audição ou limitação de movimentos.

A boa prática buscar estabelecer padrões para que todos os usuários possam explorar todo o potencial dos conteúdos.

O atributo *alt* na tag **img** é lida por leitores de tela quando a página é carregada, permitindo que uma pessoa com deficiência visual possa ouvir o texto associado à imagem, como demosntrado no ex002.

    <!DOCTYPE html>
    <html lang="pt-br">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>Acessibilidade</title>
    </head>
    <body>
        <img src="./banner.png" alt="somos longas histórias feitas de pequenos instantes">
    </body>
    </html>

A **ARIA - Acessible Ritch Internet Application** é um recurso que utiliza a estrutura *DOM - Document Object Model* da página. A ARIA não muda a característica da tag, mas da ávore DOM a partir de atributos.

## Web Scraping

*Crawler* (rastreador) é conhecido como robô, indexador, é um termo genérico para qualquer aplicação para descobrir e examinar sites automaticamente seguindo links entre páginas web.

Crawlers como o *GoogleBot* entram no site e buscam informações para serem indexadas, o HTML semântico facilita o reconhecimento dessas informações.

*Web Scraping* é a ação de um indexador entrar num site extrair uma informações e gravar num arquivo ou banco de dados.

## main, header e footer

A tag *main* não pode ser filha de nenhuma outra a não ser o *body* ou de uma *div*, pois ela é o suporte do conteúdo principal da página. 
Só pode existir um único elemento *main* por página; porém ele pode suportar os demais elementos como filhos.

## section, aside e nav

O elemento *section* é a demarcação de um conteúdo independente que vai aparecer na pesquisa depois de indexado pelo crawler.

O elemento *aside* é um conteúdo que não tem relacão direta com o conteúdo principal.

O elemento *section* deve ser usado quando for relevante seu aparecimento destacado na estrutura do documento, se for apenas como suporte de formatação o correto seria usar *div*.

## article, bloquote e q

O elemento *article* permite aninhamento interno e isso cria a ideia semântica de que um conteúdo filho esteja relacionado ao pai.

Um recurso interessante para tornar mais semântico por exemplo datas é usar a tag *time* dentro *article*.

O elemento *blockquote* é usado para citações longas, o atributo *cite* serve para informar a relação entre o artigo em que se está trabalhando e outra fonte na Web.

O elemento *q* é usado para citações curtas, acrecentando aspas, porém não suporta múltiplos parágrafos.

## figure, figcaption e picture

O elemento *figure* é um contâiner para delimitação de imagens e ilustrações, o *figcaption* cria uma legenda relaciona a imagem.

O elemento *picture* com auxílio da tag *source* cria imagens responsivas que se ajustam à tela de acordo com a largura.

    <picture>
        <source srcset="./optimus-truck-p.png" media="(max-width:300px)">
        <source srcset="./optimus-truck-p.png" media="(max-width:600px)">
        <img src="./optimus-truck.png" alt="">
    </picture>

## SEO - Search Engine Opmization

Trata-se da otimização do conteúdo para que seja mais relevante para indexação dos buscadores.

---

## Formulários

Formulaŕio é um trecho de uma página HTML onde o usuário pode inserir informação.
Essa informação do lado do cliente é enviada ao servidor através da internet, o servidor pode ou não gravar essa informação no banco de dados.

Principais elementos:

* label
* input (text, number, button, tel, email, url, date, radio, checkbox, password, file, search)
* button

## checkbox e radio

O *checkbox* é uma caixa de seleção que permite marcarmos múltiplos valores (*values*). Uma inportante dica é que o seu atributo *name* deve ser escrito acompanhado de colchetes, assim quendo o formulário for recebido no servidor o *PHP* o campo será entendido como um *array*:

    <h3>Você selecionou: Pizza de Calabreza</h3>
    <p>Quais opcionais você deseja?</p>
    <input type="checkbox" name="opcional[]" value="queijo"> + queijo<br>
    <input type="checkbox" name="opcional[]" value="calabresa"> + calabreza<br>
    <input type="checkbox" name="opcional[]" value="cebola"> + cebola<br>
    <input type="checkbox" name="opcional[]" value="azeitona"> + azeitona<br>

No *PHP*:

    ?opcional["queijo", "cebola", "azeitona"]

Ao adicionarmos a propriedade *disabled* num *checkbox* ele não poderá mais ser marcado, permanecerá desabilitado.

## buttons

Temos trŝ tipos:

* *button* - apenas um elemento clicável que só realiza uma ação se houver um script

* *submit* - envia o formulário para o servidor

* *reset* - limpa os dados do formulário

        <main>
            <form name="signup" method="get" autcomplete="on" action="#" target="_blank" onsubmit="alert('Enviado!');">
                Nome: <input type="text" name="name" id="name"><br>
                Idade: <input type="number" name="age" id="age"><br>
                Senha: <input type="password" name="password" id="password"><br>
                <button type="button" onclick="alert('Enviado!');">Button</button>
                <button type="submit">Submit</button>
                <button type="reset">Reset</button>
            </form>
        </main>


