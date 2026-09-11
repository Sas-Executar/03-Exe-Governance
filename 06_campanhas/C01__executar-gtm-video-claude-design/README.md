# C01 — EXECUTAR: GTM, Vídeos e Assets (Claude Design)

Pacote de decisão e produção audiovisual recebido em 11/09/2026 e incorporado íntegro, preservando a estrutura e a ordem de leitura da fonte.

Owner: A definir · Revisor: A definir · Estado: Fonte recebida; validação pendente.

Incorporar o pacote não aprova seu conteúdo, não autoriza produção ou publicação e não cria documentos na família dos 30 IDs canônicos.

## Ordem de leitura da fonte

Comece por [`00_COMECE_AQUI/00_MASTER_INDEX.md`](00_COMECE_AQUI/00_MASTER_INDEX.md), que define a sequência: resumo executivo → ADR-001 → ADR-002 → PRD-001 → SPEC-001 → SPEC-002 → contrato de packages → claims/QA → handoff → prompt de modo Plan.

## Conteúdo

| Pasta | Conteúdo | Natureza |
|---|---|---|
| [00_COMECE_AQUI](00_COMECE_AQUI/) | Índice mestre e resumo executivo, incluindo o primeiro frame/slide obrigatório | Orientação de leitura |
| [01_ADR](01_ADR/) | ADR-001 (sistema criativo Split View) e ADR-002 (arquitetura de UI e assets) | ADR-001 aceito na fonte; ADR-002 proposto, sujeito a inspeção do Turborepo |
| [02_PRD](02_PRD/) | PRD-001 da campanha audiovisual | Contrato de escopo proposto |
| [03_SPECS](03_SPECS/) | SPEC-001 (filmes 30s/60s/45s e cutdowns 6s/15s) e SPEC-002 (catálogo de assets) | Base para storyboard; não é aprovação de roteiro |
| [04_UI_PACKAGES](04_UI_PACKAGES/) | Contrato de fronteiras entre packages de UI | Autoridades existentes preservadas; packages novos são proposta |
| [05_HANDOFF](05_HANDOFF/) | Handoff operacional e prompt de modo Plan para Claude Design | Instrução de execução |
| [06_GOVERNANCA](06_GOVERNANCA/) | Classes de claim C0–C3, bloqueios, QA por asset e gate de publicação | Regra de campanha, a conciliar com D02 e D09 |
| [90_REFERENCIAS](90_REFERENCIAS/) | Fontes originais de GTM, UIX, tokens AKW v2, contratos de componentes e auditoria de UI | Material recebido, não normativo por si |
| [91_FONTES_RECEBIDAS](91_FONTES_RECEBIDAS/) | Posicionamento mestre e sistema de mensagens, como recebidos | Texto original sem edição |

## Fronteiras de UI declaradas pela fonte

| Package | Situação |
|---|---|
| `packages/design-system` | Existente; autoridade visual canônica, a preservar |
| `apps/storybook` | Existente; documentação e validação de componentes |
| `packages/brand-assets` | Proposta, dependente de inspeção do Turborepo |
| `packages/marketing-ui` | Proposta, dependente de inspeção do Turborepo |
| `packages/motion-system` | Proposta, dependente de inspeção do Turborepo |
| `packages/video-compositions` | Proposta, dependente de inspeção do Turborepo |

A fonte proíbe criar uma segunda identidade visual e determina que app, web, e-mail, mobile e vídeos consumam o mesmo Design System. Este repositório é documental: nenhum desses packages existe aqui, e a inspeção precisa ocorrer no repositório de produto.

## Evidências visuais relacionadas

Quatro pranchas de identidade recebidas junto ao pacote estão registradas em [`04_evidencias/D11-DOC-DSI-001/`](../../04_evidencias/D11-DOC-DSI-001/) e no [registro de evidências](../../04_evidencias/REGISTRO_EVIDENCIAS.csv), sob os IDs `EVD-20260911-001` a `EVD-20260911-004`.

## Conflitos e decisões pendentes

1. **Paleta.** As pranchas de identidade declaram sistema monocromático preto e cinza (`#000000`, `#2D2D2D`, `#9A9A9A`, `#E5E5E5`), enquanto `ADR-002` e os tokens AKW v2 fixam azul de marca (`#3157C8`, `brand`/`complete`) e âmbar de gate. As duas fontes não podem ser canônicas ao mesmo tempo; a decisão pertence a D11.
2. **Tipografia.** As pranchas usam sistema monoespaçado em caixa alta; a reconciliação com a tipografia do Design System não foi feita.
3. **Naming.** As pranchas usam assinaturas em inglês (*Simple to plan, built to execute*); o pacote determina conteúdo humano em português do Brasil e assinatura "Pare de organizar. Comece a executar.".
4. **Categoria.** A fonte de posicionamento define a categoria como "sistema de execução e entrega"; o resumo executivo do pacote escreve "sistema metodológico de execução". Unificar antes de qualquer peça pública.
5. **Packages propostos.** Nenhuma verificação do Turborepo foi feita a partir deste repositório; permanecem hipóteses.
6. **Claims.** As classes C0–C3 e os bloqueios precisam de validação por D02 (jurídico) e D09 (evidências) antes de qualquer publicação.

## Áreas vinculadas

- [D13 — Mercado e Geração de Demanda](../../01_areas/D13__mercado-e-geracao-de-demanda/README.md): posicionamento, mensagem, campanha e lançamento.
- [D11 — Experiência e Projeto](../../01_areas/D11__experiencia-e-projeto/README.md): identidade, tokens, componentes e acessibilidade.
- [D12 — Engenharia](../../01_areas/D12__engenharia/README.md): arquitetura de packages.
- [D16 — Mídias Sociais e Distribuição Digital](../../01_areas/D16__midias-sociais-e-distribuicao-digital/README.md): formatos e distribuição.
- [D02](../../01_areas/D02__juridico-riscos-e-conformidade/README.md) e [D09](../../01_areas/D09__pesquisa-e-inovacao/README.md): claims e evidências.
- Gate relacionado: [G01 — Posicionamento](../../02_lancamento/G01__posicionamento.md), pendente de verificação.
