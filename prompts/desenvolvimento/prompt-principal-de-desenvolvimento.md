# Prompt principal de desenvolvimento: do pedido ao commit

Use para conduzir uma funcionalidade, correção ou melhoria: discutir o pedido, planejar, desenvolver com
TDD, realizar cinco ciclos de revisão e publicar o trabalho na `main`.

O prompt usa as tecnologias e convenções do projeto. Você só precisa substituir o campo `PEDIDO`.

## Como usar

1. Abra a pasta da aplicação no agente e tenha o Superpowers disponível.
2. Substitua o campo entre colchetes pelo seu pedido. Informe o resultado esperado, os limites e as
   referências relevantes no mesmo campo; o agente investigará o projeto e esclarecerá o que faltar.
3. Cole o bloco completo na conversa. Ele já começa pelo Brainstorming; não é necessário iniciar a
   mesma etapa separadamente.
4. Discuta as decisões importantes e aprove a solução e o escopo. Depois, o prompt autoriza planejamento,
   execução, testes, cinco revisões e commit e push na `main`, sem repetir aprovações já concedidas.
5. Confira o resumo, as verificações, os cinco ciclos de revisão e o resultado da publicação.

## O que você precisa adaptar

| Campo | O que preencher |
| --- | --- |
| Pedido | O que deve mudar, para quem, resultado esperado e restrições conhecidas. Pode incluir referências e dúvidas a discutir. |

Exemplo de pedido: permitir que o cliente reagende um atendimento entre os horários disponíveis,
impedir conflitos e preservar o histórico. Manter as permissões e o sistema de design atuais.

A publicação depende de um repositório Git com remoto e destino identificados. O agente deve verificar
essas condições e respeitar as proteções da `main`, registrando qualquer bloqueio.

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão antes de executar esta tarefa.
Respeite as autorizações já concedidas e os limites abaixo, sem ampliar o escopo nem repetir perguntas respondidas.
Se a skill estiver indisponível, informe o impedimento e não simule seu uso.

PEDIDO
[DESCREVA AQUI O QUE DEVE SER DESENVOLVIDO OU ALTERADO]

Conduza este pedido do entendimento à entrega: Brainstorming, planejamento, execução com TDD,
cinco ciclos de revisão de código, verificação final, commit e push na main.

Após minha aprovação da solução e do escopo no Brainstorming, estão autorizadas essas etapas para
o trabalho acordado. Apresente o plano e prossiga, sem pedir novamente as mesmas aprovações.
Uma nova decisão que altere materialmente o escopo, o custo ou o risco deve ser discutida; continue
as partes independentes. Não transforme decisões técnicas reversíveis em confirmações rotineiras.

## 1. Entender o contexto e discutir o pedido

Antes de propor alterações, leia as instruções aplicáveis e a documentação relevante de produto,
arquitetura e design. Examine o código envolvido, seus chamadores, integrações, testes e configurações.

Identifique linguagem, framework, versões, gerenciador, arquivos de dependências, comandos disponíveis
e condições de execução. Verifique o estado do Git, a branch, o remoto, a main e alterações ou commits
anteriores que não pertencem a esta tarefa. Preserve o trabalho existente do usuário.

Use o Brainstorming para esclarecer o problema, o resultado esperado, os fluxos e os critérios de aceite.
Pergunte somente o que não puder descobrir no projeto e que realmente mude a solução. Faça perguntas
curtas e aproveite respostas e decisões já presentes na conversa.

Compare alternativas viáveis quando houver uma escolha relevante, explique os efeitos e recomende
a menor solução completa. Para um pedido claro, mantenha o alinhamento curto.
Apresente a solução e os limites para minha aprovação antes de implementar; reaproveite aprovação
explícita já concedida para o mesmo escopo, sem repetir o rito.

## 2. Planejar a execução

Use superpowers:writing-plans de forma proporcional ao escopo. Registre a solução acordada e um plano
com etapas pequenas, arquivos envolvidos, dependências, critérios de conclusão e verificações concretas.
Use a documentação canônica existente e evite criar documentos redundantes.

Cada etapa precisa de uma forma observável de provar o resultado. Inclua os consumidores, testes,
configurações e documentação que a mudança realmente afeta. Identifique riscos de compatibilidade,
dados e migrações quando existirem; não presuma requisitos que o projeto não possui.

Apresente o plano e execute a sequência já autorizada. Se o plano revelar uma decisão material ainda
não discutida, esclareça apenas esse ponto antes da etapa dependente.

## 3. Desenvolver com TDD

Use superpowers:test-driven-development para comportamento novo, correções e mudanças de comportamento.
Reaproveite a estrutura de testes e os padrões existentes. Inspecione scripts antes de executá-los.
Registre o estado inicial das verificações relevantes e diferencie falhas preexistentes.

Para cada comportamento:
1. Escreva a menor prova automatizada do resultado esperado ou da regressão.
2. Execute e observe a falha pelo motivo correto, sem confundir defeito de configuração com falha do produto.
3. Implemente somente o necessário para o teste passar.
4. Execute novamente e confirme o resultado.
5. Refatore apenas quando necessário, mantendo os testes verdes e os contratos preservados.

Não escreva a implementação primeiro para depois apresentar testes como se tivessem orientado a mudança.
Não enfraqueça expectativas, ignore testes, remova validações ou oculte erros para obter um resultado verde.
Teste efeitos e regras reais; simulações de dependências não comprovam integrações externas funcionando.

Para mudanças exclusivamente documentais ou sem comportamento executável, use uma verificação adequada
ao artefato e registre o motivo. Não invente testes artificiais nem alegue TDD onde ele não foi realizado.

Reutilize componentes, serviços e recursos existentes. Evite novas dependências, camadas, opções,
atualizações de versões e refatorações sem relação com o pedido.
Consulte documentação oficial compatível quando depender de APIs ou ferramentas; use Context7 quando
disponível, sem enviar código privado, segredos ou dados internos nas consultas.

Preserve segurança, acessibilidade, permissões, integridade dos dados e tratamento de erros.
Use dados fictícios e recursos locais ou de teste para validação. Não aplique migrações em produção,
envie mensagens reais ou contrate serviços como consequência desta tarefa.

## 4. Realizar cinco ciclos de revisão de código

Faça cinco ciclos consecutivos e reais, usando superpowers:requesting-code-review quando disponível.
Cada ciclo consiste em revisar, registrar achados, corrigir problemas confirmados do escopo e validar
as correções antes de iniciar o próximo. As cinco revisões não são cinco leituras idênticas nem cinco
revisores trabalhando em paralelo sobre uma versão que ainda será corrigida.

Use os seguintes focos, mantendo a inspeção do código conectado às mudanças:

1. Aderência ao pedido: critérios de aceite, regras de negócio, caminhos principais e integração funcional.
2. Arquitetura e manutenção: responsabilidades, contratos, consumidores, duplicação e simplicidade da solução.
3. Segurança e robustez: entrada, autorização, dados sensíveis, erros e integridade, conforme aplicáveis.
4. Testes e regressões: qualidade das provas, casos limites, falhas, isolamento e comportamentos vizinhos.
5. Revisão final do conjunto: diff completo, coerência das correções, documentação e efeitos relevantes
   em desempenho, interface e acessibilidade, conforme o projeto.

Use revisão independente quando a ferramenta permitir. Se houver delegação, forneça o escopo, a versão
revisada e os critérios de aceite; preserve cliente, modelo, provedor e autenticação da sessão, passando
o modelo explicitamente quando suportado. Não habilite cobrança por API ou troque de provedor em silêncio.
Se revisão independente estiver indisponível, faça passagens separadas e declare essa limitação.

Para cada achado, confirme evidência e impacto antes de corrigir. Não aceite sugestões automaticamente
nem invente defeitos para preencher um ciclo. Se não houver achados, registre o foco e a conclusão real.
Melhorias fora do escopo ficam como próximas tarefas, sem ampliar a implementação.

Reexecute as verificações afetadas por cada correção. Se uma mudança invalidar uma conclusão de ciclo
anterior, reavalie os pontos atingidos. Não repita toda a bateria de comandos sem alteração ou motivo novo.

Registre os cinco ciclos com foco, versão revisada, achados, correções e verificações. As cinco passagens
solicitadas prevalecem sobre quantidades diferentes sugeridas por fluxos auxiliares de revisão.

## 5. Verificar a entrega

Use superpowers:verification-before-completion. Confira cada critério de aceite na versão final.
Execute a suíte de testes do projeto e as demais verificações exigidas e aplicáveis, como formatação,
lint, tipos e build. Registre comandos e resultados reais, incluindo falhas e avisos relevantes.

Quando houver interface, percorra o fluxo alterado no navegador se houver ferramenta disponível.
Quando houver persistência ou integração, valide o limite correspondente com recursos de teste autorizados.
Distinga o que foi observado, simulado, inspecionado e bloqueado.

Não desative verificações para liberar a entrega. Se uma falha preexistente ou uma dependência indisponível
impedir a validação necessária, informe o bloqueio e preserve o trabalho; não publique como se estivesse pronto.
Encerre apenas processos e recursos criados por esta tarefa.

## 6. Fazer commit e push na main

O commit e o push deste trabalho na main já estão autorizados, após as revisões e verificações necessárias.

Antes de publicar, confira o diff e o conteúdo preparado para commit. Inclua somente as mudanças desta
tarefa, sem segredos, relatórios privados, arquivos temporários ou alterações não relacionadas do usuário.
Confira também os commits que serão enviados: não publique trabalho anterior apenas por estar na branch.

Identifique e confira o remoto de destino. Atualize a informação sobre a main remota e integre somente
o trabalho autorizado à main pelo fluxo compatível com o repositório. Preserve alterações existentes;
não troque de branch de forma destrutiva nem misture commits de outras tarefas.
Se a integração alterar o resultado validado, revise e verifique novamente os pontos afetados antes do push.

Crie um commit com mensagem clara seguindo a convenção do projeto e faça o push da main ao remoto
confirmado. Não use push forçado, ignore verificações ou contorne políticas de proteção.

Se não houver Git, remoto definido ou uma forma segura e permitida de integrar à main, preserve a entrega
local e informe o impedimento. Não crie um repositório público, outro destino ou uma exceção de política
por conta própria. Se não houver mudanças necessárias, não crie um commit vazio.

Confirme o resultado do push e que o commit esperado está na main remota. Se houver automação remota,
informe seu estado observado; não declare que passou enquanto estiver pendente ou sem verificação.

## 7. Entregar o resumo final

Informe de forma curta:
- O que foi entregue e como usar ou testar.
- Decisões e arquivos relevantes.
- Evidências do TDD e resultados das verificações.
- Resultado de cada um dos cinco ciclos de revisão.
- Pendências, limitações e riscos concretos restantes.
- Commit, branch, remoto e resultado confirmado do push, ou o bloqueio encontrado.

Comunique-se em português, com explicações proporcionais à necessidade. Preserve a redação normal
do projeto em código, documentação e commits. Não afirme execução, aprovação ou resultado sem evidência.
```

[Voltar ao guia](../../README.md)
