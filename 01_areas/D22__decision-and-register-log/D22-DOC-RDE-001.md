# D22-DOC-RDE-001 — Registro de Decisões do Ecossistema

## Controle documental

- Área canônica: `D22 — Decision and Register Log`
- Tipo: Registro especializado de decisões
- Estado: ATIVO
- Versão: 1.1
- Data de abertura: 2026-09-12
- Última atualização: 2026-09-12

---

## D22-DEC-001 — Padrão canônico de interface do EXECUTAR

### Estado

**ACEITA**

### Data

2026-09-12

### Decisão

Adotar como padrão canônico e default de interface do aplicativo EXECUTAR a versão consolidada na branch `chatgpt/scroll-task-prototype` do repositório `Sas-Executar/next-forge`, tendo como referência factual inicial o commit `ddb57fe9af2e82e0d889a54a17806e69edf362e0`.

A partir desta decisão, toda nova rota, tela, fluxo, componente ou evolução de interface do aplicativo deve incorporar e preservar, por padrão:

- a arquitetura de UI e navegação estabelecida nessa versão;
- o layout, a composição visual e a hierarquia operacional aprovados;
- a paleta, os design tokens e os componentes do Design System correspondente;
- Apple Human Interface Guidelines como referência obrigatória de comportamento, interação, acessibilidade e ergonomia;
- Geist como base de identidade tipográfica e visual;
- Fluent 2 como referência de hierarquia operacional, espaçamento e organização de comandos;
- os contratos transversais de responsividade, safe areas, texto escalável, redução de movimento, navegação previsível e alvos mínimos de interação;
- os modos Scroll/Foco e Lista convencional, conforme aplicáveis ao contexto funcional;
- a mesma linguagem de navegação nas demais rotas do PWA.

### Alcance

Esta decisão aplica-se:

- ao aplicativo atual;
- a todas as rotas existentes quando forem revisadas ou migradas;
- a qualquer nova rota ou funcionalidade;
- a componentes compartilhados e pacotes do Design System;
- a implementações futuras realizadas por pessoas, agentes de IA ou automações;
- à evolução de arquivos de configuração e dependências, inclusive `package.json`, quando necessária para sustentar esse padrão.

### Regra de conformidade

SE uma nova implementação alterar layout, cores, tokens, navegação, arquitetura de UI ou comportamento de interação, ENTÃO ela deve permanecer compatível com este padrão ou apresentar uma nova decisão explícita que substitua ou excepcione `D22-DEC-001`.

Exceções locais não podem redefinir silenciosamente o padrão global. Divergências devem ser documentadas antes da incorporação à linha canônica.

### Base e evidências relacionadas

- Repositório de implementação: `Sas-Executar/next-forge`
- Branch de referência: `chatgpt/scroll-task-prototype`
- Commit de referência: `ddb57fe9af2e82e0d889a54a17806e69edf362e0`
- `ADR-EXEC-UI-001.md`
- `ADR-EXEC-UI-002.md`
- `packages/design-system/EXECUTAR-UI-RULES.md`
- protótipo e implementação `scroll-task-prototype/*`
- contratos de UI e navegação associados à branch

### Consequências

- A versão escolhida passa a ser baseline normativa, não apenas protótipo ou referência visual.
- Novas rotas devem nascer aderentes ao padrão.
- Rotas existentes devem convergir para o padrão durante sua evolução.
- Design tokens e dependências devem ser centralizados e reutilizados, evitando variações paralelas não governadas.
- Mudanças estruturais futuras exigem rastreabilidade e decisão substitutiva ou excepcional.
- Testes de interface devem verificar os contratos funcionais, responsivos e de acessibilidade vinculados ao padrão.

### Estado de implementação e integração

- Decisão de produto e arquitetura: **ACEITA**
- Implementação de referência na branch: **OBSERVADA**
- Incorporação à `main`: **NÃO CONFIRMADA**
- Publicação integral em produção: **NÃO CONFIRMADA**

Esta decisão não promove automaticamente a branch para `main`, não executa merge e não equivale a liberação em produção.

### Próximos passos vinculados

1. Validar a branch contra a linha atual da `main`.
2. Consolidar os tokens e contratos no pacote canônico do Design System.
3. Executar testes funcionais, responsivos, visuais e de acessibilidade.
4. Abrir ou atualizar o fluxo de integração para a `main`.
5. Registrar separadamente merge, release e deployment quando efetivamente concluídos.

---

## D22-DEC-002 — Área Studio / Consultoria do EXECUTAR

### Estado

**ACEITA**

### Data

2026-09-12

### Decisão

Criar no EXECUTAR uma área funcional denominada **Studio / Consultoria**, destinada à exploração orientada de problemas, diagnóstico, concepção, prototipagem e preparação de artefatos antes de sua promoção para execução operacional.

O Studio deve funcionar como uma **área de trabalho de cocriação entre usuário e agente**, permitindo partir de uma intenção, briefing, problema ou oportunidade e produzir versões progressivamente refinadas de artefatos de consulta, decisão e design.

O benchmark público principal desta decisão é `https://claude.com/product/design`, usado como referência funcional e de interação, não como cópia de interface, marca ou implementação.

### Capacidades abrangidas

A área Studio / Consultoria deve suportar, de forma compatível com o contexto do EXECUTAR:

- diagnóstico e exploração de problema;
- sessões de consultoria orientadas pelo agente;
- geração e refinamento de protótipos interativos;
- wireframes e mockups;
- explorações e alternativas de design;
- one-pagers e documentos de decisão;
- apresentações e materiais visuais quando fizerem parte da entrega;
- uso do Design System canônico do EXECUTAR na geração dos artefatos;
- refinamento iterativo do artefato dentro da própria área de trabalho;
- comparação entre versões ou direções;
- preparação para handoff a código, projeto, tarefa, entregável ou ferramenta externa autorizada;
- exportação e compartilhamento dos artefatos suportados pelo produto.

### Modelo de área de trabalho

O Studio deve ser organizado como workspace persistente, contendo no mínimo os conceitos funcionais abaixo:

1. **Contexto** — briefing, problema, objetivo, restrições e evidências de entrada.
2. **Consultoria** — diálogo estruturado com o agente, hipóteses, diagnóstico e recomendações.
3. **Canvas / Artefato** — superfície principal para visualizar e refinar o resultado produzido.
4. **Variações** — alternativas, versões ou direções exploradas sem sobrescrever silenciosamente o artefato principal.
5. **Protótipo** — representação navegável ou demonstrável quando a natureza do trabalho exigir interação.
6. **Handoff** — promoção explícita do resultado para uma superfície operacional do EXECUTAR ou integração autorizada.

A nomenclatura exata de rotas, componentes e entidades persistidas permanece responsabilidade do PRD/SPEC correspondente e não é fixada por esta decisão.

### Fronteira com o Workspace operacional

O Studio **não substitui** Projeto, Value Stream, Entregável, Tarefa ou Ação e não se torna fonte paralela de verdade operacional.

SE um artefato do Studio precisar gerar trabalho executável, ENTÃO deve existir um handoff explícito que transforme ou vincule o resultado a objetos canônicos do EXECUTAR, preservando origem, versão e evidência.

SE uma alteração for realizada somente dentro de uma exploração ou protótipo, ENTÃO ela não altera automaticamente o estado operacional do projeto.

### Relação com o padrão de interface

`D22-DEC-002` complementa e não substitui `D22-DEC-001`.

Toda implementação do Studio deve utilizar:

- o Design System canônico do EXECUTAR;
- os contratos de responsividade e acessibilidade já aceitos;
- Apple Human Interface Guidelines como referência de interação;
- Geist como base visual/tipográfica quando aplicável ao Design System;
- os padrões de navegação do aplicativo;
- componentes compartilhados em vez de criar um sistema visual paralelo.

O Studio pode adotar uma superfície de trabalho própria — por exemplo canvas, painel de propriedades, preview ou área de protótipo — desde que essa superfície permaneça dentro dos contratos globais do aplicativo.

### Benchmark público observado

Na referência Claude Design, foram observadas como capacidades relevantes:

- criação de protótipos compartilháveis e interativos;
- wireframes e mockups;
- exploração de múltiplas direções de design;
- criação de decks, materiais visuais e documentos;
- importação de design systems, repositórios e codebases para geração aderente à identidade real;
- refinamento direto do conteúdo e dos elementos do artefato;
- handoff entre ambiente de design e ambiente de código;
- exportação para formatos e ferramentas externas.

Classificação da referência: `C_PUBLICADO` — página pública do fornecedor, consultada em 2026-09-12.

### Regra de conformidade

SE uma funcionalidade tiver como objetivo explorar, diagnosticar, experimentar, prototipar ou preparar uma solução antes de sua execução, ENTÃO o Studio / Consultoria é a superfície preferencial.

SE o trabalho já estiver aprovado e decomposto para execução, ENTÃO deve seguir para o Workspace operacional e seus objetos canônicos.

SE o Studio gerar um protótipo com código ou comportamento executável, ENTÃO esse resultado permanece `prototype/draft` até passar pelo fluxo aplicável de requisitos, implementação, teste, verificação e release.

### Consequências

- O EXECUTAR passa a distinguir formalmente **exploração/criação** de **execução operacional**.
- Consultoria deixa de ser apenas conversa e ganha uma superfície persistente de trabalho e artefatos.
- Protótipos podem ser criados e refinados sem contaminar o estado canônico do projeto.
- O Design System pode ser aplicado desde a fase de concepção, reduzindo divergência entre proposta e implementação.
- O handoff Studio → Execução deverá ser rastreável.
- Integrações futuras com geração de código, repositórios, documentos e ferramentas externas deverão preservar essa fronteira.

### Estado de implementação e integração

- Decisão de produto: **ACEITA**
- Benchmark externo: **OBSERVADO**
- PRD específico do Studio: **NÃO CONFIRMADO**
- SPEC técnica do Studio: **NÃO CONFIRMADA**
- Protótipo canônico da área: **NÃO CONFIRMADO**
- Implementação no aplicativo: **NÃO CONFIRMADA**
- Testes: **NÃO CONFIRMADOS**
- Release: **NÃO CONFIRMADO**

### Próximos passos vinculados

1. Criar o PRD da área Studio / Consultoria com jornada, JTBD, estados e critérios de aceitação.
2. Definir o contrato Studio → Workspace operacional e Studio → código/integrações.
3. Criar protótipo aderente a `D22-DEC-001` e ao Design System canônico.
4. Validar os modos de trabalho: consultoria, canvas, protótipo, variações e handoff.
5. Só então promover itens para implementação, teste e release.
