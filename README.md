# sas-executar-governance · transição em revisão

## 1. Propósito
GOVERNAR: autoridade, IDs, evidências, decisões, riscos e gates. Nome atual: `Programa-Sas`. O nome alvo ainda não foi aplicado.

## 2. Não é
Código de runtime e especificações de desenvolvimento não devem criar autoridades duplicadas aqui.

## 3. Source of Truth
[GOV-IDX-030-001](00_governanca/MASTER_INDEX.md), RMOC, D01–D16, 30 documentos e G00–G12 permanecem nos caminhos originais.

## 4. Relação entre repositórios
Governance → Blueprints → Ecosystem. Maestro atua transversalmente.

- [Maestro](https://github.com/Sas-Executar/Maestr-Docs): OPERAR.
- [Blueprints](https://github.com/Sas-Executar/Executar-app-Blueprint): ESPECIFICAR.
- [Governance](https://github.com/Sas-Executar/Programa-Sas): GOVERNAR.
- [Ecosystem](https://github.com/Sas-Executar/next-forge): IMPLEMENTAR + RELEASE.

## 5. Estrutura
- `00_input/`
- `01_master-index/`
- `02_areas/`
- `03_submissions/`
- `04_evidence/`
- `05_decisions/`
- `06_risks/`
- `07_gates/`
- `08_policies/`
- `99_archive/`

As estruturas anteriores são preservadas durante a transição. Diretórios novos não promovem artefatos a canônicos automaticamente.

## 6. Workflow
Entrada → inventário → trabalho em branch → validação → PR → decisão explícita → merge → atualização dos índices.

## 7. Estados
`draft ≠ review ≠ approved ≠ implemented ≠ tested ≠ verified ≠ released`. Preservar também pre_approved, accepted e demais estados encontrados. `registered`, `registered_reference`, `registered_from_source` e `registered_analysis` não significam implementação. A classificação de proveniência não altera a classificação das afirmações da fonte.

## 8. Contribuição
Usar migration/*, blueprint/*, wf/*, integration/*, fix/* ou release/*. Branch representa trabalho. main é o estado-alvo canônico após aprovação e integração explícitas. Se main não existir, a branch default observada não comprova aprovação. Não reescrever histórico ou remover fontes durante a migração.

## 9. Traceability
Origem repo/branch/SHA/path → ID → requisito → AC → target → teste/evidência → release. Campos desconhecidos: GAP; owner desconhecido fica vazio. PROPOSED não é requisito existente.

## 10. Migration status
PASS_WITH_GAPS: estrutura em revisão, fontes preservadas. Renomeação, absorções, redistribuição e archive pendentes. A cópia documental do Maestro está nos PRs 2–4 do Programa-Sas; verificação de bytes não é aprovação documental.

[README anterior](00_input/README_BEFORE_MIGRATION.md) preservado como snapshot de referência com caminhos relativos do contexto original.
