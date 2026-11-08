# Onde o Jev faz sentido no meu projeto?

Use para decidir se vale a pena adotar o [Jev, da TypeSafe AI](https://typesafe.ai/), em quais fluxos
e com quais limites. Jev é um modelo para decisões tipadas; a avaliação deve consultar sua
[documentação oficial](https://docs.typesafe.ai/introduction) e comparar alternativas no projeto real.

O prompt descobre a linguagem, a arquitetura e o estágio do projeto. Serve também para concluir que
Jev não compensa ou que faltam evidências. Não pressupõe chatbot, backend ou uso prévio de IA.

## Como usar

1. Abra a pasta do projeto no agente. Em um monorepo, indique o produto ou módulo que deseja avaliar.
2. Informe restrições conhecidas, se houver. Não precisa preencher um formulário para começar.
3. Cole o bloco abaixo. Leia o relatório antes de escolher qualquer implementação posterior.

## Como adaptar

Sem informações extras, o agente examina o projeto disponível e registra o que não conseguir descobrir.
Se necessário, acrescente ao pedido:

| Informação opcional | Exemplo |
| --- | --- |
| Foco da avaliação | Triagem de solicitações, análise de documentos ou projeto inteiro. |
| Restrições conhecidas | Operação offline, orçamento, tempo de resposta ou dados que não podem sair do ambiente. |
| Destino do relatório | Diretório local privado em que o agente pode salvar `relatorio-jev.html`. |

## O que será entregue

Um HTML independente, em português, com veredito, evidências, comparação de alternativas, fluxos propostos
e prompts para os próximos passos. O relatório funciona offline. Sua criação não instala nem integra Jev.

## Prompt

```text
Comece usando a skill superpowers:brainstorming. Leia e siga suas instruções para alinhar contexto,
objetivo, escopo, restrições e critérios de conclusão antes de executar esta tarefa.
Respeite as autorizações já concedidas e os limites abaixo, sem ampliar o escopo nem repetir perguntas respondidas.
Se a skill estiver indisponível, informe o impedimento e não simule seu uso.

Investigue este projeto e avalie se, onde e por que vale a pena usar o Jev, da TypeSafe AI
(https://typesafe.ai/; documentação: https://docs.typesafe.ai/introduction).
Quero uma decisão fundamentada sobre sua adoção, proporcional ao problema e ao estágio do projeto.

Leia o projeto antes de perguntar. Descubra a stack e as convenções existentes, sem presumir linguagem,
framework, arquitetura, infraestrutura ou presença de IA. Pergunte apenas o que mudar a recomendação.
Sem acesso ao código, solicite o contexto necessário e limite o diagnóstico ao material disponível;
não invente arquivos, fluxos ou achados. Registre lacunas como “Falta evidência”.

Faça somente a investigação e o relatório. A única escrita autorizada nesta tarefa é o HTML.
Não implemente sugestões, execute os prompts gerados, instale ferramentas ou dependências, altere código,
configurações, dados ou estado do Git, nem publique. Não faça chamadas de inferência ao Jev, contrate
serviços ou habilite cobranças. Consultar documentação pública não autoriza enviar código ou dados privados.

## 1. Entender o projeto e confirmar a ferramenta

Leia as instruções do repositório, documentação, manifestos e código relevante. Identifique produto,
fluxos críticos, integrações, controles determinísticos e testes. Verifique se Jev já é usado e onde.
Rastreie entradas, decisões, ações e consumidores dos pontos candidatos; cite arquivos e linhas.
Em projetos grandes, delimite a cobertura e registre as partes não examinadas. Em projetos iniciais
ou sem aplicação executável, diferencie necessidades planejadas de comportamentos já implementados.

Consulte a documentação oficial vigente do Jev. Use Context7 quando disponível, confirmando a origem
dos resultados; na ausência de cobertura, consulte o site oficial. Registre URLs, data e versões quando
identificadas. Confirme capacidades, contratos, limites e integração por SDK ou API compatível com a stack.
Não presuma SDK para toda linguagem, suporte local/offline ou preços e desempenho de exemplos comerciais.
Se não conseguir consultar uma informação, registre a limitação e condicione a conclusão à verificação.

Avalie onde a integração poderia executar e proteger credenciais. Não presuma que exista um servidor:
se a proposta exigir nova infraestrutura, inclua esse custo e esforço. O relatório offline não implica
que Jev possa executar offline. Não o trate como substituto de geração de texto, chatbot ou agente de código.

## 2. Encontrar oportunidades sem forçar a adoção

Procure decisões pequenas e bem delimitadas: classificação, triagem, prioridade, intenção ou sinalização
de risco. Em chatbots existentes, avalie classificação e roteamento para setores. São exemplos, não metas.
Não crie uma necessidade só para encaixar Jev, nem proponha substituição de uma integração que já funciona
sem demonstrar benefício. Uma recomendação de não adotar é um resultado válido.

Compare cada oportunidade com manter o sistema como está, usar regras simples e reaproveitar soluções
existentes. Avalie viabilidade técnica separadamente do benefício: conseguir integrar não prova que compensa.

Classifique os achados como “Faz sentido agora”, “Não compensa”, “Pode fazer sentido no futuro” ou
“Falta evidência”. Para cada um, mostre problema, evidência no projeto, ponto de integração, alternativas,
benefícios, desvantagens, esforço e riscos relevantes. Priorize por impacto e esforço, sem notas arbitrárias.
Para oportunidades futuras, indique um gatilho verificável para reavaliar; para lacunas, a evidência mínima
necessária. Não produza uma lista artificial de oportunidades para preencher o relatório.

Compare custos de implementação, manutenção e uso, latência adicional, volume conhecido e dependência
do fornecedor. Separe fatos, hipóteses e estimativas com suas premissas. Confirme preços em fonte oficial
datada antes de calcular; sem preço ou volume, apresente a fórmula e os dados faltantes, não valores inventados.
Não apresente latência anunciada ou benchmark externo como medição deste projeto.

## 3. Especificar somente os usos que merecem avançar

Para cada uso viável, proponha estado/contexto mínimo, pergunta atômica, saída tipada, regra de decisão
em código e fallback. Use Choice, Score, Noul ou outro recurso apenas conforme a documentação consultada.
Defina opções, critérios ou rubricas, validação da resposta e o comportamento quando nenhuma opção servir.
Decomponha decisões com vários fatores e explique como o código combina as respostas.

Diferencie probabilidades, confidence quando disponível e acurácia medida em exemplos rotulados.
Não interprete confidence como garantia de acerto nem suponha esse campo em todo tipo de resposta.
Escolha o sinal adequado à decisão e proponha como validar limiares, casos incertos e custos de falsos
positivos/negativos. Não adote limiares universais sem validação no domínio.

Considere minimização de dados enviados, privacidade, retenção, conteúdo não confiável, timeout, limites
de uso e indisponibilidade. Defina fallback proporcional ao risco: fluxo existente, regra determinística
ou revisão humana, conforme o caso. Preserve autenticação, autorização, validações e registros obrigatórios;
uma classificação de IA não concede acesso nem substitui controles determinísticos.

Proponha uma validação pequena contra a solução atual, com casos representativos rotulados, casos de erro,
métricas pertinentes e critérios de aprovação e abandono. Inclua adoção gradual e reversão quando cabíveis.
Descreva o experimento; não o execute nem alegue resultados que ainda não foram medidos.

## 4. Gerar o relatório HTML

Salve relatorio-jev.html em um local autorizado, fora de pastas publicadas automaticamente. Se já existir,
preserve o arquivo e use um sufixo no novo nome. Sem permissão de escrita, entregue o conteúdo na conversa
e informe que não foi salvo; não afirme ter criado um arquivo inexistente.

Produza um arquivo único, em português, com CSS e JS internos, sem dependências, fontes ou recursos externos.
Deve abrir offline e manter conteúdo e prompts legíveis mesmo sem JavaScript. Links de referência podem
apontar para a internet, sem carregar conteúdo remoto automaticamente. Escape trechos de código e texto
ao inseri-los no HTML; eles devem aparecer como conteúdo, nunca executar como marcação ou script.
Não inclua segredos, credenciais, dados pessoais ou trechos privados desnecessários.

Use hierarquia clara, bom contraste, layout responsivo, HTML semântico e navegação por teclado com foco
visível. Inclua veredito executivo, cobertura e limitações, tabela comparativa, cards das oportunidades,
etiquetas textuais de status, plano de validação e referências datadas. Não dependa só de cores.
Represente os fluxos propostos com diagramas em HTML ou SVG interno e uma explicação textual equivalente.
Se não houver oportunidades, explique o motivo; não invente cards, diagramas ou implementações.

## 5. Incluir prompts independentes para os próximos passos

Inclua no HTML um prompt pronto para copiar para cada implementação recomendada. Cada prompt deve começar,
dentro do texto copiável, repetindo as quatro linhas iniciais deste prompt sobre superpowers:brainstorming,
alinhamento, autorizações e indisponibilidade da skill. Não dependa de instruções fora do texto copiado.

Preencha cada prompt com contexto real, objetivo, arquivos envolvidos, contrato de entrada/saída, limites
de escopo, reaproveitamento existente, falhas e fallback, testes, critérios de aceite e reversão.
Diferencie caminhos existentes de arquivos propostos. Torne o texto compreensível sem o restante do HTML,
sem referências vagas como “implemente o descrito acima” e sem segredos ou campos obrigatórios vazios.
Peça para reconferir o estado do projeto e a documentação antes de alterar algo. Não conceda por padrão
permissão para publicar, migrar dados, contratar serviços ou executar chamadas pagas.

Para oportunidades futuras ou incertas, gere prompts de investigação ou validação, com a evidência exigida
e os critérios para decidir. Esses prompts não autorizam implementação; esta será uma tarefa posterior.
Para opções descartadas, explique a decisão sem gerar um prompt de implementação.

Inclua botão “Copiar prompt” em cada bloco, com retorno acessível de sucesso ou falha. Mantenha o texto
selecionável para cópia manual quando a área de transferência estiver indisponível, inclusive via file://.

## 6. Revisar e entregar

Revise coerência do veredito, evidências, referências e início de cada prompt copiável. Se houver navegador
disponível, abra o HTML local e confira layout em computador e celular, teclado, diagramas e cópia integral
de cada prompt. Verifique a leitura sem rede e sem JavaScript e a alternativa manual de cópia.
Não instale ferramentas para essa revisão; registre o que foi validado e o que não conseguiu verificar.

Ao terminar, informe o caminho real do HTML, a recomendação principal e as limitações relevantes.
Encerre após a investigação e o relatório; as sugestões e os prompts ficam para uma tarefa posterior.
```

Referências consultadas em 8 de novembro de 2026:
[introdução](https://docs.typesafe.ai/introduction),
[Jev e agentes de código](https://docs.typesafe.ai/introduction/coding-agents),
[SDKs e API](https://docs.typesafe.ai/sdk) e [confidence](https://docs.typesafe.ai/confidence).
O prompt solicita nova consulta a cada execução, pois capacidades e contratos podem mudar.

[Voltar ao guia](../../README.md)
