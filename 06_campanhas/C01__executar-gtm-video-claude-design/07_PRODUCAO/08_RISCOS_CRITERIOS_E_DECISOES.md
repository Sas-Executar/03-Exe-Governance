# 08 — Riscos, critérios de aceite e decisões pendentes

Fecha a entrega de produção documental: o que pode dar errado, o que conta como pronto e o que só uma pessoa pode decidir.

## Riscos

| # | Risco | Consequência | Mitigação aplicada |
|---|---|---|---|
| R1 | UI mostrada como real sem inspeção do Turborepo | Overclaim de funcionalidade; bloqueio no QA jurídico | Todo frame nasce `CONCEITO` na matriz; mudança de status só após inspeção |
| R2 | Bloco 7 do Manifesto reformulado na gravação | Claim clínico não autorizado, risco regulatório | Formulação C2 fixada literalmente no storyboard |
| R3 | Cor de marca decidida na produção, não em D11 | Duas identidades circulando; drift visual | Nenhum valor literal nos roteiros; um token a trocar |
| R4 | Pranchas monocromáticas adotadas como identidade | Split View perde o mecanismo, que depende de cor | Registradas como evidência, não como base; ver inventário |
| R5 | Timer lido como métrica de produto | Número vira claim de performance sem estudo | Marcado como metáfora na matriz e no storyboard |
| R6 | Cutdown de 6s com UI legível | Leitura impossível; ruído | Cena D-06 especificada sem UI legível |
| R7 | Conclusão sinalizada só por cor | Falha de acessibilidade | Ícone e texto obrigatórios em todo estado |
| R8 | Direitos de música, voz e imagem não resolvidos | Impedimento de publicação após produção | Coluna `direitos` do manifesto aberta em todos os assets |
| R9 | Neurodivergência tratada como rótulo em tela | Caricatura; dano reputacional | Nenhum bloco nomeia diagnóstico; tratada pelo desenho |
| R10 | Filme B publicado sem legenda | Três blocos ficam sem premissa | Legenda declarada obrigatória no storyboard e no manifesto |

## Critérios de aceite

Herdados de `PRD-001`, verificáveis nesta entrega:

1. Cada cena mapeia mensagem, pilar, etapa do funil e classe de claim — **atendido** em `05_MATRIZ_ROTEIRO_CENA_ASSET.csv`, 28 cenas.
2. Toda UI vem do Design System ou está rotulada como conceito — **atendido**: 100% em `CONCEITO`, por ausência de inspeção.
3. Legendas funcionam sem áudio — **atendido** para Filmes A e C; Filme B exige legenda, o que está declarado.
4. Safe areas suportam todos os formatos — **declarado** por bloco; verificação real depende do animatic.
5. Master permite recorte sem perder sujeito, UI ou CTA — **declarado**; o Filme A inclui a regra de inversão do split em 9:16.
6. Arquivos possuem ID, versão, proprietário e status — **parcial**: ID, versão e status atribuídos; proprietário a definir.
7. Editáveis, exports e especificação de uso — **pendente**: depende de produção.

## Decisões que exigem uma pessoa

| # | Decisão | Área | Bloqueia |
|---|---|---|---|
| D1 | Cor de marca: `#3157C8` ou `#0F6CBD` | D11 | Direção visual e qualquer render final |
| D2 | Família tipográfica canônica | D11 | Supers, legendas e packshot |
| D3 | Adotar ou descartar as pranchas monocromáticas | D11 | Identidade da campanha |
| D4 | Quais telas podem ser mostradas como `REAL` | D10 e D12 | Filme C inteiro |
| D5 | Aprovação da formulação de evidências do bloco 7 | D02 e D09 | Filme B |
| D6 | Owner, revisor e responsável legal da campanha | D01 | Gate de publicação |
| D7 | Orçamento, produtora e direitos de música e voz | D03 e D02 | Produção |
| D8 | Criar ou não os quatro packages propostos | D12 | Arquitetura de assets |

## O que esta entrega não é

Não é aprovação, não é autorização de produção ou publicação, não é compra de mídia e não contém nenhum arquivo de vídeo, render ou editável. É o contrato textual que permite produzir sem reabrir a estratégia a cada peça.
