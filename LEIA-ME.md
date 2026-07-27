# Desafio 04 — HTML e CSS (Portal Ford Ranger)

## Antes de entregar, faça isto

1. **Coloque seu nome** no topo do arquivo `css/style.css` (linha "Autor:") e, se seu
   professor pedir, também num comentário no `<head>` de cada HTML.
2. **Imagens**: o projeto usa as fotos reais que você enviou:
   - `img/ranger-black.jpg` — Ranger Black (hero da home, galeria e tabela)
   - `img/xl-cabine.webp` — XL Cabine Simples (galeria e tabela)
   - `img/storm.webp` — Storm (galeria e tabela)
   - `img/logo-ford.png` / `img/favicon-ford.png` — logo oficial (header, rodapé e favicon)
   - `img/info.png` — ícone de informação ao lado do nome de cada versão na tabela (mostra uma dica ao passar o mouse, via atributo `title`)

   ⚠️ Os arquivos `XL_Cabine.jpg` e `storm.jpg` que você enviou estavam, na
   verdade, no formato **WebP** (só a extensão dizia `.jpg`). Por isso eu
   salvei como `.webp` no projeto — os navegadores modernos abrem esse
   formato normalmente, mas se seu professor pedir JPG/PNG puro, é só abrir
   o arquivo em qualquer editor de imagem (ou até o Paint) e salvar de novo
   com a extensão certa.
3. **Renomeie a pasta/zip final** para o padrão pedido no roteiro:
   `desafio_4_HTML_E_CSS<SEU NOME>.zip`.
4. Abra as 3 páginas no navegador e redimensione a janela (ou use o modo
   responsivo do DevTools) para confirmar que o layout se adapta em celular.

## Estrutura de pastas

```
desafio_ford/
├── index.html          → página principal (Ação 2)
├── lancamento.html      → página do veículo (Ação 3)
├── contato.html         → página de contato (Ação 4)
├── css/
│   └── style.css        → todo o CSS do site (cores, tipografia, responsivo)
├── img/
│   ├── ranger-black.jpg      → foto oficial (hero, galeria, tabela)
│   ├── xl-cabine.webp        → foto oficial do modelo XL Cabine Simples
│   ├── storm.webp            → foto oficial do modelo Storm
│   ├── logo-ford.png         → logo oficial (header)
│   ├── favicon-ford.png      → logo oficial pequeno (rodapé / favicon)
│   ├── info.png              → ícone de informação da tabela de modelos
│   ├── facebook-50.png, instagram-50.png, youtube-50.png → ícones do rodapé
└── LEIA-ME.md
```

## Onde cada exigência do roteiro foi atendida

| Exigência do roteiro | Onde está |
|---|---|
| `<header>`, `<main>`, `<footer>` em todas as páginas (Passo 1-3) | Repetidos nos 3 arquivos HTML |
| Footer sempre na base, mesmo com pouco conteúdo (Passo 4) | `body { display:flex; flex-direction:column }` + `main { flex:1 0 auto }` + `.rodape { flex-shrink:0 }` no `style.css` |
| Site responsivo (Passo 5) | Media queries no fim do `style.css` (900px / 700px / 480px) + menu mobile 100% CSS (checkbox hack, sem JS) |
| Logomarca + menu Home/Lançamento/Contato (Passo 6) | `<header>` de `index.html` |
| Imagem do produto + texto na área central (Passo 7) | Seção `.hero` de `index.html` |
| Rodapé com redes sociais + copyright fixo (Passo 8) | `<footer>` de todas as páginas |
| Vídeo promocional + descrição (Passo 9) | Topo de `lancamento.html` (embed do YouTube) |
| 3 imagens ocupando a largura da página (Passo 10) | Seção `.galeria` de `lancamento.html` |
| Modelos disponíveis: fotos, checkbox e botão "Comparar" com movimento visual, sem funcionalidade (Passo 11, adaptado a pedido) | Cards horizontais em `.modelos-lista` no `lancamento.html` + `.btn:hover/:active` no CSS |
| Formulário: nome, e-mail, telefone, tipo de contato, mensagem, botão Enviar com movimento visual (Passo 12) | `contato.html` + `.btn--enviar:hover/:active` no CSS |
| Transição visual no botão Enviar (Passo 13, opcional) | Classe `.btn--enviar:hover` no `style.css` |
| Classes e pseudoclasses | `:hover`, `:focus-visible`, `:checked`, `:nth-of-type`, `:required:invalid`, `:valid`, `:last-of-type`, `::after`, `[aria-current]` — todas usadas com propósito real, não decorativo |
| Fontes externas | Google Fonts: Oswald, Inter, JetBrains Mono (`@import` no topo do CSS) |
| Cores obrigatórias do roteiro | `#1b357e` e `#1351d8` usadas como `--azul-profundo` e `--azul-vivo` |

## Sobre a originalidade do código

O visual segue estritamente o que as Figuras 1, 2 e 3 do roteiro mostram —
header branco com logo e menu, footer azul marinho com redes sociais e
copyright, sem elementos decorativos extras (nada de faixas, ícones fora do
pedido, textos de marketing ou seções que não estejam nos passos 1 a 13).

Para não coincidir com a entrega de outros colegas que sigam o mesmo roteiro,
a diferenciação está no nível estrutural do código, não na estética: nomes de
classes em português (padrão BEM customizado, ex.: `.nav-principal__link`,
`.tabela-modelos`), menu mobile 100% em CSS via checkbox hack (sem
JavaScript) e organização de arquivos própria. Ainda assim, **leia o código
com atenção e ajuste comentários e pequenos textos com suas próprias
palavras** antes de entregar, para garantir que reflete o seu entendimento do
conteúdo.

## Sobre os botões "Comparar carros" e "Enviar"

O projeto **não usa JavaScript**. Os dois botões têm apenas movimento visual
via CSS puro (`transition` + `transform` no `:hover`, `:focus-visible` e
`:active`, em `style.css`): eles "levantam" levemente ao passar o mouse e
"afundam" de volta ao clicar — mas nenhum dos dois executa uma ação real
(nem comparação, nem envio de fato), como o roteiro original já previa para
o botão "Comparar".
