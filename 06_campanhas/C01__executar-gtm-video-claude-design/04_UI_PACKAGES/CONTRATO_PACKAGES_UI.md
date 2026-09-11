# Contrato dos Packages de UI

## Autoridade

### `packages/design-system` — existente, preservar

Fonte compartilhada de tokens, tipografia, espaçamento, radius, shadows, estados, ícones, forms, buttons, cards, tabelas, dialogs, navegação, feedback, charts, skeletons e acessibilidade. Exporta adaptadores web e native; nunca importa packages de campanha.

### `apps/storybook` — existente, preservar

Catálogo de componentes, variantes, estados, responsividade, acessibilidade e exemplos reais. É consumidor do Design System, não segunda autoridade.

## Packages propostos — criar somente após inspeção

### `packages/brand-assets`

Logos, marcas, SVGs, lockups e manifests de direitos/versão. Não contém componentes de aplicação.

### `packages/marketing-ui`

Hero, proof blocks, feature storytelling, comparison frames, CTA bands e packshots para `apps/web`. Depende de `design-system` e `brand-assets`.

### `packages/motion-system`

Motion tokens, easing, duration, transições, supers, lower thirds, timers e comportamento `prefers-reduced-motion`. Não redefine cores ou tipografia.

### `packages/video-compositions`

Storyboards executáveis/composições, cenas, layouts por aspect ratio e manifests de render. Depende dos três packages anteriores. Renders pesados ficam fora do package ou em armazenamento apropriado.

## Regras de dependência

`design-system` não depende de marketing ou vídeo. `brand-assets` não depende de UI. `marketing-ui` e `motion-system` consomem tokens canônicos. `video-compositions` apenas compõe. Apps nunca importam vídeo bruto.

## Gate

Antes de criar qualquer package: inventariar exports existentes, detectar sobreposição, registrar ADR, validar build/caching do Turborepo e documentar no Storybook.
