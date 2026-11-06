# Investigar e corrigir um erro pela causa

Use quando uma funcionalidade falhar, apresentar um resultado errado ou funcionar apenas em algumas situações.
O agente deve reproduzir o problema antes de escolher a correção.

## Como usar

1. Descreva o que aconteceu e o que deveria acontecer. Inclua a mensagem de erro sem dados privados.
2. Informe os passos para reproduzir. Se ainda não os conhecer, escreva `a investigar`.
3. Cole o prompt no projeto e confira a prova do erro e o resultado após a correção.

## O que você precisa adaptar

| Campo | O que preencher |
| --- | --- |
| Erro | Sintoma observado. Exemplo: salvar um agendamento retorna erro após trocar o horário. |
| Esperado | Resultado correto. Exemplo: manter os dados e confirmar o novo horário. |
| Reprodução | Passos e condições conhecidos, ou `a investigar`. Exemplo: editar um agendamento existente e salvar sem mudar o cliente. |
| Escopo | Módulo ou fluxo afetado. Exemplo: edição de agendamentos. |

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão antes de executar esta tarefa.
Respeite as autorizações já concedidas e os limites abaixo, sem ampliar o escopo nem repetir perguntas respondidas.
Se a skill estiver indisponível, informe o impedimento e não simule seu uso.

Investigue e corrija o seguinte erro neste projeto.
Erro observado: [DESCREVA O SINTOMA].
Resultado esperado: [DESCREVA O COMPORTAMENTO CORRETO].
Reprodução conhecida: [PASSOS E CONDIÇÕES OU A INVESTIGAR].
Escopo: [MÓDULO OU FLUXO AFETADO].

Execute o diagnóstico, a correção e a validação. Preserve alterações existentes e mantenha o trabalho
restrito à causa do erro. Não publique, altere produção ou use operações reais de cobrança e envio de mensagens.

## 1. Reproduzir antes de corrigir

Leia as instruções aplicáveis e identifique os caminhos envolvidos, seus chamadores e testes existentes.
Inspecione scripts antes de executá-los. Registre versões e condições relevantes ao erro.

Tente reproduzir em ambiente local ou de teste, com dados fictícios. Colete apenas os logs necessários,
sem exibir segredos ou dados pessoais. Diferencie o resultado esperado do observado.

Se não conseguir reproduzir, compare hipóteses com evidências e investigue as condições que as distinguem.
Não faça uma alteração especulativa para encerrar a tarefa. Peça somente a informação indispensável
que o código e os testes não conseguem revelar.

## 2. Encontrar a causa

Acompanhe o fluxo desde a entrada até o ponto da falha, incluindo validação, estado, acesso a dados
e integrações relevantes. Teste uma hipótese por vez.

Verifique se o defeito está em código compartilhado e examine todos os chamadores afetados.
Consulte a documentação oficial da versão instalada quando a hipótese depender de comportamento externo.

Não trate a última linha do erro como prova da causa. Não oculte exceções, enfraqueça validações
ou adicione tentativas repetidas e esperas arbitrárias para mascarar o problema.

## 3. Corrigir e proteger

Crie ou adapte a menor prova de regressão adequada: teste do comportamento ou reprodução automatizada
compatível com as ferramentas existentes. Execute antes da correção e confirme que falha pelo defeito descrito.

Corrija a causa no ponto responsável, preservando contratos e tratamento de erros. Atualize os chamadores
necessários. Evite refatorações, mudanças de versão e dependências sem relação com o defeito.

Execute novamente a prova e confirme o resultado esperado. Verifique também os comportamentos próximos
que a mudança possa afetar. Se não houver automação viável, registre a reprodução manual e essa limitação.

## 4. Entregar

Informe a causa confirmada, os arquivos alterados, como reproduzir antes e como verificar depois.
Liste os comandos executados com resultados, a prova de regressão e eventuais falhas anteriores à mudança.

Declare bloqueios e limitações com clareza. Só informe que o erro foi corrigido quando houver evidência
do comportamento correto nas condições investigadas.
```

[Voltar ao guia](../../README.md)
