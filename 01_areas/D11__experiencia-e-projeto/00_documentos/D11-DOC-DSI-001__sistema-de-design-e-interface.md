---
id: D11-DOC-DSI-001
area_id: D11
tipo: especializado
titulo: "Sistema de Design e Interface"
versao: "0.2.0"
estado_documental: rascunho
validacao: pendente
owner: null
revisor: null
prazo: null
fonte_id: GOV-IDX-030-001
origem: especializado_recomendado_na_fonte
---

# D11-DOC-DSI-001 — Sistema de Design e Interface

> Rascunho com decisão de fonte-da-verdade (SoT) de design registrada; conteúdo de
> implementação, aprovação formal e responsáveis seguem pendentes.

## 1. Objetivo e função

Governa tipografia, cores, componentes, responsividade e acessibilidade.

## 2. Contexto e escopo

- **Cenário e problema**: o ecossistema (App EXECUTAR, Blog Custo Cognitivo, Cognitivo-Mapa
  e demais produtos) acumulou múltiplos pacotes de design coexistindo sem uma
  fonte-da-verdade única: `ADR-SYSTEM.md` (Green + Azure, `Desyng-System-ecossitema.`),
  o kit "Fractal Fluent" (Azul + Verde, implementado em produção em
  `Sas-Executar/Sas-Executar` → `packages/design-system/styles/exec-tokens.css`) e o
  pacote "Editorial Hybrid v6 (NatGeo × Apple UX)" (Amarelo + Preto, handoff recebido
  em 07/09/2026).
- **Decisão registrada nesta versão** (comunicada pelo owner do ecossistema em
  07/09/2026): ver tabela da seção 3.
- **Inclusões**: metadados de paleta, tokens, tipografia, espaçamento, componentes,
  estados, motion e acessibilidade dos dois pacotes vigentes.
- **Exclusões explícitas**: stack técnico de implementação (Astro, Next.js, Payload,
  runtime Expo, etc.) — registrado apenas como referência de onde cada pacote roda,
  nunca como decisão de arquitetura deste documento. O kit "Fractal Fluent" (Azul)
  não é excluído/apagado de sua origem — apenas registrado aqui como **não-SoT**
  a partir desta versão, preservando rastreabilidade histórica.
- **Resultado e critério mensurável**: todo produto do ecossistema, exceto o App
  EXECUTAR, deve consumir os tokens do Editorial Hybrid v6 como fonte-da-verdade de
  paleta/tipografia/componentes; o App EXECUTAR consome os tokens do pacote
  Green + Expo. Critério de aceite pendente de definição pelo owner (ver seção 5).

## 3. Conteúdo específico

### Pesquisa de experiência

- Necessidades de usuários: A preencher conforme a função deste documento.
- Jornadas: A preencher conforme a função deste documento.

### Fluxos e protótipos

- Navegação e interação: ver `.drawer` + `.bottom-bar` (mobile) e nav horizontal
  (desktop) descritos no pacote Editorial Hybrid v6, seção "Componentes" abaixo.
- Validação de usabilidade: pendência aberta na fonte — busca (`⌕`) ainda sem view
  associada; foco/teclado do drawer sem *focus trap* (ver seção 6).

### Sistema de design

#### Decisão de fonte-da-verdade (SoT) por escopo

| Escopo | Pacote | Fonte | Paleta/estilo |
|---|---|---|---|
| **App EXECUTAR (exceção)** | Green + Expo | `Desyng-System-ecossitema.` → `ADR-SYSTEM.md` | Verde `#00BF63` + Azure `#1F93FF`, IBM Plex, Expo/RN/Tamagui |
| **Todo o resto do ecossistema (SoT global)** | Editorial Hybrid v6 (NatGeo × Apple UX) | Handoff recebido do owner em 07/09/2026 (`DESIGN-HYBRID-APPLE-007`, v6) | Amarelo `#ffcc00` + preto, **sem azul no sistema**, SF Pro/New York, nav estilo Outlook mobile (drawer + bottom bar de 3 itens), cantos retos |
| **Não-SoT (histórico, registrado, não excluído da origem)** | Fractal Fluent | `Sas-Executar/Sas-Executar` → `docs/design-system/identidade-executar/` | Azul `#0F6CBD` marca, Verde `#1BA957` só "concluído", sistema + JetBrains Mono |

#### Editorial Hybrid v6 (NatGeo × Apple UX) — metadados registrados da fonte

**Identidade**: `DESIGN-HYBRID-APPLE-007`, versão 6.0. Sistema editorial para blog de
leitura de conteúdo; superfície clara dominante, preto usado uma única vez (seção
"Nossa Seleção") como contraste intencional; toda imagem de destaque é vertical,
largura total da tela.

**Tokens de cor**:

| Token | Valor | Uso |
|---|---|---|
| `--yellow` / `--action-accent` | `#ffcc00` | Destaque de atenção — no máximo 1 vez por tela |
| `--action-primary` | `#000000` | Cor de ação padrão (botões, estado ativo) |
| `--charcoal` | `#111111` | Única superfície escura do sistema |
| `--charcoal-soft` | `#1c1c1e` | Cards dentro da seção escura |
| `--ink` | `#1d1d1f` | Texto principal sobre superfície clara |
| `--muted` | `#6e6e73` | Texto secundário, legendas |
| `--paper` | `#ffffff` | Superfície padrão |
| `--soft` / `--soft-2` | `#f5f5f7` / `#fbfbfd` | Superfícies neutras pontuais |
| `--line` / `--line-dark` | `#d2d2d7` / `rgba(255,255,255,.12)` | Hairlines claro/escuro |

Regra de cor da fonte: **não existe azul no sistema**; nenhuma terceira cor de ação
sem atualizar o token file de origem.

**Tipografia**: `--sf` (SF Pro Display/Text, -apple-system) para toda UI; `--ny`
(New York/Iowan Old Style/Georgia) só para corpo de artigo. Escala:
`--display-lg clamp(2.5rem,6vw,5rem)` (H1 hero), `--display-md clamp(2rem,4vw,3.5rem)`
(H2/overlay).

**Layout/forma**: coluna de leitura `--read 720px`; `--radius-card 0px` (nunca
arredondar cards/imagens); `--radius-btn 8px` (único desvio, exclusivo de botões);
`--radius-nav-icon 4px`; `--nav-h 56px`; `--bottombar-h 64px`; `--drawer-w
min(84vw,360px)`; easing padrão `--ease cubic-bezier(.22,1,.36,1)`.

**Componentes registrados na fonte**: `.global-nav`, `.nav-links-desktop`/
`.category-rail-desktop` (desktop ≥900px), `.drawer`+`.drawer-backdrop` (mobile
<900px, grupos "Navegar"/"Categorias"), `.bottom-bar` (exatamente 3 `.bottom-tab` —
nunca um 4º item), `.btn` (`primary`/`accent`/`outline-light`/`outline-dark`, min
56px), `.hero`, `.feature-media` (100vh, sem gutter/raio), `.tile` (grade 2×2
desktop / 1 coluna mobile), `.article` (`.lead`, `.pullquote` 0–1, `.inline-media`
0–1), `.selection`+`.selection-card` (única superfície `--charcoal`, imagem 3:4),
`.carousel-card` (scroll horizontal com snap), `footer`.

**Motion**: exatamente dois momentos animados por página (entrada do hero + reveal
da mídia de destaque) além do chrome sincronizado (nav + bottom bar saem/voltam
juntos no scroll, 280ms). Nunca fade-in por card/seção ou hover-reveal em imagens.

**Acessibilidade**: contrastes checados, todos ≥ 4.5:1 (WCAG AA); alvos de toque
≥44px (botões 56px, ícones nav 40px, abas bottom bar 64px); `prefers-reduced-motion`
respeitado em toda animação; `:focus-visible` com outline amarelo 2px.
**Pendência registrada na própria fonte, não resolvida**: drawer sem *focus trap* de
teclado — obrigatório corrigir antes de produção.

**Decisões já tomadas na fonte (não reabrir sem revisão)**: não reintroduzir azul
como cor de ação; não arredondar cards/imagens; não adicionar 4º item na bottom
bar nem 3º grupo no topo mobile; não repetir navegação principal no rodapé; não
usar imagem horizontal em `.feature-media`/`.selection-img`/`.carousel-card
.visual`; não animar mais de dois momentos por página sem revisão de quem aprovou.

#### Green + Expo (App EXECUTAR) — metadados registrados da fonte

Fonte: `ADR-SYSTEM.md` (`Desyng-System-ecossitema.`, status Accepted/SOT). Paleta:
Green `#00BF63` (ação principal/execução/progresso/sucesso) + Azure `#1F93FF`
(informação/navegação/link) + Neutral (texto/superfície/borda) + Warning/Error
estimados. Tipografia IBM Plex Sans (leitura/interface) + IBM Plex Mono
(IDs/dados/código). Plataforma: Expo/React Native/Tamagui. Regra crítica da fonte:
nenhum componente consome HEX diretamente — sempre via `color.semantic.*`.

#### Fractal Fluent (registrado como não-SoT a partir desta versão)

Fonte: `Sas-Executar/Sas-Executar` → `docs/design-system/identidade-executar/README.md`.
Azul `#0F6CBD` (marca/CTA), Verde `#1BA957` (só "concluído"), régua de espaçamento
4px, dois vocabulários de raio (objeto 2px / controle 6px), alvo de toque mínimo
44×44px, fonte de sistema + JetBrains Mono. Registrado aqui apenas para
rastreabilidade da decisão de substituição — nenhum arquivo de origem foi alterado
ou excluído por este registro.

### Entrega própria de DSI

Governa tipografia, cores, componentes, responsividade e acessibilidade. Registrar
aqui os elementos que pertencem especificamente a este documento; referenciar os
demais sem duplicar sua fonte canônica.

### Campos próprios do documento especializado

- Tokens, paleta e tipografia: registrados na seção 3 acima, por pacote.
- Componentes e estados: registrados na seção 3 acima (Editorial Hybrid v6).
- Layouts e responsividade: ver tabela de breakpoints na fonte (desktop ≥900px,
  tablet/mobile <900px, mobile pequeno <620px) — detalhamento completo no anexo
  `01__tokens-e-componentes/D11-DOC-DSI-001__editorial-hybrid-v6-tokens.css`.
- Acessibilidade e critérios de validação: ver seção 3 (Editorial Hybrid v6) e
  pendência de *focus trap* do drawer, ainda não corrigida na fonte.

## 4. Decisões, dependências e interfaces

| ID relacionado | Relação ou dependência | Decisão necessária |
|---|---|---|
| D11-DOC-EEP-001 | Avaliar vínculo | A preencher |
| — (externo) `Desyng-System-ecossitema.` / `ADR-SYSTEM.md` | Fonte do pacote Green + Expo | Nenhuma — decisão já registrada pelo owner em 07/09/2026 |
| — (externo) handoff Editorial Hybrid v6 | Fonte do pacote SoT global | Nenhuma — decisão já registrada pelo owner em 07/09/2026 |
| — (externo) `Sas-Executar/Sas-Executar` / kit Fractal Fluent | Pacote hoje implementado em produção, agora não-SoT | Migração de código para o novo SoT — fora do escopo deste registro documental |

## 5. Plano e responsabilidades

| Ação | Responsável | Prazo | Critério de aceite | Estado |
|---|---|---|---|---|
| Validar formalmente esta decisão de SoT com o owner do ecossistema | A definir | A definir | Owner e revisor preenchidos, decisão assinada na seção 8 | Não iniciado |
| Corrigir pendência de *focus trap* do drawer (Editorial Hybrid v6) antes de qualquer implementação em produção | A definir | A definir | Ciclo de foco fechado implementado e testado | Não iniciado |
| Planejar migração de código do kit Fractal Fluent para Editorial Hybrid v6 nos produtos fora do App EXECUTAR | A definir | A definir | Plano de migração registrado e aprovado | Não iniciado |

## 6. Riscos e controles

| Risco | Impacto | Controle | Owner | Evidência |
|---|---|---|---|---|
| Kit Fractal Fluent (Azul) continua implementado em produção (`packages/design-system/styles/exec-tokens.css`) apesar de deixar de ser SoT | Divergência entre o que está documentado como SoT e o que está em produção | Planejar migração antes de qualquer nova feature visual; não remover o kit atual sem plano aprovado | A definir | EVD-D11-DSI-001-01 |
| Drawer do Editorial Hybrid v6 sem *focus trap* de teclado (pendência já registrada na própria fonte) | Barreira de acessibilidade para navegação por teclado/leitor de tela | Não implementar em produção sem corrigir; tratar como bloqueante | A definir | EVD-D11-DSI-001-02 |

## 7. Evidências e fontes

- `EVD-D11-DSI-001-01` — `ADR-SYSTEM.md` (GitHub `Desyng-System-ecossitema.`), pacote
  Green + Expo, confirmado pelo owner como correto para o App EXECUTAR em 07/09/2026.
- `EVD-D11-DSI-001-02` — Handoff "Editorial Hybrid — NatGeo × Apple UX v6"
  (`DESIGN-HYBRID-APPLE-007`), recebido do owner em 07/09/2026, confirmado como SoT
  global do ecossistema (exceto App EXECUTAR).
- Ver `04_evidencias/REGISTRO_EVIDENCIAS.csv` para caminho, data e limites completos
  de cada evidência.

## 8. Revisão e aprovação

- Revisor: A definir.
- Decisão: Pendente.
- Data: Não aplicável.
- Submissão relacionada: Não criada.

## 9. Histórico

| Versão | Data | Alteração |
|---|---|---|
| 0.1.0 | 2026-09-07 | Criação do modelo; conteúdo pendente |
| 0.2.0 | 2026-09-07 | Registro da decisão de SoT de design: Green + Expo para o App EXECUTAR (exceção); Editorial Hybrid v6 (NatGeo × Apple UX) como SoT global do restante do ecossistema; kit Fractal Fluent (Azul) registrado como não-SoT, sem exclusão da origem. Aprovação formal e owner ainda pendentes. |
