---
name: Calendário de Férias
description: Planner anual de períodos de folga contra fins de semana e feriados nacionais.
colors:
  bg: "#f6f7fb"
  card: "#ffffff"
  fg: "#1b1f2e"
  muted: "#5f6577"
  line: "#e3e6ef"
  field: "#f1f3f8"
  holiday: "#e5484d"
  holiday-text: "#c42f35"
  on-accent: "#ffffff"
  period-0: "#2563eb"
  period-1: "#12a37a"
  period-2: "#d9822b"
  period-3: "#7c3aed"
  period-4: "#e0457b"
  period-5: "#0e9fbf"
  dark-bg: "#11131a"
  dark-card: "#191c26"
  dark-fg: "#e8eaf2"
  dark-muted: "#9298ad"
  dark-line: "#2a2e3c"
  dark-field: "#222634"
  dark-holiday: "#ff6b6f"
  dark-on-accent: "#11131a"
  dark-period-0: "#6b95ff"
  dark-period-1: "#3cc79c"
  dark-period-2: "#f0a052"
  dark-period-3: "#a78bfa"
  dark-period-4: "#f472a0"
  dark-period-5: "#38c3e0"
typography:
  display:
    fontFamily: "Space Grotesk, system-ui, sans-serif"
    fontSize: "1.9rem"
    fontWeight: 700
  headline:
    fontFamily: "Space Grotesk, system-ui, sans-serif"
    fontSize: "1.6rem"
    fontWeight: 700
  title:
    fontFamily: "Space Grotesk, system-ui, sans-serif"
    fontSize: "1.05rem"
    fontWeight: 700
  body:
    fontFamily: "Inter, system-ui, sans-serif"
    fontSize: "1rem"
    fontWeight: 400
  day:
    fontFamily: "Inter, system-ui, sans-serif"
    fontSize: "0.82rem"
    fontWeight: 400
    fontFeature: "tnum"
  label:
    fontFamily: "Inter, system-ui, sans-serif"
    fontSize: "0.72rem"
    fontWeight: 400
    letterSpacing: "0.06em"
rounded:
  day: "6px"
  control: "8px"
  row: "10px"
  card: "12px"
  full: "50%"
spacing:
  xs: "4px"
  sm: "8px"
  md: "10px"
  lg: "16px"
  xl: "24px"
  page: "28px"
components:
  button-primary:
    backgroundColor: "{colors.period-0}"
    textColor: "{colors.on-accent}"
    rounded: "{rounded.control}"
    padding: "9px 14px"
  button-ghost:
    backgroundColor: "transparent"
    textColor: "{colors.muted}"
    rounded: "{rounded.control}"
    padding: "9px 14px"
  button-year:
    backgroundColor: "{colors.card}"
    textColor: "{colors.fg}"
    rounded: "{rounded.row}"
    size: "40px"
  button-delete:
    backgroundColor: "{colors.card}"
    textColor: "{colors.muted}"
    rounded: "{rounded.control}"
    size: "34px"
  input:
    backgroundColor: "{colors.card}"
    textColor: "{colors.fg}"
    rounded: "{rounded.control}"
    padding: "7px 9px"
  card:
    backgroundColor: "{colors.card}"
    rounded: "{rounded.card}"
    padding: "16px"
  period-row:
    backgroundColor: "{colors.field}"
    rounded: "{rounded.row}"
    padding: "10px"
  day-cell:
    rounded: "{rounded.day}"
    typography: "{typography.day}"
---

# Design System: Calendário de Férias

## Overview

**Creative North Star: "O Planner de Mesa"**

Papel limpo, grade precisa, cor só onde há significado. A página se comporta como um planner anual sobre a mesa: fundo frio e claro, cartões brancos de borda fina, e a grade dos meses como protagonista. Nada compete com as datas; a cor existe para marcar períodos e feriados, não para decorar.

Densidade média, coluna única de até 900px. Componentes discretos e precisos: bordas de 1px, cantos suaves, pouco peso tipográfico fora dos títulos. Tema claro e escuro seguem o sistema, com override por `data-theme`. O que está na tela precisa exportar limpo para PNG, então a hierarquia é feita por cor e peso, nunca por efeitos.

**Key Characteristics:**
- Grade de meses é o herói; controles ficam acima e recuam visualmente.
- Cor semântica: cada período tem sua cor; vermelho é exclusivo de feriado.
- Flat: profundidade só por tom (bg → card → field) e borda fina.
- Números tabulares em toda data e contagem.
- Funciona igual em celular e desktop.

## Colors

Neutros frios levemente azulados, com uma paleta de seis cores de período e um vermelho reservado a feriados.

### Primary
- **Azul Agenda** (period-0): primeiro período, botão primário, anel de foco e hover da navegação de ano.

### Secondary
- **Paleta de Períodos** (period-1 a period-5: verde-esmeralda, âmbar, violeta, rosa-framboesa, ciano): atribuídas em ordem a cada novo período. Dentro do período o dia leva a cor a 22% (`color-mix`); início e fim levam a cor cheia com texto branco.

### Tertiary
- **Vermelho Feriado** (holiday): anel interno de 2px e ponto de 6px no canto do dia; hover do botão remover. O número do dia de feriado fora de período usa o tom mais escuro (holiday-text) para passar AA. Ponto facultativo usa o mesmo vermelho em anel tracejado e ponto vazado.

### Neutral
- **Papel Frio** (bg): fundo da página e da barra de ano fixa.
- **Folha** (card): cartões, campos, botões secundários.
- **Tinta** (fg): texto principal; também fundo do segmento ativo (invertido).
- **Grafite Suave** (muted): rótulos, fins de semana, notas, botões ghost.
- **Fio** (line): todas as bordas de 1px.
- **Bandeja** (field): fundo das linhas de período no editor.

Texto sobre a cor cheia de um período: branco em period-0 e period-3, Tinta (fg) nos demais (tokens `--o0`…`--o5`). Tema escuro troca cada token pelo par `dark-*` e usa dark-on-accent sobre todas as cores de período.

### Named Rules
**The Red Is Holiday Rule.** Vermelho só significa feriado (ou remoção no hover). Nunca use para período, alerta genérico ou ênfase.
**The Color Means Period Rule.** Cor saturada na grade sempre corresponde a um período da legenda. Não há cor decorativa.

## Typography

**Display Font:** Space Grotesk (com system-ui)
**Body Font:** Inter (com system-ui)

**Character:** Space Grotesk dá personalidade geométrica aos títulos (página, ano, meses); Inter cuida de tudo que é lido e operado.

### Hierarchy
- **Display** (700, 1.9rem): título da página, `text-wrap: balance`.
- **Headline** (700, 1.6rem, tabular): ano na barra de navegação.
- **Title** (700, 1.05rem / 1rem): nome do mês e títulos de cartão.
- **Body** (400, 1rem; listas 0.92rem): texto corrido, listas de resumo e feriados.
- **Day** (400, 0.82rem, tabular; 600 dentro de período, 700 em feriado isolado): números da grade.
- **Label** (0.72rem, uppercase, 0.06em): rótulos de campo e dias da semana (0.7rem).

### Named Rules
**The Tabular Dates Rule.** Toda data, contagem de dias e ano usa `font-variant-numeric: tabular-nums`.

## Layout

Coluna única centralizada (`max-width: 900px`), gap vertical de 24px, padding lateral mínimo de 16px respeitando safe-area. Ordem: cabeçalho → cartão do editor → legenda → barra de ano (sticky no topo) → grade de meses → listas.

Meses em grid `auto-fill, minmax(min(100%, 260px), 1fr)` com gap de 16px: 3 colunas no desktop, 1 no celular. Listas em `auto-fit, minmax(min(100%, 300px), 1fr)`.

Linha de período: grid de 6 colunas (ponto, início, segmento, valor, info, remover). Abaixo de 640px reorganiza em 3 colunas: início + remover na primeira linha, segmento abaixo, valor + info na terceira.

## Elevation & Depth

Totalmente flat. Nenhuma sombra de elevação. Profundidade vem de camadas tonais (Papel Frio → Folha → Bandeja) e bordas de 1px. O único `box-shadow` é `inset 0 0 0 2px` no dia de feriado, usado como anel, não como elevação.

### Named Rules
**The Flat Paper Rule.** Superfícies não flutuam. Separação por tom e fio, nunca por sombra.

## Shapes

Cantos suaves que crescem com o tamanho do elemento: dia 6px, controles 8px, linha de período e botões de ano 10px, cartões 12px. Círculos só para o ponto de cor do período e o ponto de feriado. Bordas sempre 1px sólidas em `line`.

## Components

### Buttons
Discretos e precisos.
- **Shape:** cantos suaves (8px).
- **Primary:** Azul Agenda com texto branco, peso 600, padding 9px 14px. Usado só para "Adicionar período".
- **Ghost:** transparente, texto muted, borda `line`, peso 500. Importar, Exportar, Exportar PNG, Ano atual.
- **Year nav:** quadrado 40px, raio 10px, fundo card, borda `line`; hover troca a borda para Azul Agenda.
- **Delete:** quadrado 34px; hover pinta texto e borda de vermelho feriado.
- **Focus:** outline 2px Azul Agenda, offset 2px em todo botão, input e select.

### Segmented control
Grupo inline com borda `line`, raio 8px, overflow oculto. Opção inativa: texto muted, fundo transparente. Ativa (`aria-pressed="true"`): invertida, fundo `fg`, texto `bg`.

### Inputs / Fields
- **Style:** fundo card, borda 1px `line`, raio 8px, padding 7px 9px, fonte herdada.
- **Label:** acima, estilo Label (uppercase muted), gap 4px.

### Cards / Containers
- **Corner Style:** 12px.
- **Background:** card, borda 1px `line`, sem sombra.
- **Internal Padding:** 16px.

### Navigation
Barra de ano sticky com fundo `bg` (cobre a grade ao rolar): ‹ ano › e "Ano atual" alinhado à direita. Setas do teclado também paginam.

### Day Cell (signature)
Quadrado (`aspect-ratio: 1`), raio 6px, número centralizado.
- **Fim de semana:** texto muted.
- **Dentro de período:** fundo da cor do período a 22%, texto fg, peso 600.
- **Início/fim:** cor cheia, texto de contraste da cor (branco ou Tinta), peso 600.
- **Folga emendada:** tinta da cor a 8% e contorno tracejado de 1.5px na cor do período.
- **Sobreposição:** listras diagonais alternando as duas cores a 45%.
- **Ponto facultativo:** anel vermelho tracejado e ponto vazado.
- **Hoje:** número sublinhado.
- **Feriado:** anel interno vermelho 2px + ponto 6px no canto superior direito; se fora de período, número vermelho peso 700.

### Legend
Linha flex, 0.85rem; amostras de 18px para início/fim, dentro, folga emendada, feriado nacional e ponto facultativo, seguidas de uma nota curta explicando folga, ponto facultativo e a regra da CLT.

### Period block (editor)
Um bloco Bandeja por período: cabeçalho (nome com ponto de cor que leva ao mês, duração, remover), controles e, abaixo, folga, avisos (ícone de alerta + texto em peso 600) e feriados próximos. Cada período guarda a própria cor.

## Do's and Don'ts

### Do:
- **Do** usar tokens `--p0`…`--p5` para períodos, na ordem, e o par `dark-*` no tema escuro.
- **Do** marcar estados de dia combinando fundo, anel e ponto, para feriado dentro de período continuar legível.
- **Do** manter bordas de 1px `line` e raios da escala (6/8/10/12px).
- **Do** usar números tabulares em datas e contagens.
- **Do** testar cada mudança visual também no PNG exportado e em 375px.

### Don't:
- **Don't** usar vermelho para qualquer coisa que não seja feriado ou remoção.
- **Don't** adicionar sombras de elevação, gradientes ou brilhos; o sistema é flat.
- **Don't** introduzir uma terceira família tipográfica.
- **Don't** usar cor decorativa na grade que não corresponda a um item da legenda.
