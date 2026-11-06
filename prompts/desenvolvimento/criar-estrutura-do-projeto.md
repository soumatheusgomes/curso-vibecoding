# Aula 3.1: O prompt base: criando a estrutura do projeto com /brainstorm

Este prompt prepara a base técnica de uma aplicação: estrutura de pastas, ferramentas, banco local,
Docker, verificações automatizadas e documentação. As funcionalidades do produto serão desenvolvidas
depois, uma por vez.

## Antes de começar

1. Conclua a [preparação do ambiente](../ambiente/preparar-ambiente-de-desenvolvimento.md).
2. Crie uma pasta para a aplicação e abra essa pasta no VS Code. Mantenha o projeto separado deste guia
   de prompts e do repositório do toolkit.
3. Abra o agente com acesso ao terminal e confirme que ele está no diretório da aplicação.

## Como usar

1. O bloco já solicita o Brainstorming do Superpowers para organizar a ideia: problema, público, fluxos
   e limites da primeira versão. Não é necessário iniciar a mesma etapa separadamente com `/brainstorm`.
2. Substitua todos os campos entre colchetes na seção `PROJETO` pelas informações da sua aplicação.
3. Revise os requisitos técnicos do prompt e adapte os que forem diferentes no seu projeto.
4. Cole o bloco completo no agente, dentro da pasta da aplicação, e peça a execução.
5. Ao terminar, confira o relatório, as pendências e o comando informado para iniciar a aplicação.

## O que você precisa adaptar

Preencha os campos com informações concretas. Quanto mais claro o contexto, mais adequada será a base gerada.

| Campo | O que preencher |
| --- | --- |
| Nome | Nome da aplicação. Exemplo: Agenda Fácil. |
| Problema | Necessidade que será resolvida. Exemplo: organizar os agendamentos de um salão. |
| Público | Quem utilizará o sistema. Exemplo: recepcionistas e profissionais do salão. |
| Fluxos principais | Ações previstas para o produto. Exemplo: cadastrar serviços, consultar horários e agendar atendimentos. |
| Restrições | Prazos, orçamento, dispositivos atendidos, integrações obrigatórias e limites da primeira versão. |

Os fluxos principais serão registrados em `PRODUCT.md` para orientar as próximas tarefas. Nesta aula,
a entrega é a base técnica funcionando.

O roteiro usa Next.js e os requisitos abaixo adotam npm, PostgreSQL, Drizzle, shadcn/ui, Docker e
GitHub Actions. Revise essas escolhas conforme seu projeto. Se trocar o banco, por exemplo, ajuste também
a integração de dados, as variáveis de ambiente, o Compose e os testes correspondentes. Projetos com
outra tecnologia precisam de um roteiro compatível.

Use o prompt com os campos preenchidos e as escolhas técnicas ajustadas antes de enviá-lo ao agente.

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão antes de executar esta tarefa.
Respeite as autorizações já concedidas e os limites abaixo, sem ampliar o escopo nem repetir perguntas respondidas.
Se a skill estiver indisponível, informe o impedimento e não simule seu uso.

Leia https://raw.githubusercontent.com/soumatheusgomes/vibe-coding-toolkit/main/docs/prompts/11-next-project-bootstrap.md
e execute integralmente a seção “Prompt” no diretório atual.

PROJETO
Nome: [NOME DA APLICAÇÃO]
Problema: [QUAL PROBLEMA O PROJETO RESOLVE]
Público: [QUEM VAI UTILIZAR A APLICAÇÃO]
Fluxos principais: [PRINCIPAIS AÇÕES PREVISTAS PARA O PRODUTO]
Restrições: [LIMITES, PRAZOS, ORÇAMENTO E EXIGÊNCIAS DO PROJETO]

ESCOPO
Entregue somente a base técnica funcionando. Registre os fluxos em PRODUCT.md; as funcionalidades serão
implementadas depois, uma por vez.

Complemente a preparação inicial com os requisitos abaixo, que prevalecem sobre padrões conflitantes
do roteiro referenciado:

1. Use npm com package-lock.json. Padronize uma versão LTS compatível do Node.js em .nvmrc, engines,
   Docker e integração contínua.

2. Adote shadcn/ui, Lucide e Prettier. Crie apenas os componentes necessários à página inicial mínima,
   com layout responsivo, acessibilidade e tokens visuais.

3. Organize futuras funcionalidades em src/domains, integrações em src/infrastructure e contratos em
   src/contracts. Mantenha rotas finas, serviços independentes do Next.js e acesso ao banco por
   repositórios de dados. Documente os limites sem criar camadas vazias.

4. Configure Docker Compose com PostgreSQL local, volume persistente e verificação de saúde. Crie um
   Dockerfile de produção com múltiplas etapas, saída standalone, usuário sem privilégios e .dockerignore.

5. Complete .env.example e crie .env.local ignorado pelo Git, com valores exclusivos do ambiente local.
   Garanta carregamento coerente entre aplicação, Drizzle, scripts e Compose. Documente variáveis de
   compilação e execução; segredos não devem entrar na imagem nem no código enviado ao navegador.

6. Configure GitHub Actions executando npm ci, verificação de formatação, lint, typecheck, testes e build,
   incluindo as verificações próprias do toolkit, sem depender de credenciais reais.

7. Valide a inicialização da aplicação, a conexão ao PostgreSQL local, as migrações quando houver schema
   e a compilação e inicialização da imagem Docker. Não invente tabelas para demonstrar funcionamento.

8. Atualize a documentação canônica do projeto, conforme o toolkit, com os comandos e resultados reais,
   sem duplicar instruções. Mantenha as explicações e a documentação em português, preservando nomes
   oficiais, comandos e identificadores técnicos.

Use versões estáveis atuais e compatíveis, verificadas durante a execução. Reutilize instalações
existentes e implemente a menor solução completa.

Entregue a base configurada, o comando para iniciar, as verificações executadas, as pendências e a próxima
tarefa do MVP.
```

[Voltar ao guia](../../README.md)
