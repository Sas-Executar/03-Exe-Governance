# Status report — reorganização SAS · EXECUTAR

**Data:** 2026-09-12  
**Escopo:** seis ondas do plano de reorganização multi-repositório.  
**Estado geral:** `CUTOVER_BLOCKED` — a execução documental e os controles de migração estão prontos para revisão; não houve merge, renomeação, arquivamento, exclusão de origem ou publicação de conteúdo privado.

## Resultado por onda

| Onda | Resultado verificável | Estado |
|---|---|---|
| 1 — Baseline + Maestro → Governance | 67 cópias verificadas por SHA; 36 artefatos de registros classificados; origem preservada | `READY_FOR_REVIEW` |
| 2 — Governance canônico | Matrizes de reconciliação, corte e nomes-alvo registradas | `READY_FOR_REVIEW` |
| 3 — Maestro operacional | 24 entradas operacionais e 19 artefatos estruturais/registries validados | `READY_FOR_REVIEW` |
| 4 — Blueprints multiárea | 10/10 shells validados; 126/126 blobs de Product-Spec mapeados com SHA idêntico | `BLOCKED_BY_VISIBILITY` |
| 5 — Design + Ecosystem | 63 documentos do Desyng preservados; 31 binários pendentes; 120 arquivos apps/packages mapeados | `PARTIAL_RECONCILIATION` |
| 6 — Corte controlado | Readiness, rollback e rastreabilidade registrados; fontes continuam intactas | `BLOCKED_BY_OWNER_ACTIONS` |

## Nomes e responsabilidades finais

| Estado atual | Nome-alvo | Responsabilidade | README de transição |
|---|---|---|---|
| `Programa-Sas` | `sas-executar-governance` | GOVERNAR — IDs, evidências, decisões, riscos, políticas e gates | [README](README.md) |
| `Maestr-Docs` | `sas-executar-maestro` | OPERAR — agents, skills, prompts, workflows, plugins, MCP, tools, specialties e evals | PR de transição no repositório de origem |
| `Executar-app-Blueprint` | `sas-executar-blueprints` | ESPECIFICAR — produto, domínio, requisitos, contratos, arquitetura e development packets | PR de transição no repositório de origem |
| `next-forge` | `sas-executar-ecosystem` | IMPLEMENTAR + TESTAR + VERIFICAR + RELEASE | PR de transição no repositório de origem |
| `EXECUTAR-Product-Spec` | arquivar após absorção validada | fonte migrada para Blueprints | n/a |
| `Desyng-System-ecossitema.` | read-only ou arquivar após integração validada | fonte de Design; o ponto final faz parte do nome atual | n/a |

## Ações do owner para 100%

1. **Definir visibilidade de Blueprints.** Recomendada: tornar `Executar-app-Blueprint` privado antes de integrar o conteúdo de `EXECUTAR-Product-Spec`, que é privado. Alternativa: autorizar explicitamente a divulgação pública do conteúdo.
2. **Transferir e validar os 31 binários do Desyng.** Usar um meio com suporte a binários e validar SHA/paths contra a matriz `30-design/DESYNG_MIGRATION_MATRIX.csv`.
3. **Decidir a reconciliação técnica dos 120 arquivos `apps/**` e `packages/**`.** Para cada grupo: adotar no Ecosystem, manter a implementação existente ou criar adaptação. Só então executar build, testes e verificação de acessibilidade/release.
4. **Revisar e integrar os PRs encadeados.** Integrar apenas após as decisões 1–3; retargetar filhos quando o pai for integrado. Não tratar a cópia de bytes como aprovação semântica.
5. **Criar/definir a branch canônica `main` no Governance.** Hoje o default de `Programa-Sas` é `claude/plugin-engineer-workflow-klbtix`; o corte precisa apontar `main` para a árvore aprovada e torná-la default.
6. **Renomear os quatro repositórios ativos** para os nomes-alvo, atualizar links e executar a validação pós-rename.
7. **Arquivar os dois repositórios extintos** somente após os passos anteriores: `EXECUTAR-Product-Spec` e `Desyng-System-ecossitema.` (ou deixar este último read-only, se essa for a decisão).
8. **Executar o checklist de corte e rollback** em `FINAL_ARCHIVE_READINESS.md` e registrar evidências de build/test/release.

## Limitações do conector atual

A conexão não expõe operações de alteração de visibilidade, renomeação de repositório, troca de branch padrão ou arquivamento. Essas ações precisam ser feitas por um administrador nas configurações do GitHub; depois devem ser revalidadas antes do corte.

## PRs de controle

- Governance: #7, #8 e #9
- Maestro: #3 e #4
- Blueprints: #10, #13, #14 e #15
- Ecosystem: #4
