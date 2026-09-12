# Classificação controlada — registros do Maestro

**Workflow:** WF-01 · Maestro → Governance  
**Data:** 2026-09-12  
**Origem:** `Sas-Executar/Maestr-Docs@main` · árvore `48db71b13e8108479bcf1961a812c1785140a44f`  
**Review branch:** `migration/maestro-records-classification`

## Resultado

Foram classificados **36 artefatos copiados**. A classificação é uma hipótese de roteamento, não uma promoção de autoridade. Nenhum ID interno, byte de origem ou arquivo do Maestro foi alterado.

## Distribuição por destino candidato

| Destino/dominio | Artefatos |
|---|---:|
| BLUEPRINTS | 2 |
| D02 | 1 |
| D05 | 2 |
| D06 | 6 |
| D08 | 1 |
| D09 | 3 |
| D13 | 1 |
| MAESTRO | 1 |
| MULTI_DOMAIN | 6 |
| REGISTRY | 13 |

## Regras aplicadas

- `COPY` preserva a cópia de entrada; não autoriza remoção na origem.
- `REFERENCE` indica artefato transversal ou de Blueprints que exige PR próprio para distribuição.
- `KEEP` foi aplicado ao material PMBOK com instrução explícita para agente; seu destino candidato é Maestro.
- `PROPOSED` não cria requisito, não altera IDs e não substitui o GOV-IDX-030-001.

## Conflitos e gaps

| Status | Quantidade | Tratamento |
|---|---:|---|
| BINARY_REVIEW_REQUIRED | 1 | Manter em fila; não distribuir automaticamente. |
| CROSS_REPO_BOUNDARY | 2 | Manter em fila; não distribuir automaticamente. |
| MIXED_AGENT_INSTRUCTION | 1 | Manter em fila; não distribuir automaticamente. |
| MULTI_DOMAIN | 6 | Manter em fila; não distribuir automaticamente. |
| REQUIRES_RECONCILIATION | 26 | Manter em fila; não distribuir automaticamente. |

Os arquivos de workbook consolidados e os registros multidomínio exigem roteamento por registro/linha ou por estrutura interna. O XLSX permanece com inspeção semântica pendente.

## Saídas

- `MAESTRO_RECORDS_CLASSIFICATION.csv` é o registro detalhado, com proveniência e destino candidato.
- `MAESTRO_RECORDS_DISTRIBUTION_QUEUE.csv` é a fila de decisões de distribuição.
- A fila original permanece como evidência do intake inicial; esta classificação é seu adendo controlado.
