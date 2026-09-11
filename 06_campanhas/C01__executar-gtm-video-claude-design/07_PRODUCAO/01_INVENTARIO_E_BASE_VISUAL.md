# 01 — Inventário e base visual

Executa o passo 1 do handoff: inventariar fontes, UI real, tokens e assets existentes antes de qualquer produção.

## O que foi inspecionado

| Fonte | Local | Resultado |
|---|---|---|
| Tokens AKW v2 | `90_REFERENCIAS/WI_UIX_TOKENS.json` | Completo: cor, espaçamento, radius, motion e impressão |
| Resumo UIX | `90_REFERENCIAS/08_UIX_DESIGN_SYSTEM.md` | Tokens-chave e regra para novos templates |
| Perfil AKW | `90_REFERENCIAS/10_AKW_DESIGN_PROFILE.md` | Mudanças em relação à UIX v1.1 |
| Contratos de componentes | `90_REFERENCIAS/COMPONENT_CONTRACTS.json` | Contratos recebidos |
| Pranchas de identidade | `04_evidencias/D11-DOC-DSI-001/` | Quatro pranchas monocromáticas |
| Índice do Executar App | `90_REFERENCIAS/SUPER_MASTER_INDEX_EXECUTAR_APP.csv` | Índice recebido |

## O que não pôde ser inspecionado

`packages/design-system`, `apps/storybook` e a UI real do Executar App **não existem neste repositório**, que é documental. O passo 1 do handoff e o item 1 do prompt de modo Plan exigem inspecionar o Turborepo do produto; isso permanece pendente e nenhuma afirmação sobre a UI real foi feita a partir daqui.

Consequência direta: **nenhuma tela pode ser marcada `REAL`** nesta entrega. Todo frame de produto produzido a partir destes documentos nasce com status `CONCEITO`, conforme SPEC-002, até que a inspeção confirme o contrário.

## Conflito de paleta entre as três fontes

As fontes recebidas não concordam sobre a cor de marca nem sobre a cor de conclusão:

| Papel | `WI_UIX_TOKENS.json` v2 | `08_UIX_DESIGN_SYSTEM.md` | Pranchas de identidade | `ADR-002` |
|---|---|---|---|---|
| Marca | `#0F6CBD` (`blue_50`) | `#3157C8` | Nenhuma cor; monocromático | `#3157C8`, declarado "referência recebida" |
| Conclusão | `#0F6CBD` (azul) | `#16876F` (verde) | — | Azul de marca, "não verde genérico" |
| Gate | `#C05A22` | `#C95D32` | — | — |
| Canvas | `#FFFFFF` | `#F4F7FB` | `#E5E5E5` | — |

Na cor de conclusão o conflito já tem resolução declarada: o override AKW v2.0 e o `ADR-002` determinam azul, e o verde `#16876F` da UIX v1.1 está superado. Na cor de marca não há resolução: `#3157C8` e `#0F6CBD` disputam o mesmo papel.

## Base visual adotada nesta entrega

Para produzir sem travar, adoto a base abaixo **como premissa explícita**, não como decisão:

| Token | Valor | Origem |
|---|---|---|
| `brand` | `#3157C8` | Nomeado no `ADR-002`, que é o documento de decisão do pacote |
| `complete` | `#3157C8` | Override AKW v2.0: conclusão em azul de marca |
| `gate` | `#C05A22` | `WI_UIX_TOKENS.json` v2, camada mais recente |
| `text_primary` | `#242424` | `WI_UIX_TOKENS.json` v2 |
| `text_secondary` | `#616161` | `WI_UIX_TOKENS.json` v2 |
| `surface` / `canvas` | `#FFFFFF` / `#FAFAFA` | `WI_UIX_TOKENS.json` v2 |
| `stroke_default` | `#EDEDED` | `WI_UIX_TOKENS.json` v2 |
| `inverse_surface` | `#121B34` | `navy_95`, usado no lado Administração e em end cards |
| Motion | 100 / 200 / 260 ms, `cubic-bezier(.2,.8,.2,1)` | `WI_UIX_TOKENS.json` v2 |
| Radius | objeto 2px, controle 6px, overlay 8px | `WI_UIX_TOKENS.json` v2 |

Se D11 decidir `#0F6CBD` como marca, a troca é de um token e não invalida storyboard, matriz nem apresentação — foi por isso que nenhum valor literal foi escrito nos roteiros.

## Papel das pranchas monocromáticas

As quatro pranchas recebidas não foram adotadas como identidade. Elas descrevem um sistema preto e cinza sem cor de marca, o que é incompatível com o Split View, cuja gramática inteira depende do contraste `Administração em P&B` versus `Execução em cor`. Adotá-las eliminaria o mecanismo central da campanha.

Permanecem registradas como evidência recebida (`EVD-20260911-001` a `004`) e como decisão aberta de D11.

## Lacunas que bloqueiam produção final

1. Inspeção do Turborepo, sem a qual nenhuma tela é `REAL`.
2. Decisão de marca entre `#3157C8` e `#0F6CBD`.
3. Tipografia: nenhuma família tipográfica está declarada nos tokens; as pranchas usam monoespaçada, o sistema de produto não declara nada.
4. Direitos de música, voz e imagem: não há registro de licença no pacote.
5. Owner, revisor e responsável legal da campanha não definidos.
