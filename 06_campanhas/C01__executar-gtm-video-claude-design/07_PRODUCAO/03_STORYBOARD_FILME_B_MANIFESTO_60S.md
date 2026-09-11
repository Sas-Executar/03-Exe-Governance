# 03 — Storyboard: Filme B, Manifesto, 60s

Executa o passo 5 do handoff para o master de categoria e confiança. Preserva os oito blocos de `SPEC-001` sem alterar seus limites de tempo.

O Manifesto sai do split, mas mantém contraste, progressão e packshot, conforme `ADR-001`.

## Gramática

Montagem contínua com progressão de densidade: começa saturado de interface e termina sem interface nenhuma. A cor entra por acúmulo — os primeiros blocos são quase monocromáticos, e `brand` aparece pela primeira vez no bloco 4, quando o método age.

Locução em português do Brasil, primeira pessoa do plural, sem promessa clínica.

## Decupagem

### Bloco 1 · 00:00–00:07 · O trabalho antes do trabalho

| Campo | Conteúdo |
|---|---|
| Imagem | Sequência rápida de superfícies de administração: colunas, etiquetas, campos, notificações, uma agenda cheia. Nenhuma delas é um produto identificável. |
| Locução | "Antes de começar, existe outro trabalho." |
| Super | Nenhum. |
| Cor | Dessaturado. |
| Claim | C0. |

### Bloco 2 · 00:07–00:14 · O projeto complexo

| Campo | Conteúdo |
|---|---|
| Imagem | Um projeto real em toda a sua extensão: muitas frentes simultâneas, dependências cruzadas, prazos sobrepostos. A câmera afasta e o volume assusta. |
| Locução | "O problema raramente é falta de vontade. É volume, dependência e contexto." |
| Super | Nenhum. |
| Cor | Dessaturado. |
| Claim | C0. |

### Bloco 3 · 00:14–00:22 · Decomposição

| Campo | Conteúdo |
|---|---|
| Imagem | O volume se organiza em `Projeto → Entregável → Workflow → Tarefa → Ação`. Um nível por vez, cascata de 260ms, sem corte. |
| Locução | "Executar decompõe o projeto até a menor unidade acionável." |
| Super | **Projeto → Entregável → Workflow → Tarefa → Ação** |
| Cor | Primeiros traços de `stroke_strong`; ainda sem `brand`. |
| UI | Hierarquia do trabalho · `CONCEITO` |
| Claim | C1. |

### Bloco 4 · 00:22–00:30 · Priorização explicável

| Campo | Conteúdo |
|---|---|
| Imagem | Entre muitas ações possíveis, uma é elevada. Ao lado dela, os critérios aparecem em texto legível: dependência, prazo, esforço, contexto. Primeira entrada de `brand` no filme. |
| Locução | "Com critérios explícitos, que você pode ler e contestar." |
| Super | **"IA orientada por método."** |
| UI | Painel de explicabilidade · `CONCEITO` |
| Claim | C1 para a existência dos critérios. Não afirmar superioridade de resultado. |

### Bloco 5 · 00:30–00:38 · Ação única

| Campo | Conteúdo |
|---|---|
| Imagem | Tudo o mais sai de quadro. Resta uma ação e o tempo para executá-la. O quadro respira pela primeira vez. |
| Locução | "Uma ação por vez. A próxima já está preparada." |
| Super | **"Menos trabalho antes do trabalho."** |
| UI | Tela de execução · `CONCEITO` |
| Claim | C0 no super; C1 na preparação da próxima ação. |

### Bloco 6 · 00:38–00:46 · Analógico e digital

| Campo | Conteúdo |
|---|---|
| Imagem | O trabalho real acontece fora da tela: papel, oficina, quadro branco, conversa, código, campo. A interface aparece apenas nas bordas, entrando e saindo. |
| Locução | "O trabalho não acontece dentro do aplicativo." |
| Super | Nenhum. |
| Cor | Cor plena. |
| Claim | C0. |

### Bloco 7 · 00:46–00:53 · Metodologia pública

| Campo | Conteúdo |
|---|---|
| Imagem | A metodologia exposta como documento legível: princípios, critérios e limites, incluindo o que o sistema **não** afirma. |
| Locução | "Nossa metodologia é pública, com decisões orientadas por evidências, princípios de ergonomia cognitiva e práticas consolidadas de gestão." |
| Super | **"Método público. Limites declarados."** |
| Claim | **C2 — formulação obrigatória.** Este é o bloco de maior risco jurídico do pacote: a locução deve usar exatamente a formulação recomendada e nunca "cientificamente comprovado". Ver `06_GOVERNANCA/CLAIMS_QA_E_APROVACAO.md`. |

### Bloco 8 · 00:53–01:00 · Conclusão e saída

| Campo | Conteúdo |
|---|---|
| Imagem | O aplicativo é fechado. A pessoa continua trabalhando. Packshot. |
| Locução | "Organizar é função do sistema. Executar é função sua." |
| Super | **"O aplicativo desenhado para você sair dele."** · Packshot · **"Pare de organizar. Comece a executar."** |
| Claim | C0. |

## Poster frame

Bloco 5, no frame da ação única — é o frame que comunica a promessa sem texto.

## Mensagem para neurodivergência

O Manifesto trata neurodivergência pelo desenho do sistema, não por rótulo em tela. Nenhum bloco nomeia diagnóstico, nenhum bloco representa uma pessoa neurodivergente como personagem-problema. A frase da fonte — "um sistema que considera como o trabalho exige atenção, memória, decisão, iniciação e retomada" — pode ser usada em peças de texto, **não** como locução deste filme, onde viraria promessa implícita de efeito.

## Verificação de narrativa sem áudio

Os blocos 1, 2 e 6 não têm super e dependem de locução. Em versões sem áudio, a legenda obrigatória cobre os três; sem legenda o filme perde a premissa. Esta é a diferença principal em relação ao Filme A, que funciona mudo.
