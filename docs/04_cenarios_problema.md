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

## Cenário C02 — {{título}}

**Autor(a):** {{nome — matrícula}}  
**Persona(s) relacionada(s):** {{P01}}  
**Necessidade relacionada:** {{R01}}  
**Situação concreta da Entrega 1 relacionada:** {{seção 4.4 / H01 / outra ou “nova situação justificada”}}  
**Hipóteses ainda presentes:** {{H01, H02 ou —}}

### 1. Cenário inicial

{{narrativa}}

### 2. Questões de refinamento

Use os tipos de questões/taxonomia definidos na aula. As perguntas devem revelar informações **ainda ausentes** do cenário, não repetir o que já foi respondido.

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
|---|---|---|---|
| Q1 | {{...}} | {{...}} | {{...}} |

### 3. Cenário refinado

Reescreva o cenário incorporando as respostas. Marque o conteúdo novo de forma consistente (por exemplo, `**[NOVO: ...]**`).

{{narrativa refinada}}

### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| Ator(es) | {{...}} |
| Objetivo(s) | {{...}} |
| Contexto | {{...}} |
| Recursos/informações | {{...}} |
| Ações | {{...}} |
| Problemas/rupturas | {{...}} |
| Consequências | {{...}} |

### 5. Implicações para as próximas entregas

Quais tarefas merecem análise? Quais informações precisam ser coletadas? **Não desenhe a solução ainda.**

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
