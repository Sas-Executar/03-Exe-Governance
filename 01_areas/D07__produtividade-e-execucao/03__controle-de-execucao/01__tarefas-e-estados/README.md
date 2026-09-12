# D07-T03-S01 — Tarefas e estados

Diretório operacional canônico do Orchestrator Agent Runner.

As tarefas são registradas aqui e distribuídas por área primária D01–D16. A hierarquia lógica é:

`Área → Subárea → Objetivo → Workflow → Fase → Ação → Tarefa → Evidência`.

## Estrutura

- `00_MASTER/`: índices, registries e filas globais.
- `00_ORCHESTRATOR/`: contrato, configuração, schemas, regras de roteamento e skills.
- `D01__...` até `D16__...`: `TASKS.csv` de cada domínio.

## Regras obrigatórias

1. Toda tarefa tem `task_id` estável e exatamente uma `area_id` primária.
2. Tarefa multidomínio mantém uma área primária e registra áreas relacionadas ou dependências; não é duplicada.
3. Antes de criar tarefa, o Runner verifica equivalência ou duplicidade.
4. Entradas sem classificação segura ficam em `00_MASTER/REVIEW_QUEUE.csv`.
5. `DONE` exige critério de aceite atendido e evidência quando a tarefa requer comprovação.
6. Não apagar tarefas para representar mudança de escopo: usar `HOLD` ou `CANCELLED`.
7. O master é uma visão consolidada; o `TASKS.csv` da área é a materialização operacional por domínio.
8. Migrações preservam IDs e referências de origem.

## Estados

`INBOX | BACKLOG | READY | ACTIVE | BLOCKED | REVIEW | DONE | HOLD | CANCELLED`

## Prioridades

`P0 | P1 | P2 | P3 | HOLD`

## Fluxo do Runner

`capturar → classificar → vincular objetivo/workflow → decompor → registrar dependências → persistir → priorizar → executar → validar evidência → fechar`.

O blueprint de governança está no documento `D07-DOC-PEX-001__plano-de-execucao.md` da área D07.
