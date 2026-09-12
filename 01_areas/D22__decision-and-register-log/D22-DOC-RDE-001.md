# D22-DOC-RDE-001 — Registro de Decisões do Ecossistema

## Controle documental

- Área canônica: `D22 — Decision and Register Log`
- Tipo: Registro especializado de decisões
- Estado: ATIVO
- Versão: 1.0
- Data de abertura: 2026-09-12

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
