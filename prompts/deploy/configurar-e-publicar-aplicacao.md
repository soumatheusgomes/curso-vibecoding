# Configurar o deploy: aplicação, banco, domínio e HTTPS

Copie e cole o prompt no agente com a pasta da aplicação aberta. Não há campos obrigatórios para preencher.
O agente descobre o ambiente, configura produção e deixa as próximas publicações automáticas pela `main`.

## Como usar

1. Abra o projeto no agente e cole o bloco completo.
2. Acompanhe o progresso enquanto ele inspeciona o projeto e configura os serviços.
3. Quando houver autenticação ou uma decisão indispensável, conclua a etapa indicada e avise para continuar.

O padrão usa DigitalOcean App Platform, Supabase e Cloudflare. Se preferir outros provedores, diga isso
na conversa; não é necessário editar o prompt. Configurações existentes compatíveis devem ser reaproveitadas.

Depois do setup, cada push na `main` inicia uma nova implantação. O agente deve deixar essa integração
ativa na hospedagem, registrada no repositório e verificada, sem exigir nova configuração manual a cada entrega.

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão com as informações do projeto e os padrões abaixo.
Não abra um questionário nem pause para aprovar um plano genérico: a execução deste setup já está autorizada.
Se a skill estiver indisponível, informe o impedimento sem simular seu uso.

PADRÕES JÁ DEFINIDOS
Ambiente: produção.
Hospedagem: DigitalOcean App Platform.
Dados: Supabase, apenas para os serviços necessários ao projeto.
DNS: Cloudflare, sem proxy por padrão.
Branch de produção: main.
Publicação: automática a cada push na main.

Configure e conclua o deploy da aplicação, com dados conectados, endereço público e HTTPS válido.
Deixe o repositório e a hospedagem preparados para atualizar produção nos próximos pushes na main.
Execute o trabalho, sem exigir preenchimento prévio ou entregar somente um tutorial.

## 1. Descobrir e avançar sem perguntas desnecessárias

Leia as instruções, a documentação, o código e as configurações relevantes. Descubra runtime, comandos,
porta, diretório, banco, variáveis, domínio, remoto Git e recursos existentes antes de perguntar.
Não pergunte se o ambiente é produção, qual é a branch ou qual framework usar: os padrões e o projeto
orientam essas decisões. Não peça ao usuário informações que ferramentas e arquivos conseguem revelar.

Use os provedores padrão em um setup novo; respeite escolhas explícitas e recursos compatíveis já usados.
Não migre uma produção funcional de provedor apenas para adequá-la ao exemplo. Escolha região e tamanho
inicial compatíveis com a aplicação e os dados, evitando recursos adicionais sem necessidade.

Faça um plano curto com as decisões descobertas e prossiga nas etapas autorizadas. Consulte documentação
oficial atual e Context7 quando necessário, sem enviar segredos ou dados internos nas consultas.
Preserve alterações do usuário e diferencie configurações locais de desenvolvimento das de produção.

## 2. Pedir intervenção apenas no ponto necessário

Use conectores, APIs e CLIs oficiais quando suficientes, e navegador para login e operações de painel.
Agent Browser ou outra ferramenta disponível pode conduzir a navegação. Instale somente ferramentas
oficiais indispensáveis e ausentes. Não substitua App Platform por Droplets silenciosamente.

Quando precisar de login, MFA, CAPTCHA ou autorização de acesso, abra a tela oficial, diga qual ação
preciso concluir e aguarde minha confirmação. Verifique a sessão e a conta antes de continuar do ponto
pendente. Avance nas etapas independentes enquanto aguarda; tempo decorrido não comprova autenticação.

Se faltar domínio, pergunte somente na etapa de domínio e continue antes pela URL provisória.
Se houver contas ou recursos indistinguíveis, peça a escolha concreta no momento de usá-los.
Para criar recursos cobrados, apresente a opção mínima compatível e seu custo atual para aprovação,
a menos que essa cobrança já esteja autorizada. Não abra um formulário genérico de orçamento.
Mudanças destrutivas, migração de dados ou troca de um serviço em uso exigem decisão específica antes
da operação. Não compre ou transfira domínios, contrate extras ou contorne políticas de acesso.

Faça perguntas curtas, uma decisão por vez, explicando a opção recomendada. Não repita autorizações.
Nunca solicite senhas, tokens, códigos ou cartão no chat. Use os mecanismos seguros dos provedores;
não exponha credenciais em Git, logs, capturas, argumentos ou histórico do terminal.
Mantenha um registro sem segredos do progresso e dos recursos para retomar sem duplicar instalações.

## 3. Preparar os dados e a aplicação

Reutilize recursos de produção apropriados; não conecte produção ao banco de desenvolvimento por engano.
No Supabase, preserve o ORM e escolha conexão, pooling, TLS e limites conforme rede e driver. Confira
separadamente a conexão de migrações. Não desative validação de certificado para resolver conectividade.

Aplique somente o schema real necessário. Em banco com dados, preserve backup e restauração antes
de mudanças e siga a transição autorizada. Não use reset ou recriação para simplificar o deploy.
Configure migrações versionadas em uma etapa controlada de publicação, quando necessárias, evitando
execução concorrente em cada instância e mudanças destrutivas automáticas nos próximos pushes.

Configure variáveis de compilação e execução no escopo correto. Segredos ficam no mecanismo seguro
da hospedagem, fora da imagem e do navegador. Versione apenas nomes, exemplos fictícios e referências
adequadas. Diferencie chaves públicas de credenciais privilegiadas; preserve autorização e RLS aplicáveis.
Configure URLs de autenticação e serviços adicionais somente quando utilizados pelo projeto.

Ajuste build, inicialização, porta e verificações de saúde. Execute testes e verificações pertinentes
antes de publicar, preservando dados reais e integrações existentes. Não atualize toda a aplicação
nem crie bibliotecas, banco duplicado ou funcionalidades para demonstrar o deploy.

## 4. Configurar o deploy automático da main durante este setup

Identifique o repositório e seu proprietário pelo remoto Git. Conecte o repositório correto à hospedagem,
concluindo a autorização da integração com minha intervenção quando necessária. Use a main como origem;
se ela ou o remoto não existirem, trate esse bloqueio concreto sem publicar em outro destino por suposição.

Escolha uma única automação responsável pelo deploy. O padrão é o gatilho nativo; se já existir workflow
de publicação adequado, reutilize-o sem ativar um segundo gatilho. Preserve verificações já exigidas
pelo projeto: um deploy nativo não deve ser tratado como se aguardasse outro workflow.

No DigitalOcean App Platform, quando usar o gatilho nativo, configure a origem Git e habilite o deploy
automático nos componentes pertinentes. Para origem GitHub, confira no app spec o repositório real em github.repo,
github.branch: main e github.deploy_on_push: true, conforme o formato suportado na execução.
Aplique a configuração no App Platform e confirme que está ativa. Não basta salvar um arquivo no Git.

Crie ou atualize a configuração versionada no projeto, preferindo .do/app.yaml quando adequada, ou
reutilizando o arquivo canônico existente. Não deixe campos pendentes para o usuário preencher depois.
Preserve componentes e segredos ao aplicar atualizações; uma operação pode substituir a configuração
completa. Mantenha valores de credenciais no provedor, sem copiá-los para o arquivo versionado.

Documente como reaplicar alterações de infraestrutura: não presuma que versionar o app spec faz o
provedor aplicar automaticamente toda mudança nele. Diferencie isso do gatilho de publicação do código.
Em outro provedor, configure e verifique a integração equivalente para pushes na main.

Use CI adicional somente se necessário. Quando um workflow controlar a publicação, mantenha o deploy
nativo desativado e verifique o gatilho equivalente a cada push na main.

Faça commit e push somente dos ajustes deste setup na main do remoto identificado, sem incluir alterações
nem commits de outras tarefas e respeitando suas proteções. Não force push. Use esse push real para verificar o gatilho,
acompanhe a implantação e relacione o commit enviado com a versão publicada. Não crie commit vazio
ou use um deploy manual como prova de que o gatilho automático funcionou.

Se o teste do gatilho não puder ser observado, registre essa pendência. Não declare a automação validada
apenas porque uma opção está marcada no painel. Corrija problemas com evidências, sem recriar recursos
por tentativa, e valide a aplicação na URL provisória antes de alterar um domínio em uso.

## 5. Configurar domínio e HTTPS

Descubra o domínio nas configurações e nos serviços. Se faltar uma escolha, peça o endereço desejado
nesta etapa, mantendo a publicação provisória. Não invente nem compre um domínio para evitar a pergunta.
Separe registrador e DNS autoritativo; usar Cloudflare para DNS não exige transferir o registro.

Preserve o estado anterior e os registros de e-mail, outros sites e verificações, incluindo MX, TXT,
SPF, DKIM, DMARC e CAA relevantes. Troca de delegação e mudanças com impacto em serviços existentes
precisam de uma decisão específica. Confira DNSSEC, registros DS e compatibilidade antes de alterar
proteções. Não enfraqueça a configuração para contornar um erro.

Use os valores reais fornecidos pelos serviços para os apontamentos. Com Cloudflare apenas como DNS,
siga o fluxo de domínio e certificado do App Platform. Se proxy ou CDN externo forem necessários,
confira o roteiro próprio; origem, Host e responsabilidade pelos certificados podem mudar.
Garanta HTTPS válido, sem desativar verificações TLS nem criar ciclos de redirecionamento.
Acompanhe DNS e certificado sem recriar recursos enquanto aguarda propagação.

## 6. Validar e deixar as próximas entregas prontas

Confirme aplicação saudável, versão e commit corretos, conexão aos dados, domínio e HTTPS. Teste os
fluxos essenciais com dados de teste de baixo impacto, sem enviar mensagens reais, cobrar pagamentos,
executar carga ou excluir dados existentes. Verifique erros e exposição de segredos sem divulgar valores.

Se houver falha, preserve ou recupere o serviço anterior conforme o caso. Retornar o código não restaura
schema, dados ou DNS automaticamente. Informe bloqueios e recursos que continuam ativos ou cobrando.
Não declare sucesso para uma etapa não verificada.

Atualize a documentação canônica de deploy e as instruções lidas pelos agentes no projeto. Registre:
- Produção é publicada pela main, com provedor, recurso e origem corretos.
- Quais arquivos controlam o deploy e como aplicar mudanças de configuração.
- Como preparar e publicar novas alterações: verificações, commit e push na main, sem novo setup manual.
- Como acompanhar falhas e retornar a uma versão anterior, respeitando dados e migrações.

Entregue URL pública, estado do domínio/HTTPS, arquivos configurados, commit e implantação associados,
prova do deploy automático, custos aprovados e pendências. Se o domínio próprio ainda depender de mim,
explique isso sem tratar a URL provisória como domínio configurado.
```

## Referências oficiais

- [Origem Git e deploy automático no App Platform](https://docs.digitalocean.com/products/app-platform/how-to/manage-source-repo/).
- [Configuração do App Platform](https://docs.digitalocean.com/products/app-platform/reference/app-spec/).
- [Atualização da configuração no App Platform](https://docs.digitalocean.com/products/app-platform/how-to/update-app-spec/).
- [Domínios no App Platform](https://docs.digitalocean.com/products/app-platform/how-to/manage-domains/).
- [CDN externo no App Platform](https://docs.digitalocean.com/products/app-platform/how-to/configure-external-cdn/).
- [Variáveis de ambiente no App Platform](https://docs.digitalocean.com/products/app-platform/how-to/use-environment-variables/).
- [Conexões PostgreSQL no Supabase](https://supabase.com/docs/guides/database/connecting-to-postgres).
- [Chaves de acesso do Supabase](https://supabase.com/docs/guides/getting-started/api-keys).
- [Delegação de DNS no Cloudflare](https://developers.cloudflare.com/dns/zone-setups/full-setup/setup/).

[Voltar ao guia](../../README.md)
