# Prompt principal de desenvolvimento: do pedido ao commit

Use para desenvolver uma funcionalidade, correção ou melhoria, do alinhamento inicial à publicação na `main`.

## Como usar

1. Abra o projeto no agente, com Superpowers disponível.
2. Troque somente o campo `PEDIDO`: descreva o resultado esperado, as restrições e as referências relevantes.
3. Cole o bloco e participe do Brainstorming. Após aprovar a solução e o escopo, as demais etapas estão autorizadas.

Exemplo de pedido: permitir reagendamento sem conflito de horários, preservando histórico e permissões.

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de aceite. Se indisponível, informe o bloqueio sem simular seu uso.

PEDIDO
[DESCREVA AQUI O QUE DEVE SER DESENVOLVIDO OU ALTERADO]

Leia as instruções e o código relevantes. Reutilize os padrões existentes e preserve dados, segredos
e trabalho do usuário. Consulte Context7 ou fontes oficiais quando necessário; valide em ambiente de teste.

Após minha aprovação da solução e do escopo, prossiga sem repetir aprovações. Discuta apenas decisões
novas que alterem materialmente escopo, custo ou risco.

## 1. Planejamento
Use superpowers:writing-plans com etapas pequenas e verificações concretas. Apresente o plano e execute.

## 2. TDD
Use superpowers:test-driven-development: teste falhando pelo motivo correto, implementação mínima
e refatoração com testes verdes. Para documentação, valide o artefato sem inventar testes.

## 3. Cinco ciclos de revisão
Use superpowers:requesting-code-review em cinco ciclos consecutivos, com estes focos:
1. Funcionamento e aderência ao pedido.
2. Arquitetura, contratos e simplicidade.
3. Segurança e integridade dos dados.
4. Testes, casos limites e regressões.
5. Diff final, documentação, desempenho e acessibilidade aplicáveis.

Em cada ciclo, revise, corrija achados confirmados e valide antes do próximo. Reavalie pontos afetados
por correções, sem inventar alterações ou repetir verificações desnecessárias.
Prefira revisão independente; declare autorrevisão. Ao delegar, preserve modelo e autenticação e passe
o modelo explicitamente quando suportado.

## 4. Verificação e publicação
Use superpowers:verification-before-completion: confira os critérios de aceite, a suíte de testes
e os demais checks aplicáveis, distinguindo falhas preexistentes.

Confira diff, remoto e main remota. Faça commit e push na main somente do trabalho autorizado,
sem misturar alterações ou commits anteriores, forçar push ou contornar proteções. Revalide se houver
mudanças na integração e confirme o commit remoto. Não crie commit vazio.
Se a validação ou publicação estiver bloqueada, preserve o trabalho e informe a pendência sem declarar sucesso.

Finalize com o que mudou, como testar, resultados dos cinco ciclos, verificações, pendências e commit/push.
```

[Voltar ao guia](../../README.md)
