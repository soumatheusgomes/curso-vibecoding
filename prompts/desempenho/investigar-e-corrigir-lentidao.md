# Medir e corrigir a lentidão do projeto

Use quando uma tela, consulta ou tarefa estiver lenta. O agente deve localizar o gargalo e medir a diferença
após a mudança, considerando as mesmas condições de teste.

## Como usar

1. Escolha um fluxo lento e explique em que situação ele acontece.
2. Informe o volume conhecido de dados e de uso. Se não souber, escreva `a medir`.
3. Cole o prompt em ambiente local ou de teste. Confira os números e as condições da comparação.

## O que você precisa adaptar

| Campo | O que preencher |
| --- | --- |
| Fluxo | A operação percebida como lenta. Exemplo: abrir a lista de agendamentos de um mês. |
| Sintoma | Quando e como ocorre. Exemplo: a lista demora após selecionar outro profissional. |
| Condições | Volume e carga conhecidos, ou `a medir`. Exemplo: dez mil agendamentos de teste e um usuário navegando. |

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão antes de executar esta tarefa.
Respeite as autorizações já concedidas e os limites abaixo, sem ampliar o escopo nem repetir perguntas respondidas.
Se a skill estiver indisponível, informe o impedimento e não simule seu uso.

Investigue e corrija a lentidão neste fluxo: [TELA, CONSULTA OU TAREFA].
Sintoma e momento: [QUANDO E COMO A LENTIDÃO ACONTECE].
Dados e carga conhecidos: [CONDIÇÕES DE USO OU A MEDIR].

Execute diagnóstico, melhoria pontual e comparação. Preserve resultados funcionais, permissões e
alterações existentes. Use ambiente local ou de teste com dados fictícios; não execute carga em produção,
ative serviços pagos ou mude a infraestrutura durante esta tarefa.

## 1. Estabelecer uma medida útil

Leia as instruções, entenda o fluxo e identifique as ferramentas e versões existentes.
Escolha uma medida ligada ao sintoma: tempo até concluir a tarefa, resposta da API, duração e quantidade
de consultas, transferência, uso de CPU ou memória, conforme o caso.

Registre ambiente, comando, conjunto de dados, carga, rede simulada quando houver e estado dos caches.
Diferencie execução de desenvolvimento, versão otimizada e medições de usuários reais.

Repita a medição o suficiente para observar variação e registre as amostras ou seu resumo.
Não invente percentis com amostras insuficientes nem trate uma única execução como ganho comprovado.

## 2. Localizar o gargalo

Acompanhe o tempo entre interface, rede, servidor, banco e integrações relevantes ao fluxo.
Procure a causa sustentada pelas medidas: trabalho repetido, consultas em excesso, dados desnecessários,
processamento bloqueante, renderizações custosas, recursos grandes ou contenção, quando aplicáveis.

Use os diagnósticos existentes. Examine scripts e ferramentas antes de executá-los e consulte a
documentação oficial compatível quando necessário. Análises que executam consultas ou tarefas precisam
permanecer em recursos descartáveis, sem alterar dados reais.

Formule e verifique uma hipótese de cada vez. Se não houver evidência suficiente, informe a instrumentação
ou o dado faltante, sem aplicar uma otimização especulativa.

## 3. Melhorar a causa comprovada

Implemente a menor mudança capaz de reduzir o gargalo. Preserve ordenação, filtros, consistência,
autorização e comportamento em erro. Use as soluções e os padrões existentes.

Não introduza cache, filas, outro banco ou uma biblioteca apenas por promessa de velocidade.
Se o problema exigir nova infraestrutura, migração ou uma decisão sobre consistência, entregue a
justificativa e o plano dessa evolução como próxima tarefa, sem executá-la automaticamente.

Crie ou ajuste a prova de comportamento relevante. Evite testes de tempo frágeis que falham apenas
porque a máquina está ocupada; use medição controlada para o ganho e testes para a correção funcional.

## 4. Comparar e entregar

Repita a medição com dados, carga, configuração e estado dos caches equivalentes. Registre as diferenças
inevitáveis. Confira também consumo de recursos e efeitos em fluxos vizinhos quando a mudança puder afetá-los.

Se a melhoria não aparecer de forma confiável ou causar regressão, reveja a hipótese e descarte somente
a alteração especulativa desta tarefa, preservando o trabalho anterior do usuário.

Entregue a causa confirmada, os arquivos alterados, a tabela de antes e depois com unidades e condições,
os testes e comandos executados e o que ainda falta medir. Distingua resultados locais de evidências
de produção. Não apresente estimativa como medição real.
```

Referência: [métricas de desempenho centradas no usuário](https://web.dev/articles/user-centric-performance-metrics).

[Voltar ao guia](../../README.md)
