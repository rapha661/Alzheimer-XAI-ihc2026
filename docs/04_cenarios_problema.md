# Entrega 4 — Cenários de análise/problema

**Data:** {{dd/mm/aaaa}}  
**Status:** ⬜ não iniciada  
**Responsabilidade:** 1 solução completa por integrante

## Objetivo da atividade

Descrever situações atuais em que o usuário tenta alcançar um objetivo e encontra dificuldades. O cenário de análise/problema deve tornar visível **o contexto, os atores, as ações e as rupturas**, sem antecipar a interface que será projetada.

> **Regra central:** cenário de problema é a “história do problema”. Se o texto já diz “o sistema mostra”, “o aplicativo resolve” ou descreve botões/telas futuras, provavelmente está misturando problema com solução.

Sempre que possível, o cenário deve aprofundar uma **situação concreta já registrada na Entrega 1**.

### Quando o TCC não possuía interface

O cenário continua sendo uma história de **problema/atividade humana**, não uma história do futuro sistema. Descreva como o profissional realiza hoje uma atividade semelhante ou como lida atualmente com dados, resultados, configurações, logs, decisões e limitações que o tema do TCC pretende apoiar.

Exemplo: em vez de “o DBA abre o novo dashboard e executa o algoritmo”, descreva “o DBA precisa investigar uma consulta lenta, reúne informações em ferramentas distintas, compara planos manualmente e tem dificuldade para estimar o impacto de uma mudança”.

A interface da disciplina aparecerá somente depois, nos cenários de interação.

Se o integrante escolher um novo problema/situação, explique por que ele passou a ser relevante e indique a evidência que motivou sua inclusão.

## Cenário C01 — A decisão sem números

**Autor(a):** Raphael Garavati Erbert — 22.123.014-7
**Persona(s) relacionada(s):** P03 — Regina Albuquerque Marins
**Necessidade relacionada:** Relatório agregado com indicadores objetivos de ganho (tempo médio de diagnóstico, taxa de concordância entre médicos, incidentes) — campo "Necessidades" de P03, Entrega 3
**Situação concreta da Entrega 1 relacionada:** nova situação, justificada abaixo
**Hipóteses ainda presentes:** H04

### 1. Cenário inicial

Regina precisa decidir, na reunião trimestral do comitê de tecnologia do hospital, se o piloto de uma ferramenta de apoio diagnóstico por IA — usada nos últimos meses por parte da equipe de neurologia — deve continuar sendo custeada, ser expandida para outras unidades, ou ser encerrada. Não existe nenhum relatório consolidado sobre o uso da ferramenta. Regina pede à secretária do comitê que reúna informações com os médicos envolvidos. A resposta vem por e-mails avulsos: um neurologista diz que "sente que os casos ficaram mais rápidos"; outro reclama que "às vezes discorda do que a ferramenta sugere"; o setor financeiro manda uma planilha com o custo da licença, mas sem nenhum dado de contrapartida em ganho. Regina tenta cruzar isso manualmente numa planilha própria, mas não sabe comparar o tempo de diagnóstico de antes da ferramenta com o de agora, porque esse dado nunca foi registrado de forma padronizada. Ela chega à reunião com uma impressão geral, não com um número. A decisão acaba sendo adiada para o próximo trimestre.

### 2. Questões de refinamento

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
|---|---|---|---|
| Q1 | Existe algum registro (mesmo informal) do tempo de diagnóstico antes do piloto começar, para servir de linha de base de comparação? | Sem uma linha de base, qualquer "ganho percebido" é apenas opinião, não evidência — é o núcleo do problema de H04 | Consultar prontuário eletrônico/registros de data de solicitação vs. data de conclusão do diagnóstico, período pré-piloto |
| Q2 | Quem, hoje, é formalmente responsável por compilar dados de avaliação de novas tecnologias antes de uma decisão do comitê? | Define se o problema é de processo (ninguém tem essa função) ou de ferramenta (a função existe, mas falta instrumento) | Entrevista com secretaria do comitê de tecnologia / regimento interno do comitê |
| Q3 | Com que frequência esse tipo de decisão de adoção/descontinuação é revisitada, e o que acontece quando a decisão é adiada (como no cenário)? | Mostra o custo real do adiamento — se a ferramenta continua sendo paga "por inércia" enquanto a decisão não sai | Atas de reuniões anteriores do comitê de tecnologia |
| Q4 | Os médicos que dão feedback informal (e-mail) representam a totalidade dos usuários da ferramenta, ou só quem tem opinião forte (positiva ou negativa) se manifesta? | Levanta um viés de amostragem no processo atual — decisão pode estar sendo tomada com base em quem reclama mais, não em uso real | Levantar quantos médicos usaram a ferramenta no período vs. quantos responderam ao pedido de feedback |
| Q5 | Como o hospital decidiu, no passado, sobre a adoção de outra tecnologia clínica (ex.: um novo equipamento ou sistema de PACS)? Existiu algum critério objetivo usado então? | Se já existe um precedente de processo mais estruturado, o problema é a falta de dado específico dessa ferramenta, não a falta de processo institucional | Entrevista com Regina ou levantamento de atas/relatórios de decisões de compra anteriores |

### 3. Cenário refinado

Regina precisa decidir, na reunião trimestral do comitê de tecnologia do hospital, se o piloto de uma ferramenta de apoio diagnóstico por IA — usada nos últimos meses por parte da equipe de neurologia — deve continuar sendo custeada, ser expandida para outras unidades, ou ser encerrada. Regina pede à secretária que reúna informações com os médicos envolvidos. A resposta vem por e-mails avulsos: um neurologista diz que "sente que os casos ficaram mais rápidos"; outro reclama que "às vezes discorda do que a ferramenta sugere". O setor financeiro manda uma planilha com o custo da licença, mas sem nenhum dado de contrapartida em ganho. Regina tenta cruzar isso manualmente numa planilha própria, mas não sabe comparar o tempo de diagnóstico de antes da ferramenta com o de agora. Ela chega à reunião com uma impressão geral, não com um número. A decisão acaba sendo adiada para o próximo trimestre.

### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| Ator(es) | Regina (gestora/diretora clínica); secretária do comitê de tecnologia; médicos neurologistas usuários do piloto; setor financeiro |
| Objetivo(s) | Decidir, com base em evidência, se a ferramenta deve ser mantida, expandida ou descontinuada |
| Contexto | Reunião trimestral do comitê de tecnologia do hospital; decisão institucional, fora do fluxo clínico do dia a dia |
| Recursos/informações | E-mails avulsos de feedback médico; planilha de custo do setor financeiro; dados de prontuário eletrônico não consolidados; atas de reuniões anteriores |
| Ações | Solicitar feedback informal por e-mail; tentar compilar dados manualmente em planilha própria; comparar custo sem contrapartida de ganho |
| Problemas/rupturas | Ausência de responsável formal pela compilação de dados; viés de amostragem no feedback (só quem tem opinião forte responde); dado de linha de base existe mas nunca foi extraído; ausência de indicador comparável antes/depois |
| Consequências | Decisão adiada por falta de evidência; padrão institucional recorrente de manter tecnologias "por inércia" sem avaliação formal concluída |

### 5. Implicações para as próximas entregas

- Mapear a tarefa "compilar indicador de tempo de diagnóstico antes/depois da adoção" como tarefa central a ser modelada — hoje ela não existe como tarefa formal, é feita de improviso.
- Investigar quais indicadores (dos citados nas necessidades de P03: tempo, concordância entre médicos, incidentes) são de fato extraíveis dos sistemas já existentes (prontuário eletrônico) sem exigir novo processo manual de coleta.
- Levantar, com o grupo, se o viés de amostragem no feedback informal (só quem tem opinião forte se manifesta) é um padrão conhecido em outras decisões hospitalares — se sim, isso reforça a necessidade de um mecanismo de coleta estruturada, não apenas de exibição de dado (fora do escopo de IHC desta disciplina, mas relevante registrar).
- Coletar, se possível, as atas de decisões anteriores do comitê de tecnologia citadas no cenário, para confirmar (ou refutar) o padrão de "manutenção por inércia" como fato, não apenas como elemento narrativo.
- Não desenhar ainda nenhuma tela de relatório — isso é hipótese de solução, a ser tratado apenas a partir da Entrega 6 em diante.

## Cenário C02 — O laudo que não explica

**Autor(a):** Nathan Gabriel da Fonseca Leite - 221230287
**Persona(s) relacionada(s):** P01 — Dr. Marcos Andrade (ator principal); P04 — Otávio Rezende Prado (persona negativa)
**Necessidade relacionada:** Explicação clara combinando imagem e dados clínicos, e caminho fácil para encaminhar ao especialista (campo "Necessidades" de P01, Entrega 3); atividade A03 (Entrega 1, item 3.2)  
**Situação concreta da Entrega 1 relacionada:** item 4.4 (falso negativo: "atrofia muito leve, pode ser normal para idade") e item 4.2 (fila longa, interpretação subjetiva, laudo sem justificativa técnica). A situação é contada do ponto de vista do médico clínico, que não aparece como ator no caso Maria Silva (item 4.5).  
**Hipóteses ainda presentes:** H01, H03, H06

### 1. Cenário inicial

Em uma quinta-feira à tarde, o Dr. Marcos Andrade, clínico geral de um hospital geral, recebe o retorno do Sr. Antônio Ferreira, 69 anos, que vem acompanhado da filha, Luciana. Três meses antes, Luciana contou que o pai vinha esquecendo recados e repetindo as mesmas perguntas. Marcos aplicou o MMSE (26 pontos) e pediu uma ressonância magnética do crânio. Agora o laudo chegou com a frase "redução volumétrica hipocampal discreta, a correlacionar com dados clínicos". Marcos lê o laudo duas vezes. Ele não sabe se "discreta" indica algo esperado para a idade ou um sinal inicial de Alzheimer, e o documento não traz nenhuma medida nem justificativa.

Luciana pergunta diretamente: "Doutor, é Alzheimer?". Marcos responde que ainda não é possível afirmar. Pensa em encaminhar o paciente ao neurologista, mas a fila do hospital é de vários meses. Tenta falar por telefone com um colega neurologista, sem sucesso. Com a consulta atrasada e outros pacientes esperando, ele registra no prontuário "declínio cognitivo leve a esclarecer", pede para repetir o teste em seis meses e não encaminha. Luciana sai do consultório sem saber o que esperar e sem entender por que o médico não conseguiu dar uma resposta.

### 2. Questões de refinamento

As questões seguem a técnica da aula e cobrem todos os elementos do cenário (objetivo, ambiente, atores, planejamento, ação, evento e avaliação), com questões exploratórias ("Por que…?", "Como…?", "O que é…?") e de verificação. Na coluna "Fonte", **[F]** indica resposta já sustentada pela Entrega 1 e **[H]** indica resposta plausível que ainda precisa ser confirmada (Entrega 7).

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
|---|---|---|---|
| Q1 | **(Objetivo — Por que)** Por que Marcos precisa chegar a uma conduta nesta consulta, em vez de apenas aguardar o especialista? | Explica a urgência que motiva as ações e o custo de adiar a decisão | [F] Entrega 1, item 4.2 (espera de 6 a 12 meses por especialista) e item 5.6 (progressão sem acompanhamento) |
| Q2 | **(Objetivo — O que é)** Que informações Marcos precisa reunir para decidir? | Revela os objetos do domínio e seus atributos, que depois alimentam a análise de tarefas | [F] Entrega 1, item 4.3 (MMSE/MoCA, sinais na MRI, histórico clínico e familiar); [H] exames de sangue para excluir causas reversíveis, a confirmar com médicos |
| Q3 | **(Ambiente — Pressões)** Quais pressões de tempo e institucionais existem durante a consulta? | Mostra por que a decisão é tomada às pressas e o que empurra o médico para não encaminhar | [F] Entrega 1, item 5.3 (pressão de tempo e fila de pacientes); [H] H06 — orientação da diretoria financeira para reduzir encaminhamentos (P04), a investigar em entrevista |
| Q4 | **(Ambiente — Tecnologias)** Que tecnologias Marcos usa no consultório e como as usa? | Mostra o que ele consegue ou não consultar no momento da decisão | [F] Entrega 1, item 5.2 (desktop com prontuário eletrônico); [H] no consultório ele só tem o laudo em texto, não as imagens, que ficam no PACS da radiologia |
| Q5 | **(Atores — De quem depende)** De quem depende a informação necessária para a decisão? | Identifica quem fornece dados e onde a informação se perde | [F] Entrega 1, item 5.4 (radiologista interpreta a imagem; neurologista valida casos complexos); relato da filha como fonte do histórico |
| Q6 | **(Atores — Quem consome o resultado)** Quem depende da decisão de Marcos e precisa ser informado dela? | Mostra o alcance da decisão além do consultório | [F] Entrega 1, item 2.3 (familiares e cuidadores afetados pelo diagnóstico) e item 5.5 (registro para auditoria) |
| Q7 | **(Planejamento — Estratégias)** Que estratégias Marcos tem hoje quando fica em dúvida, e quando usa cada uma? | Revela alternativas atuais e por que nenhuma resolve bem o caso | [F] Entrega 1, item 6.1 (segunda opinião, encaminhamento ao especialista); Entrega 3, P01 (liga para um colega em caso de dúvida) |
| Q8 | **(Planejamento — Decisão errada)** Quais as consequências se Marcos decidir errado? | Dimensiona o risco da ruptura e justifica a relevância do cenário | [F] Entrega 1, itens 4.4 e 5.6 (falso negativo com progressão irreversível; falso positivo com ansiedade e medicação desnecessária) |
| Q9 | **(Ação — Como)** Como Marcos interpreta um laudo que diz "redução volumétrica discreta"? | Mostra a dificuldade concreta da atividade mais crítica (A03) | [F] Entrega 1, item 4.2 (laudo sem justificativa técnica, interpretação subjetiva) e item 4.3 (sem quantificação objetiva de rotina) |
| Q10 | **(Ação — Erros)** Que erros podem ser cometidos no registro da conduta, e como são desfeitos? | Mostra que a decisão registrada influencia quem atende o paciente depois | [H] Entrega 1, item 4.2 (viés cognitivo não detectado); correção só acontece em nova consulta, a confirmar com médicos |
| Q11 | **(Evento)** Que evento dispara a necessidade de decidir agora? | Explica o que muda entre a consulta anterior e esta | [H] relato novo da família e chegada do laudo; a confirmar em entrevista |
| Q12 | **(Avaliação — Objetivo)** Como Marcos sabe se tomou a decisão certa? | Mostra se existe retorno sobre a qualidade da decisão | [H] não há retorno sistemático; ele só descobre no retorno seguinte ou se o paciente for atendido por outro profissional |
| Q13 | **(Verificação)** A justificativa do encaminhamento faz parte do registro da consulta? | Verifica se a documentação é uma ação única ou duas ações separadas | [H] a guia de encaminhamento é um formulário à parte, preenchido depois do registro no prontuário; a confirmar com médicos |

### 3. Cenário refinado

Convenção: o texto em **negrito** foi acrescentado no refinamento, e o número entre colchetes indica a questão respondida naquele trecho.

Em uma quinta-feira à tarde, o Dr. Marcos Andrade, clínico geral de um hospital geral, recebe o retorno do Sr. Antônio Ferreira, 69 anos, que vem acompanhado da filha, Luciana. **A agenda tem mais de vinte pacientes, com cerca de quinze minutos por consulta, e Marcos já está atrasado [Q3].** Três meses antes, Luciana contou que o pai vinha esquecendo recados e repetindo as mesmas perguntas. Marcos aplicou o MMSE (26 pontos) e pediu uma ressonância magnética do crânio **e exames de sangue para descartar causas reversíveis, como deficiência de vitamina B12 e alterações da tireoide [Q2]**. **Na semana anterior, Luciana ligou para o hospital preocupada: o pai tinha se perdido no caminho de volta da padaria, trajeto que faz há vinte anos [Q11].**

Agora o laudo chegou com a frase "redução volumétrica hipocampal discreta, a correlacionar com dados clínicos". **No consultório, Marcos tem apenas o prontuário eletrônico e o laudo em texto; as imagens ficam no sistema da radiologia, que ele não usa no dia a dia [Q4].** Marcos lê o laudo duas vezes. Ele não sabe se "discreta" indica algo esperado para a idade ou um sinal inicial de Alzheimer, e o documento não traz nenhuma medida nem justificativa **que permita comparar o achado com o esperado para um homem de 69 anos [Q9]**. **Os exames de sangue estão normais, e o MMSE de 26 pontos está na faixa limítrofe, que não confirma nem descarta o quadro [Q2].** **Para decidir, ele depende do que o radiologista escreveu, do relato da filha e, se conseguir, da opinião de um neurologista [Q5].**

Luciana pergunta diretamente: "Doutor, é Alzheimer?". Marcos responde que ainda não é possível afirmar. **Ele sabe que, se o paciente estiver no início da doença, esperar significa perder o período em que o tratamento e o planejamento familiar fazem mais diferença [Q1].** Pensa em encaminhar o paciente ao neurologista, mas a fila do hospital é de vários meses. **Além disso, no mês anterior a diretoria enviou um comunicado pedindo que os médicos evitassem "encaminhamentos não essenciais", e Marcos não tem um argumento técnico claro para mostrar que este é essencial [Q3].** **Quando está em dúvida, ele costuma ligar para um colega, encaminhar ou reavaliar o paciente depois de alguns meses [Q7].** Tenta falar por telefone com um colega neurologista, sem sucesso. **Encaminhar exigiria ainda preencher uma guia separada, com justificativa própria, além do registro no prontuário [Q13].**

Com a consulta atrasada e outros pacientes esperando, ele registra no prontuário "declínio cognitivo leve a esclarecer", pede para repetir o teste em seis meses e não encaminha. **Ele sabe que, se estiver errado, o paciente pode avançar na doença sem acompanhamento; se encaminhar sem necessidade, ocupa uma vaga disputada e deixa a família ansiosa sem motivo [Q8].** **O registro fica no prontuário e será a primeira coisa lida por qualquer médico que atender o Sr. Antônio depois; um termo vago pode levar o próximo profissional a tratar o caso como envelhecimento normal, e isso só será revisto em uma nova consulta [Q10].** Luciana sai do consultório sem saber o que esperar e sem entender por que o médico não conseguiu dar uma resposta. **É ela quem vai cuidar do pai nos próximos meses, e precisa saber o que observar e quando voltar [Q6].** **Marcos também não terá nenhum retorno sobre a decisão: só vai saber se acertou quando o paciente voltar, daqui a seis meses, ou se for atendido por outro profissional [Q12].**

### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| Ator(es) | Dr. Marcos Andrade (médico clínico, P01); Sr. Antônio Ferreira (paciente); Luciana (filha e cuidadora); radiologista (autor do laudo); neurologista (colega não alcançado); diretoria do hospital (fonte da pressão para reduzir encaminhamentos, representada pela persona negativa P04) |
| Objetivo(s) | Decidir a conduta para um paciente com suspeita de Alzheimer inicial: tratar, encaminhar ou acompanhar; dar à família uma resposta compreensível |
| Contexto | Consulta de retorno em hospital geral; agenda cheia e consulta de cerca de quinze minutos; sem especialista disponível; fila longa para neurologia; pressão institucional para reduzir encaminhamentos; família ansiosa |
| Recursos/informações | Laudo de MRI em texto livre; MMSE limítrofe (26); exames de sangue normais; relato da filha; prontuário eletrônico; telefone; guia de encaminhamento em formulário separado |
| Ações | Ler e reler o laudo; conferir exames; responder à família; tentar contato com neurologista; considerar encaminhamento; registrar conduta vaga no prontuário; pedir nova avaliação em seis meses |
| Problemas/rupturas | Laudo sem medida nem comparação com o esperado para a idade; imagens inacessíveis no consultório; MMSE limítrofe sem outro critério objetivo; colega não disponível; fila longa; pressão da diretoria sem critério técnico para justificar o encaminhamento; documentação de encaminhamento duplicada; nenhum retorno sobre a qualidade da decisão |
| Consequências | Encaminhamento não realizado; risco de falso negativo e de progressão sem acompanhamento; registro vago que pode ancorar outros profissionais; família sem orientação; médico sem saber se decidiu bem |

### 5. Implicações para as próximas entregas

- Modelar na Entrega 5 a tarefa "interpretar laudo e exames para decidir a conduta" (A03), incluindo o ponto em que o médico decide entre encaminhar, acompanhar ou tratar. É nessa decisão que o cenário mostra a ruptura.
- Modelar também a tarefa "encaminhar a especialista com justificativa" (F07), registrando que hoje ela exige um documento separado do registro no prontuário (Q13, ainda hipótese).
- Coletar na Entrega 7, com médicos clínicos, como eles interpretam termos vagos de laudo ("discreta", "a correlacionar") e o que os faria encaminhar ou não. Isso alimenta H01 e H03.
- Investigar na Entrega 7 se existe pressão institucional real para reduzir encaminhamentos (H06). Se for confirmada, reforça as decisões de design de P04; se for refutada, a persona negativa deve ser revista.
- Confirmar se o médico clínico tem ou não acesso às imagens de MRI no consultório (Q4), porque isso muda o ponto de partida da interação.
- Registrar a família/cuidadora como stakeholder que precisa de uma explicação compreensível, sem torná-la usuária da interface (coerente com H05).
- Atualizar a RASTREABILIDADE.md com a ligação C02 → P01 → A03/F07 → H01, H03 e H06.
- Não desenhar ainda nenhuma tela: o cenário descreve apenas a situação atual.

> Repita para C02, C03... com autoria individual.

## Checklist

- [ ] Há um cenário completo por integrante.
- [ ] Cada cenário tem título, ator, objetivo, contexto e problema.
- [ ] O cenário possui origem rastreável na Entrega 1 ou justifica claramente a inclusão de uma nova situação.
- [ ] O texto descreve a situação atual, sem antecipar a solução.
- [ ] Para TCC sem interface original, o cenário descreve uma prática humana plausível relacionada à contribuição técnica, e não “a falta de uma tela”.
- [ ] Questões de refinamento acrescentam informação nova.
- [ ] O refinamento mostra claramente o que foi adicionado/alterado.
- [ ] Cenários são diferentes o suficiente para cobrir objetivos/problemas relevantes.
- [ ] Cada cenário está ligado a persona/necessidade na matriz de rastreabilidade.
