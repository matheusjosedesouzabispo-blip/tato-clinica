# Regras Globais do Projeto — Tato Clínica

Este documento descreve o projeto de forma completa para que qualquer IA ou desenvolvedor possa entender o contexto, a estrutura e os padrões antes de trabalhar no código. Leia antes de fazer qualquer alteração.

---

## 1. O que é a Tato Clínica

A **Tato Clínica** (nome formal: Clínica Tato Tecnologia Assistiva Terapia Ocupacional e Reabilitação Ltda.) é uma clínica interdisciplinar localizada em **Bauru/SP**, no bairro Vila Mesquita, na Rua Gerson França, 1177. Está em funcionamento **há 7 anos** no mesmo endereço.

O foco principal é o **neurodesenvolvimento** — atendimento a crianças, adolescentes e adultos com condições como autismo (TEA), TDAH, dificuldades de aprendizagem, atrasos de desenvolvimento, entre outros. O atendimento é humanizado, interdisciplinar e baseado em evidências científicas.

**CNPJ:** 24.986.228/0001-60
**Telefone:** (14) 3213-9611
**WhatsApp:** (14) 99102-7820 → `https://wa.me/5514991027820`
**Instagram e Facebook:** @tatoclinica
**Redes:** `https://instagram.com/tatoclinica` · `https://facebook.com/tatoclinica`

---

## 2. Equipe (7 profissionais)

| Nome | Especialidade | Registro | Áreas |
|---|---|---|---|
| Rosemaí N. Colombo | Terapeuta Ocupacional | CREFITO 2348-TO | Adulto e infantil · ortopedia e neurologia · órteses · tecnologia assistiva · Terapia da Mão |
| Évelyn Raquel Benati | Terapeuta Ocupacional | CREFITO 10549-TO | Desenvolvimento infantil · aprendizagem escolar · estimulação cognitiva e precoce · integração sensorial |
| Francine A. Olibone | Terapeuta Ocupacional | CREFITO 3-13668-TO | Neuropsicopedagogia · educação inclusiva · saúde mental · reorganização sensorial no autismo · neurodesenvolvimento |
| Ana Carolina | Fisioterapeuta | CREFITO 3-178934-F | Estimulação precoce e intervenção infantil — Conceito Neuroevolutivo Bobath |
| Larissa Helena Zani | Psicóloga | CRP 06/134371 | Doutora em Psicologia, Mestre em Educação Especial · ABA/PECS/TEACCH · avaliação diagnóstica para TEA |
| Gabriela Teixeira | Psicóloga | CRP 06/13471 | Psicologia clínica para adultos e crianças · MBA em Gerontologia · urgência e emergência |
| Eloá Tessaroli | Nutricionista | CRN 58438 | Nutrição materno-infantil (INADES) · alergias alimentares · introdução alimentar e seletividade |

As fotos de cada profissional estão em `assets/img/` com o padrão de nome: `nome-equipe-tatoclinica-200x200.jpg`.

---

## 3. Áreas de atendimento (8 áreas)

1. Avaliação Neuropsicológica
2. Psicologia ABA (Análise do Comportamento Aplicada)
3. Psicologia TCC (Terapia Cognitivo-Comportamental)
4. Psiconeuropedagogia
5. Neuropsicopedagogia
6. Fonoaudiologia
7. Terapia Ocupacional — ABA e Integração Sensorial
8. Musicoterapia

---

## 4. Missão, Visão e Valores

**Missão:** Oferecer atendimento interdisciplinar, humanizado e baseado em evidências, acolhendo cada pessoa de forma integral e individualizada — fortalecendo potencial, autonomia, bem-estar e qualidade de vida em todas as fases.

**Visão:** Ser referência em atendimento interdisciplinar no neurodesenvolvimento, reconhecida pela excelência técnica e pelo acolhimento humano, transformando vidas e contribuindo para uma sociedade mais consciente, acessível e humana.

**Valores (8):** Humanização · Acolhimento · Excelência · Trabalho em equipe · Desenvolvimento contínuo · Respeito à individualidade · Inclusão e autonomia · Compromisso com famílias

---

## 5. Estrutura de arquivos

```
tato-clinica/
├── index.html              ← homepage (única página existente no início)
├── style.css               ← todo o CSS do projeto
├── script.js               ← todo o JS do projeto
├── sobre/
│   └── index.html
├── equipe/
│   └── index.html
├── blog/
│   ├── index.html          ← listagem de posts
│   ├── o-que-e-terapia-aba/
│   │   └── index.html
│   ├── integracao-sensorial-criancas/
│   │   └── index.html
│   └── orientando-familias-no-processo-terapeutico/
│       └── index.html
├── contato/
│   └── index.html
├── assets/
│   ├── docs/
│   │   ├── pages-spec.md   ← especificação técnica das páginas
│   │   └── project-rules.md ← este arquivo
│   └── img/
│       ├── logo-fundo-claro-tatoclinica_.png
│       ├── cartaz-tatoclinica.jpg
│       ├── sobre-clinica-tatoclinica.jpg
│       ├── sobre-historia-tatoclinica.jpg
│       ├── equipe-colaboracao-tatoclinica.jpg
│       ├── blog-banner-tatoclinica.jpg
│       ├── blog-thumb-aba-tatoclinica.jpg
│       ├── blog-thumb-integracao-sensorial-tatoclinica.jpg
│       ├── blog-thumb-familia-tatoclinica.jpg
│       ├── rosemari-equipe-tatoclinica-200x200.jpg
│       ├── evelin-raquel-equipe-tatoclinica-200x200.jpg
│       ├── francine-equipe-tatoclinica-200x200.jpg
│       ├── ana-carolina-equipe-tatoclinica-200x200.jpg
│       ├── larissa-helena-equipe-tatoclinica-200x200.jpg
│       ├── gabriela-teixeira-equipe-tatoclinica-200x200.jpg
│       ├── eloa-equipe-tatoclinica-200x200.jpg
│       ├── favicon.ico
│       ├── favicon-16x16.png
│       ├── favicon-32x32.png
│       ├── apple-touch-icon.png
│       ├── android-chrome-192x192.png
│       ├── android-chrome-512x512.png
│       └── site.webmanifest
└── .vscode/
    └── settings.json       ← Live Server na porta 4578
```

**Regra importante:** Nunca criar um arquivo `style.css` ou `script.js` separado por página. Há apenas um de cada, na raiz. As subpáginas os acessam via paths relativos (`../style.css`, `../../style.css`).

---

## 6. Identidade visual

### Paleta de cores (variáveis CSS)

| Variável | Hex | Uso |
|---|---|---|
| `--carvao` | `#3B3E47` | Texto principal, headings |
| `--branco` | `#FFFFFF` | Fundo padrão |
| `--coral` | `#FF6C48` | Destaque, botões primários, eyebrows, acentos |
| `--coral-700` | `#E25232` | Hover do coral |
| `--coral-200` | `#FFE3DA` | Fundo suave de acentos |
| `--roxo` | `#46459B` | Cor secundária, nav, hero backgrounds |
| `--roxo-800` | `#33326F` | Topbar, footer, header do hero |
| `--roxo-600` | `#54539F` | Ícones em hexágono |
| `--roxo-300` | `#9897cf` | Detalhes, rings |
| `--roxo-050` | `#F1F1FB` | Fundo roxo clarinho (seção de equipe, cards suaves) |
| `--warm` | `#FBF8F6` | Fundo quente alternativo (seção áreas, blog) |
| `--muted` | `#6c6f7a` | Texto secundário, legendas |
| `--line` | `#e9e6f0` | Bordas de cards e separadores |

### Tipografia

- **Títulos e display:** `Cormorant Garamond` (Google Fonts) — pesos 500, 600, 700 e 600 itálico. Aplicada via `font-family: var(--font-display)`.
- **Corpo e UI:** `Montserrat` (Google Fonts) — pesos 400, 500, 600. Aplicada via `font-family: var(--font-body)`.
- Ambas devem ser carregadas via `<link>` do Google Fonts em toda página. O `<link>` exato está no `index.html` e deve ser copiado idêntico.

### Motivo visual: hexágono

O hexágono coral é o símbolo visual recorrente do site. Aparece:
- Como decoração flutuante no hero (`.hex`)
- Como moldura de fotos da equipe (`.member__frame`, via `clip-path`)
- Como ícone de áreas de atendimento (`.area-card__icon`)
- Como fundo de números dos valores (`.value__hex`)
- Como ícone de contato (`.contact__ic`)
- Como detalhe de acento em imagens (`.hexframe__accent`)

Sempre usar o `clip-path` padrão do projeto: `polygon(50% 0,100% 25%,100% 75%,50% 100%,0 75%,0 25%)`.

### Tom visual dos textos

- Títulos usam `<em>` itálico para destacar uma palavra-chave em coral: ex. `Cuidado que desenvolve <em>potencial</em>`
- Eyebrows (`.eyebrow`) são rótulos em maiúsculo espaçado, sempre em coral
- Botões primários: `.btn btn--coral` (coral sólido)
- Botões secundários: `.btn btn--ghost` (transparente com borda branca, em fundos escuros) ou `.btn btn--white` (branco, em fundo coral)

---

## 7. Arquitetura do CSS (`style.css`)

O arquivo é único e organizado em blocos comentados nesta ordem:

1. Variáveis (`:root`)
2. Reset e base
3. Tipografia base
4. Botões
5. Top bar
6. Header/Nav
7. Hexágonos decorativos
8. Hero (homepage)
9. Stats
10. Sobre
11. Áreas
12. Missão/Visão (Purpose)
13. Valores
14. Equipe
15. CTA Band
16. Contato
17. Footer
18. WhatsApp flutuante
19. Animações (`@keyframes float`, `@keyframes pulse`, `[data-reveal]`, stagger)
20. Responsivo (`@media`)
21. *(Adições para subpáginas no final, antes do `prefers-reduced-motion`)*

**Nunca duplicar uma classe já existente.** Se uma classe precisa de variação de contexto, usar especificidade ou modificador BEM.

---

## 8. Comportamentos do JavaScript (`script.js`)

O arquivo é único, sem dependências externas, e roda no `DOMContentLoaded`. Comportamentos implementados:

### Ano automático no footer
Busca `#year` e insere o ano atual. Toda página deve ter `<span id="year">2026</span>` no footer.

### Header com sombra ao rolar
Adiciona `.is-scrolled` ao `.site-header` quando `window.scrollY > 20`. Não modificar.

### Menu mobile
Usa os IDs: `#hamburger` (abre), `#navClose` (fecha), `#navOverlay` (fecha ao clicar fora), `#primary-nav` (recebe `.is-open`). **Todos os IDs são obrigatórios em todas as páginas.** Sem eles, o menu mobile quebra.

### Rolagem suave para âncoras
Intercepta cliques em `a[href^="#"]` e usa `window.scrollTo` com `behavior: smooth`. Desconta 80px para o header fixo.

### Reveal ao rolar (IntersectionObserver)
Seleciona todos os elementos com `[data-reveal]`. Quando 12% do elemento entra na viewport (com margem inferior de 60px), adiciona `.is-visible`. Isso ativa a transição definida no CSS: `opacity: 0 → 1` e `translateY(28px) → 0`.

### Stagger em grids
Para os seletores `.areas__grid`, `.values__grid`, `.team__grid` (e `.blog-grid` após adição), aplica `--d` (delay CSS) incremental a cada filho `[data-reveal]` em grupos de 4.

### Contador animado
Seleciona `.stat__num[data-count]`. Ao entrar na viewport, anima de 0 até o valor em `data-count`, concatenando `data-suffix`. Duração: 1400ms com easing cúbico.

---

## 9. Convenções e boas práticas

### Nomes de arquivos de imagem
Padrão: `descricao-contexto-tatoclinica.ext` — sempre em minúsculo, sem acentos, palavras separadas por hífen. Ex: `cartaz-tatoclinica.jpg`, `sobre-clinica-tatoclinica.jpg`.

### Atributos `alt` em imagens
Sempre descritivos e em português. Nunca vazio em imagens de conteúdo. Imagens puramente decorativas (hexágonos SVG, etc.) usam `aria-hidden="true"`.

### Links externos
Sempre com `target="_blank"` e `rel="noopener"`.

### Idioma
Todo o conteúdo é em **português brasileiro** (`lang="pt-BR"` no `<html>`).

### Semântica
Seções de conteúdo usam `<section>`. Cards de especialidades, valores e membros da equipe usam `<article>`. Títulos de seção usam `<h2>`. Subtítulos dentro de cards usam `<h3>`. Não pular níveis de heading.

### IDs de âncora
Apenas a homepage usa IDs de âncora para rolagem interna (`#inicio`, `#sobre`, `#areas`, `#proposito`, `#valores`, `#equipe`, `#contato`). Páginas internas não precisam de IDs de âncora, exceto `id="topo"` no `<header>` para o link "Voltar ao topo" do footer.

---

## 10. Tom de comunicação

O conteúdo do site deve sempre refletir os valores da clínica:

- **Humano e acolhedor:** evitar linguagem clínica fria ou excessivamente técnica. Falar com as famílias como parceiros no cuidado.
- **Baseado em ciência:** sem afirmações sem fundamento. Referir-se a "evidências científicas" e "abordagens baseadas em evidências".
- **Inclusivo:** nunca usar linguagem que exclua ou estigmatize condições neurológicas. Preferir "pessoa com autismo" ou "no espectro autista" a terminologias ultrapassadas.
- **Esperançoso, mas honesto:** não prometer resultados. Falar em "potencial", "desenvolvimento", "avanços", "autonomia".
- **Direto e claro:** parágrafos curtos, frases sem ambiguidade. O público são pais e cuidadores, não especialistas.
