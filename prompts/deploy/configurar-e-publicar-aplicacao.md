# Configurar o deploy: aplicação, banco, domínio e HTTPS

Use para colocar uma aplicação no ar, configurando os serviços necessários pelo computador e pelo
navegador. O agente executa o trabalho e pede sua intervenção nos logins, sem solicitar senhas no chat.

O exemplo usa DigitalOcean App Platform para a aplicação, Supabase para os dados e Cloudflare para DNS.
Você pode trocar os três provedores. O agente deve verificar a compatibilidade das escolhas com o projeto.

## Como usar

1. Abra a pasta da aplicação no agente. Tenha acesso ao repositório e às contas dos serviços escolhidos.
2. Revise os três provedores e preencha domínio, ambiente, recursos existentes, orçamento e restrições.
3. Cole o bloco completo. Ele já começa pelo Brainstorming para alinhar o plano, os custos e as mudanças.
4. Quando o agente indicar um login ou autorização de conta, conclua essa etapa na tela oficial e avise
   que terminou. O agente deve conferir o acesso e continuar do ponto em que parou.
5. Confira a aplicação publicada, o domínio, o HTTPS e as verificações do relatório final.

## O que você precisa adaptar

| Campo | O que preencher ou alterar |
| --- | --- |
| Hospedagem | O exemplo usa DigitalOcean App Platform. Troque pelo serviço que executará a aplicação, verificando suporte à tecnologia do projeto. |
| Dados | O exemplo usa Supabase. Troque pelo banco ou serviço de dados escolhido; a mudança precisa ser compatível com a aplicação. |
| DNS | O exemplo usa Cloudflare. Pode ser GoDaddy, Hostinger ou outro serviço que gerencie os registros do domínio. |
| Domínio | Endereço desejado, como `app.meudominio.com`. Se ainda não tiver domínio próprio, informe `usar URL provisória`. |
| Ambiente | Homologação ou produção. Informe também se já existe uma aplicação atendendo nesse endereço. |
| Recursos existentes | Contas, organizações, projetos, aplicações e bancos que devem ser reutilizados. Se não souber, escreva `identificar comigo`. Sem credenciais. |
| Orçamento | Limite, moeda e período, ou `somente recursos sem cobrança`. Se ainda não decidiu, escreva `propor custos para aprovação`. |
| Restrições | O que preservar e limites adicionais. Exemplo: manter o e-mail do domínio e não migrar os dados existentes nesta etapa. |

O registrador mantém o registro do domínio; o provedor de DNS gerencia seus apontamentos. Eles podem
ser empresas diferentes. Usar Cloudflare para DNS não exige transferir o registro do domínio.

Trocar um nome no prompt não garante compatibilidade: uma hospedagem estática pode não executar seu
servidor, e outro banco pode exigir mudanças na aplicação. Essas diferenças devem aparecer no planejamento.

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão antes de executar esta tarefa.
Respeite as autorizações já concedidas e os limites abaixo, sem ampliar o escopo nem repetir perguntas respondidas.
Se a skill estiver indisponível, informe o impedimento e não simule seu uso.

CONFIGURAÇÃO DESEJADA
Hospedagem da aplicação: DigitalOcean App Platform
Serviço de dados: Supabase
Provedor de DNS: Cloudflare
Domínio: [DOMÍNIO OU SUBDOMÍNIO, OU USAR URL PROVISÓRIA]
Ambiente: [HOMOLOGAÇÃO OU PRODUÇÃO, INFORMANDO SE JÁ HÁ UMA APLICAÇÃO NO ENDEREÇO]
Recursos existentes: [CONTAS E RECURSOS A REUTILIZAR OU IDENTIFICAR COMIGO, SEM CREDENCIAIS]
Orçamento: [LIMITE, MOEDA E PERÍODO, SOMENTE RECURSOS SEM COBRANÇA OU PROPOR CUSTOS PARA APROVAÇÃO]
Restrições: [DADOS, SERVIÇOS E CONFIGURAÇÕES A PRESERVAR OU NENHUMA RESTRIÇÃO ADICIONAL]

Configure e conclua o deploy deste projeto, com aplicação pública funcionando, dados conectados e
domínio com HTTPS válido. Se escolhi URL provisória, ela será o endereço público desta entrega.
Execute o trabalho; não entregue somente um tutorial ou uma lista de recomendações.

Adapte o procedimento aos provedores informados, ao projeto, ao sistema operacional, às ferramentas
disponíveis e à documentação oficial atual. Não copie valores, telas ou comandos antigos sem conferir.

## 1. Diagnosticar o projeto e os destinos

Leia as instruções aplicáveis, a documentação, os arquivos de dependências, a configuração de ambiente
e os comandos de testes, build e execução. Preserve alterações existentes do usuário.

Identifique runtime, framework, gerenciador, versão compatível, porta, diretório da aplicação e método
de implantação. Verifique uso de banco, arquivos persistentes, autenticação, tarefas em segundo plano
e integrações apenas quando existirem. Não suponha que arquivos no disco local persistirão na hospedagem.

Confira o repositório, o remoto, a branch de publicação e o commit que será implantado. Não inclua
alterações ou commits de outras tarefas só porque estão no diretório ou na branch atual.

Mapeie contas, organizações, projetos, regiões e recursos existentes. Confirme os destinos pelas
informações disponíveis e esclareça seleções ambíguas antes de criar ou alterar recursos.
Separe hospedagem, banco, DNS e registrador do domínio; descubra quais servidores DNS são autoritativos.

Avalie a compatibilidade dos provedores escolhidos com o código e os dados existentes. Se a escolha
exigir trocar ORM, reescrever integração ou migrar dados, apresente essa transição antes de executá-la.
Não substitua um serviço por outro produto do mesmo fornecedor silenciosamente.

## 2. Alinhar o plano, a autorização e os custos

Apresente um plano curto com recursos a reutilizar ou criar, região, publicação, variáveis, banco,
domínio, validações e retorno ao estado anterior. Compare com a infraestrutura existente.

Consulte preços, limites e condições atuais em fontes oficiais. Informe custos recorrentes e eventuais
de aplicação, dados, armazenamento, tráfego e recursos adicionais pertinentes, com data e premissas.
Não trate limite de orçamento ou alerta de gasto como garantia de interrupção automática da cobrança.

Obtenha minha aprovação do plano e dos custos antes de criar recursos cobrados, contratar adicionais,
migrar dados ou substituir uma aplicação e seus apontamentos em uso. Se o orçamento ainda estiver
indefinido, não presuma autorização para cobrança. Não compre nem transfira domínios por conta própria.

Após a aprovação, execute as operações previstas sem repetir as mesmas confirmações. Estão autorizadas
as configurações locais necessárias, o uso das ferramentas e do navegador, a criação ou atualização dos
recursos acordados, a publicação e os ajustes de DNS especificamente aprovados.

Quando necessários ao deploy aprovado, prepare e publique somente os ajustes relacionados à tarefa
no repositório e na branch confirmados. Não force push nem contorne proteção ou políticas de acesso.

Instale apenas ferramentas oficiais indispensáveis e ausentes, de forma compatível com o computador.
Não faça uma atualização geral do ambiente. Não habilite recursos pagos, replicação, escalonamento
ou serviços adicionais fora do plano. Se surgir custo ou impacto novo, esclareça somente essa diferença.

## 3. Operar o computador e retomar após autenticação

Use conectores, APIs e CLIs oficiais quando disponíveis e suficientes. Use o navegador para painéis,
autenticação e operações sem suporte adequado nas ferramentas. Reaproveite integrações existentes.
Agent Browser ou outra ferramenta de navegação disponível pode executar o fluxo, conforme seu suporte.

Não confunda uma ferramenta que cria Droplets com suporte ao App Platform: use o produto escolhido.
Se faltar acesso ao terminal ou ao navegador necessário, informe a capacidade ausente sem simular ações.

Mantenha um registro curto do progresso, dos identificadores dos recursos e da próxima etapa, sem
segredos. Após uma interrupção, confira o estado real antes de repetir operações; não crie recursos
duplicados porque uma tela, comando ou sessão demorou a responder.

Quando houver login, MFA, CAPTCHA, consentimento de acesso ou outra ação pessoal:
1. Abra a página oficial pertinente, quando possível, e informe o serviço, a conta e a ação necessária.
2. Solicite que eu conclua a autenticação diretamente na interface oficial, sem enviar credenciais no chat.
3. Aguarde minha confirmação e observe novamente a sessão, a conta e as permissões disponíveis.
4. Continue do ponto pendente, preservando as etapas concluídas. Avance em etapas independentes enquanto aguarda.

Tempo decorrido não comprova autenticação nem aprovação. Não contorne desafios, políticas ou permissões.
Não solicite cartão, senha, token ou código no chat. Minimize os acessos e escopos de autorização.
Armazene credenciais apenas pelos mecanismos seguros do cliente ou provedor, sem valores em logs,
capturas, argumentos expostos, histórico do shell ou arquivos versionados.

## 4. Preparar os dados e as variáveis

Reutilize ou crie o recurso de dados aprovado. No exemplo, use o PostgreSQL do Supabase; não crie outro
banco gerenciado na hospedagem para duplicar a mesma função. Configure apenas os serviços necessários.

Escolha a conexão adequada à rede e ao processo: conexão direta ou pooler conforme suporte, duração
das conexões e necessidades do driver. No Supabase, confira IPv4 e IPv6, modos de pooling, limites,
TLS e compatibilidade de sessões, transações e prepared statements. Verifique separadamente a conexão
adequada para migrações. Não desative validação de certificado para contornar falhas de conexão.

Preserve o ORM e as migrações existentes. Em banco novo, aplique apenas o schema real necessário,
após conferir o destino e os comandos. Não invente tabelas de demonstração.
Em banco com dados, faça backup e verifique a possibilidade de restauração antes de mudanças; siga
somente a transição aprovada. Não use reset, recriação ou sincronização destrutiva por conveniência.

Mapeie variáveis necessárias à aplicação, à compilação, à execução e às migrações. Configure segredos
no mecanismo apropriado da hospedagem; mantenha valores fora do Git, da imagem e do código do navegador.
Atualize exemplos de ambiente somente com nomes, descrições e valores fictícios.

Diferencie chaves destinadas ao cliente de credenciais privilegiadas. No Supabase, siga a classificação
atual de chaves públicas e secretas; não exponha credenciais administrativas ou de conexão ao banco.
Se a aplicação acessar dados diretamente pelo cliente, confira políticas de acesso e RLS aplicáveis.
Uma chave pública não substitui autorização de usuário; uma conexão privilegiada também exige controles.

Configure autenticação, URLs de retorno, armazenamento e outros serviços apenas se usados pelo projeto.
Restrinja os endereços autorizados aos necessários e preserve integrações existentes.
Documente limites de disponibilidade, backup e recuperação do plano escolhido, sem contratar adicionais
para resolver pendências sem minha escolha.

## 5. Publicar a aplicação na hospedagem

Prepare somente os ajustes de deploy necessários. Execute as verificações pertinentes do projeto,
incluindo testes e build quando aplicáveis, e corrija falhas introduzidas pela configuração.

No DigitalOcean App Platform, use a aplicação, o projeto e a região aprovados. Configure o repositório
ou imagem, a branch ou versão, o diretório, o método de build, a inicialização, a porta e as verificações
de saúde conforme o projeto e a documentação atual. Em outro provedor, use os mecanismos equivalentes.

Configure o tamanho e a quantidade de recursos aprovados, variáveis por escopo e a política de atualização
automática acordada. Evite duas automações concorrentes implantando a mesma aplicação.
Reaproveite configurações declarativas existentes; quando útil, versione uma configuração reproduzível
suportada pelo provedor, sem segredos ou duplicação de definições.
Ao atualizar por API ou configuração declarativa, confira se a operação altera campos ou substitui
a configuração completa. Preserve componentes e definições existentes fora do escopo aprovado.

Acompanhe a implantação e analise logs sem expor valores sensíveis. Corrija configuração de build,
rede, inicialização e conexão com base em evidências, sem recriar recursos por tentativa.

Valide a URL provisória antes de encaminhar um domínio que já recebe tráfego: resposta da aplicação,
rotas relevantes, recursos estáticos, HTTPS e conexão ao serviço de dados pelo caminho real do servidor.

## 6. Configurar domínio e HTTPS

Se escolhi URL provisória, preserve sua configuração e registre que não foi configurado domínio próprio.
Caso contrário, confirme a posse e o acesso aos serviços responsáveis pelo domínio informado.

Registre o estado anterior dos apontamentos necessários antes de alterá-los. Preserve e-mail, outros
sites, subdomínios e verificações, incluindo MX, TXT, SPF, DKIM, DMARC, CAA e registros relevantes.
Não trate a importação automática de uma zona como garantia de que todos os registros foram preservados.

Use o DNS autoritativo correto. Se for necessário mudar a delegação, inclua essa mudança no plano
aprovado, com inventário da zona e retorno. Não transfira o registro do domínio para conseguir editar DNS.
Verifique DNSSEC, registros DS e compatibilidade dos serviços antes de mudar a delegação ou a proteção;
não remova proteções por tentativa. Siga o procedimento oficial pertinente e valide a cadeia resultante.
Se um provedor não suportar a proteção ou o modelo atual, apresente a incompatibilidade antes de
mudar a solução; não enfraqueça a configuração sem uma decisão explícita.

Configure apenas os nomes e registros necessários, usando os valores efetivamente fornecidos pelos
serviços. Trate domínio raiz, subdomínio e redirecionamento conforme o caso; não invente IPs ou CNAMEs.

No exemplo, Cloudflare é usado como DNS, sem ativar seu proxy por padrão. Configure o domínio e o
certificado no App Platform conforme o fluxo oficial para DNS externo.
Se proxy ou CDN externo fizer parte do plano, siga o roteiro atual específico: destino de origem,
Host, validação de domínio e responsabilidade pelo certificado podem ser diferentes. Não combine
automaticamente o fluxo de domínio direto do App Platform com o de CDN externo.

Garanta HTTPS válido e configuração coerente entre as camadas. Não use modos inseguros ou desative
verificação TLS para fazer a conexão parecer funcional. Configure redirecionamentos e URLs canônicas
apenas quando necessários ao projeto, evitando ciclos e preservando caminhos relevantes.

Acompanhe DNS e emissão do certificado com consultas e verificações limitadas, registrando o estado.
Não recrie a aplicação nem sobrescreva registros repetidamente enquanto aguarda propagação.
Se algo ainda estiver pendente, declare a etapa e o critério que falta confirmar.

## 7. Validar o deploy completo

Verifique a implantação e a versão realmente ativas, a saúde dos componentes, o domínio e o certificado.
Teste os fluxos essenciais pelo endereço público escolhido, incluindo conexão com dados e autenticação
quando existentes. Confira erros de navegador e servidor sem divulgar conteúdo privado.

Use operações de baixo impacto e dados de teste autorizados, isolados dos dados reais. Não envie
mensagens, faça pagamentos, execute carga ou apague registros existentes como teste de publicação.
Limpe somente recursos descartáveis criados pelos testes, sem remover serviços ou dados da aplicação.

Confira o que o navegador recebe: segredos de servidor não podem aparecer no código público.
Valide os limites de acesso relevantes sem tratar uma simples resposta HTTP como prova de todos os fluxos.

Em domínio com serviço anterior, confirme também a preservação dos registros e serviços que não deveriam
mudar. Registre limitações de verificação, sem fingir que testou e-mail ou integrações que não acionou.

Se houver falha, siga o plano de recuperação antes de novas mudanças incompatíveis. Retornar a versão
da aplicação não restaura automaticamente schema, dados gravados ou DNS; trate cada parte afetada.

## 8. Documentar e entregar

Atualize a documentação canônica com o procedimento real de publicação, recursos e ambientes,
branch e versão de origem, nomes das variáveis, locais de configuração, verificações e recuperação.
Registre como repetir o deploy e retomar etapas pendentes, sem incluir segredos nem dados privados.

Entregue um resumo com:
- URL pública, domínio e resultado observado do HTTPS.
- Provedores, recursos e versão efetivamente utilizados.
- Configurações realizadas e recursos reaproveitados ou criados.
- Custos aprovados, limites relevantes e possíveis cobranças variáveis.
- Testes executados, resultados e limites da validação.
- Alterações de DNS e recuperação correspondente.
- Pendências, bloqueios, próxima ação e intervenções ainda necessárias da minha parte.

Só declare deploy concluído quando os critérios combinados estiverem comprovados. Um login, um build
verde, uma tela de criação ou um registro DNS salvo não bastam para afirmar que a aplicação está no ar.
```

## Referências oficiais

- [Domínios no DigitalOcean App Platform](https://docs.digitalocean.com/products/app-platform/how-to/manage-domains/).
- [CDN externo no App Platform](https://docs.digitalocean.com/products/app-platform/how-to/configure-external-cdn/).
- [Variáveis de ambiente no App Platform](https://docs.digitalocean.com/products/app-platform/how-to/use-environment-variables/).
- [Conexões PostgreSQL no Supabase](https://supabase.com/docs/guides/database/connecting-to-postgres).
- [Chaves de acesso do Supabase](https://supabase.com/docs/guides/getting-started/api-keys).
- [Delegação de DNS no Cloudflare](https://developers.cloudflare.com/dns/zone-setups/full-setup/setup/).

[Voltar ao guia](../../README.md)
