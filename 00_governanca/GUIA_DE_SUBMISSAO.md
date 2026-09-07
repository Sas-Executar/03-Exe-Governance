# Guia de preenchimento e futura submissão

## Identidade e localização

As 16 áreas e os 30 IDs seguem o anexo; os tópicos são propostas ajustáveis. Cada documento possui um único caminho canônico no índice mestre. Arquivos administrativos, READMEs e registros não ampliam a família dos 30 documentos.

## Preenchimento

1. Selecione o ID existente e atribua owner e revisor.
2. Atualize o modelo canônico e sua versão; preencha objetivo, conteúdo específico, dependências e aceite.
3. Coloque anexos temáticos no subtópico adequado; use `<ID-documento>__<descricao>.<ext>`.
4. Registre fontes e evidências por ID, sem usar existência de arquivo como prova de conclusão.
5. Atualize o registro mestre na mesma alteração do documento.

## Submissão quando o plano começar

1. Crie um registro com ID `SUB-AAAAMMDD-NNN` em `03_submissoes/REGISTRO_SUBMISSOES.csv`.
2. Copie o modelo para `03_submissoes/<ID-submissao>/README.md`, preenchendo IDs, versões, caminhos, revisor e critérios.
3. Faça a alteração em branch de trabalho e abra uma pull request com o ID da submissão.
4. O revisor registra aprovado, ajustes solicitados ou rejeitado com justificativa e evidências.
5. Após aprovação e integração, atualize os registros e mantenha a rastreabilidade do commit.

Não foi criado cronograma de submissões nem designado responsável nesta etapa.

## Estados distintos

- Estado documental: modelo → rascunho → em revisão → aprovado → arquivado.
- Estado de evidência/implementação, quando aplicável: mencionado → existente → implementado → testado → verificado → publicado.
- Validação dos especializados e da taxonomia: pendente até decisão expressa do responsável.

A aprovação documental não implica produto testado, publicado ou lançamento autorizado.

## Proteção da informação

O repositório é público; materiais restritos ficam em local com acesso controlado, com referência não sensível no registro. Nunca inserir segredos, dados pessoais de clientes ou contratos confidenciais.

## Conclusão verificável de uma submissão

ID único, caminho válido, versão consistente, owner, revisor, escopo, critérios atendidos, evidências verificadas e decisão registrada.
