# ADR-002 — Arquitetura de UI e Assets

## Status

Proposto para validação no Turborepo.

## Contexto

O Next Forge já preserva `packages/design-system` e `apps/storybook`. Criar uma identidade paralela para marketing ou vídeo geraria divergência visual.

## Decisão

1. Preservar `packages/design-system` como fachada canônica de tokens e componentes EXECUTAR.
2. Fazer app, web, e-mail, mobile e peças audiovisuais consumirem os mesmos tokens semânticos.
3. Manter `apps/storybook` como catálogo e prova de estados.
4. Separar composições comerciais e motion sem duplicar primitives.
5. Não armazenar renders pesados no package de UI; manter manifests, templates e referências versionáveis.

## Fluxo

`Tokens canônicos → Design System → Componentes de produto → Composições comerciais/motion → Vídeo e assets → QA`.

## Invariantes

- Azul de marca `#3157C8` é referência recebida, sujeito à reconciliação com tokens atuais.
- Conclusão usa azul de marca, não verde genérico.
- Valores visuais literais pertencem à camada de tokens.
- Estados precisam de texto/ícone, não apenas cor.
- Motion deve respeitar redução de movimento.

## Alternativa rejeitada

Criar um design system exclusivo para campanha. Rejeitado por duplicar autoridade e aumentar drift.
