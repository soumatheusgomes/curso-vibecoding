# Plano de implementação: oito guias de prompts

> Execução na sessão atual com revisão independente ao final, conforme o escopo aprovado.

**Objetivo:** escrever e publicar oito guias completos, úteis e distintos.
**Estrutura:** um arquivo por tarefa, seguindo os guias existentes, com índice no README.md.
**Tecnologia:** Markdown e Git; sem novas dependências ou código de aplicação.
**Especificação:** [Escopo aprovado](../specs/2026-11-06-oito-guias-de-prompts-design.md).

## Restrições gerais

- Conteúdo em português, mantendo nomes oficiais e identificadores técnicos.
- Oito prompts novos; aulas anteriores preservadas.
- Blocos independentes, sem exigir roteiros externos.
- Instruções de uso, campos com exemplos e limites claros em todos os arquivos.
- Publicar somente após revisão e validação dos documentos.

## Pontos da revisão

- Um aluno copia apenas o bloco: contexto, campos e limites continuam completos.
- Ferramenta ou aplicação indisponível: registrar bloqueio sem inventar resultados.
- Repositório com alterações existentes: preservar o trabalho do usuário.
- Ambiente com dados reais: evitar operações destrutivas, exposição e efeitos externos.
- Problemas entre aulas: arquitetura, saneamento, desempenho e evolução mantêm objetivos distintos.

## Tarefa 1: manutenção e qualidade

- [x] Criar `prompts/manutencao/sanear-projeto.md`.
- [x] Criar `prompts/arquitetura/revisar-arquitetura.md`.
- [x] Criar `prompts/manutencao/investigar-e-corrigir-bug.md`.
- [x] Criar `prompts/testes/proteger-fluxos-principais.md`.
- [x] Conferir manualmente objetivo, exemplos, limites e entrega de cada bloco.

## Tarefa 2: segurança, interface e evolução

- [x] Criar `prompts/seguranca/revisar-e-corrigir-seguranca.md`.
- [x] Criar `prompts/design/revisar-interface-com-agent-browser.md`.
- [x] Criar `prompts/desempenho/investigar-e-corrigir-lentidao.md`.
- [x] Criar `prompts/planejamento/avaliar-evolucao-tecnica.md`.
- [x] Conferir referências oficiais pertinentes e os limites de atuação de cada prompt.

## Tarefa 3: integração, revisão e publicação

- [x] Atualizar o README.md com os oito links e orientação para escolher o guia.
- [x] Verificar links relativos, campos preenchíveis, blocos completos e preservação das aulas anteriores.
- [x] Solicitar uma revisão independente e corrigir problemas relevantes.
- [x] Executar `git diff --check`, criar o commit e enviar ao GitHub.
- [x] Comparar o commit e o conteúdo publicados com os arquivos locais.

## Decisões de execução

- Escopo e publicação já aprovados; continuar sem novas confirmações rotineiras.
- Somente documentação: verificar os artefatos diretamente, sem criar testes de aplicação ou dependências.
- Manter o fluxo existente de publicação em `main`, com seleção explícita dos arquivos do trabalho.

## Resultado

Oito guias novos, 23 campos preenchíveis e quatro guias anteriores preservados. Links relativos,
blocos completos e índice verificados. Revisão independente sem achados que exijam alteração.
Publicação do conteúdo conferida no commit `2c9a3e3`, com os 15 arquivos idênticos por hash.
A execução dos prompts em aplicações reais permanece fora desta validação documental.
