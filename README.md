# auxilioacidente.keniaportilho.com.br

Landing page de auxílio-acidente do escritório **Kênia Portilho — Advocacia Previdenciária**.

Site estático, sem framework e sem build. É só HTML, CSS e JavaScript em um único arquivo (`index.html`), com as imagens em `assets/`. Qualquer alteração vale imediatamente depois do commit.

---

## Estrutura

```
.
├── index.html                 página inteira (HTML + CSS + JS)
├── CNAME                      domínio do GitHub Pages
├── robots.txt
├── sitemap.xml
├── .nojekyll                  impede o Jekyll de processar o repositório
└── assets/
    ├── logo.png               logotipo negativo (texto branco) — topo e rodapé
    ├── logo-verde.png         logotipo positivo (reserva, para fundo claro)
    ├── ampulheta.png          símbolo isolado — marca d'água do hero
    ├── kenia.jpg              retrato da seção "Quem vai cuidar do seu caso"
    ├── og-image.jpg           1200x630, prévia em WhatsApp e redes
    ├── favicon.ico
    ├── favicon-512.png
    └── apple-touch-icon.png
```

---

## O que você mais vai querer alterar

Abra `index.html` e procure pelo bloco `var CONFIG` (perto do fim do arquivo).

```js
var CONFIG = {
  whatsapp:   "5531995565510",   // sem +, sem espaço, sem traço
  googleUrl:  "...",             // link do Perfil da Empresa no Google
  googleNota: "5,0",             // alimenta o hero, o painel e o cartão
  googleQtd:  "",                // ex.: "38 avaliações" — vazio oculta
  avaliacoes: []                 // avaliações reais do Google
};
```

### Publicar as avaliações do Google

Enquanto `avaliacoes` estiver vazio, a página mostra apenas o convite para ler as avaliações no Google. Para exibir os textos na própria página, copie do seu perfil **sem editar o texto do cliente**:

```js
avaliacoes: [
  { nome: "Maria S.",  quando: "há 2 meses", texto: "..." },
  { nome: "João P.",   quando: "há 5 meses", texto: "..." }
]
```

### Trocar o número do WhatsApp

Altere apenas `CONFIG.whatsapp`. Todos os sete botões da página são montados a partir dele, cada um com uma mensagem pré-preenchida diferente (topo, hero, negativa do INSS, autoteste, CTA final, rodapé e botão flutuante). As mensagens ficam logo abaixo, no objeto `msgs`.

### Trocar a foto

Substitua `assets/kenia.jpg` mantendo o mesmo nome. Formato vertical, largura em torno de 760 px.

---

## Padrão visual

Cores e tipografia seguem o Manual de Aplicações da Marca. Estão declaradas como variáveis no topo do `<style>`:

| token       | valor     | uso                          |
|-------------|-----------|------------------------------|
| `--verde`   | `#1E4E4F` | cor principal do manual      |
| `--verde-esc` | `#123334` | hero, topo, CTA final      |
| `--verde-prof`| `#0B2122` | retroativos, rodapé        |
| `--nude`    | `#AB9883` | secundária, eyebrows, filetes|
| `--champ`   | `#F7E5CB` | terciária, texto sobre verde |
| `--papel`   | `#FCF8F3` | fundo das seções claras      |

Fonte de display: **Fahkwang** (a do manual), carregada do Google Fonts. Corpo: Karla.

---

## Observações de conformidade

O rodapé traz o aviso de finalidade informativa (Código de Ética da OAB e Provimento nº 205/2021 do CFOAB). A página não promete resultado, não menciona honorários e não usa superlativo comparativo. Ao editar qualquer texto, mantenha esse padrão.

O endereço aparece identificado como sede administrativa, sem atendimento presencial.

---

## Publicação

Hospedado no GitHub Pages, branch `main`, pasta raiz. O arquivo `CNAME` fixa o domínio `auxilioacidente.keniaportilho.com.br`. Não apague esse arquivo: sem ele o Pages volta a servir em `usuario.github.io`.

Depois de qualquer commit, o Pages republica sozinho em um ou dois minutos.
