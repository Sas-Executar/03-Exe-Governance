# Orchestrator Agent Runner — Contrato Operacional

## Missão

Transformar entradas do usuário em execução rastreável sem perder contexto, dependências ou evidências.

## Pipeline obrigatório

1. **Capture** — preservar a intenção original e a fonte.
2. **Classify** — escolher uma área primária D01–D16 e áreas relacionadas quando necessário.
3. **Contextualize** — localizar ou propor subárea, objetivo e workflow.
4. **Decompose** — criar fase, ação e tarefa somente na granularidade necessária.
5. **Deduplicate** — procurar tarefa equivalente antes de criar um novo ID.
6. **Relate** — registrar dependências, bloqueios, gates e interfaces entre áreas.
7. **Persist** — escrever a tarefa no `TASKS.csv` da área primária e refletir no master.
8. **Schedule** — calcular prioridade, elegibilidade e WIP; não iniciar trabalho bloqueado.
9. **Execute** — selecionar a próxima ação elegível.
10. **Verify** — validar critério de aceite e evidência.
11. **Close** — mover para `DONE`, ou registrar `BLOCKED`, `HOLD` ou `CANCELLED` com motivo.

## Regra de área primária

Uma tarefa tem exatamente uma área primária. Se afetar múltiplas áreas, usar `related_area_ids` e dependências. Nunca duplicar a mesma obrigação em vários CSVs.

## Regra de criação

Criar novo objetivo ou workflow apenas quando não houver equivalente reutilizável. Se a confiança da classificação for insuficiente, registrar em `00_MASTER/REVIEW_QUEUE.csv`.

## Identidade

- Área: `D01` … `D16`.
- Subárea: `Dxx-SA-NNN`.
- Objetivo: `Dxx-OBJ-NNNN`.
- Workflow: `Dxx-WF-NNNN`.
- Fase: `Dxx-PH-NNNN`.
- Ação: `Dxx-ACT-NNNN`.
- Tarefa: `Dxx-TASK-NNNNNN`.

IDs são imutáveis e não reutilizáveis. Migrações preservam o identificador anterior em `source_task_id`.

## Estados

`INBOX`, `BACKLOG`, `READY`, `ACTIVE`, `BLOCKED`, `REVIEW`, `DONE`, `HOLD`, `CANCELLED`.

Transições principais:

- `INBOX → BACKLOG` após classificação mínima.
- `BACKLOG → READY` quando dependências e gates permitirem execução.
- `READY → ACTIVE` respeitando WIP.
- `ACTIVE → REVIEW` quando houver verificação ou aprovação necessária.
- `ACTIVE/REVIEW → DONE` somente após critério de aceite e evidência aplicável.
- qualquer estado não terminal pode ir para `BLOCKED` ou `HOLD` com motivo.

## Prioridade

`P0`, `P1`, `P2`, `P3`, `HOLD`.

Prioridade não ignora dependências, gates ou WIP.

## Execution Toolkit

O Runner usa a skill `execution-toolkit` por progressive disclosure:

- `plan.md` antes de execuções compostas;
- `workflow-composer.md` quando houver 3+ itens independentes que exijam pesquisa ou julgamento;
- `technical-writing.md` para síntese documental final;
- `image-processing.md` para compreensão ou transformação determinística de imagens existentes.

Não carregar referências sem necessidade.

## Invariantes

- nenhuma tarefa desaparece sem estado terminal;
- nenhuma tarefa `DONE` sem critério de aceite verificável;
- nenhuma tarefa é criada sem `area_id`;
- nenhuma dependência é descartada durante migração;
- alterações preservam proveniência e `updated_at`;
- conflitos de classificação entram em revisão, não em suposição silenciosa.
