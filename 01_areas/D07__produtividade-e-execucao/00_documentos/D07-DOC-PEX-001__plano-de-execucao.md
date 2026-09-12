---
id: D07-DOC-PEX-001
area_id: D07
tipo: macro
titulo: "Plano de Execução"
versao: "0.2.0"
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

`entrada → área D01–D16 → objetivo → workflow → fase → ação → tarefa → evidência`.

O PEX é a autoridade de governança do sistema. Os registros operacionais de tarefas ficam em `03__controle-de-execucao/01__tarefas-e-estados/`, distribuídos pelas 16 áreas oficiais.

## 2. Princípios de arquitetura

1. Toda tarefa possui exatamente uma área primária D01–D16.
2. Relações com outras áreas são registradas como interfaces ou dependências, sem duplicar a tarefa.
3. D07 governa o mecanismo de execução; uma tarefa só pertence a D07 quando seu objeto de trabalho for produtividade, planejamento ou controle de execução.
4. Tarefas nunca são apagadas para representar mudança de decisão; usam estado `CANCELLED` ou `HOLD`.
5. Uma tarefa só pode chegar a `DONE` quando cumprir seu critério de aceite e registrar a evidência exigida.
6. Entradas ambíguas são preservadas em fila de revisão; o Orchestrator não inventa classificação silenciosamente.
7. IDs são estáveis e não são reutilizados.
8. CSV é a interface operacional e de inspeção. JSON Schema define o contrato de dados do Runner.

## 3. Estrutura operacional

```text
03__controle-de-execucao/
└── 01__tarefas-e-estados/
    ├── 00_MASTER/
    ├── 00_ORCHESTRATOR/
    ├── D01__gestao-empresarial/
    ├── D02__juridico-riscos-e-conformidade/
    ├── D03__financas/
    ├── D04__pessoas-e-recursos-humanos/
    ├── D05__dados/
    ├── D06__conhecimento-e-busca-corporativa/
    ├── D07__produtividade-e-execucao/
    ├── D08__operacoes/
    ├── D09__pesquisa-e-inovacao/
    ├── D10__gestao-de-produto/
    ├── D11__experiencia-e-projeto/
    ├── D12__engenharia/
    ├── D13__mercado-e-geracao-de-demanda/
    ├── D14__vendas/
    ├── D15__atendimento-e-sucesso-do-cliente/
    └── D16__midias-sociais-e-distribuicao-digital/
```

Cada diretório D01–D16 contém `TASKS.csv`. Subárea, objetivo, workflow, fase e ação são campos hierárquicos do registro e podem ganhar materializações próprias quando houver volume ou necessidade operacional.

## 4. Contrato hierárquico

| Nível | Função | Exemplo de ID |
|---|---|---|
| Área | domínio primário | `D12` |
| Subárea | contexto funcional | `D12-SA-001` |
| Objetivo | resultado pretendido | `D12-OBJ-0001` |
| Workflow | processo para atingir o objetivo | `D12-WF-0001` |
| Fase | estágio do workflow | `D12-PH-0001` |
| Ação | agrupamento operacional | `D12-ACT-0001` |
| Tarefa | unidade granular executável | `D12-TASK-000001` |

## 5. Estados e prioridade

Estados permitidos: `INBOX`, `BACKLOG`, `READY`, `ACTIVE`, `BLOCKED`, `REVIEW`, `DONE`, `HOLD`, `CANCELLED`.

Prioridades permitidas: `P0`, `P1`, `P2`, `P3`, `HOLD`.

O WIP é controlado no nível da fila de execução. A existência de uma tarefa P0 não implica início automático se houver dependência, gate ou limite de WIP.

## 6. Orchestrator Agent Runner

Para cada entrada, o Runner deve:

1. interpretar intenção e resultado esperado;
2. localizar ou criar vínculo com área, objetivo e workflow;
3. decompor somente até a granularidade necessária para execução;
4. detectar duplicidade antes de criar novo ID;
5. registrar dependências, bloqueios, owner, prazo e evidência quando conhecidos;
6. persistir a tarefa no `TASKS.csv` da área primária e refletir no master;
7. calcular elegibilidade para `READY`/`ACTIVE` sem violar WIP;
8. exigir evidência para fechamento;
9. preservar proveniência da entrada e alterações relevantes.

## 7. Execution Toolkit do Runner

O Runner incorpora a skill **execution-toolkit**, com progressive disclosure:

- `plan.md`: estruturar a execução antes de agir;
- `workflow-composer.md`: fan-out/map-reduce quando houver 3+ itens independentes que exijam julgamento;
- `technical-writing.md`: síntese e documentação técnica final;
- `image-processing.md`: análise ou transformação determinística de imagens existentes.

O Runner carrega apenas a referência necessária para a etapa corrente.

## 8. Baseline para migração

Existe um baseline externo já normalizado com 430 tarefas do Control Center v2. Ele **não é considerado migrado** para a taxonomia D01–D16 até que o crosswalk seja validado. A migração deve preservar IDs de origem em campo próprio e gerar novos IDs canônicos D01–D16 sem perda de rastreabilidade.

## 9. Roadmap de implementação

| Etapa | Entrega | Estado |
|---|---|---|
| R1 | contrato do Orchestrator + schemas | Implementado nesta versão |
| R2 | diretórios D01–D16 + registries mestres | Implementado nesta versão |
| R3 | crosswalk das 430 tarefas para D01–D16 | Próximo |
| R4 | priorização P0/P1/P2/P3/HOLD | Pendente |
| R5 | piloto com 1–2 workflows | Pendente |
| R6 | sincronização Linear/GitHub/Drive | Pendente |
| R7 | automação de evidências e atualização de estado | Futuro |

## 10. Evidências e fontes

Registrar para cada tarefa, quando aplicável: fonte, caminho/URL, data, versão, critério de aceite, evidência de conclusão e limitações da comprovação.

## 11. Histórico

| Versão | Data | Alteração |
|---|---|---|
| 0.1.0 | 2026-09-07 | Criação do modelo; conteúdo pendente |
| 0.2.0 | 2026-09-12 | Blueprint do Orchestrator Agent Runner, taxonomia D01–D16, contrato hierárquico e roadmap |
