# Especificação Técnica de Páginas — Tato Clínica

Este documento instrui a criação das páginas internas do site. Leia tudo antes de começar qualquer arquivo. Nunca copie HTML de um exemplo externo — construa a partir das regras abaixo e do `index.html` existente como referência de estrutura.

---

## 1. Arquivos a criar

| Arquivo | URL final |
|---|---|
| `sobre/index.html` | `/sobre/` |
| `equipe/index.html` | `/equipe/` |
| `blog/index.html` | `/blog/` |
| `contato/index.html` | `/contato/` |
| `blog/o-que-e-terapia-aba/index.html` | `/blog/o-que-e-terapia-aba/` |
| `blog/integracao-sensorial-criancas/index.html` | `/blog/integracao-sensorial-criancas/` |
| `blog/orientando-familias-no-processo-terapeutico/index.html` | `/blog/orientando-familias-no-processo-terapeutico/` |

---

## 2. Regras de paths relativos

Os paths variam conforme a profundidade da pasta.

### Páginas de primeiro nível (`sobre/`, `equipe/`, `blog/`, `contato/`)
- CSS: `../style.css`
- JS (no final do body): `../script.js`
- Logo e imagens: `../assets/img/NOME.ext`
- Favicon `.ico`: `../assets/img/favicon.ico`
- Favicon 32px: `../assets/img/favicon-32x32.png`
- Favicon 16px: `../assets/img/favicon-16x16.png`
- Apple touch icon: `../assets/img/apple-touch-icon.png`
- Manifest: `../assets/img/site.webmanifest`

### Posts do blog (`blog/slug/`)
Mesmas regras, mas com dois níveis acima: `../../style.css`, `../../script.js`, `../../assets/img/NOME.ext` etc.

### Links de navegação (topbar, nav, footer)
Todos os hrefs de navegação são **caminhos absolutos** e ficam iguais em toda página: `/`, `/sobre/`, `/equipe/`, `/blog/`, `/contato/`. No footer, links de âncora da home devem usar `/#areas`, `/#equipe` etc. (não `#areas`, pois o usuário não está na home).

---

## 3. Regras do shell HTML

O shell é o conjunto de elementos que aparece em **todas** as páginas: topbar, header/nav, footer e botão flutuante do WhatsApp.

### Topbar
Idêntica ao `index.html`. Contém telefone, endereço e ícones de redes sociais. Não modificar.

### Header e Nav
Idêntico ao `index.html`, ajustando apenas:
- Path da logo: `../assets/img/logo-fundo-claro-tatoclinica_.png`
- O link da página atual no `<nav>` recebe a classe `nav__link is-active`. Os demais ficam apenas com `nav__link`.

**IDs obrigatórios para o JS funcionar** — devem estar presentes exatamente assim:
- `id="topo"` no `<header>`
- `id="primary-nav"` no `<nav>`
- `id="hamburger"` no botão do menu mobile
- `id="navClose"` no botão de fechar o menu mobile
- `id="navOverlay"` na div de overlay
- `id="year"` no `<span>` do ano no rodapé

### Footer
Idêntico ao `index.html`, ajustando paths de imagem com `../assets/img/`. Os links internos do footer para âncoras da home usam prefixo `/` (ex: `/#areas`).

### Botão flutuante WhatsApp (`.wa-float`)
Idêntico ao `index.html`. Path do SVG não muda (inline). Link: `https://wa.me/5514991027820?text=Ol%C3%A1!%20Vim%20pelo%20site%20da%20Tato%20Cl%C3%ADnica.`

### Favicons
O `index.html` tem um bug: aponta favicons para a raiz `/favicon.ico`. Nas novas páginas, usar os paths relativos corretos conforme seção 2.

---

## 4. Regras de animação

- Todo elemento que deve aparecer com fade+slide ao rolar a página recebe o atributo `data-reveal` diretamente na tag.
- Títulos de seção (`.section-head`), cards individuais (`.area-card`, `.value`, `.member`, `.purpose__card`) e blocos de texto (parágrafos em seções de conteúdo) devem ter `data-reveal`.
- Em grids com múltiplos cards (`.blog-grid`, `.values__grid`, `.team__grid`), cada card filho recebe `data-reveal`. O stagger é aplicado automaticamente pelo JS para grids com os seletores `.areas__grid`, `.values__grid`, `.team__grid`. Para `.blog-grid`, adicionar o seletor no array do JS em `script.js` (linha que define `['.areas__grid', '.values__grid', '.team__grid']`) — incluir `'.blog-grid'` nesse array.
- Nunca colocar `data-reveal` no topbar, header ou footer.

---

## 5. CSS adicional necessário

Adicionar ao final de `style.css`, antes do bloco `@media (prefers-reduced-motion)`, os estilos abaixo. Eles são necessários para as novas páginas e não existem ainda.

```css
/* ---------- Hero de páginas internas ---------- */
.page-hero{
  position:relative;
  background:linear-gradient(150deg,var(--roxo) 0%,var(--roxo-800) 100%);
  color:#fff;overflow:hidden;padding:80px 0 110px;text-align:center;
}
.page-hero::before{
  content:"";position:absolute;inset:0;
  background:radial-gradient(circle at 70% 20%, rgba(255,108,72,.18), transparent 45%);
  pointer-events:none;
}
.page-hero__inner{position:relative;max-width:720px;margin:0 auto}
.page-hero__title{font-size:clamp(2.2rem,5vw,3.8rem);color:#fff;margin:10px 0 20px;line-height:1.06}
.page-hero__title em{font-style:italic;color:var(--coral)}
.page-hero__lead{font-size:1.08rem;color:#e6e6f5;max-width:560px;margin:0 auto}
.page-hero__wave{
  position:absolute;left:0;right:0;bottom:-1px;height:70px;
  background:var(--branco);clip-path:polygon(0 60%,100% 0,100% 100%,0 100%);
}
.page-hero--warm .page-hero__wave{background:var(--warm)}

/* ---------- Blog — listagem ---------- */
.blog-section{padding:96px 0;background:var(--warm)}
.blog-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:28px}
.blog-card{
  background:#fff;border:1px solid var(--line);border-radius:var(--radius);
  overflow:hidden;display:flex;flex-direction:column;
  transition:transform .35s var(--ease),box-shadow .35s var(--ease);
}
.blog-card:hover{transform:translateY(-8px);box-shadow:var(--shadow-md)}
.blog-card__thumb{aspect-ratio:16/10;overflow:hidden}
.blog-card__thumb img{width:100%;height:100%;object-fit:cover;transition:transform .4s var(--ease)}
.blog-card:hover .blog-card__thumb img{transform:scale(1.04)}
.blog-card__body{padding:26px 24px;flex:1;display:flex;flex-direction:column}
.blog-card__cat{
  font-size:.75rem;font-weight:600;text-transform:uppercase;
  letter-spacing:.18em;color:var(--coral);margin-bottom:10px;
}
.blog-card h3{font-size:1.32rem;margin-bottom:10px;line-height:1.2}
.blog-card p{color:var(--muted);font-size:.92rem;flex:1;margin-bottom:20px}
.blog-card__link{
  display:inline-flex;align-items:center;gap:6px;
  font-size:.88rem;font-weight:600;color:var(--roxo);
  transition:color .2s,gap .2s;
}
.blog-card__link:hover{color:var(--coral);gap:10px}

/* ---------- Blog — artigo ---------- */
.post-wrap{max-width:780px;margin:0 auto;padding:72px 20px 104px}
.post-back{
  display:inline-flex;align-items:center;gap:8px;color:var(--roxo);
  font-weight:600;font-size:.9rem;margin-bottom:40px;transition:color .2s,gap .2s;
}
.post-back:hover{color:var(--coral);gap:12px}
.post-header{margin-bottom:44px}
.post-header__cat{
  font-size:.78rem;font-weight:600;text-transform:uppercase;
  letter-spacing:.2em;color:var(--coral);display:inline-block;margin-bottom:14px;
}
.post-header__title{
  font-family:var(--font-display);font-weight:700;
  font-size:clamp(1.9rem,4.5vw,3.2rem);
  color:var(--carvao);line-height:1.08;margin-bottom:18px;
}
.post-header__meta{
  color:var(--muted);font-size:.86rem;
  display:flex;gap:16px;flex-wrap:wrap;align-items:center;
}
.post-header__meta span{display:inline-flex;align-items:center;gap:5px}
.post-header__thumb{
  margin-top:36px;border-radius:var(--radius);
  overflow:hidden;box-shadow:var(--shadow-md);
}
.post-header__thumb img{width:100%;height:auto;display:block}
.post-body{color:#4d505b;font-size:1.04rem;line-height:1.8;margin-top:48px}
.post-body h2{font-family:var(--font-display);font-size:1.85rem;color:var(--carvao);margin:44px 0 16px}
.post-body h3{font-family:var(--font-display);font-size:1.4rem;color:var(--carvao);margin:34px 0 12px}
.post-body p{margin-bottom:20px}
.post-body ul,.post-body ol{margin:0 0 20px 22px}
.post-body li{margin-bottom:8px}
.post-body strong{color:var(--carvao)}
.post-cta{
  margin-top:60px;padding:40px 36px;background:var(--roxo-050);
  border-radius:var(--radius);border:1px solid var(--line);text-align:center;
}
.post-cta h3{font-size:1.65rem;margin-bottom:10px}
.post-cta p{color:var(--muted);margin-bottom:24px}

/* ---------- Contato — formulário ---------- */
.contact-form{margin-top:36px;display:flex;flex-direction:column;gap:18px}
.form-group label{
  display:block;font-size:.84rem;font-weight:600;
  color:var(--carvao);margin-bottom:6px;
}
.form-group input,
.form-group select,
.form-group textarea{
  width:100%;padding:13px 16px;
  border:1.5px solid var(--line);border-radius:12px;
  font-family:var(--font-body);font-size:.95rem;color:var(--ink);
  background:#fff;outline:none;
  transition:border-color .2s,box-shadow .2s;
}
.form-group input:focus,
.form-group select:focus,
.form-group textarea:focus{
  border-color:var(--roxo);
  box-shadow:0 0 0 3px rgba(70,69,155,.1);
}
.form-group textarea{resize:vertical;min-height:110px}

/* ---------- Responsivo adicional ---------- */
@media(max-width:980px){
  .blog-grid{grid-template-columns:repeat(2,1fr)}
}
@media(max-width:560px){
  .blog-grid{grid-template-columns:1fr}
  .post-wrap{padding:48px 0 70px}
  .post-cta{padding:28px 22px}
}
```

Além disso, no `script.js`, na linha que contém o array `['.areas__grid', '.values__grid', '.team__grid']`, adicionar `'.blog-grid'` ao final do array, para que os cards do blog também recebam o stagger de animação.

---

## 6. Página: Sobre Nós (`sobre/index.html`)

**`<title>`:** `Sobre Nós — Tato Clínica`
**Meta description:** `Conheça a história, a missão e os valores da Tato Clínica — há 7 anos em Bauru/SP cuidando do desenvolvimento humano com ética, ciência e acolhimento.`
**Nav ativo:** link `/sobre/`
**Wave do page-hero aponta para:** fundo branco (`var(--branco)`) — classe padrão

### Seções em ordem

**1. Hero (`.page-hero`)**
- Eyebrow: `Clínica Interdisciplinar · Bauru/SP`
- Título (`.page-hero__title`): `Uma clínica feita de <em>cuidado</em> e propósito.`
- Lead (`.page-hero__lead`): `Há 7 anos no coração da Vila Mesquita, acompanhamos cada história com dedicação, ciência e humanidade.`
- Deco hexágonos: usar as mesmas spans `.hex` decorativas do hero do `index.html` (hex--a, hex--b, hex--c, hex--ring)
- Incluir `.page-hero__wave` ao final da section

**2. Stats (`.stats`)**
Reaproveitar exatamente a seção de stats do `index.html` — três cards com data-count e data-suffix. Isso reusa o JS de contador animado que já existe.

**3. Nossa História (`.sobre` + `.sobre__grid`)**
Usar a mesma estrutura da seção `#sobre` do `index.html` com grid de 2 colunas. Imagem: `../assets/img/sobre-clinica-tatoclinica.jpg` com classe `.hexframe`. Adicionar `hexframe__accent` e o pseudo-elemento de anel roxo como está na home.
- Eyebrow: `Nossa história`
- Título: `Sete anos cuidando de quem importa.`
- Parágrafos de conteúdo:
  > Fundada em 2018 na Vila Mesquita, Bauru/SP, a Tato Clínica nasceu da crença de que cada pessoa — independente da sua condição neurológica, etapa da vida ou desafio de desenvolvimento — merece um cuidado integral, humanizado e baseado em ciência.
  >
  > O nome Tato vem da essência do nosso trabalho: tocar vidas com sensibilidade. Surgimos como uma clínica de Terapia Ocupacional e Tecnologia Assistiva, e ao longo dos anos fomos crescendo de forma orgânica, sempre seguindo as necessidades das famílias que atendemos e a dedicação dos profissionais que se juntaram à nossa equipe.
  >
  > Hoje somos uma clínica interdisciplinar com 8 áreas de atendimento integradas, um time de especialistas comprometidos e um único foco: contribuir para que cada paciente viva com mais autonomia, participação e qualidade de vida.
- Pills: `Fundada em 2018` · `Vila Mesquita, Bauru/SP` · `8 especialidades` · `Atendimento para todas as idades`

**4. Missão e Visão (`.purpose`)**
Reaproveitar exatamente a seção `#proposito` do `index.html` com os dois cards e os textos existentes. Remover o `id="proposito"` pois aqui não é âncora.

**5. Valores (`.values`)**
Reaproveitar exatamente a seção `#valores` do `index.html` com os 8 values em grid. Remover o `id="valores"`.

**6. Sobre a equipe — chamada (`.sobre` com fundo `var(--warm)`)**
Seção simples com fundo warm, grid de 2 colunas invertido (texto na esquerda, imagem na direita).
- Imagem: `../assets/img/sobre-historia-tatoclinica.jpg` com `.hexframe`
- Eyebrow: `Quem cuida de você`
- Título: `Uma equipe interdisciplinar, unida por um propósito.`
- Parágrafo:
  > Cada profissional da Tato Clínica foi escolhido não apenas pela sua formação técnica, mas pela forma como enxerga o cuidado: com empatia, responsabilidade e comprometimento com a história de cada paciente.
- Link/botão: `<a href="/equipe/" class="btn btn--coral">Conheça a equipe</a>` — sem `data-reveal` individual, mas o bloco de texto pode ter

**7. CTA Band (`.cta-band`)**
Idêntico ao `index.html`. Deco com hex--f e hex--g. Texto e botões iguais.

---

## 7. Página: Equipe (`equipe/index.html`)

**`<title>`:** `Equipe — Tato Clínica`
**Meta description:** `Conheça os profissionais da Tato Clínica — especialistas em terapia ocupacional, psicologia, fisioterapia, fonoaudiologia, neuropsicopedagogia, nutrição e musicoterapia.`
**Nav ativo:** link `/equipe/`
**Wave do page-hero aponta para:** `var(--roxo-050)` (fundo da seção de equipe abaixo) — adicionar classe `.page-hero--team` com `background:var(--roxo-050)` na wave, OU usar um `<div style="background:var(--roxo-050)">` para envolver a seção team. O mais simples: usar `.page-hero__wave` com estilo inline `style="background:var(--roxo-050)"`.

### Seções em ordem

**1. Hero (`.page-hero`)**
- Imagem de fundo wide: inserir dentro de `.page-hero` uma `<figure>` com `position:absolute;inset:0;z-index:0;opacity:.12` contendo `../assets/img/equipe-colaboracao-tatoclinica.jpg` com `object-fit:cover;width:100%;height:100%`. O gradiente roxo já cobre, então a imagem fica sutil ao fundo.
- Eyebrow: `Nossa equipe`
- Título: `Profissionais que fazem a <em>diferença</em> a cada atendimento.`
- Lead: `Uma equipe interdisciplinar comprometida com o desenvolvimento, o bem-estar e a autonomia de cada paciente.`
- Wave apontando para fundo roxo claro

**2. Equipe (`.team` com `background:var(--roxo-050)`)**
Reaproveitar exatamente a seção `#equipe` do `index.html` — mesmo `.team__grid` com os 7 `.member` cards, mesmas imagens, mesmos textos. Remover o `id="equipe"`. Manter `data-reveal` em cada card.

**3. Chamada de valores (`.sobre` com fundo branco)**
Seção curta de texto centralizado, sem grid.
- Usar `.section-head` com `text-align:center`
- Eyebrow: `Nossa forma de trabalhar`
- Título: `Integração que gera resultados.`
- Parágrafo (max-width 680px, centralizado):
  > Na Tato Clínica, os profissionais não atuam de forma isolada. Discutimos casos, compartilhamos estratégias e construímos planos terapêuticos juntos — porque acreditamos que o olhar múltiplo sobre um mesmo paciente é o que transforma o atendimento em cuidado de verdade.

**4. CTA Band (`.cta-band`)**
Idêntico ao `index.html`.

---

## 8. Página: Blog (`blog/index.html`)

**`<title>`:** `Blog — Tato Clínica`
**Meta description:** `Artigos sobre neurodesenvolvimento, terapias e orientações para famílias — escritos pela equipe da Tato Clínica em Bauru/SP.`
**Nav ativo:** link `/blog/`
**Wave do page-hero aponta para:** `var(--warm)` — adicionar estilo inline `style="background:var(--warm)"` na `.page-hero__wave`

### Seções em ordem

**1. Hero (`.page-hero`)**
- Eyebrow: `Conteúdo da equipe`
- Título: `Conteúdo para <em>famílias</em> e cuidadores.`
- Lead: `Informação acessível e baseada em evidências sobre neurodesenvolvimento, terapias e cuidado.`

**2. Listagem de posts (`.blog-section`)**
Container `.container` com:
- Header `.section-head data-reveal`: eyebrow `Artigos recentes`, título `O que escrevemos`, sem subtítulo
- Grid `.blog-grid` com 3 cards `.blog-card`, cada um com `data-reveal`

**Card 1 — Post ABA:**
- `.blog-card__thumb`: imagem `../assets/img/blog-thumb-aba-tatoclinica.jpg`, alt `Terapia ABA — criança em sessão terapêutica`
- `.blog-card__cat`: `Psicologia`
- `<h3>`: `O que é a Terapia ABA e como ela ajuda no neurodesenvolvimento`
- `<p>`: `Entenda os fundamentos da Análise do Comportamento Aplicada e por que ela é uma das abordagens mais indicadas para crianças com TEA e outros perfis neuroatípicos.`
- `.blog-card__link` com `href="/blog/o-que-e-terapia-aba/"`: texto `Ler artigo →`

**Card 2 — Post Integração Sensorial:**
- `.blog-card__thumb`: imagem `../assets/img/blog-thumb-integracao-sensorial-tatoclinica.jpg`, alt `Sala de integração sensorial para crianças`
- `.blog-card__cat`: `Terapia Ocupacional`
- `<h3>`: `Integração sensorial: o que é, como identificar dificuldades e como a TO pode ajudar`
- `<p>`: `Crianças que se incomodam muito com barulho, evitam certas texturas ou parecem "não sentir dor" podem ter dificuldades de processamento sensorial. Saiba mais.`
- `.blog-card__link` com `href="/blog/integracao-sensorial-criancas/"`: texto `Ler artigo →`

**Card 3 — Post Famílias:**
- `.blog-card__thumb`: imagem `../assets/img/blog-thumb-familia-tatoclinica.jpg`, alt `Família e cuidado no processo terapêutico`
- `.blog-card__cat`: `Família`
- `<h3>`: `Como a família faz parte do processo terapêutico — e por que isso muda tudo`
- `<p>`: `A terapia não termina quando a sessão acaba. Veja como o envolvimento familiar no processo é um dos fatores que mais impacta os resultados do atendimento.`
- `.blog-card__link` com `href="/blog/orientando-familias-no-processo-terapeutico/"`: texto `Ler artigo →`

**3. CTA Band (`.cta-band`)**
Idêntico ao `index.html`.

---

## 9. Página: Contato (`contato/index.html`)

**`<title>`:** `Contato — Tato Clínica`
**Meta description:** `Entre em contato com a Tato Clínica em Bauru/SP. Telefone, WhatsApp, endereço e formulário de agendamento. Atendimento humanizado e especializado.`
**Nav ativo:** link `/contato/`
**Wave do page-hero aponta para:** `var(--branco)`

### Seções em ordem

**1. Hero (`.page-hero`)**
- Eyebrow: `Estamos aqui`
- Título: `Vamos conversar sobre essa <em>história</em> juntos.`
- Lead: `Entre em contato, tire suas dúvidas ou agende uma avaliação. Respondemos pelo WhatsApp e por telefone.`

**2. Seção de contato completa (`.contact`)**
Reaproveitar a seção `#contato` do `index.html` com grid de 2 colunas. Remover o `id="contato"`. Manter mapa do Google, lista de contatos e nota de rodapé. 

Abaixo da lista de contatos (dentro de `.contact__info`), adicionar um formulário com classe `.contact-form` e `id="contact-form"`. Campos:
- Nome: `<input type="text" id="cf-name" placeholder="Seu nome" required>`
- Telefone/WhatsApp: `<input type="tel" id="cf-phone" placeholder="(14) 9 0000-0000">`
- Assunto: `<select id="cf-subject">` com opções: `Agendar uma avaliação`, `Informações sobre atendimento`, `Dúvida sobre especialidades`, `Outro assunto`
- Mensagem: `<textarea id="cf-msg" placeholder="Escreva sua mensagem (opcional)"></textarea>`
- Botão submit: `<button type="submit" class="btn btn--coral">Enviar pelo WhatsApp</button>`

O formulário não usa backend. Ao submeter, deve abrir o WhatsApp com mensagem montada a partir dos campos. Usar o seguinte `<script>` inline antes do `</body>` (mas após o `<script src="...script.js">`):

```javascript
(function(){
  var f = document.getElementById('contact-form');
  if(!f) return;
  f.addEventListener('submit', function(e){
    e.preventDefault();
    var name = document.getElementById('cf-name').value || 'não informado';
    var phone = document.getElementById('cf-phone').value || 'não informado';
    var subj = document.getElementById('cf-subject').value;
    var msg  = document.getElementById('cf-msg').value;
    var text = 'Olá! Me chamo ' + name + ' e gostaria de: ' + subj + '.'
             + (phone !== 'não informado' ? ' Meu telefone é ' + phone + '.' : '')
             + (msg ? ' ' + msg : '');
    window.open('https://wa.me/5514991027820?text=' + encodeURIComponent(text), '_blank');
  });
})();
```

**3. Horário de atendimento**
Seção simples com fundo `var(--warm)`, `padding:80px 0`, `.container` centralizado com `.section-head`.
- Eyebrow: `Funcionamento`
- Título: `Quando estamos disponíveis`
- Abaixo, uma lista simples (sem classe especial) com os horários. Como o horário real da clínica não está no site, usar como placeholder editável:
  - Segunda a sexta: 8h às 18h
  - Sábado: mediante agendamento
  - Atendimento somente com agendamento prévio

**4. CTA Band (`.cta-band`)**
Idêntico ao `index.html`.

---

## 10. Posts do Blog

Todos os posts seguem a mesma estrutura de `<main>`:
1. Seção branca com `.container > .post-wrap`
2. Dentro do `.post-wrap`: link de volta `.post-back`, depois `.post-header`, depois `.post-body`, depois `.post-cta`
3. Após a section branca: `.cta-band` (idêntico ao `index.html`)

O shell dos posts usa paths de 2 níveis (`../../`). Nav ativo: link `/blog/`.

`.post-back` sempre aponta para `/blog/` com texto `← Voltar para o Blog`.

`.post-cta` sempre tem:
- `<h3>`: `Quer saber mais ou agendar uma avaliação?`
- `<p>`: `Nossa equipe está pronta para conversar sobre o desenvolvimento do seu filho ou de você mesmo. Fale com a gente.`
- Botão: `<a href="https://wa.me/5514991027820?text=..." class="btn btn--coral btn--lg">Falar no WhatsApp</a>` com mensagem pré-preenchida contextual ao tema do post

---

### Post 1 — O que é a Terapia ABA

**Arquivo:** `blog/o-que-e-terapia-aba/index.html`
**`<title>`:** `O que é a Terapia ABA e como ela ajuda no neurodesenvolvimento — Tato Clínica`
**Meta description:** `Entenda o que é a Análise do Comportamento Aplicada (ABA), como ela funciona na prática e por que é uma das principais abordagens para crianças com TEA e perfis neuroatípicos.`

**`.post-header__cat`:** `Psicologia`
**`.post-header__title`:** `O que é a Terapia ABA e como ela ajuda no neurodesenvolvimento`
**`.post-header__meta`:** `Equipe Tato Clínica` · `Junho de 2026` · `Leitura: 5 min`
**Imagem (`.post-header__thumb`):** `../../assets/img/blog-thumb-aba-tatoclinica.jpg`, alt `Criança em sessão de terapia ABA`

**Corpo do artigo (`.post-body`):**

```
<h2>O que é a ABA?</h2>
<p>A Análise do Comportamento Aplicada, conhecida pela sigla <strong>ABA</strong> (do inglês <em>Applied Behavior Analysis</em>), é uma ciência baseada nos princípios do comportamento humano. Desenvolvida a partir dos estudos de B.F. Skinner sobre aprendizagem, ela investiga como o ambiente influencia os comportamentos e usa esse conhecimento para promover mudanças positivas e funcionais na vida das pessoas.</p>
<p>Na prática clínica, a ABA é utilizada principalmente no atendimento de crianças com <strong>Transtorno do Espectro Autista (TEA)</strong>, mas seus princípios também são aplicados com eficácia a pessoas com TDAH, deficiência intelectual, atrasos de desenvolvimento e outros perfis neuroatípicos.</p>

<h2>Como funciona na prática?</h2>
<p>O trabalho em ABA começa com uma avaliação detalhada do repertório da criança — o que ela já sabe fazer, quais habilidades ainda precisam ser desenvolvidas e quais comportamentos interferem no seu aprendizado e convivência social. A partir dessa análise, o terapeuta elabora um programa individualizado, com metas claras e estratégias específicas para aquela criança.</p>
<p>As sessões são estruturadas e consistentes, mas também adaptadas ao contexto e às preferências do paciente. Algumas estratégias comuns incluem:</p>
<ul>
  <li><strong>Reforço positivo:</strong> valorizar e recompensar comportamentos desejados para aumentar sua frequência</li>
  <li><strong>Ensino por tentativas discretas (DTT):</strong> dividir habilidades complexas em pequenos passos e ensiná-las de forma sistemática</li>
  <li><strong>Ensino naturalístico:</strong> aproveitar situações do cotidiano para promover aprendizagem de forma mais espontânea</li>
  <li><strong>Modelagem e encadeamento:</strong> construir habilidades progressivamente, partindo do que a criança já consegue</li>
</ul>

<h2>ABA e TEA: por que essa abordagem é tão indicada?</h2>
<p>A ABA é uma das abordagens com maior <strong>respaldo científico</strong> no tratamento do autismo. Décadas de pesquisas demonstram que, quando aplicada de forma intensiva, individualizada e iniciada precocemente, ela pode promover ganhos significativos em comunicação, habilidades sociais, autonomia e comportamentos adaptativos.</p>
<p>É importante entender que a ABA moderna não busca "normalizar" a criança ou suprimir características do autismo. O objetivo é ampliar o repertório funcional — ajudar a criança a se comunicar melhor, a participar de atividades com mais independência e a lidar com situações do cotidiano com menos sofrimento.</p>

<h2>ABA na Tato Clínica</h2>
<p>Na Tato Clínica, a Psicologia ABA é conduzida por profissionais com formação especializada, que trabalham de forma integrada com os demais terapeutas da equipe. Isso significa que as metas trabalhadas em sessão são alinhadas com o que acontece na escola, em casa e nas demais terapias — criando uma rede de apoio coerente e eficaz para a criança.</p>
<p>Se você tem dúvidas sobre se a ABA é indicada para o seu filho ou quer entender melhor como seria o processo na nossa clínica, entre em contato. Estamos aqui para conversar.</p>
```

**Link WhatsApp no `.post-cta`:** `https://wa.me/5514991027820?text=Ol%C3%A1!%20Li%20o%20artigo%20sobre%20Terapia%20ABA%20e%20gostaria%20de%20saber%20mais%20sobre%20o%20atendimento.`

---

### Post 2 — Integração Sensorial em Crianças

**Arquivo:** `blog/integracao-sensorial-criancas/index.html`
**`<title>`:** `Integração Sensorial: como identificar dificuldades e como a Terapia Ocupacional pode ajudar — Tato Clínica`
**Meta description:** `Saiba o que é processamento sensorial, como identificar dificuldades em crianças e como a Terapia Ocupacional com foco em integração sensorial pode transformar o desenvolvimento.`

**`.post-header__cat`:** `Terapia Ocupacional`
**`.post-header__title`:** `Integração sensorial: o que é, como identificar dificuldades e como a TO pode ajudar`
**`.post-header__meta`:** `Equipe Tato Clínica` · `Junho de 2026` · `Leitura: 5 min`
**Imagem (`.post-header__thumb`):** `../../assets/img/blog-thumb-integracao-sensorial-tatoclinica.jpg`, alt `Sala de integração sensorial para crianças`

**Corpo do artigo (`.post-body`):**

```
<h2>O que é integração sensorial?</h2>
<p>Nosso sistema nervoso recebe, a todo momento, uma enorme quantidade de informações vindas do ambiente e do próprio corpo — sons, texturas, luz, temperatura, movimento, posição dos membros. A <strong>integração sensorial</strong> é o processo pelo qual o cérebro organiza todas essas informações e produz respostas adequadas a cada situação.</p>
<p>Quando esse processo funciona bem, a criança consegue brincar, aprender, interagir e realizar atividades do cotidiano com relativa facilidade. Quando há <strong>dificuldades de processamento sensorial</strong>, o cérebro pode ter dificuldade para filtrar, interpretar ou responder aos estímulos de forma funcional.</p>

<h2>Como identificar dificuldades sensoriais</h2>
<p>As dificuldades sensoriais podem se manifestar de formas muito diferentes, dependendo de como o sistema nervoso de cada criança responde aos estímulos. Alguns sinais comuns que podem indicar a necessidade de avaliação:</p>
<ul>
  <li>Incomodo excessivo com barulhos do cotidiano (liquidificador, secador, aplausos)</li>
  <li>Recusa em tocar certas texturas de alimento, roupa ou superfície</li>
  <li>Dificuldade em permanecer sentada ou com o corpo parado</li>
  <li>Busca constante por movimentos intensos (girar, pular, se jogar)</li>
  <li>Aparente insensibilidade à dor ou ao frio/calor</li>
  <li>Dificuldade em realizar tarefas que exigem coordenação motora fina</li>
  <li>Cansaço fácil em ambientes com muito estímulo (festas, salas de aula movimentadas)</li>
</ul>
<p>Esses comportamentos não indicam necessariamente má criação ou "frescura". Na maioria dos casos, a criança está respondendo da única forma que consegue a um sistema nervoso que está sendo sobrecarregado — ou que precisa de mais estímulo para funcionar.</p>

<h2>O papel da Terapia Ocupacional</h2>
<p>A Terapia Ocupacional com abordagem de <strong>integração sensorial</strong> é conduzida por um terapeuta especializado e utiliza atividades lúdicas e estruturadas para ajudar o cérebro a processar os estímulos de forma mais organizada e eficiente.</p>
<p>Diferente do que muitos imaginam, não se trata de "acostumar" a criança aos estímulos pela exposição forçada. A TO trabalha de forma gradual, respeitando o limite da criança e oferecendo experiências sensoriais controladas — em quantidade e intensidade adequadas — para que o sistema nervoso possa se organizar progressivamente.</p>
<p>O ambiente terapêutico é pensado para isso: equipamentos como balanços, camas elásticas, materiais de diferentes texturas e pesos fazem parte do trabalho, sempre dentro de um contexto seguro e prazeroso para a criança.</p>

<h2>Quando procurar uma avaliação?</h2>
<p>Se você percebe que o seu filho tem reações muito intensas (ou muito fracas) a estímulos sensoriais, e que isso está afetando a vida dele — na escola, em casa, nas brincadeiras — vale conversar com um terapeuta ocupacional.</p>
<p>Na Tato Clínica, a avaliação sensorial é feita de forma individualizada, levando em conta a história da criança, as queixas da família e a observação clínica. A partir daí, construímos um plano terapêutico pensado para aquele perfil específico.</p>
```

**Link WhatsApp no `.post-cta`:** `https://wa.me/5514991027820?text=Ol%C3%A1!%20Li%20sobre%20integra%C3%A7%C3%A3o%20sensorial%20e%20gostaria%20de%20agendar%20uma%20avalia%C3%A7%C3%A3o%20de%20Terapia%20Ocupacional.`

---

### Post 3 — Orientando Famílias no Processo Terapêutico

**Arquivo:** `blog/orientando-familias-no-processo-terapeutico/index.html`
**`<title>`:** `Como a família faz parte do processo terapêutico — e por que isso muda tudo — Tato Clínica`
**Meta description:** `A terapia não termina quando a sessão acaba. Entenda como o envolvimento da família no processo terapêutico é um dos fatores que mais impacta os resultados do desenvolvimento.`

**`.post-header__cat`:** `Família`
**`.post-header__title`:** `Como a família faz parte do processo terapêutico — e por que isso muda tudo`
**`.post-header__meta`:** `Equipe Tato Clínica` · `Junho de 2026` · `Leitura: 5 min`
**Imagem (`.post-header__thumb`):** `../../assets/img/blog-thumb-familia-tatoclinica.jpg`, alt `Família acolhendo criança no processo terapêutico`

**Corpo do artigo (`.post-body`):**

```
<h2>A terapia não termina quando a sessão acaba</h2>
<p>Uma das crenças mais comuns — e mais limitantes — sobre a terapia infantil é a de que ela acontece apenas dentro do consultório. Na prática, o que ocorre nos outros 23 horas do dia tem tanto impacto quanto a própria sessão terapêutica.</p>
<p>Isso não significa que as famílias precisam se tornar terapeutas em casa. Significa que, quando os pais, cuidadores e a escola entendem o que está sendo trabalhado e por quê, o desenvolvimento da criança avança de forma muito mais consistente e significativa.</p>

<h2>Por que o envolvimento familiar faz diferença?</h2>
<p>As habilidades desenvolvidas em sessão precisam ser generalizadas — ou seja, a criança precisa ser capaz de usá-las em diferentes contextos, com diferentes pessoas, em diferentes situações. Quando a família está alinhada com os objetivos terapêuticos, ela cria oportunidades naturais para que isso aconteça no dia a dia.</p>
<p>Além disso, a família é a principal fonte de informação do terapeuta. São os pais e cuidadores que convivem com a criança em casa, que percebem mudanças, que enfrentam os desafios cotidianos. Esse olhar é insubstituível.</p>

<h2>Como participar sem sobrecarregar</h2>
<p>Participar do processo terapêutico não precisa — e não deve — ser mais uma tarefa pesada na rotina familiar. Algumas formas práticas de estar presente:</p>
<ul>
  <li><strong>Compareça às devolutivas:</strong> peça para conversar periodicamente com o terapeuta sobre os avanços, as metas e as estratégias que você pode usar em casa</li>
  <li><strong>Comunique mudanças:</strong> novos medicamentos, mudanças de escola, eventos familiares significativos — tudo isso impacta a criança e o terapeuta precisa saber</li>
  <li><strong>Aplique as orientações com consistência:</strong> pequenas adaptações no dia a dia, quando feitas com regularidade, têm efeito acumulativo enorme</li>
  <li><strong>Cuide de você também:</strong> famílias que se sustentam emocionalmente conseguem oferecer um suporte muito mais qualificado às suas crianças</li>
</ul>

<h2>O papel da Tato Clínica nesse processo</h2>
<p>Na Tato Clínica, a orientação familiar é parte estruturante do atendimento — não um opcional. Nossos profissionais dedicam tempo para conversar com as famílias, explicar o raciocínio clínico por trás das intervenções e co-construir estratégias que façam sentido dentro da rotina de cada casa.</p>
<p>Acreditamos que o cuidado mais efetivo é aquele que envolve todos que fazem parte da vida da criança. Quando a família e a equipe terapêutica caminham juntas, os resultados aparecem — e se sustentam.</p>
<p>Se você tem dúvidas sobre como se envolver mais no processo terapêutico do seu filho, ou quer entender melhor o que acontece nas sessões, fale com a nossa equipe. Estamos aqui para isso.</p>
```

**Link WhatsApp no `.post-cta`:** `https://wa.me/5514991027820?text=Ol%C3%A1!%20Li%20o%20artigo%20sobre%20o%20papel%20da%20fam%C3%ADlia%20na%20terapia%20e%20gostaria%20de%20conversar%20com%20a%20equipe.`
