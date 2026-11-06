# Aula 4.3: Aplicando o Design System no projeto

Use este prompt para transformar uma exportação do Claude Design em um sistema de design integrado ao
seu projeto. A entrega inclui os componentes necessários, tokens visuais, referências e orientações de uso.

## Antes de começar

1. Tenha o projeto funcionando. Se estiver começando, siga a aula de
   [criação da estrutura do projeto](../desenvolvimento/criar-estrutura-do-projeto.md).
2. Coloque a exportação do Claude Design na pasta `design-system-export`, na raiz da aplicação.
   Preserve a organização dos arquivos, incluindo HTMLs, estilos, imagens e fontes presentes na exportação.
3. Abra a pasta da aplicação no VS Code e confirme que o agente tem acesso aos arquivos e ao terminal.

## Como usar

1. Confira os caminhos e as escolhas da tabela abaixo. Ajuste o prompt ao contexto da sua aplicação.
2. Cole o bloco completo no agente, dentro da pasta do projeto, e peça a execução.
3. Ao terminar, abra a página de demonstração informada pelo agente e revise os componentes,
   os estados e os temas suportados.
4. Confira o relatório de integração, as verificações executadas e eventuais pendências.

## O que você precisa adaptar

| Item | O que conferir ou alterar |
| --- | --- |
| Pasta de origem | O prompt espera `design-system-export` na raiz. Se sua exportação estiver em outro caminho, altere todas as referências a essa pasta, inclusive na etapa de limpeza. |
| Pasta de destino | O prompt usa `design-system`. Se o projeto já tiver uma biblioteca com outra organização, informe isso ao agente e ajuste o destino para reaproveitar a estrutura. |
| Página de demonstração | O prompt reaproveita uma página existente ou cria `/design-system`. Ajuste esse caminho se o projeto utilizar outra rota. |
| Temas e componentes | Informe quais temas o projeto suporta e quais componentes são necessários. O agente também examinará a aplicação e a exportação antes de integrar. |

A pasta original será removida somente após a validação da integração e a confirmação de que nenhum
arquivo depende dela. Se alguma validação necessária estiver bloqueada, o prompt orienta a preservar a origem.

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão antes de executar esta tarefa.
Respeite as autorizações já concedidas e os limites abaixo, sem ampliar o escopo nem repetir perguntas respondidas.
Se a skill estiver indisponível, informe o impedimento e não simule seu uso.

Na raiz existe a pasta design-system-export, uma exportação bruta do Claude Design. Use esse material
para criar e integrar um sistema de design em design-system, adaptado ao projeto e contendo apenas
o necessário.

Após o alinhamento inicial pelo Brainstorming, execute de ponta a ponta sem repetir confirmações já concedidas.
Em ambiguidades técnicas reversíveis, preserve o que já funciona e registre a decisão no relatório final.
Só interrompa diante de um impedimento real.

## 1. Diagnóstico

Antes de alterar arquivos, examine o projeto e a exportação.

Identifique o framework e as versões instaladas, a presença e a versão de Tailwind e shadcn/ui,
o carregamento de fontes, os temas claro e escuro, os estilos, os componentes e as configurações de lint.
Consulte a documentação atual correspondente às versões utilizadas.

Levante também os arquivos Markdown que funcionam como contrato ou instrução: DESIGN.md, AGENTS.md,
CLAUDE.md, README.md, CONTRIBUTING.md, docs/ e equivalentes.

## 2. Seleção do material

Separe conteúdo útil, duplicatas e artefatos internos da ferramenta. Compare componentes repetidos
e escolha a versão canônica considerando completude, variantes e estados.

Resgate os DESIGN.md relevantes, inclusive em subpastas, e as configurações de lint de aderência ao
sistema de design.

Preserve os HTMLs de referência em design-system/references, com os recursos e os caminhos funcionando
após a remoção da origem.

## 3. Adaptação e integração

Crie em design-system os componentes funcionais, tokens, recursos, padrões de composição e diretrizes
de uso necessários ao projeto. Incorpore apenas o material necessário, incluindo componentes funcionais
além dos tokens.

Para os componentes incorporados, preserve as variantes e os estados aplicáveis, incluindo foco,
desabilitado, carregamento, erro e seleção, com acessibilidade.

Respeite os padrões e as versões de Tailwind e shadcn/ui existentes. Reaproveite componentes equivalentes,
evitando bibliotecas paralelas.

Padronize cores, fontes, espaçamentos e raios por tokens, sem introduzir novos valores fixos desses
atributos fora dos tokens.

Integre as regras de lint úteis e compatíveis. Evite dependências, atualizações de tecnologias
e refatorações sem necessidade.

Use a página de demonstração existente ou crie uma rota /design-system para apresentar os componentes
incorporados, seus estados e os temas suportados pelo projeto.

## 4. Documentação

Crie ou atualize o DESIGN.md da raiz como contrato visual e fonte da verdade dos tokens.

Documente a estrutura de design-system, a localização das referências e como usar ou criar componentes.
Nas instruções lidas pelos agentes, registre o uso da biblioteca e dos tokens.

Preserve integralmente o conteúdo não relacionado à tarefa. Atualize apenas as seções necessárias.
Confirme as convenções atuais das ferramentas antes de renomear ou consolidar arquivos; preserve
o conteúdo anterior e prefira acrescentar quando houver dúvida.

Não crie documentação redundante ou desproporcional ao projeto.

## 5. Validação e limpeza

Instale apenas as dependências necessárias. Execute build, typecheck, lint e os testes pertinentes.

Abra a página de demonstração, confira os temas e estados e verifique os HTMLs no novo caminho.
Corrija as falhas introduzidas.

Antes de remover a origem, verifique importações, caminhos e scripts que possam apontar para ela.
Somente após validar a integração e confirmar que nada depende da pasta original, apague
design-system-export inteira.

Se houver impedimento de validação, preserve a origem e informe o bloqueio.

Finalize com um resumo do que foi integrado, descartado, padronizado e validado, incluindo decisões
tomadas e eventuais pendências.
```

[Voltar ao guia](../../README.md)
