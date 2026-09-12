---
id: D07-DOC-PEX-001
area_id: D07
tipo: macro
titulo: "Plano de Execução"
versao: "0.2.1"
estado_documental: em_implementacao
validacao: parcial
owner: null
revisor: null
prazo: null
fonte_id: GOV-IDX-030-001
origem: macro_enumerado_na_fonte
---

# D07-DOC-PEX-001 — Plano de Execução

## 1. Objetivo e função

Governar o **Orchestrator Agent Runner** e converter intenção em execução rastreável.

Fluxo canônico:

`entrada → área D01–D16 → subárea → objetivo → workflow → fase → ação → tarefa → evidência`.

O PEX é a autoridade de governança. Os registros operacionais ficam em `03__controle-de-execucao/01__tarefas-e-estados/`.

## 2. Princípios

1. Toda tarefa possui exatamente uma área primária D01–D16.
2. Relações com outras áreas são registradas como interfaces ou dependências, sem duplicar a tarefa.
3. D07 governa o mecanismo; uma tarefa só pertence a D07 quando seu objeto for produtividade, planejamento ou controle de execução.
4. Tarefas não são apagadas para representar mudança de decisão; usam `CANCELLED` ou `HOLD`.
5. `DONE` exige critério de aceite atendido e evidência quando aplicável.
6. Entradas ambíguas vão para revisão; o Orchestrator não inventa classificação silenciosamente.
7. IDs são estáveis e não são reutilizados.
8. CSV é a interface operacional; o contrato de campos e schema governam a estrutura dos registros.

## 3. Estrutura operacional

```text
03__controle-de-execucao/
└── 01__tarefas-e-estados/
    ├── 00_MASTER/
    ├── 00_ORCHESTRATOR/
    ├── D01/
    ├── D02/
    ├── D03/
    ├── D04/
    ├── D05/
    ├── D06/
    ├── D07/
    ├── D08/
    ├── D09/
    ├── D10/
    ├── D11/
    ├── D12/
    ├── D13/
    ├── D14/
    ├── D15/
    └── D16/
```

O nome e escopo de cada código D01–D16 são definidos em `00_MASTER/AREA_MAP.md`. Cada área possui `TASKS.csv`.

## 4. Contrato hierárquico

| Nível | Exemplo de ID |
|---|---|
| Área | `D12` |
| Subárea | `D12-SA-001` |
| Objetivo | `D12-OBJ-0001` |
| Workflow | `D12-WF-0001` |
| Fase | `D12-PH-0001` |
| Ação | `D12-ACT-0001` |
| Tarefa | `D12-TASK-000001` |

## 5. Estados e prioridades

Estados: `INBOX`, `BACKLOG`, `READY`, `ACTIVE`, `BLOCKED`, `REVIEW`, `DONE`, `HOLD`, `CANCELLED`.

Prioridades: `P0`, `P1`, `P2`, `P3`, `HOLD`.

Prioridade não ignora dependências, gates ou WIP.

## 6. Orchestrator Agent Runner

Para cada entrada, o Runner deve:

1. preservar a intenção e a fonte;
2. classificar a área D01–D16;
3. localizar ou criar vínculo com subárea, objetivo e workflow;
4. decompor até a granularidade necessária;
5. detectar duplicidade antes de criar ID;
6. registrar dependências, bloqueios, owner, prazo e evidência quando conhecidos;
7. persistir no `TASKS.csv` da área primária e refletir no master;
8. calcular elegibilidade para execução sem violar WIP;
9. validar critério de aceite e evidência para fechamento.

## 7. Execution Toolkit

O Runner incorpora `execution-toolkit` por progressive disclosure:

- `plan.md`: estrutura a execução antes de agir;
- `workflow-composer.md`: fan-out/map-reduce para itens independentes;
- `technical-writing.md`: documentação técnica final;
- `image-processing.md`: processamento determinístico de imagens existentes.

O Runner carrega apenas a referência necessária para a etapa corrente.

## 8. Baseline de migração

Há um baseline externo normalizado com **430 tarefas** do Control Center v2. Ele ainda não é considerado migrado para D01–D16. O crosswalk deve preservar o ID anterior em `source_task_id`, atribuir área canônica e manter dependências e proveniência.

## 9. Roadmap

| Etapa | Entrega | Estado |
|---|---|---|
| R1 | contrato do Orchestrator + contrato de campos | Implementado |
| R2 | `00_MASTER`, `00_ORCHESTRATOR` e diretórios D01–D16 | Implementado |
| R3 | crosswalk das 430 tarefas para D01–D16 | Próximo |
| R4 | priorização P0/P1/P2/P3/HOLD | Pendente |
| R5 | piloto com 1–2 workflows | Pendente |
| R6 | sincronização Linear/GitHub/Drive | Pendente |
| R7 | automação de evidências e estado | Futuro |

## 10. Histórico

| Versão | Data | Alteração |
|---|---|---|
| 0.1.0 | 2026-09-07 | Criação do modelo |
| 0.2.0 | 2026-09-12 | Blueprint inicial do Orchestrator |
| 0.2.1 | 2026-09-12 | Diretórios canônicos D01–D16 e contrato operacional alinhados |
