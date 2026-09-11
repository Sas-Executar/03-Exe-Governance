# 07 — Produção

Execução dos passos 1, 2 e 5 do handoff e da estrutura de dez slides, a partir dos contratos do pacote. Diferente das pastas `00_` a `06_`, que são fonte recebida preservada, **esta pasta é trabalho derivado** produzido neste repositório.

Owner: A definir · Estado: Entregue para revisão; nada aprovado.

## Ordem de leitura

| # | Documento | Executa |
|---|---|---|
| 01 | [Inventário e base visual](01_INVENTARIO_E_BASE_VISUAL.md) | Passo 1 do handoff: o que foi inspecionado, o que não pôde ser, a base visual adotada como premissa e o conflito de paleta entre as três fontes |
| 02 | [Storyboard Filme A — Split View 30s](02_STORYBOARD_FILME_A_SPLIT_VIEW_30S.md) | Passo 5, master de aquisição |
| 03 | [Storyboard Filme B — Manifesto 60s](03_STORYBOARD_FILME_B_MANIFESTO_60S.md) | Passo 5, master de categoria |
| 04 | [Storyboard Filme C — Demo 45s](04_STORYBOARD_FILME_C_DEMO_45S.md) | Passo 5, master de prova |
| 05 | [Matriz roteiro → cena → asset](05_MATRIZ_ROTEIRO_CENA_ASSET.csv) | Passo 2: 28 cenas com mensagem, pilar, funil, UI, componente, claim e caveat |
| 06 | [Manifesto de assets](06_MANIFESTO_DE_ASSETS.csv) | SPEC-002: 28 assets com ID, formato, dimensões, claim, status, versão e direitos |
| 07 | [Primeira apresentação](07_PRIMEIRA_APRESENTACAO.md) | Os dez slides do handoff, em texto |
| 08 | [Riscos, critérios e decisões](08_RISCOS_CRITERIOS_E_DECISOES.md) | 10 riscos, os 7 critérios de aceite do PRD verificados e 8 decisões que exigem uma pessoa |

## Versão visual da apresentação

Os arquivos em [`apresentacao/`](apresentacao/) são a fonte editável dos dez slides, um arquivo `.dc.html` por slide mais o layout em `canvas.json`. São eles que geram a peça visual; para regerar, use o mesmo conjunto de artboards.

## Premissas declaradas

1. **Cor de marca `#3157C8`**, nomeada no ADR-002, adotada como premissa contra `#0F6CBD` dos tokens AKW v2. Decisão real pertence a D11.
2. **Tipografia Archivo + IBM Plex** como placeholder: nenhuma família está declarada nas fontes recebidas.
3. **Pranchas monocromáticas não adotadas** como identidade, por serem incompatíveis com o mecanismo Split View, que depende de cor.
4. **Toda UI em `CONCEITO`**, sem exceção, por ausência de inspeção do Turborepo.

## Limites

Nenhum arquivo de vídeo, render ou editável de produção existe aqui, e nada nesta pasta está aprovado, autorizado para produção ou liberado para publicação. O gate de publicação continua sendo o de `06_GOVERNANCA/CLAIMS_QA_E_APROVACAO.md`.
