# Avaliar evoluções técnicas: filas, cache e banco de dados

Use para decidir se o projeto precisa de uma nova tecnologia. O agente examina o problema e compara
alternativas, incluindo resolver a necessidade com o que já existe.

## Como usar

1. Descreva a dificuldade ou o objetivo, como tarefas demoradas, consultas repetidas ou concorrência no banco.
2. Informe os dados conhecidos e as restrições de custo e operação. Declare o que ainda não sabe.
3. Cole o prompt. Escolha uma alternativa após ler a comparação; instalação e migração serão outra tarefa.

## O que você precisa adaptar

| Campo | O que preencher |
| --- | --- |
| Objetivo | Problema a resolver ou oportunidade a investigar. Exemplo: processar relatórios sem prender a requisição. |
| Uso conhecido | Volume, concorrência, duração ou falhas observadas. Exemplo: relatórios levam 40 segundos; concorrência ainda desconhecida. |
| Restrições | Orçamento, hospedagem, equipe e contratos. Exemplo: manter a hospedagem atual e evitar novo serviço pago nesta fase. |

Uma fila organiza trabalho para execução posterior; um cache reaproveita resultados. A necessidade
de cada um deve ser avaliada separadamente. Para bancos, compare requisitos concretos, como os que
poderiam justificar uma transição de SQLite para PostgreSQL.

## Prompt

```
Avalie oportunidades de evolução técnica neste projeto.
Objetivo ou dificuldade: [PROBLEMA OU OPORTUNIDADE].
Uso e evidências conhecidos: [VOLUME, CONCORRÊNCIA, TEMPOS OU INFORMAÇÕES AINDA DESCONHECIDAS].
Restrições: [ORÇAMENTO, HOSPEDAGEM, EQUIPE E CONTRATOS A PRESERVAR].

Entregue diagnóstico e recomendação para minha escolha. Não instale pacotes, crie serviços, altere código,
modifique configurações, migre dados ou habilite cobranças nesta execução. Preserve o estado do projeto.

## 1. Entender a necessidade

Leia as instruções, a documentação e os caminhos envolvidos no objetivo. Identifique a tecnologia e a
infraestrutura atuais, os limites conhecidos e as evidências disponíveis.

Relacione a oportunidade a uma necessidade observável do produto. Diferencie volume real, previsão
e suposição. Se faltarem medidas, proponha a menor coleta ou experiência capaz de orientar a decisão.

Não invente problemas de escala. Se o projeto já atender à necessidade, recomende manter a solução
e explique quais sinais justificariam reavaliar depois.

## 2. Comparar soluções proporcionais

Selecione poucas alternativas viáveis. Inclua manter a solução atual ou fazer um ajuste simples com
os recursos existentes. Considere apenas opções relacionadas ao problema observado.

Quando o tema for trabalho assíncrono, avalie duração, confirmação ao usuário, persistência das tarefas,
tentativas, execução repetida, idempotência, falhas, ordem e acompanhamento, conforme necessário.

Quando o tema for cache, avalie o que pode ficar desatualizado, por quanto tempo, como invalidar,
como separar dados de usuários e qual será o comportamento quando o cache falhar.

Quando o tema for banco, avalie modelo de dados, consultas, transações, concorrência, integridade,
backup, restauração, operação e compatibilidade com as ferramentas atuais.

Não trate fila, cache e banco principal como soluções intercambiáveis, nem escolha Redis ou qualquer
outro produto antes de definir o papel necessário.

Consulte documentação oficial atual das alternativas e compatibilidade das versões. Use Context7
quando disponível, sem enviar dados privados. Se houver custos, verifique preços e limites atuais
em fontes oficiais, informe a data e separe valores conhecidos de estimativas com suas premissas.

## 3. Avaliar o custo completo

Compare benefício esperado, complexidade de implementação, manutenção, operação, custos, limites,
dependência do fornecedor, impacto nos testes e risco de perda ou inconsistência de dados.

Para uma transição recomendada, descreva consumidores afetados, compatibilidade, preparação dos dados,
backup e prova de restauração, validação e retorno à solução anterior. Considere também dados gravados
após a troca; dizer apenas “voltar a configuração” não resolve esse caso.

Não monte um plano extenso para opções descartadas. Preserve a menor solução que resolva o problema.

## 4. Entregar a decisão proposta

Entregue as evidências, uma comparação curta das alternativas e uma recomendação clara: manter,
medir melhor ou adotar uma mudança específica. Justifique a escolha e os motivos para descartar as demais.

Indique o que a alternativa recomendada resolve, o que não resolve e quais decisões ainda dependem de mim.
Finalize com a próxima tarefa pequena e verificável para validar ou implementar a opção escolhida.
Encerre antes de qualquer instalação ou migração; a recomendação não é autorização para executá-la.
```

[Voltar ao guia](../../README.md)
