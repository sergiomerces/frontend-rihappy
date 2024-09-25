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