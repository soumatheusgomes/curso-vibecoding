# Preparando o ambiente: VS Code, Docker, GitHub e o prompt que instala tudo

Use esta aula para preparar um computador novo ou revisar um ambiente de desenvolvimento existente.

## Links da aula

Endereços oficiais para baixar ferramentas, consultar a instalação e criar ou acessar suas contas:

- [VS Code](https://code.visualstudio.com/): editor de código.
- [ChatGPT](https://chatgpt.com/): acesso ao ChatGPT.
- [Claude](https://claude.ai/): acesso ao Claude.
- [Docker Desktop](https://docs.docker.com/desktop/): instalação e requisitos do Docker Desktop.
- [GitHub](https://github.com/): conta para hospedar seus repositórios.

## Como usar

Copie o bloco completo abaixo e envie a um agente com acesso ao terminal do computador que será preparado. A
instalação das ferramentas locais pode ser feita pelo próprio agente; autenticações e exigências do sistema
podem depender da sua intervenção.

## Prompt

```
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão antes de executar esta tarefa.
Respeite as autorizações já concedidas e os limites abaixo, sem ampliar o escopo nem repetir perguntas respondidas.
Se a skill estiver indisponível, informe o impedimento e não simule seu uso.

Em um ambiente novo sem Superpowers, faça primeiro apenas o diagnóstico, instale os pré-requisitos mínimos
e habilite Superpowers pelos mecanismos oficiais. Assim que a skill estiver disponível, retome o Brainstorming
antes das demais alterações. Se houver incompatibilidade ou bloqueio, informe o que impede essa etapa.

# Instalar, configurar, atualizar e otimizar o ambiente de desenvolvimento

Prepare este computador para desenvolvimento, principalmente com Node.js, e para uso do VS Code, Codex e
Claude Code.

Este prompt deve funcionar em dois cenários:

- Ambiente novo, sem ferramentas: instalar e configurar toda a base obrigatória, incluindo plugins, skills,
  MCPs e hooks.
- Ambiente existente: inventariar, atualizar, corrigir, limpar duplicatas e melhorar as integrações.

Execute o trabalho. Não entregue apenas um tutorial ou recomendações.

Adapte comandos, caminhos e métodos ao sistema operacional, à arquitetura, ao shell e à data da execução.
Consulte a documentação oficial atual.

## 1. Autorização e regras

Estão autorizados:

- Instalação de todos os componentes da lista obrigatória.
- Atualização de todos os componentes globais de desenvolvimento existentes.
- Configuração e ativação dos plugins, skills, MCPs e hooks obrigatórios.
- Remoção de duplicatas confirmadas e resíduos dispensáveis.
- Correção do PATH, da inicialização do shell e das integrações.
- Execução de comandos e leitura ou alteração de arquivos fora do projeto quando necessárias à preparação do
  ambiente.

Preserve projetos, dependências locais, arquivos de trava de dependências, credenciais, sessões, históricos e
configurações personalizadas.

Faça backup antes de alterar configurações ou remover componentes com dados relevantes. Registre como
restaurar.

Não repita pedidos de autorização já concedida. Solicite minha intervenção somente para autenticação,
exigências do sistema, custos, novos extras ou migrações com impacto incompatível com a preservação do
ambiente.

Não publique conteúdo, envie mensagens, contrate serviços ou altere projetos como consequência da preparação
do ambiente.

O processo deve ser repetível: novas execuções devem verificar, atualizar e corrigir sem duplicar instalações
ou configurações.

## 2. Base obrigatória

Todos os itens abaixo devem ser instalados quando ausentes, atualizados quando necessário e configurados para
uso. Apenas verificar sua existência não atende ao objetivo.

### Editor

- VS Code, incluindo acesso ao terminal integrado e às ferramentas instaladas.
- Comando `code` disponível no terminal quando oficialmente suportado.

Preserve perfis, preferências, atalhos e extensões existentes do editor.

### Sistema e desenvolvimento

- Pré-requisitos necessários para certificados, download, extração e compilação.
- Git.
- GitHub CLI.
- Gerenciador de pacotes adequado ao sistema.
- Gerenciador de versões do Node.js, preferencialmente fnm quando compatível e adequado.
- Node.js LTS e npm.
- pnpm.
- ripgrep, fd e jq, ou equivalentes justificados quando houver incompatibilidade.

### Contêineres

- Docker, incluindo cliente e servidor funcionais.
- Docker Compose disponível pelo comando `docker compose`.
- Componentes necessários ao funcionamento, conforme o sistema operacional.

### Agentes

- Codex CLI.
- Claude Code CLI.

### Produtividade e extensões dos agentes

- RTK: instalação e integração para os comandos suportados.
- Ponytail: plugin ou skills, com intensidade `full` como padrão para tarefas de programação.
- Caveman: skills e comunicação concisa como padrão, preservando clareza e redação normal em código,
  documentação e commits.
- Superpowers: instalação das skills e configuração nos agentes compatíveis.
- Context7: instalação ou conexão do servidor MCP e configuração nos clientes compatíveis.
- Graphify: instalação e configuração do mecanismo oficialmente suportado.

Resolva a identidade e a origem corretas dessas ferramentas antes de instalar. Não instale um pacote apenas
porque possui nome semelhante.

Use os mecanismos oficiais de cada projeto e plataforma. Quando um componente não for suportado, registre a
incompatibilidade, continue os demais e apresente a alternativa adequada.

Plugins obrigatórios não são extras opcionais e não devem ser ignorados porque ainda não existem na máquina.

## 3. Diagnóstico e inventário

Antes de alterar o ambiente, identifique:

- Sistema operacional, versão, distribuição e arquitetura.
- Ambiente nativo, WSL, máquina virtual, contêiner ou remoto.
- Shell, terminal, PATH, arquivos de inicialização e privilégios.
- Gerenciadores de pacotes e ambientes de execução.
- Ferramentas globais por usuário, sistema e ambiente de execução.
- Plugins, skills, MCPs, hooks e extensões dos agentes e editores.
- Configurações globais e por projeto, incluindo sua precedência.
- Componentes ativos, desativados, duplicados, incompatíveis ou descontinuados.
- Requisitos dos projetos relevantes.

Registre nome, finalidade, versão ou revisão, caminho, origem, método de atualização e integrações de cada
componente.

Use os mecanismos de inventário de cada ecossistema. Não dependa apenas dos executáveis encontrados no PATH.

Diferencie duplicatas reais de links simbólicos, referências compartilhadas e instalações necessárias em
ambientes distintos.

Se houver um inventário ou manifesto do ambiente de origem, inclua seus componentes na reprodução do ambiente
novo. Sem esse inventário, instale toda a base obrigatória e informe que ferramentas não identificadas da
máquina anterior não podem ser reproduzidas automaticamente.

## 4. Instalação e atualização

Execute na ordem adequada às dependências:

1. Diagnóstico e backups.
2. Pré-requisitos e gerenciador de pacotes.
3. VS Code, Git, GitHub CLI e utilitários.
4. Gerenciador de versões, Node.js, npm e pnpm.
5. Codex CLI e Claude Code CLI.
6. Plugins, skills, MCPs e hooks obrigatórios.
7. Docker e Docker Compose.
8. Atualização dos demais componentes globais existentes.
9. Limpeza, validação e relatório.

Para cada componente:

- Consulte fontes oficiais atuais.
- Use uma versão estável compatível.
- Reaproveite instalações que já estejam adequadas.
- Preserve o método de instalação existente quando suportado.
- Evite instalar a mesma ferramenta por gerenciadores diferentes.
- Confirme a versão, o caminho e o executável efetivamente utilizado.

Atualize também os componentes globais de desenvolvimento existentes que não aparecem na lista obrigatória:
pacotes, CLIs, plugins, skills, MCPs locais, extensões e ferramentas utilizadas por hooks.

Preserve alterações locais em plugins ou skills personalizados. Não descarte trabalho do usuário para forçar
uma atualização.

Para serviços MCP remotos, verifique compatibilidade e conexão; não trate o serviço como um pacote local.

Atualizar um componente anteriormente desativado não autoriza ativá-lo. Essa restrição não se aplica aos
componentes obrigatórios que precisam ser configurados nesta preparação.

Não atualize dependências locais dos projetos nem aplicativos sem relação com desenvolvimento.

## 5. Shell, Node.js e projetos

Configure o PATH e a inicialização nos arquivos corretos do shell.

Garanta funcionamento em novas sessões, no terminal integrado do VS Code e nos terminais utilizados pelos
agentes.

Configure a versão LTS mais recente e compatível do Node.js como padrão fora dos projetos. Configure a seleção
automática de versão por projeto quando suportada.

Respeite `.node-version`, `.nvmrc`, `engines`, `packageManager` e os arquivos de trava de dependências.
Preserve versões específicas exigidas pelos projetos.

Identifique conflitos entre requisitos e explique a resolução.

Configure o pnpm pelo mecanismo oficialmente suportado. Preserve os gerenciadores escolhidos pelos projetos.

Não altere dependências, arquivos de trava ou versões declaradas como parte da preparação do ambiente.

Corrija permissões na causa, sem permissões indiscriminadas ou uso de administrador por padrão.

No Windows, diferencie ambiente nativo e WSL. Não misture executáveis e dependências entre eles.

## 6. Plugins, skills, MCPs e hooks

Instale e configure cada componente obrigatório nos agentes em que houver suporte oficial.

Verifique instalação, descoberta, carregamento e funcionamento. Use os formatos e caminhos documentados para
cada cliente.

Preserve instruções personalizadas e preferências existentes.

Identifique hooks duplicados, execução repetida de comandos e integrações concorrentes. Não duplique
instalações quando uma distribuição já incluir as mesmas skills.

Não suponha que a configuração no Codex também configure o Claude Code, ou vice-versa.

Configure as preferências:

- Ponytail: intensidade `full` para programação, preservando segurança, acessibilidade e requisitos
  explícitos.
- Caveman: respostas concisas em português; explicações completas quando solicitadas; código, documentação e
  commits com redação normal.
- Context7: documentação atual de bibliotecas, APIs e ferramentas quando pertinente; nunca enviar segredos nas
  consultas.
- RTK: integração com os mecanismos de execução suportados, evitando aplicação dupla de wrappers ou hooks.
- Superpowers: skills disponíveis e carregadas nos clientes compatíveis.
- Graphify: ferramenta e integração prontas para uso pelo mecanismo suportado.

Para trabalhos com LLM de Graphify e Caveman, preserve o uso de Codex nativo, do modelo da sessão e da
autenticação ChatGPT. Passe o modelo explicitamente quando houver delegação suportada. Não troque
silenciosamente para outro provedor, modelo mais barato, cobrança por API ou proxy.

As instruções deste prompt e minhas preferências explícitas prevalecem sobre fluxos de skills que repetiriam
autorizações já concedidas.

## 7. Codex, Claude Code e permissões

Garanta o funcionamento de ambas as CLIs em terminais novos.

Preserve modelos, provedores, sessões e configurações existentes. Em ambiente novo, use os fluxos oficiais de
autenticação.

Verifique autenticação sem revelar credenciais. Abra o fluxo de login quando necessário e informe exatamente
qual intervenção é necessária da minha parte.

Não habilite cobrança por API ou troque a modalidade de autenticação sem minha escolha.

### Codex

Configure acesso completo, rede e ausência de aprovações rotineiras pelos mecanismos oficiais suportados, com
persistência quando disponível.

Diferencie permissões da CLI, do aplicativo para computador, do sistema operacional e da organização.
Verifique cada contexto utilizado.

Não presuma que mudar um arquivo altera automaticamente as permissões da sessão atual. Confirme em nova
sessão.

### Sistema operacional

Verifique as permissões necessárias às funcionalidades utilizadas. Confirme a identidade dos aplicativos e
componentes.

Abra as telas pertinentes quando possível. Oriente sobre elevação de privilégios, senha no sistema,
autenticação biométrica ou reinicialização.

Nunca solicite senhas, tokens ou códigos de autenticação no chat.

Não contorne proteções ou políticas administrativas. Se uma política impedir a configuração, registre a
restrição e continue as etapas independentes.

## 8. Docker e Docker Compose

Instale e configure uma solução Docker funcional, incluindo servidor, cliente e Compose.

No macOS e no Windows, utilize Docker Desktop quando adequado e configure os pré-requisitos oficiais.

No Linux, utilize Docker Engine e o plugin Docker Compose compatíveis com a distribuição.

Verifique arquitetura, virtualização, requisitos do sistema e licença. Se houver custo aplicável, peça minha
escolha antes de contratar.

Reutilize uma instalação funcional e evite servidores ou serviços Docker concorrentes.

Configure o contexto correto, o acesso do usuário e a inicialização persistente quando suportada.

Preserve contêineres, imagens, volumes, redes e configurações existentes.

Informe intervenções necessárias e reinicializações.

Docker só está pronto quando o cliente consegue acessar o servidor e executar contêineres e projetos Compose.

## 9. Limpeza e remoção de duplicatas

Identifique qual instalação está em uso antes de remover outra. Verifique referências no PATH, shell, agentes,
editores e hooks.

Remova duplicatas confirmadas pelo gerenciador responsável. Preserve ou consolide as configurações
necessárias.

Elimine entradas repetidas, links quebrados e referências obsoletas. Remova resíduos comprovadamente
dispensáveis.

Limpe caches pelos mecanismos oficiais quando houver benefício concreto.

Não remova ferramentas apenas por serem antigas ou semelhantes. Não trate versões exigidas por projetos como
duplicatas.

Preserve arquivos de finalidade desconhecida. Não execute limpeza indiscriminada de volumes ou outros dados do
Docker.

Confirme o funcionamento após cada remoção.

Se houver dúvida sobre dependência ou impacto, preserve o componente e registre a pendência.

## 10. Melhorias adicionais

Depois da base completa, avalie melhorias relevantes para:

- Terminal e navegação.
- Git e colaboração.
- Documentação e contexto dos agentes.
- Automação de navegador.
- Testes, formatação, análise de código e acessibilidade.
- Contêineres e ambientes reproduzíveis.
- Diagnóstico, desempenho e consumo de recursos.

Considere ferramentas atuais e alternativas melhores, sem instalar por novidade ou popularidade.

Para cada recomendação, informe o problema resolvido, benefício, compatibilidade, manutenção, sobreposição,
custos e escopo de instalação.

Priorize poucas melhorias de alto impacto. Prefira recursos nativos ou soluções existentes quando suficientes.

Instale novos extras após minha escolha. A base obrigatória e a atualização dos componentes existentes não
dependem dessa escolha.

## 11. Validação

Teste em nova sessão, sem depender de variáveis temporárias:

- Abertura do VS Code, terminal integrado e comando `code`, quando suportado.
- Git, GitHub CLI e gerenciadores utilizados.
- Node.js LTS padrão, npm e pnpm.
- Acesso HTTPS ao registro de pacotes configurado.
- Troca de versão por projeto e retorno ao padrão.
- Inicialização e autenticação de Codex e Claude Code.
- Instalação e funcionamento de RTK.
- Descoberta e carregamento de Ponytail, Caveman e Superpowers.
- Conexão do Context7 e dos demais MCPs habilitados.
- Funcionamento do Graphify.
- Execução dos hooks sem duplicação.
- Persistência das configurações e permissões verificáveis.
- Ausência de conflitos relevantes e referências quebradas.

Para Docker:

1. Execute `docker version` e confirme cliente e servidor.
2. Execute `docker info`.
3. Execute `docker compose version`.
4. Execute `docker run --rm hello-world`.
5. Crie um projeto Compose mínimo em um diretório temporário.
6. Execute `docker compose up -d` e confirme o serviço funcionando.
7. Encerre com `docker compose down` e remova apenas os recursos criados pelo teste.

Use diretórios temporários para testes. Preserve projetos existentes.

Execute diagnósticos oficiais pertinentes, como `brew doctor` quando aplicável. Investigue avisos relevantes.

Não execute chamadas pagas apenas para validar sem autorização.

## 12. Entrega e reprodução

Entregue um relatório em Markdown com:

- Ambiente identificado.
- Lista de verificação de toda a base obrigatória.
- Componentes instalados, atualizados ou reaproveitados.
- Versões anteriores e finais quando aplicável.
- Origens, caminhos e métodos de instalação.
- Plugins, skills, MCPs e hooks configurados.
- Duplicatas removidas e limpeza realizada.
- Configurações alteradas, backups e instruções de restauração.
- Testes e resultados.
- Pendências, incompatibilidades e bloqueios.
- Melhorias adicionais recomendadas.

Gere também um manifesto reutilizável do ambiente final, com componentes, fontes, versões ou revisões, escopos
e configurações necessárias. Não inclua segredos ou dados privados.

Esse manifesto deve permitir reproduzir o ambiente em outra máquina, adaptando caminhos e requisitos ao
sistema de destino.

Não considere o trabalho concluído apenas porque as instalações terminaram. Confirme a configuração e o
funcionamento de cada componente obrigatório e deixe explícito o que ainda depende de mim.
```

[Voltar ao guia](../../README.md)
