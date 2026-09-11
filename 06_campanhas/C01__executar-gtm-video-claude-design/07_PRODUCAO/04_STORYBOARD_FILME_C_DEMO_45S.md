# 04 — Storyboard: Filme C, Demo de Produto, 45s

Executa o passo 5 do handoff para o master de prova. Percorre o fluxo `objetivo → estrutura → ação → retomada` definido em `SPEC-001`.

Este é o filme com maior exposição de UI e, por isso, o de maior risco de overclaim. **Nenhuma tela aqui pode ir ao ar como `REAL` antes da inspeção do Turborepo**; até lá, todo frame carrega marcação `CONCEITO`.

## Gramática

Captura de tela em primeiro plano, sem locução narrativa: apenas supers curtos e som de interface. Cada bloco mostra uma transformação, não uma lista de funcionalidades. A câmera é a própria interface.

## Decupagem

### Bloco 1 · 00:00–00:06 · Objetivo em linguagem natural

| Campo | Conteúdo |
|---|---|
| Ação | O usuário escreve um objetivo em uma frase comum, sem sintaxe especial, sem campos obrigatórios. |
| UI | Entrada de objetivo · `CONCEITO` |
| Super | **"Comece pelo objetivo. Não pela configuração."** |
| Áudio | Digitação e um confirm curto. |
| Claim | C1. |

### Bloco 2 · 00:06–00:14 · Entregáveis

| Campo | Conteúdo |
|---|---|
| Ação | O objetivo se abre em entregáveis. O usuário não preencheu nenhum formulário para isso. Cascata 260ms. |
| UI | Lista de entregáveis derivada do objetivo · `CONCEITO` |
| Super | **"O sistema propõe a estrutura."** |
| Claim | C1. **Caveat obrigatório**: a proposta é do sistema e permanece editável; não afirmar acerto automático. |

### Bloco 3 · 00:14–00:22 · Workflows, tarefas e ações

| Campo | Conteúdo |
|---|---|
| Ação | Um entregável se decompõe em workflow, tarefas e ações. As dependências aparecem como ligações, e o que está bloqueado fica visivelmente bloqueado. |
| UI | Decomposição com dependências e bloqueios · `CONCEITO` |
| Super | **Projeto → Entregável → Workflow → Tarefa → Ação** |
| Claim | C1. |

### Bloco 4 · 00:22–00:30 · Tela de execução

| Campo | Conteúdo |
|---|---|
| Ação | Uma ação assume a tela inteira. Timer, contexto necessário e nada mais. O usuário executa e conclui; a conclusão usa `complete`, em azul de marca, com rótulo textual junto ao ícone. |
| UI | Tela de execução com WIP unitário · `CONCEITO` |
| Super | **"Uma ação. O contexto que ela exige."** |
| Claim | C1 para o comportamento. **C3 para WIP=1**: não afirmar que executar uma ação por vez tem eficácia comprovada. |
| Acessibilidade | Estado de conclusão nunca por cor isolada: ícone e texto obrigatórios. |

### Bloco 5 · 00:30–00:37 · Retomada com contexto

| Campo | Conteúdo |
|---|---|
| Ação | Corte para o dia seguinte. O usuário reabre o aplicativo e a tela mostra onde parou, o que mudou e qual é a próxima ação — sem reconstrução mental. |
| UI | Retomada com contexto preservado · `CONCEITO` |
| Super | **"Volte sem reconstruir."** |
| Claim | C1. Este é o bloco de maior valor demonstrável do filme. |

### Bloco 6 · 00:37–00:41 · Níveis de evidência

| Campo | Conteúdo |
|---|---|
| Ação | Um painel curto distingue, em tela e por escrito, o que é evidência, o que é prática consolidada e o que é hipótese de produto. |
| UI | Painel de níveis de evidência · `CONCEITO` |
| Super | **"Evidência, prática e hipótese são coisas diferentes."** |
| Claim | **C2.** Este bloco é o que autoriza o tom do restante da campanha; removê-lo enfraquece a defesa de todos os outros claims. |

### Bloco 7 · 00:41–00:45 · Packshot

| Campo | Conteúdo |
|---|---|
| Ação | Aplicativo fechado. Packshot e assinatura. |
| Super | **"O aplicativo desenhado para você sair dele."** · **"Pare de organizar. Comece a executar."** |
| Claim | C0. |

## Poster frame

Bloco 5, na retomada com contexto.

## Regra de UI para este filme

Cada frame de UI precisa constar da matriz `05_MATRIZ_ROTEIRO_CENA_ASSET.csv` com origem declarada. Quando a inspeção do Turborepo confirmar que uma tela existe e está publicada, o status muda de `CONCEITO` para `REAL` na matriz e a marcação em tela é removida — nunca o contrário, e nunca por decisão de produção isolada.

## Verificação de narrativa sem áudio

O Demo é integralmente legível sem som: todos os sete blocos têm super. É o master indicado para feed silencioso.
