# Entrega 4 — Cenários de análise/problema

- **Data:** {17/09/2026}  
- **Status:** 🟩 concluída
- **Responsabilidade:** 1 solução completa por integrante

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

## Cenário C02 — O parecer que se perdeu

**Autor(a):** Paulo Hudson Josué da Silva — 22.222.013-9
**Persona(s) relacionada(s):** P01 — Dr. Marcos Andrade (ator principal); P02 — Dr. César Andrade de Melo (neurologista consultado informalmente)
**Necessidade relacionada:** "Caminho fácil para encaminhar a um especialista quando necessário" (campo "Necessidades" de P01, Entrega 3); jornada de P01, etapa 9 (Entrega 3) — identificou a lacuna de reabrir/atualizar um caso após retorno do especialista
**Situação concreta da Entrega 1 relacionada:** item 5.4 (turnos e continuidade — "caso iniciado por um profissional pode ser finalizado por outro"; requisito de handoff claro entre profissionais) e item 5.5 (necessidade de histórico e rastreabilidade). É uma situação nova: a jornada da Entrega 3 apontou essa lacuna, mas ainda não havia um cenário concreto que a sustentasse — este cenário cobre esse vazio.
**Hipóteses ainda presentes:** H03, H06

### 1. Cenário inicial

Dois meses atrás, o Dr. Marcos Andrade encaminhou informalmente o Sr. Ivo Bittencourt, 71 anos, ao neurologista Dr. César Andrade de Melo, depois de identificar um MMSE limítrofe e um laudo de MRI pouco conclusivo. Como a fila oficial de encaminhamento levaria meses, Marcos ligou para César, que atendeu o caso como favor entre colegas. César respondeu por telefone que os achados eram "compatíveis com comprometimento cognitivo leve, sem elementos fortes para Alzheimer neste momento" e sugeriu reavaliação em seis meses. Marcos anotou rapidamente "neuro: sem AD por ora, reavaliar" numa nota de rodapé do prontuário, sem detalhar o raciocínio. Hoje, o Sr. Ivo retorna à consulta acompanhado do filho, relatando piora perceptível da memória nas últimas semanas. Marcos abre o prontuário e encontra apenas essa anotação breve. Ele não lembra quais exames o neurologista revisou, nem por que descartou Alzheimer naquele momento. Tenta ligar para César, mas ele está em cirurgia e não retorna a tempo da consulta. Marcos precisa decidir se pede um novo exame do zero, se reencaminha o paciente ao mesmo neurologista, ou se toma uma conduta sozinho, sem o contexto completo da avaliação anterior.

### 2. Questões de refinamento

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
|---|---|---|---|
| Q1 | **(Objetivo — Por que)** Por que Marcos precisa reconstruir o raciocínio do neurologista antes de decidir, em vez de tratar o caso como novo? | Decidir sem esse contexto pode repetir exames desnecessários ou ignorar um raciocínio clínico já validado, desperdiçando um parecer que já foi obtido | [H] plausível a partir da lógica clínica; a confirmar o quanto disso se perde na prática (Entrega 7) |
| Q2 | **(Objetivo — O que é)** Que informações do parecer anterior seriam necessárias para retomar o caso com segurança? | Revela os objetos do domínio que precisam ser preservados entre um atendimento e outro | [F] Entrega 1, item 4.3 (achados de MRI, MMSE); [H] o critério específico usado pelo neurologista para descartar AD não ficou documentado |
| Q3 | **(Ambiente — Pressões)** Que pressão de tempo existe nesse retorno, e o que ela empurra Marcos a fazer? | Mostra por que a decisão é tomada às pressas, sem tempo de reconstruir o histórico com calma | [F] Entrega 1, item 5.3 (pressão de tempo, agenda cheia) |
| Q4 | **(Ambiente — Tecnologias)** Que sistema Marcos usa para registrar ou consultar o parecer do colega, e quais suas limitações? | Mostra que não existe hoje um campo estruturado para pareceres obtidos informalmente | [F] Entrega 1, item 5.4; [H] o prontuário atual não distingue "parecer formal" de "anotação de ligação entre colegas" |
| Q5 | **(Atores — De quem depende)** De quem depende a reconstrução do raciocínio do parecer anterior? | Identifica por que o parecer não é simplesmente "recuperável" a qualquer momento | [F] Entrega 3, P02 (Dr. César, alta carga de casos, prefere atalhos) — explica por que ele não tem tempo de reconstruir o caso por telefone toda vez |
| Q6 | **(Atores — Quem consome)** Quem mais seria afetado se a conduta atual for tomada sem o contexto do parecer anterior? | Mostra o alcance da decisão além do consultório | [F] Entrega 1, item 2.3 (familiares/cuidadores); o filho do Sr. Ivo espera uma resposta consistente com a anterior |
| Q7 | **(Planejamento — Estratégias)** Que estratégias Marcos tem hoje quando o parecer anterior não está claro no registro? | Revela que nenhuma alternativa atual reaproveita o trabalho clínico já feito | [H] ligar de novo para o colega (nem sempre disponível), pedir exame novo do zero, ou decidir sozinho |
| Q8 | **(Planejamento — Decisão errada)** Que consequência existe se Marcos decidir sem o contexto do parecer anterior? | Dimensiona o risco da ruptura | [F] Entrega 1, item 5.6 (falso negativo/positivo); reencaminhar sem necessidade ocupa uma vaga de fila já escassa (item 4.2) |
| Q9 | **(Ação — Como)** Como, hoje, o parecer de um especialista consultado informalmente chega ao prontuário? | Mostra a fragilidade do registro que origina o problema do cenário | [H] depende de o médico solicitante anotar de memória, resumidamente, logo após a ligação, sem revisão do especialista sobre o que foi registrado |
| Q10 | **(Evento)** Que evento dispara a necessidade de retomar esse caso especificamente agora? | Explica o que mudou entre a consulta anterior e esta | [F] Entrega 1, item 4.4/4.5 — piora relatada pela família, mesmo padrão de gatilho já visto no caso Maria Silva |
| Q11 | **(Avaliação — Objetivo)** Como Marcos vai saber, desta vez, se a conduta tomada foi adequada? | Mostra a ausência de retorno sobre a qualidade da decisão | [H] não há retorno sistemático; só descobre se o paciente piorar ou for atendido por outro profissional |
| Q12 | **(Verificação)** O parecer informal de um colega passa pelo mesmo processo de documentação que um encaminhamento formal? | Verifica se existe, hoje, algum tratamento diferenciado para pareceres informais | [H] não; é tratado como "conversa entre colegas", a confirmar em entrevista (Entrega 7) |

### 3. Cenário refinado

Convenção: o texto em **negrito** foi acrescentado no refinamento, e o número entre colchetes indica a questão respondida naquele trecho.

**Antes de decidir, Marcos precisa entender o que o neurologista já concluiu meses atrás — não apenas partir do zero, como se o Sr. Ivo fosse um paciente novo [Q1].** Dois meses atrás, o Dr. Marcos Andrade encaminhou informalmente o Sr. Ivo Bittencourt, 71 anos, ao neurologista Dr. César Andrade de Melo, depois de identificar um MMSE limítrofe e um laudo de MRI pouco conclusivo. Como a fila oficial de encaminhamento levaria meses e o quadro não parecia grave o suficiente para justificar a espera, Marcos preferiu resolver por conhecimento pessoal **[Q7]**. Ligou para César, que atendeu o caso como favor entre colegas — **como boa parte dos neurologistas, César tem a agenda cheia de casos e prefere resolver dúvidas rápidas por telefone a formalizar cada parecer informal [Q5]**. César respondeu que os achados eram "compatíveis com comprometimento cognitivo leve, sem elementos fortes para Alzheimer neste momento" e sugeriu reavaliação em seis meses. Marcos, ainda em meio a outros atendimentos, anotou rapidamente **[Q9]** "neuro: sem AD por ora, reavaliar" numa nota de rodapé do prontuário, sem detalhar quais achados de imagem ou critérios o colega usou para chegar a essa conclusão **[Q2]**.

### 3. Cenário refinado

Convenção: o texto em **negrito** foi acrescentado no refinamento, e o número entre colchetes indica a questão respondida naquele trecho.

Dois meses atrás, o Dr. Marcos Andrade encaminhou informalmente o Sr. Ivo Bittencourt, 71 anos, ao neurologista Dr. César Andrade de Melo, depois de identificar um MMSE limítrofe e um laudo de MRI pouco conclusivo. Como a fila oficial de encaminhamento levaria meses e o quadro não parecia grave o suficiente para justificar a espera, Marcos preferiu resolver por conhecimento pessoal **[Q7]**. Ligou para César, que atendeu o caso como favor entre colegas — **como boa parte dos neurologistas, César tem a agenda cheia de casos e prefere resolver dúvidas rápidas por telefone a formalizar cada parecer informal [Q5]**. César respondeu que os achados eram "compatíveis com comprometimento cognitivo leve, sem elementos fortes para Alzheimer neste momento" e sugeriu reavaliação em seis meses. Marcos, ainda em meio a outros atendimentos, anotou rapidamente **[Q9]** "neuro: sem AD por ora, reavaliar" numa nota de rodapé do prontuário, sem detalhar quais achados de imagem ou critérios o colega usou para chegar a essa conclusão **[Q2]**.

Hoje, o Sr. Ivo retorna à consulta acompanhado do filho, **depois que a família notou piora perceptível da memória nas últimas semanas [Q10]**. Marcos abre o prontuário e encontra apenas essa anotação breve — **o sistema não tem um campo separado para pareceres obtidos por telefone entre colegas; tudo vira uma linha igual a qualquer outra anotação de rotina [Q4]**. Ele não lembra quais exames o neurologista revisou, nem por que descartou Alzheimer naquele momento. **Decidir agora sem recuperar esse raciocínio seria tratar o Sr. Ivo como se fosse um paciente novo, descartando uma avaliação clínica que já foi feita [Q1].** A agenda do dia está cheia e o próximo paciente já aguarda **[Q3]**. Tenta ligar para César, mas ele está em cirurgia e não retorna a tempo da consulta. Marcos precisa decidir se pede um novo exame do zero, se reencaminha o paciente ao mesmo neurologista — **ocupando de novo uma vaga de fila já escassa, sem saber se é realmente necessário [Q8]** — ou se toma uma conduta sozinho, sem o contexto completo da avaliação anterior. **O filho do Sr. Ivo espera uma resposta consistente com o que já foi dito à família na primeira consulta [Q6].** **Qualquer que seja a conduta, Marcos só vai saber se foi a certa se o paciente piorar visivelmente ou for atendido por outro profissional depois [Q11] — e o parecer de César, por ter sido dado informalmente entre colegas, nunca passou pelo mesmo processo de registro que um encaminhamento formal teria [Q12].**

### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| Ator(es) | Dr. Marcos Andrade (médico clínico, P01); Sr. Ivo Bittencourt (paciente); filho do Sr. Ivo (cuidador); Dr. César Andrade de Melo (neurologista consultado informalmente, P02) |
| Objetivo(s) | Retomar com segurança a conduta de um paciente cujo parecer especializado anterior não está claramente documentado; decidir entre repetir exame, reencaminhar ou conduzir sozinho |
| Contexto | Consulta de retorno em hospital geral, agenda cheia; parecer especializado obtido informalmente por telefone dois meses antes, sem processo formal de registro; especialista indisponível no momento da nova decisão |
| Recursos/informações | Anotação breve no prontuário ("neuro: sem AD por ora, reavaliar"); MMSE e MRI anteriores; relato do filho sobre piora recente; tentativa de contato telefônico com o neurologista |
| Ações | Ler a anotação anterior; tentar contato telefônico; avaliar se repete exame, reencaminha, ou decide sozinho; atender o novo relato da família |
| Problemas/rupturas | Parecer informal não documentado com detalhe suficiente para ser retomado; ausência de processo formal para pareceres obtidos por telefone entre colegas; especialista indisponível quando o caso é retomado; risco de reencaminhamento desnecessário ocupando vaga escassa; nenhum retorno sistemático sobre a qualidade da decisão anterior |
| Consequências | Decisão tomada com informação incompleta; possível repetição de exames já feitos; possível perda de tempo com reencaminhamento evitável; família recebendo resposta potencialmente inconsistente com a anterior |

### 5. Implicações para as próximas entregas

- Modelar na Entrega 5 a tarefa "retomar um caso após parecer de especialista", incluindo o sub-passo de consultar/reconstruir o raciocínio anterior — hoje inexistente como tarefa formal.
- Usar este cenário como evidência de apoio à **H06** (permitir reabrir/atualizar um caso após retorno do especialista) antes da investigação formal na Entrega 7.
- Investigar na Entrega 7, com médicos clínicos e neurologistas, se pareceres informais (telefone/e-mail) são comuns e como são registrados hoje, para confirmar ou refutar Q9/Q12.
- Atualizar a `RASTREABILIDADE.md` com a ligação C02 → P01/P02 → H03, H06.
- Não desenhar ainda nenhuma tela: o cenário descreve apenas a situação atual, antes de qualquer interface.

## Cenário C03 — O exame que precisou ser refeito

**Autor(a):** Nathan Gabriel da Fonseca Leite — 221230287
**Persona(s) relacionada(s):** P04 — Bruno Tavares Lima
**Necessidade relacionada:** Conferir a qualidade da imagem e os dados clínicos obrigatórios antes de liberar o exame (campo "Necessidades" de P04, Entrega 3); atividade A01 (Entrega 1, item 3.2)
**Situação concreta da Entrega 1 relacionada:** item 4.1 (aquisição de MRI e armazenamento no PACS) e item 4.2 (protocolos variam; inconsistência de qualidade; falta de especialistas no local)
**Hipóteses ainda presentes:** H07

### 1. Cenário inicial

Numa segunda-feira de manhã, Bruno Tavares Lima, técnico em radiologia, recebe no setor de imagem a Sra. Aparecida Souza, 74 anos, acompanhada do filho, Rogério. O pedido médico diz apenas "RM de crânio — investigação de déficit cognitivo". Bruno usa o protocolo padrão de crânio que o setor aplica na maioria dos casos. Durante o exame, Dona Aparecida fica inquieta e mexe a cabeça várias vezes. Bruno repete uma das sequências, mas ela pede para sair e ele encerra o exame. Na tela, as imagens parecem aceitáveis. Depois que a paciente vai embora, Bruno envia o exame ao PACS e copia do prontuário as informações clínicas que encontra para a requisição de laudo. Três dias depois, o laudo volta com a observação "exame limitado por artefato de movimento; ausência de sequência volumétrica; dados clínicos incompletos". Dona Aparecida precisa ser chamada de novo, e o diagnóstico atrasa algumas semanas.

### 2. Questões de refinamento

As questões seguem a técnica da aula e cobrem todos os elementos do cenário (objetivo, ambiente, atores, planejamento, ação, evento e avaliação), com questões exploratórias ("Por que…?", "Como…?", "O que é…?") e de verificação. Na coluna "Fonte", **[F]** indica resposta já sustentada pela Entrega 1 e **[H]** indica resposta plausível que ainda precisa ser confirmada (Entrega 7).

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
|---|---|---|---|
| Q1 | **(Objetivo — Por que)** Por que é importante que o exame saia completo na primeira tentativa? | Mostra o custo da ruptura para o paciente e para o hospital | [F] Entrega 1, item 3.2 (qualidade dos dados afeta todo o processo) e item 4.2 (fila e atraso); [H] dificuldade de reconvocar idosos, a confirmar com o setor de imagem |
| Q2 | **(Objetivo — O que é)** O que compõe um exame "completo" para investigação de Alzheimer? | Revela os objetos do domínio e seus atributos, que depois alimentam a análise de tarefas | [F] Entrega 1, item 4.1 (sinais buscados: atrofia hipocampal, perda de matéria cinzenta) e item 4.3 (MMSE/MoCA, histórico); [H] sequência volumétrica T1 como requisito, a confirmar com radiologista |
| Q3 | **(Ambiente — Pressões)** Quais pressões existem no setor de imagem durante o exame? | Explica por que Bruno encerra o exame sem refazer tudo | [H] agenda cheia no scanner e intervalo curto entre pacientes; nuança o item 2.4 da Entrega 1 ("pressão baixa"), a confirmar |
| Q4 | **(Ambiente — Tecnologias)** Que tecnologias Bruno usa e como as usa nesse processo? | Mostra onde a informação está e onde ela se perde | [F] Entrega 1, item 4.1 (scanner e PACS) e item 5.2 (prontuário eletrônico); [H] a requisição de laudo é preenchida à mão com dados copiados do prontuário |
| Q5 | **(Atores — Características)** Que características da paciente e de Bruno ajudam ou atrapalham o objetivo? | Liga as rupturas ao perfil dos atores, não só ao processo | [F] Entrega 1, item 2.4 (técnico com conhecimento operacional, sem interpretação diagnóstica); [H] pacientes com declínio cognitivo têm dificuldade de ficar parados |
| Q6 | **(Atores — De quem depende)** De quem Bruno depende para saber o que o caso exige? | Mostra que a informação necessária para escolher o protocolo não chega até ele | [F] Entrega 1, item 5.4 (médico solicita e decide; radiologista interpreta); [H] pedido médico sem indicação de protocolo |
| Q7 | **(Atores — Quem consome)** Quem depende do trabalho de Bruno? | Mostra o alcance da falha além do setor de imagem | [F] Entrega 1, item 5.4 (radiologista laudista) e item 4.1 (médico clínico lê o laudo para decidir); [F] item 4.2 (falta de neurorradiologistas); [H] laudo feito por especialista de outra unidade |
| Q8 | **(Planejamento — Estratégias)** Que alternativas Bruno tem quando o paciente se mexe? | Revela as decisões que ele toma sozinho e sem critério definido | [H] repetir a sequência, orientar o paciente, pedir ajuda do acompanhante ou encerrar; a confirmar com técnicos |
| Q9 | **(Ação — Como)** Como Bruno avalia se a imagem está boa o suficiente? | Mostra a dificuldade concreta da atividade A01 | [F] Entrega 1, item 4.2 (sem padrão ouro objetivo; protocolos variam); [H] avaliação visual rápida no console, sem critério escrito |
| Q10 | **(Ação — Informações e erros)** Como os dados clínicos são reunidos, e que erros podem acontecer? | Mostra risco de dado incompleto ou do paciente errado | [F] Entrega 1, item 5.3 (dados sensíveis, LGPD); [H] cópia manual do prontuário, com risco de omitir o MMSE ou trocar pacientes com nomes parecidos |
| Q11 | **(Evento)** Que evento revela o problema, e quando? | Mostra a distância entre o erro e sua descoberta | [H] H07 — o laudo volta dias depois com a observação "exame limitado" |
| Q12 | **(Avaliação — Ação)** Como Bruno sabe, no momento, se o exame foi concluído com sucesso? | Mostra que não existe confirmação no momento certo | [H] não sabe; só confia na própria avaliação visual |
| Q13 | **(Verificação)** A escolha do protocolo faz parte do pedido médico ou é decidida pelo técnico? | Verifica em que ponto do processo essa decisão deveria estar | [H] hoje fica com o técnico, por falta de informação no pedido; a confirmar com o setor de imagem |

### 3. Cenário refinado

Tudo que está em **negrito** foi acrescentado no refinamento, e o número entre colchetes indica a questão respondida naquele trecho.

Numa segunda-feira de manhã, Bruno Tavares Lima, técnico em radiologia, recebe no setor de imagem a Sra. Aparecida Souza, 74 anos, acompanhada do filho, Rogério. **A agenda do aparelho está cheia, com um paciente a cada meia hora, e o seguinte já aguarda na recepção [Q3].** O pedido médico diz apenas "RM de crânio — investigação de déficit cognitivo". **O pedido não indica protocolo, e o médico solicitante não está no hospital para ser consultado; a escolha fica com Bruno [Q6] [Q13].** Bruno usa o protocolo padrão de crânio que o setor aplica na maioria dos casos. **Esse protocolo não inclui a sequência volumétrica que permite avaliar com precisão o hipocampo, algo que Bruno só saberia se o pedido dissesse que se trata de investigação de Alzheimer [Q2].**

Durante o exame, Dona Aparecida fica inquieta e mexe a cabeça várias vezes. **Ela não lembra por que está ali e pergunta ao filho, pelo interfone, quando vai acabar [Q5].** **Bruno sabe que pode repetir a sequência, conversar com a paciente ou pedir que o filho fique ao lado dela, mas cada tentativa atrasa o próximo exame [Q8].** Bruno repete uma das sequências, mas ela pede para sair e ele encerra o exame. Na tela, as imagens parecem aceitáveis. **Bruno faz apenas uma olhada rápida no console; não existe um critério escrito que diga quanto movimento ainda é tolerável [Q9].** **Sem nenhuma outra confirmação, ele considera o exame concluído [Q12].**

Depois que a paciente vai embora, Bruno envia o exame ao PACS e copia do prontuário as informações clínicas que encontra para a requisição de laudo. **Ele alterna entre duas janelas, procurando idade, queixa e resultado do MMSE. O MMSE está registrado em uma evolução antiga, que ele não encontra, e o campo fica em branco. No mesmo dia, há outra paciente com sobrenome Souza na agenda, e ele confere duas vezes para não misturar os dados [Q4] [Q10].** **Como o hospital não tem neurorradiologista, o exame é laudado por um especialista de outra unidade, que depende inteiramente do que Bruno enviou; o laudo, por sua vez, será usado pelo médico clínico para decidir a conduta [Q7].**

Três dias depois, o laudo volta com a observação "exame limitado por artefato de movimento; ausência de sequência volumétrica; dados clínicos incompletos". **É só nesse momento que Bruno descobre que o exame não serviu [Q11].** Dona Aparecida precisa ser chamada de novo, e o diagnóstico atrasa algumas semanas. **Rogério precisa faltar ao trabalho mais uma vez para acompanhar a mãe, e a nova vaga no aparelho só aparece quinze dias depois; enquanto isso, o médico continua sem informação para decidir [Q1].**

### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| Ator(es) | Bruno Tavares Lima (técnico em radiologia, P04); Sra. Aparecida Souza (paciente); Rogério (filho e acompanhante); médico solicitante (ausente); radiologista laudista de outra unidade; médico clínico que usará o laudo (P01, indiretamente) |
| Objetivo(s) | Realizar e enviar um exame de MRI completo e com qualidade, acompanhado dos dados clínicos corretos, para investigação de Alzheimer |
| Contexto | Setor de imagem de hospital geral; agenda cheia no aparelho; paciente idosa com dificuldade de colaborar; pedido médico sem protocolo; laudo feito por especialista de outra unidade |
| Recursos/informações | Pedido médico em texto livre; protocolo padrão de crânio; console do scanner; PACS; prontuário eletrônico; requisição de laudo preenchida à mão |
| Ações | Escolher o protocolo; realizar o exame; repetir uma sequência; avaliar as imagens visualmente; encerrar o exame; enviar ao PACS; copiar dados clínicos do prontuário; conferir identidade da paciente |
| Problemas/rupturas | Pedido sem indicação de protocolo; ausência da sequência necessária; artefato de movimento; nenhum critério objetivo de qualidade; dados clínicos espalhados e MMSE não encontrado; risco de trocar pacientes; erro descoberto só dias depois, no laudo |
| Consequências | Exame inútil para o diagnóstico; reconvocação da paciente; atraso de semanas no diagnóstico; custo para a família e para a agenda do setor; médico clínico sem informação para decidir |

### 5. Implicações para as próximas entregas

- Modelar na Entrega 5 a tarefa "preparar e enviar os dados do paciente" (A01), separando as subtarefas de escolher o protocolo, conferir a qualidade da imagem, reunir os dados clínicos e confirmar a identidade do paciente.
- Registrar que, hoje, a verificação de qualidade acontece depois que o paciente sai do setor. Esse é o ponto da ruptura e deve orientar a análise da tarefa.
- Coletar na Entrega 7, com técnicos e radiologistas, quais sequências e dados clínicos são de fato necessários para investigação de Alzheimer (Q2) e quem decide o protocolo (Q13).
- Investigar na Entrega 7 com que frequência exames de demência são reconvocados por falta de qualidade ou de dados (H07).
- Confirmar se o laudo é feito por especialista de outra unidade (Q7), porque isso muda quem consome os dados preparados por Bruno.
- Atualizar a `RASTREABILIDADE.md` com a ligação C03 → P04 → A01/F01 → H07.
- Não desenhar ainda nenhuma tela: o cenário descreve apenas a situação atual.

# Cenário C04 — A dúvida sobre a autonomia do paciente

- **Autor(a):** Ana Carolina Lazzuri  22.123.001-4
- **Persona(s) relacionada(s):** P02 — Dr. César (Neurologista)  
- **Necessidade relacionada:** Entender se os achados do exame de imagem realmente explicam as falhas de atenção e memória observadas no dia a dia para tomar uma decisão segura sobre a rotina do paciente  
- **Situação concreta da Entrega 1 relacionada:** Dificuldade de relacionar o resultado genérico de um exame de imagem com as queixas práticas do paciente e seus testes de memória  
- **Hipóteses ainda presentes:** H01, H05  


### 1. Cenário inicial

Em um fim de tarde, o Dr. César atende o Sr. Roberto, de 71 anos, que mora sozinho e foi levado à consulta por sua vizinha, Dona Lúcia. Lúcia relata que o vizinho quase provocou um acidente de carro recente por se confundir no trânsito e que ele tem esquecido panelas no fogo com frequência. O Sr. Roberto, no entanto, insiste que está bem e quer autorização médica para continuar dirigindo. César olha a ressonância do cérebro e o teste de memória do paciente. O laudo do exame de imagem diz apenas que o cérebro tem "alterações normais para a idade". Mas o teste de memória mostra que a atenção e o raciocínio do Sr. Roberto estão bem abaixo do esperado. César tenta olhar a imagem por conta própria para ver se encontra alguma região desgastada que justifique esses erros no trânsito, mas o laudo não aponta em qual parte da imagem ele deve prestar atenção. Sem conseguir conversar com o médico que fez o laudo e sem ter certeza se o problema de memória é grave o bastante, César fica num impasse: proibir o paciente de dirigir e tirar sua independência sem ter certeza, ou liberar e correr o risco de um acidente grave.


### 2. Questões de refinamento

| # | Questão | Por que precisa ser respondida | Fonte / Forma de obter resposta |
|---|---|---|---|
| Q1 | **(Objetivo — Por que)** Por que César precisa entender o exame de imagem em detalhes em vez de só ler o laudo? | O laudo diz que o exame está "normal", mas o comportamento do paciente na vida real indica perigo. | [F] Entrega 1 (divergência entre laudo e comportamento); [H] decisão de segurança. |
| Q2 | **(Objetivo — O que é)** Quais informações César precisa cruzar para tomar essa decisão? | Identifica os dados necessários para avaliar a autonomia do paciente. | [F] Entrega 1 (imagens do cérebro, notas do teste de memória e relatos da vizinha). |
| Q3 | **(Ambiente — Pressões)** O que pressiona o tempo de César durante a consulta? | Mostra o contexto de consulta cheia e a pressão para dar uma resposta imediata à família/vizinha. | [F] Entrega 1 (tempo curto de atendimento no ambulatório). |
| Q4 | **(Ambiente — Tecnologias)** Que ferramentas o sistema oferece para ajudar César a comparar as informações? | Mostra que os sistemas atuais mostram o texto e a imagem em telas separadas, sem ligar uma coisa à outra. | [F] Entrega 1 (prontuário digital simples e programa de ver imagem). |
| Q5 | **(Atores — De quem depende)** César consegue falar com o médico que fez o laudo para tirar a dúvida? | Mostra a falta de comunicação rápida entre os médicos do hospital. | [F] Entrega 1 (dificuldade de contato direto com o setor de exames). |
| Q6 | **(Atores — Quem consome)** Quem é afetado pela decisão de César? | Mostra o impacto da decisão na vida e segurança do paciente e de outras pessoas no trânsito. | [F] Entrega 1 (o Sr. Roberto e a comunidade ao redor). |
| Q7 | **(Planejamento — Estratégias)** Quais escolhas César tem diante dessa dúvida? | Mostra os caminhos possíveis quando não há clareza nos dados. | [H] Proibir de dirigir temporariamente, pedir um exame mais detalhado ou liberar com restrições. |
| Q8 | **(Planejamento — Decisão errada)** Qual é o perigo de tomar a decisão errada aqui? | Dimensiona a gravidade da consequência social e de saúde. | [F] Entrega 1 (causar um acidente de trânsito ou tirar a autonomia de um idoso sem necessidade). |
| Q9 | **(Ação — Como)** Como César tenta encontrar a resposta na imagem por conta própria? | Mostra a tentativa manual de procurar desgastes no cérebro olhando corte por corte. | [H] Olhar as fatias da imagem no computador tentando achar alguma alteração a olho nu. |
| Q10 | **(Evento)** O que faz César parar e investigar mais a fundo? | O momento em que a história da vizinha contraria o laudo "normal". | [F] O relato dos episódios no trânsito e o resultado baixo no teste de memória. |
| Q11 | **(Avaliação — Objetivo)** Como César vai saber se tomou a decisão certa? | Mostra como é difícil ter certeza imediata nesse tipo de caso. | [H] Apenas no acompanhamento das próximas consultas ou se ocorrer algum incidente. |
| Q12 | **(Verificação)** O problema é a falta de conhecimento de César ou a falta de clareza sobre o que o laudo analisou? | Garante que o problema principal é a falta de transparência entre a imagem e o resultado. | [H] A ausência de indicação de quais partes do cérebro foram checadas no laudo. |


### 3. Cenário refinado

Tudo o que está em **negrito** foi acrescentado no refinamento.

Em um fim de tarde, o Dr. César atende o Sr. Roberto, de 71 anos, que mora sozinho e foi levado à consulta por sua vizinha, Dona Lúcia **[Q6]**. Lúcia relata que o vizinho quase provocou um acidente de carro recente por se confundir no trânsito e que ele tem esquecido panelas no fogo com frequência **[Q10]**. O Sr. Roberto, no entanto, insiste que está bem e quer autorização médica para continuar dirigindo **[Q1]**. **Como a consulta está no final do expediente e há outro paciente aguardando, César precisa decidir a conduta rapidamente [Q3].**

César olha a ressonância do cérebro e o teste de memória do paciente, **precisando abrir o resultado do teste em uma folha de papel e a imagem no computador [Q4]**. O laudo do exame de imagem diz apenas que o cérebro tem "alterações normais para a idade". Mas o teste de memória mostra que a atenção e o raciocínio do Sr. Roberto estão bem abaixo do esperado **[Q2, Q10]**. César tenta olhar a imagem por conta própria para ver se encontra alguma região desgastada que justifique esses erros no trânsito **[Q9]**, mas o laudo não aponta em qual parte da imagem ele deve prestar atenção **[Q12]**. **O texto do laudo é muito resumido e não explica se as áreas do cérebro responsáveis pela atenção e orientação espacial foram avaliadas com cuidado [Q12].**

César tenta ligar para o setor que fez a ressonância para tirar dúvidas sobre a imagem, **mas ninguém atende no momento [Q5]**. **Diante dessa dúvida, César fica dividido entre três caminhos: proibir o paciente de dirigir imediatamente, pedir um novo exame de imagem mais caro ou apenas orientar a vizinha a vigiá-lo mais de perto [Q7].** Sem conseguir conversar com o médico que fez o laudo e sem ter certeza se o problema de memória é grave o bastante, César fica num impasse **[Q1, Q12]**. **Ele sabe que proibir o Sr. Roberto de dirigir sem uma prova clara vai causar um grande impacto na independência do idoso, enquanto liberar o carro pode resultar em um acidente grave na rua [Q8].** Sem tempo para investigar mais e sem certeza nos dados visuais do exame, César opta por proibir a direção temporariamente e pede para retornarem em três meses para novos testes, deixando o paciente frustrado e a vizinha preocupada com a rotina dele **[Q7, Q11]**.


### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| **Ator(es)** | Dr. César (Neurologista); Sr. Roberto (paciente); Dona Lúcia (vizinha/acompanhante); Médico do laudo (indisponível). |
| **Objetivo(s)** | Verificar se os dados do exame de imagem confirmam a perda de atenção para decidir se é seguro autorizar o paciente a continuar dirigindo e morando sozinho. |
| **Contexto** | Consulta no fim do dia; paciente idoso que mora sozinho; divergência entre o laudo que diz "normal" e os erros graves no trânsito relatados pela vizinha. |
| **Recursos/informações** | Exame de ressonância do cérebro; laudo em texto; resultado do teste de memória em papel; relato da vizinha sobre os quase acidentes. |
| **Ações** | Ler o laudo; comparar as notas do teste com o relato do paciente; olhar as fatias da imagem no computador; tentar ligar para o setor de exames; proibir o paciente de dirigir temporariamente. |
| **Problemas/rupturas** | O laudo não mostra em quais partes do cérebro se baseou; divergência entre o exame "normal" e a perda de memória real do paciente; falta de comunicação entre os médicos. |
| **Consequências** | Perda da independência do paciente sem uma confirmação visual clara; insatisfação do paciente; necessidade de remarcar consulta em três meses. |


### 5. Implicações para as próximas entregas

- **Análise de Tarefas (Entrega 5):** Mapear a tarefa de "Avaliação de aptidão e autonomia do paciente", focando em como o médico cruza queixas do dia a dia (como dirigir) com testes cognitivos e imagens.
- **Rastreabilidade:** Vincular este cenário (C04) à Persona **P02 (Dr. César - Neurologista)** e às Hipóteses H01/H05.
- **Validação com Usuários (Entrega 7):** Entrevistar neurologistas para entender como eles lidam com situações em que precisam restringir tarefas do paciente (como dirigir) quando o laudo do exame vem como "normal para a idade".
- **Regra de IHC:** Foco total nas dificuldades de processo do médico, sem sugerir telas ou soluções de tecnologia.

## Checklist

- [x] Há um cenário completo por integrante.
- [x] Cada cenário tem título, ator, objetivo, contexto e problema.
- [x] O cenário possui origem rastreável na Entrega 1 ou justifica claramente a inclusão de uma nova situação.
- [x] O texto descreve a situação atual, sem antecipar a solução.
- [ ] Para TCC sem interface original, o cenário descreve uma prática humana plausível relacionada à contribuição técnica, e não “a falta de uma tela”.
- [x] Questões de refinamento acrescentam informação nova.
- [x] O refinamento mostra claramente o que foi adicionado/alterado.
- [x] Cenários são diferentes o suficiente para cobrir objetivos/problemas relevantes.
- [x] Cada cenário está ligado a persona/necessidade na matriz de rastreabilidade.
