# Revisar UI/UX navegando com Agent Browser

Use para avaliar a experiência real de uma aplicação: concluir tarefas, compreender mensagens, navegar
por teclado e utilizar telas menores. O resultado é uma revisão com evidências e prioridades.

## Como usar

1. Deixe a aplicação disponível em ambiente local ou de teste e tenha o Agent Browser configurado.
2. Escolha as jornadas e o perfil de teste. Use dados fictícios e faça o login pelo fluxo apropriado.
3. Cole o prompt. Confira as reproduções e escolha quais correções deseja implementar depois.

## O que você precisa adaptar

| Campo | O que preencher |
| --- | --- |
| Endereço | URL local ou de teste autorizado. Exemplo: `http://localhost:3000`, se essa for a porta real da aplicação. |
| Jornadas | Tarefas com começo e resultado esperado. Exemplo: encontrar um horário disponível e concluir um agendamento. |
| Perfil | Papel do usuário de teste e contexto de uso. Exemplo: cliente usando o celular. Não inclua credenciais. |

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão antes de executar esta tarefa.
Respeite as autorizações já concedidas e os limites abaixo, sem ampliar o escopo nem repetir perguntas respondidas.
Se a skill estiver indisponível, informe o impedimento e não simule seu uso.

Faça uma revisão de UI/UX desta aplicação usando Agent Browser para navegar de verdade.
Endereço autorizado: [URL LOCAL OU DE TESTE].
Jornadas: [TAREFAS E RESULTADOS ESPERADOS].
Perfil e contexto: [PAPEL DO USUÁRIO DE TESTE E CONTEXTO, SEM CREDENCIAIS].

Entregue diagnóstico e recomendações com evidências. Não altere código, dependências, configurações
ou dados existentes. Navegue e realize apenas operações de teste com dados fictícios e efeitos limitados
ao ambiente autorizado. Não efetue pagamentos, envie mensagens reais ou acione operações irreversíveis.

## 1. Preparar a navegação

Leia as instruções e o contrato visual do projeto, como DESIGN.md. Entenda os fluxos e confirme o
endereço de destino antes de interagir. Não amplie a revisão para outros sites ou ambientes.

Verifique se Agent Browser está disponível. Consulte a orientação da versão instalada, começando por
`agent-browser skills get core` quando suportado, e a documentação oficial para comandos necessários.
Use uma sessão própria para a revisão, preservando as sessões pessoais existentes.

Se o navegador ou a aplicação estiver indisponível, informe o bloqueio. Uma inspeção de código pode
complementar o trabalho, mas não deve ser apresentada como uma navegação que não aconteceu.
Não instale ferramentas ou contrate serviços como consequência desta revisão.

Use conta de teste e autenticação já autorizada. Se o login exigir minha intervenção, informe a etapa
sem pedir senhas ou códigos no chat. Não copie cookies ou estados autenticados para arquivos públicos.

## 2. Executar as jornadas

Percorra cada jornada desde a entrada até o resultado esperado. Use snapshots atuais para identificar
elementos e capturas de tela para registrar o resultado visual; atualize as referências após mudanças
de página ou estado. Registre o que foi observado em vez de deduzir tudo pelo código.

Verifique orientação, nomes de ações, hierarquia de informações, consistência com o sistema de design
e clareza de mensagens. Observe estados vazios, carregamento, sucesso, erro e validação quando alcançáveis.

Repita os pontos relevantes em dimensões representativas de computador e celular, registrando as medidas.
Procure cortes, rolagem horizontal inesperada, controles inacessíveis e perda de informação.

Teste navegação por teclado, ordem de foco, foco visível, rótulos de campos, abertura e fechamento
de diálogos e recuperação de erros. Quando houver ferramenta compatível, use a análise automatizada
de acessibilidade como complemento e confirme seus achados.

Inspecione erros de console e requisições relevantes ao fluxo sem registrar conteúdo privado.
Não transforme a revisão em teste de carga ou auditoria ofensiva de segurança.

## 3. Confirmar e priorizar

Reproduza cada problema importante e, quando houver acesso ao código, localize sua provável origem.
Separe falhas funcionais, barreiras de acessibilidade, dificuldades de uso e preferências visuais.

Para cada achado, informe página e jornada, dimensão da tela, passos, resultado esperado e observado,
impacto para o usuário, evidência e sugestão concreta de correção. Evite recomendações genéricas como
“melhorar o layout” sem indicar o problema observado.

Uma análise automatizada ou um snapshot não comprova acessibilidade completa. Declare os aspectos
que dependem de avaliação humana, tecnologia assistiva ou ambientes que não foram testados.

## 4. Entregar

Entregue as jornadas concluídas e bloqueadas, achados priorizados e uma ordem sugerida de correção.
Registre a ferramenta utilizada e as verificações realmente feitas.

Salve evidências, se necessárias, em diretório privado fora do Git, usando dados fictícios e ocultando
informações sensíveis. Não publique capturas nem estados de autenticação.
Encerre somente sessões e recursos criados para esta revisão.

Não implemente as recomendações nesta execução. A próxima tarefa deve selecionar o problema a corrigir
e repetir sua jornada para verificar o resultado.
```

Referências: [Agent Browser](https://agent-browser.dev/) e
[verificações iniciais de acessibilidade do W3C](https://www.w3.org/WAI/test-evaluate/preliminary/).

[Voltar ao guia](../../README.md)
