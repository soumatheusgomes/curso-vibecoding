# Guia de prompts do curso

Prompts em português para criar e cuidar de sistemas com inteligência artificial. Este repositório acompanha o curso e reúne exemplos prontos para adaptar ao seu projeto.

## Como usar

1. Encontre o prompt pelo tema na tabela abaixo.
2. Abra o link e copie o bloco do prompt.
3. Substitua os campos entre colchetes pelo contexto do seu projeto.
4. Envie o bloco na conversa do agente, com a pasta da sua aplicação aberta. Confira em cada guia se a tarefa executa mudanças ou entrega uma revisão.

## Padrão de início: Brainstorming do Superpowers

Todos os prompts começam solicitando a skill `superpowers:brainstorming` dentro do próprio bloco para copiar.
O agente deve ler e seguir a skill para alinhar contexto, objetivo, escopo, restrições e critérios de conclusão
antes de executar a tarefa, respeitando as autorizações já concedidas e os limites de cada guia.

O comando `/brainstorm` pode aparecer como atalho no agente, conforme sua configuração. O bloco já contém
a instrução de início; não é necessário repetir a mesma etapa manualmente.

Superpowers precisa estar disponível no agente. O guia de preparação do ambiente explica como tratar
uma instalação nova em que a skill ainda não esteja disponível, sem simular seu uso.

## Prompts disponíveis

| Tema | Prompt | Quando usar |
| --- | --- | --- |
| Preparação do ambiente | [Preparar o ambiente de desenvolvimento](prompts/ambiente/preparar-ambiente-de-desenvolvimento.md) | Instalar, configurar e validar as ferramentas da aula em um computador novo ou existente. |
| Desenvolvimento de sistemas | [Aula 3.1: criar a estrutura do projeto com /brainstorm](prompts/desenvolvimento/criar-estrutura-do-projeto.md) | Descrever o projeto e preparar a base técnica antes de implementar as funcionalidades. |
| Sistemas de design | [Aula 4.3: aplicar o sistema de design no projeto](prompts/design/aplicar-sistema-de-design.md) | Adaptar uma exportação do Claude Design e integrar componentes, tokens e referências ao projeto. |

## Guias práticos para projetos existentes

Oito prompts completos para manter e evoluir uma aplicação. Escolha pelo problema que precisa resolver;
cada guia explica o que adaptar e o resultado esperado.

| Tema | Prompt | Quando usar |
| --- | --- | --- |
| Manutenção | [Sanear o projeto](prompts/manutencao/sanear-projeto.md) | Remover sobras comprovadas e dependências sem uso, preservando o funcionamento. |
| Arquitetura | [Revisar arquitetura e organização](prompts/arquitetura/revisar-arquitetura.md) | Entender responsabilidades, dependências e mudanças que dificultam a manutenção. |
| Manutenção | [Investigar e corrigir um erro](prompts/manutencao/investigar-e-corrigir-bug.md) | Reproduzir uma falha, corrigir sua causa e proteger contra regressão. |
| Testes | [Proteger os fluxos principais](prompts/testes/proteger-fluxos-principais.md) | Criar testes confiáveis para os resultados e riscos importantes do produto. |
| Segurança | [Revisar e corrigir a segurança](prompts/seguranca/revisar-e-corrigir-seguranca.md) | Investigar riscos e corrigir falhas confirmadas em ambiente local. |
| Sistemas de design | [Revisar UI/UX com Agent Browser](prompts/design/revisar-interface-com-agent-browser.md) | Navegar nas jornadas reais e registrar problemas de uso, acessibilidade e responsividade. |
| Desempenho | [Medir e corrigir lentidão](prompts/desempenho/investigar-e-corrigir-lentidao.md) | Localizar um gargalo e comparar o resultado da melhoria nas mesmas condições. |
| Planejamento | [Avaliar evoluções técnicas](prompts/planejamento/avaliar-evolucao-tecnica.md) | Decidir se filas, cache, outro banco ou uma solução existente atendem à necessidade. |

Arquitetura, UI/UX e evolução técnica entregam revisões e recomendações para a próxima decisão.
Os demais guias executam a tarefa descrita, respeitando os limites e as verificações de cada prompt.

## Organização

Os prompts ficam na pasta `prompts`, separados por tema. Cada arquivo traz um título, uma orientação de uso e um bloco para copiar.

Os temas incluem ambiente, desenvolvimento, sistemas de design, manutenção, arquitetura, testes, segurança, desempenho e evolução técnica.
