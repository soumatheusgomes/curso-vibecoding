# Criar testes para os fluxos principais

Use quando uma alteração puder quebrar uma parte importante do produto e ainda faltar uma verificação confiável.
O foco são resultados para o usuário e regras de negócio.

## Como usar

1. Escolha poucos fluxos importantes e descreva o resultado esperado em cada um.
2. Informe erros ou limites que merecem proteção, como dados inválidos e acesso sem permissão.
3. Cole o prompt. Confira o que os testes provam e quais dependências reais ainda não foram verificadas.

## O que você precisa adaptar

| Campo | O que preencher |
| --- | --- |
| Fluxos | Ações e resultados esperados. Exemplo: criar um agendamento e encontrá-lo na lista. |
| Riscos | Erros relevantes. Exemplo: impedir horário ocupado e acesso a agendamentos de outro usuário. |

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão antes de executar esta tarefa.
Respeite as autorizações já concedidas e os limites abaixo, sem ampliar o escopo nem repetir perguntas respondidas.
Se a skill estiver indisponível, informe o impedimento e não simule seu uso.

Crie testes confiáveis para os seguintes fluxos deste projeto: [FLUXOS E RESULTADOS ESPERADOS].
Proteja especialmente contra: [ERROS, PERMISSÕES OU LIMITES IMPORTANTES].

Implemente e execute os testes. Preserve o comportamento do produto e as alterações existentes do usuário.
Não implemente novas funcionalidades nem altere regras de negócio para fazer os testes passarem.

## 1. Escolher o que precisa de prova

Leia a documentação de produto, os fluxos implementados e os testes existentes. Identifique as ferramentas,
os comandos e as convenções já usados. Inspecione scripts e hooks antes de executá-los.

Relacione cada risco a um comportamento observável e a um resultado esperado sustentado pelo projeto.
Se a regra estiver ambígua, peça apenas a decisão necessária; avance nos casos independentes.
Não invente funcionalidades para poder criar testes.

## 2. Usar o nível adequado

Use testes pequenos para regras isoladas, integração para limites entre componentes e poucos testes
de ponta a ponta para jornadas que precisem dessa prova completa.

Reaproveite a estrutura existente. Se não houver suporte a testes, configure apenas o mínimo compatível,
consultando a documentação atual e preservando o gerenciador e o arquivo de trava do projeto.
Não instale uma segunda solução para cobrir algo que a atual já permite verificar.

Cubra o caminho principal e as falhas relevantes: entradas inválidas, ausência de dados, permissões,
duplicação ou limites, apenas quando fizerem parte dos fluxos escolhidos.

Verifique resultados, efeitos e negações de acesso. Evite testes que apenas repitam a implementação,
confirmem constantes ou validem que uma função simulada retornou o valor configurado.

## 3. Isolar sem esconder problemas

Use dados fictícios e recursos locais descartáveis. Não use bancos de produção, credenciais reais,
pagamentos ou envio de mensagens. Não apague dados existentes durante a preparação ou a limpeza.

Controle relógio, aleatoriedade e dependências externas quando necessário, mantendo o teste reproduzível.
Simule apenas os limites externos apropriados; uma simulação não comprova a conexão ou o comportamento
de um serviço real. Declare essa diferença.

Garanta que cada teste possa rodar sem depender da ordem dos demais. Limpe apenas recursos criados
pela própria execução e evite esperas fixas para sincronizar processos.

## 4. Provar que os testes detectam falhas

Execute os testes e confirme que verificam o comportamento pretendido. Quando viável, em uma cópia
descartável separada, introduza a falha que deveriam detectar e observe a falha do teste. Não faça essa
experiência no diretório de trabalho do usuário. Registre o que foi possível comprovar.

Se os testes revelarem um defeito real do produto, registre a reprodução e o resultado esperado.
Não enfraqueça a expectativa, ignore o teste ou altere uma regra sem decisão para obter um resultado verde.
Informe que a correção do produto é a próxima tarefa.

## 5. Entregar

Execute os testes novos e os existentes afetados. Integre o comando à rotina automatizada já existente,
quando possível, sem depender de credenciais reais.

Informe cenários cobertos, comandos e resultados, duração observada, limites das simulações e bloqueios.
Entregue o comando para repetir os testes. Não use uma porcentagem de cobertura como prova suficiente
de que os fluxos estão protegidos.
```

[Voltar ao guia](../../README.md)
