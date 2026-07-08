# Regras Globais do Projeto — Tato Clínica

Este documento descreve o projeto de forma completa para que qualquer IA ou desenvolvedor possa entender o contexto, a estrutura e os padrões antes de trabalhar no código. Leia antes de fazer qualquer alteração.

---

## 1. O que é a Tato Clínica

A **Tato Clínica** (nome formal: Clínica Tato Tecnologia Assistiva Terapia Ocupacional e Reabilitação Ltda.) é uma clínica interdisciplinar localizada em **Bauru/SP**, no bairro Vila Mesquita, na Rua Gerson França, 1177. Está em funcionamento **há mais de 10 anos** no mesmo endereço.

O foco principal é o **neurodesenvolvimento** — atendimento a crianças, adolescentes e adultos com condições como autismo (TEA), TDAH, dificuldades de aprendizagem, atrasos de desenvolvimento, entre outros. O atendimento é humanizado, interdisciplinar e baseado em evidências científicas.

**CNPJ:** 24.986.228/0001-60
**Telefone:** (14) 3313-9611
**WhatsApp:** (14) 99102-7820 → `https://wa.me/5514991027820`
**Instagram e Facebook:** @tatoclinica
**Redes:** `https://instagram.com/tatoclinica` · `https://facebook.com/tatoclinica`

---

## 2. Equipe

| Nome | Especialidade | Registro | Áreas |
|---|---|---|---|
| Sandra Furquim | Musicoterapeuta | — | Saúde mental: ansiedade, depressão e estresse · TEA/TDAH/Síndrome de Down · estimulação cognitiva em idosos · reabilitação em atrasos do desenvolvimento infantil · apoio em dificuldades sensoriais, motoras e de linguagem · ABA para autismo · música e cognição · educação especial · neuropsicopedagogia · arteterapia · psicanálise |
| Mariana Alcantara | Terapeuta Ocupacional | — | TEA · TDAH · Síndrome de Down · atrasos neuropsicomotores · dificuldades sensoriais, motoras e cognitivas · estimulação infantil · integração sensorial · AVDs · coordenação motora · funções executivas · autonomia · orientação familiar |
| Diego Lima | Terapeuta Ocupacional | — | UFSCar · Integração Sensorial de Ayres · ABA · Bobath · TEA · TDAH · paralisia cerebral · Síndrome de Down · avaliação ocupacional · integração sensorial · orientação familiar |
| Rosemari Colombo | Terapeuta Ocupacional | — | avaliação funcional · órteses em termoplástico · adequação postural para cadeiras de rodas · meios auxiliares adaptados · tecnologia assistiva · autonomia e qualidade de vida · atendimento humanizado |
| Caroline Zucari | Fonoaudióloga | — | Mestre em Processos e Distúrbios da Comunicação · atraso de linguagem · transtornos de fala · TDAH · aprendizagem · leitura e escrita · consciência fonológica · avaliação fonoaudiológica · terapia de linguagem · orientação familiar |
| Fernanda F. Monteiro | Fonoaudióloga | — | Transtorno motor oral · motricidade orofacial · disfagia · TEA · atraso de linguagem · transtornos de fala · PROFFI · CAA · bandagem elástica · terapia ABA · Terapia ReST |
| Amanda Lacerda | Neuropsicopedagoga | — | TDAH · TEA · dislexia · discalculia · disgrafia · transtornos globais do desenvolvimento · avaliação neuropsicopedagógica · funções executivas · atenção e memória · plano de intervenção |
| Dra. Livia Sperandio | Neuropsicóloga | — | TDAH · TEA · dificuldades de aprendizagem · deficiência intelectual · avaliação neuropsicológica · funcionamento cognitivo e comportamental · funções executivas · laudo e devolutiva |

As fotos de cada profissional ficam em `assets/img/` no padrão `nome-equipe-tatoclinica.webp` (com `.jpg` de fallback via `<picture>`). Cards com banner usam a classe `member--showcase`. O grid da equipe exibe **4 colunas** no desktop (igual à seção Valores), 2 no tablet e 1 no mobile.

---

## 3. Áreas de atendimento (8 áreas)

1. Avaliação Neuropsicológica
2. Psicologia ABA (Análise do Comportamento Aplicada)
3. Psicologia TCC (Terapia Cognitivo-Comportamental)
4. Psicopedagogia
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
│       ├── comemoracao-10-anos-tatoclinica.png
│       ├── sobre-clinica-tatoclinica.jpg
│       ├── sobre-historia-tatoclinica.jpg
│       ├── equipe-colaboracao-tatoclinica.jpg
│       ├── blog-banner-tatoclinica.jpg
│       ├── blog-thumb-aba-tatoclinica.jpg
│       ├── blog-thumb-integracao-sensorial-tatoclinica.jpg
│       ├── blog-thumb-familia-tatoclinica.jpg
│       ├── sandra-furquim-equipe-tatoclinica.webp
│       ├── sandra-furquim-equipe-tatoclinica.jpg
│       ├── mariana-alcantara-equipe-tatoclinica.webp
│       ├── mariana-alcantara-equipe-tatoclinica.jpg
│       ├── diego-lima-equipe-tatoclinica.webp
│       ├── diego-lima-equipe-tatoclinica.jpg
│       ├── rosemari-colombo-equipe-tatoclinica.webp
│       ├── rosemari-colombo-equipe-tatoclinica.jpg
│       ├── caroline-zucari-equipe-tatoclinica.webp
│       ├── caroline-zucari-equipe-tatoclinica.jpg
│       ├── fernanda-monteiro-equipe-tatoclinica.webp
│       ├── fernanda-monteiro-equipe-tatoclinica.jpg
│       ├── amanda-lacerda-equipe-tatoclinica.webp
│       ├── amanda-lacerda-equipe-tatoclinica.jpg
│       ├── livia-sperandio-equipe-tatoclinica.webp
│       ├── livia-sperandio-equipe-tatoclinica.jpg
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
