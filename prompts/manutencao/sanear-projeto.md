# Sanear o projeto: remover sobras sem quebrar o funcionamento

Use quando o projeto acumulou arquivos esquecidos, dependências aparentemente sem uso e código morto.
O objetivo é limpar com evidências, preservando as funcionalidades e os dados.

## Como usar

1. Abra a pasta da aplicação no agente. Preserve uma cópia ou um commit do estado atual antes da limpeza.
2. Preencha o escopo e os itens que precisam ser preservados. Comece por um módulo se o projeto for grande.
3. Cole o bloco completo e confira o relatório com as remoções e verificações.

## O que você precisa adaptar

| Campo | O que preencher |
| --- | --- |
| Escopo | Uma pasta, um módulo ou `projeto inteiro`. Exemplo: módulo de agendamentos. |
| Preservar | Arquivos e integrações que não devem ser removidos. Exemplo: importadores antigos usados por clientes. Se não houver restrição adicional, escreva isso. |

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão antes de executar esta tarefa.
Respeite as autorizações já concedidas e os limites abaixo, sem ampliar o escopo nem repetir perguntas respondidas.
Se a skill estiver indisponível, informe o impedimento e não simule seu uso.

Faça o saneamento deste projeto no escopo: [PASTA, MÓDULO OU PROJETO INTEIRO].
Preserve especialmente: [ITENS A PRESERVAR OU NENHUMA RESTRIÇÃO ADICIONAL].

Execute a limpeza comprovadamente segura e valide o resultado. O objetivo é remover sobras sem mudar
o comportamento do produto. Preserve alterações existentes do usuário; não faça reset nem descarte
trabalho do usuário. Não publique nem limpe dados como parte desta tarefa.

## 1. Conhecer o estado atual

Leia as instruções aplicáveis, a documentação e os manifestos. Identifique a tecnologia, os gerenciadores,
os arquivos de trava de dependências, os comandos existentes e o estado do Git.

Inspecione os scripts antes de executá-los. Rode as verificações disponíveis e pertinentes ao escopo,
como lint, tipos, testes e build. Registre os resultados reais e as falhas anteriores à limpeza.
Se uma falha impedir verificar a segurança de determinada remoção, preserve esse item e explique o motivo.

## 2. Procurar sobras e comprovar o uso

Procure importações sem uso, código inalcançável, arquivos órfãos, duplicatas dispensáveis, artefatos
gerados indevidamente versionados e dependências sem função atual.

Antes de remover, examine referências em código, configurações, scripts, testes, documentação operacional,
geradores e convenções do framework. Considere importações dinâmicas, descoberta automática, assets,
dependências exigidas por outras bibliotecas e interfaces consumidas fora deste repositório.

Uma busca sem resultados ou um alerta de ferramenta não prova que um arquivo é dispensável.
Componentes parecidos também não são necessariamente duplicatas.

Revise TODOs e comentários antigos somente quando houver prova de que perderam a finalidade.
Preserve avisos sobre limitações reais, histórico útil e arquivos de finalidade desconhecida.

## 3. Limpar o que foi confirmado

Remova apenas os itens com evidência suficiente. Use o gerenciador já adotado para remover dependências
e atualizar o manifesto e o arquivo de trava de forma coerente.

Faça alterações pequenas e relacionadas. Não atualize versões, reorganize a arquitetura, reescreva
funcionalidades ou instale ferramentas de análise por costume.

Não apague migrações, dados, volumes, arquivos locais do usuário ou recursos apenas por serem antigos.
Quando houver dúvida, mantenha o item e registre o que falta comprovar. Continue a limpeza independente.

## 4. Validar e entregar

Verifique os pontos afetados após cada conjunto coerente de remoções. Ao final, repita as verificações
necessárias para comparar com o estado inicial e corrija as regressões introduzidas pela limpeza.

Entregue:
- Itens removidos, com caminho, motivo e evidência de que não eram necessários.
- Dependências removidas e ajustes nos arquivos de dependências.
- Resultados anteriores e finais dos comandos realmente executados.
- Itens preservados por dúvida, falhas preexistentes e validações bloqueadas.

Não declare que algo foi validado sem executar a verificação correspondente.
Encerre quando o escopo estiver saneado e verificado; registre trabalhos de arquitetura como próximas tarefas.
```

[Voltar ao guia](../../README.md)
