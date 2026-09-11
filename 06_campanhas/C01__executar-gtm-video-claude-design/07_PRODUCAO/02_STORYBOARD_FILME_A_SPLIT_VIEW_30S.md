# 02 — Storyboard: Filme A, Split View, 30s

Executa o passo 5 do handoff para o master de aquisição. Deriva de `03_SPECS/SPEC-001_FILMES_E_CUTDOWNS.md` sem alterar os blocos de tempo da fonte.

Todo frame de produto é `CONCEITO` até a inspeção do Turborepo. Nenhum valor de cor literal aparece abaixo: apenas papéis de token, conforme `01_INVENTARIO_E_BASE_VISUAL.md`.

## Gramática

Tela dividida ao meio por um divisor vertical de 2px em `stroke_strong`.

- **Esquerda — Administração.** Dessaturada, `inverse_surface` esmaecido, enquadramento fixo, UI densa, muitos campos, cursor em movimento constante e improdutivo. A câmera nunca se move deste lado.
- **Direita — Execução.** Identidade EXECUTAR, `surface` clara, um único elemento dominante por frame, movimento deliberado em 200ms. A câmera acompanha a ação.
- **Timers.** Um contador no topo de cada lado, mesma tipografia, mesmo tamanho. É metáfora visual de tempo decorrido na cena, nunca estatística de produto. Nenhum número é apresentado como medição.
- **Divisor.** Desloca-se para a esquerda a cada bloco, ganhando área para o lado Execução. No frame final o divisor sai de quadro.

## Decupagem

### Bloco 1 · 00:00–00:04 · Hook visual

| Campo | Conteúdo |
|---|---|
| Ação esquerda | Cursor preenche campos de um formulário de configuração: prioridade, etiqueta, prazo, responsável, estimativa. Nenhum trabalho começa. |
| Ação direita | Tela única com uma ação e um botão. O cursor toca o botão e a ação inicia. |
| UI mostrada | Esquerda: formulário de configuração genérico, sem marca. Direita: tela Próxima ação · `CONCEITO` |
| Copy em tela | Nenhuma. O hook é visual. |
| Áudio | Silêncio quase total; dois cliques do lado esquerdo, um do lado direito. |
| Transição de entrada | Corte seco a partir de preto. |
| Safe area | Timers a 10% do topo, dentro da safe area de 9:16. |
| Nota de recorte | Em 9:16 o split vira horizontal: Administração em cima, Execução embaixo. |

### Bloco 2 · 00:04–00:09 · O custo de organizar

| Campo | Conteúdo |
|---|---|
| Ação esquerda | O usuário reorganiza o que já havia organizado: arrasta cartões entre colunas, renomeia, recolhe e expande. Timer avança. |
| Ação direita | Primeira ação concluída. Um indicador de conclusão em `complete` aparece por 260ms. |
| UI mostrada | Esquerda: quadro de colunas genérico. Direita: estado concluído · `CONCEITO` |
| Copy em tela | **"Organizar também custa atenção."** Super inferior, dentro da safe area. |
| Áudio | Entra base rítmica discreta, marcando o contraste entre repetição e progresso. |
| Transição | Divisor desliza 5% à esquerda em 260ms. |
| Claim | C0 — linguagem de posicionamento. |

### Bloco 3 · 00:09–00:15 · Permanecer versus continuar

| Campo | Conteúdo |
|---|---|
| Ação esquerda | O usuário continua dentro do sistema: abre configurações, cria mais uma visão, ajusta filtros. |
| Ação direita | Concluída a ação, a próxima aparece sozinha, já com o contexto anterior visível. |
| UI mostrada | Direita: continuidade entre ações, com contexto preservado · `CONCEITO` |
| Copy em tela | **"Menos sistema."** |
| Áudio | A base ganha uma camada do lado direito; o lado esquerdo perde presença sonora. |
| Transição | Divisor desliza mais 10%. |
| Claim | C0. |

### Bloco 4 · 00:15–00:21 · Hierarquia vira ação

| Campo | Conteúdo |
|---|---|
| Ação | O lado Execução assume 70% do quadro. A hierarquia `Projeto → Entregável → Workflow → Tarefa → Ação` aparece como cascata e colapsa em uma única ação destacada. Cascata em 260ms, um nível por vez. |
| UI mostrada | Decomposição da hierarquia do trabalho · `CONCEITO` |
| Copy em tela | **"O Executar estrutura o trabalho para você encontrar o que fazer agora."** |
| Áudio | Cinco marcações sonoras curtas, uma por nível da hierarquia. |
| Transição | A cascata colapsa para a ação única. |
| Claim | C1 — benefício funcional observável; exige produto demonstrável antes de publicar. |

### Bloco 5 · 00:21–00:26 · Método explicável

| Campo | Conteúdo |
|---|---|
| Ação | Sobre a ação escolhida, abre-se um painel curto com os critérios que a colocaram em primeiro lugar: dependência resolvida, prazo, esforço e contexto disponível. Texto legível, não decorativo. |
| UI mostrada | Painel de explicabilidade da priorização · `CONCEITO` |
| Copy em tela | **"IA orientada por método."** |
| Áudio | Redução de camadas; a voz do design fica no texto. |
| Transição | Painel entra em 200ms a partir da borda da ação. |
| Claim | C1 para a existência dos critérios; **C3 se sugerir eficácia**. Não afirmar que a priorização produz resultado superior comprovado. |

### Bloco 6 · 00:26–00:30 · Saída e assinatura

| Campo | Conteúdo |
|---|---|
| Ação | O usuário fecha o aplicativo. O quadro fica com a pessoa executando o trabalho real, sem nenhuma interface visível. O divisor sai de quadro. |
| UI mostrada | Nenhuma. Este é o frame da Big Idea. |
| Copy em tela | **"O aplicativo desenhado para você sair dele."** · Packshot · **"Pare de organizar. Comece a executar."** |
| Áudio | Resolução da base e silêncio no packshot. |
| Transição de saída | Corte para end card. |
| Claim | C0. |

## Poster frame

Bloco 6, no instante em que a Big Idea está em tela junto ao packshot.

## Verificação de narrativa sem áudio

Os supers dos blocos 2, 3, 4, 5 e 6 sustentam a história sozinhos. O bloco 1 é deliberadamente mudo: o contraste de comportamento carrega o sentido. Legendas obrigatórias em todos os blocos com áudio.

## Restrições aplicadas

Nenhum concorrente identificável; o lado Administração é genérico e sem marca. Nenhuma caricatura de usuário ou de neurodivergência: o lado esquerdo mostra trabalho legítimo sendo consumido por configuração, não uma pessoa incompetente. Nenhum número de performance. Nenhuma estética clínica.
