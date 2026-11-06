# Revisar a arquitetura e a organização do código

Use quando estiver difícil descobrir onde uma regra fica, alterar um fluxo sem quebrar outro ou entender
as dependências entre módulos. A revisão entrega um diagnóstico e um plano de correção.

## Como usar

1. Abra o projeto e indique o módulo ou os fluxos que estão difíceis de manter.
2. Informe os limites que a revisão deve respeitar, como contratos públicos e integrações existentes.
3. Cole o prompt. Use as evidências para escolher uma refatoração pequena como próxima tarefa.

## O que você precisa adaptar

| Campo | O que preencher |
| --- | --- |
| Escopo | Uma parte do sistema ou `projeto inteiro`. Exemplo: agendamento e cobrança. |
| Dificuldade | Problema concreto de manutenção. Exemplo: alterar um agendamento exige editar cinco módulos. Se ainda não souber, escreva `avaliar os fluxos principais`. |
| Restrições | Contratos e limites a preservar. Exemplo: manter a API pública e o banco atual. |

## Prompt

```
Revise a arquitetura deste projeto no escopo: [MÓDULOS OU PROJETO INTEIRO].
Dificuldade observada: [PROBLEMA DE MANUTENÇÃO OU AVALIAR OS FLUXOS PRINCIPAIS].
Restrições: [CONTRATOS E LIMITES A PRESERVAR].

Faça uma revisão com evidências e um plano de melhoria. Não altere código, dependências, configurações
ou estado do Git. Não implemente a refatoração durante esta revisão.

## 1. Entender o projeto

Leia as instruções, a documentação de produto e arquitetura e os manifestos. Identifique a tecnologia,
as convenções do framework, as interfaces públicas e a organização realmente usada.

Considere o tamanho da equipe, o estágio do produto e as restrições informadas quando conhecidos.
Registre informações ausentes como limitações da análise, sem inventar requisitos de escala.

## 2. Percorrer os fluxos

Selecione fluxos representativos do escopo e acompanhe o caminho real: entrada, validação, autorização,
regra de negócio, integração e persistência, conforme existirem.

Mostre os arquivos envolvidos e as dependências relevantes. Examine também os chamadores e contratos
dos pontos suspeitos. Use caminho e linha para sustentar cada observação.

## 3. Avaliar responsabilidades e acoplamento

Procure regras espalhadas, responsabilidades misturadas, dependências circulares, acesso a dados que
contorna limites existentes, duplicação de regras e módulos que exigem mudanças simultâneas desnecessárias.

Avalie nomes, coesão e legibilidade pelo efeito na compreensão e na manutenção.
Uma pasta diferente, um arquivo grande ou a ausência de um padrão conhecido não constituem um problema
por si. Não imponha arquitetura limpa, camadas, repositories ou novas abstrações sem necessidade demonstrada.

Diferencie um defeito com consequência concreta de uma preferência de estilo. Reconheça os limites que
já funcionam. Consulte a documentação oficial da versão usada quando uma conclusão depender do framework.

## 4. Propor mudanças proporcionais

Para cada problema confirmado, descreva o impacto, os arquivos envolvidos e a menor mudança capaz
de resolver a causa. Explique o que deve continuar funcionando e como verificar isso.

Separe ajustes locais de mudanças em contratos, persistência ou integrações. Para estas últimas,
registre consumidores afetados e necessidade de compatibilidade ou transição.

Não transforme a revisão em uma reescrita. Itens apenas de limpeza podem ser encaminhados ao saneamento.

## 5. Entregar a revisão

Entregue um mapa curto dos fluxos e dependências, achados por impacto com evidências e um plano
priorizado com até cinco primeiras tarefas executáveis. Cada tarefa precisa de objetivo, limite e prova
de que preserva o comportamento. Registre outros achados relevantes separadamente.

Informe o que foi inspecionado, o que não foi possível verificar e quais hipóteses ainda precisam de prova.
Não atribua notas de qualidade ou alegue que a arquitetura foi validada apenas pela aparência das pastas.
```

[Voltar ao guia](../../README.md)
