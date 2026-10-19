# Entrega 4 — Cenários de análise/problema

- **Data:** {17/09/2026}  
- **Status:** 🟦 revisada após feedback
- **Responsabilidade:** 1 solução completa por integrante

## Objetivo da atividade

Descrever situações atuais em que o usuário tenta alcançar um objetivo e encontra dificuldades. O cenário de análise/problema deve tornar visível **o contexto, os atores, as ações e as rupturas**, sem antecipar a interface que será projetada.

> **Regra central:** cenário de problema é a “história do problema”. Se o texto já diz “o sistema mostra”, “o aplicativo resolve” ou descreve botões/telas futuras, provavelmente está misturando problema com solução.

Sempre que possível, o cenário deve aprofundar uma **situação concreta já registrada na Entrega 1**.

---

## Cenário C01 — O laudo que não disse nada

**Autor(a):** Raphael Garavati Erbert — 22.123.014-7  
**Persona(s) relacionada(s):** P03 — Dra. Helena Siqueira Prado (radiologista)  
**Necessidade relacionada:** Receber a pergunta clínica junto ao exame; ter uma referência objetiva para atrofia limítrofe; conseguir indicar no laudo o que foi avaliado.  
**Situação concreta da Entrega 1 relacionada:** Item 4.1 (o radiologista examina as imagens no PACS e escreve o relatório em texto livre), item 4.2 (interpretação subjetiva; inconsistência de qualidade) e item 4.3 (atrofia hipocampal sem quantificação objetiva de rotina).
**Hipóteses ainda presentes:** H01, H08  

### 1. Cenário inicial

Numa quarta-feira à tarde, a Dra. Helena Siqueira Prado, radiologista de um serviço de telerradiologia, tem 41 exames na fila de laudos, vindos de hospitais diferentes. Ela abre a ressonância de crânio de um paciente idoso. O pedido diz apenas "RM de crânio — investigação de déficit cognitivo", e o campo de dados clínicos traz só a idade. Helena percorre os cortes e nota que os hipocampos parecem um pouco reduzidos, mas não o suficiente para afirmar atrofia com segurança em um paciente dessa idade. Não há exame anterior para comparar. Ela pensa em medir, mas fazer a medição à mão levaria um tempo que a fila de laudos não permite. Escreve: "Redução volumétrica hipocampal discreta, que pode ser compatível com a faixa etária. Correlacionar com dados clínicos." Libera o laudo e abre o próximo exame. Ela não fica sabendo o que o médico que pediu o exame fez com aquela frase.

### 2. Questões de refinamento

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
|---|---|---|---|
| Q1 | **(Ambiente)** Existe uma meta de produtividade formal no serviço de telerradiologia (prazo por exame ou laudos por hora) e ela é cobrada? | O cenário mostra a fila, mas não diz se o tempo de investigação gera atrasos puníveis | [H] Prática comum em serviços de telerradiologia — entrevistas com radiologistas |
| Q2 | **(Ambiente)** Que recursos de medição o PACS do serviço oferece para o hipocampo, e por que não são usados de rotina? | Esclarece se a limitação é tecnológica ou de fluxo de trabalho | [F] Entrega 1, item 4.3 e item 6.3; [H] ausência de volumetria automática |
| Q3 | **(Atores)** Quem preenche os dados clínicos que acompanham o exame antes do envio para a telerradiologia? | Mostra onde a informação clínica se perde antes de chegar a quem lauda | [F] Entrega 4, C03 (o técnico copia do prontuário o que encontra) |
| Q4 | **(Planejamento)** Que alternativas Helena considerava (como usar escalas visuais) antes de optar pela frase cautelosa padrão? | Revela a estratégia mental diante da ausência de padrões objetivos | [F] Entrega 1, item 4.2 (interpretação subjetiva) |
| Q5 | **(Evento)** Durante a rotina da fila, exames de urgência (como AVC ou trauma) passam na frente, comprimindo ainda mais o tempo para os casos de demência? | Mostra o evento externo que desorganiza o planejamento da fila | [H] Priorização de urgências em telerradiologia |
| Q6 | **(Avaliação)** O serviço possui algum mecanismo interno de auditoria de qualidade ou dupla leitura para laudos inconclusivos? | Verifica se existe retorno sobre a assertividade das descrições genéricas | [?] Entrevistas com supervisores de serviços de imagem |

### 3. Cenário refinado

Numa quarta-feira à tarde, a Dra. Helena Siqueira Prado, radiologista de um serviço de telerradiologia, tem 41 exames na fila de laudos, vindos de hospitais diferentes. **O serviço opera sob metas estritas de prazo por exame, monitoradas por relatórios de produtividade [H, Q1]**. Ela abre a ressonância de crânio de um paciente idoso. O pedido diz apenas "RM de crânio — investigação de déficit cognitivo", e o campo de dados clínicos traz só a idade. **Esses dados clínicos foram repassados de forma resumida pelo técnico do hospital de origem [F, Q3]**. Helena percorre os cortes e nota que os hipocampos parecem um pouco reduzidos, mas não o suficiente para afirmar atrofia com segurança. Não há exame anterior para comparar. Ela pensa em medir, mas fazer a medição à mão levaria um tempo que a fila não permite; **o PACS do serviço dispõe apenas de ferramentas de medidas lineares, carecendo de volumetria automática para o hipocampo [H, Q2]**. **Enquanto analisa o caso, chegam exames de urgência (como suspeita de AVC) que ganham prioridade imediata na fila, comprimindo ainda mais o tempo disponível [H, Q5]**. Sem ferramentas objetivas e sem contexto clínico, Helena opta por escrever uma frase cautelosa ("Redução volumétrica hipocampal discreta... Correlacionar com dados clínicos") para se proteger de falsos positivos, **sem dispor de um canal ágil para sanar a dúvida com o solicitante ou de auditoria interna que avalie o impacto dessa inconclusão no destino do paciente [?, Q6]**. Libera o laudo e abre o próximo exame.

### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| Ator(es) | Dra. Helena Siqueira Prado (radiologista, P03) |
| Objetivo(s) | Emitir um laudo útil e seguro para um caso limítrofe dentro do prazo da fila |
| Contexto | Serviço de telerradiologia; fila de exames; prazo cobrado; exames urgentes com prioridade |
| Recursos/informações | Pedido em texto livre; idade no campo clínico; MRI sem exame anterior; PACS com medidas lineares |
| Ações | Percorrer cortes; pensar em medir e desistir; escrever frase cautelosa; liberar laudo |
| Problemas/rupturas | Falta de contexto clínico; ausência de referência objetiva para atrofia; restrição severa de tempo |
| Consequências | Laudo genérico devolvido ao solicitante; risco de atraso diagnóstico |

### 5. Implicações para as próximas entregas

- Manter este cenário documentado como contexto de telerradiologia e análise de imagem, servindo de base para discussões futuras de suporte à interpretação de P03.

---

## Cenário C02 — O parecer que se perdeu

**Autor(a):** Paulo Hudson Josué da Silva — 22.222.013-9  
**Persona(s) relacionada(s):** P01 — Dr. Marcos Andrade (ator principal); P02 — Dr. César Andrade de Melo (neurologista consultado) 
**Necessidade relacionada:** "Caminho fácil para encaminhar a um especialista quando necessário" (Entrega 3); reabrir/atualizar um caso após retorno do especialista (H06).  
**Situação concreta da Entrega 1 relacionada:** Item 5.4 (continuidade e handoff entre profissionais) e item 5.5 (necessidade de histórico e rastreabilidade).  
**Hipóteses ainda presentes:** H03, H06  

### 1. Cenário inicial

Dois meses atrás, o Dr. Marcos Andrade encaminhou informalmente o Sr. Ivo Bittencourt, 71 anos, ao neurologista Dr. César Andrade de Melo, após identificar um MMSE limítrofe e um laudo de MRI pouco conclusivo. Como a fila oficial de encaminhamento levaria meses, Marcos ligou para César, que atendeu o caso como favor entre colegas. César respondeu por telefone que os achados eram "compatíveis com comprometimento cognitivo leve, sem elementos fortes para Alzheimer neste momento" e sugeriu reavaliação em seis meses. Marcos anotou rapidamente "neuro: sem AD por ora, reavaliar" numa nota de rodapé do prontuário, sem detalhar o raciocínio. Hoje, o Sr. Ivo retorna à consulta acompanhado do filho, relatando piora perceptível da memória nas últimas semanas. Marcos abre o prontuário e encontra apenas essa anotação breve. Ele não lembra quais exames o neurologista revisou, nem por que descartou Alzheimer naquele momento. Tenta ligar para César, mas ele está em cirurgia e não retorna a tempo da consulta. Marcos precisa decidir se pede um novo exame do zero, se reencaminha o paciente ao mesmo neurologista, ou se toma uma conduta sozinho, sem o contexto completo da avaliação anterior.

### 2. Questões de refinamento

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
|---|---|---|---|
| Q1 | **(Ambiente)** Como o sistema de prontuário atual categoriza registros oriundos de ligações informais entre médicos? | Descobre se há algum campo específico ou se tudo é tratado como nota livre indiferenciada | [F] Entrega 1, item 5.4; [H] ausência de metadados para pareceres externos |
| Q2 | **(Atores)** Quais critérios específicos o Dr. César utilizou mentalmente para afastar Alzheimer na ligação inicial? | Identifica o detalhe técnico que se perdeu na transição do canal verbal para a nota de rodapé | [?] Entrevista com neurologistas sobre o formato padrão de repasse telefônico |
| Q3 | **(Planejamento)** Quais são as opções exatas de encaminhamento formal disponíveis no sistema quando o canal informal falha? | Mostra o custo administrativo de corrigir a falta de registro prévia | [F] Entrega 1, fluxo de regulação de vagas |
| Q4 | **(Ação)** Qual é o tempo médio que o médico clínico gasta tentando buscar histórico disperso antes de desistir e solicitar novos exames? | Mensura o impacto operacional da ruptura de continuidade | [H] Observação de campo em consultório geral |
| Q5 | **(Avaliação)** Como o médico clínico valida se a decisão tomada sem o parecer original causou prejuízo ao plano de cuidado do paciente? | Identifica o mecanismo tardio de feedback clínico | [H] Retorno de urgência ou reatendimento por outro profissional |

### 3. Cenário refinado

Dois meses atrás, o Dr. Marcos Andrade encaminhou informalmente o Sr. Ivo Bittencourt, 71 anos, ao neurologista Dr. César Andrade de Melo, após identificar um MMSE limítrofe e um laudo de MRI pouco conclusivo. Como a fila oficial de encaminhamento levaria meses e o quadro não parecia grave o suficiente para justificar a espera, Marcos preferiu resolver por conhecimento pessoal. Ligou para César, que atendeu o caso como favor entre colegas. César respondeu que os achados eram "compatíveis com comprometimento cognitivo leve, sem elementos fortes para Alzheimer neste momento" e sugeriu reavaliação em seis meses. Marcos anotou rapidamente "neuro: sem AD por ora, reavaliar" numa nota de rodapé do prontuário. **Como o prontuário eletrônico atual não possui campos estruturados para distinguir pareceres informais de anotações comuns [H, Q1]**, os critérios técnicos exatos utilizados por César para afastar Alzheimer não foram gravados no sistema **[H, Q2]**.

Hoje, o Sr. Ivo retorna à consulta acompanhado do filho, relatando piora perceptível da memória nas últimas semanas. Marcos abre o prontuário e encontra apenas essa anotação breve. Ele não lembra quais exames o neurologista revisou, nem por que descartou Alzheimer naquele momento. A agenda do dia está cheia. Tenta ligar para César, mas ele está em cirurgia e não retorna a tempo da consulta. **Na ausência de um canal estruturado para resgatar o histórico, Marcos estima que gastaria preciosa parte da consulta tentando auditar papéis físicos ou registros dispersos [H, Q4]**. Marcos precisa decidir se pede um novo exame do zero, se reencaminha o paciente ao mesmo neurologista — sobrecarregando a fila oficial — ou se toma uma conduta sozinho, sem o contexto completo da avaliação anterior. **Qualquer que seja a conduta tomada nesta consulta, Marcos só saberá se ela foi adequada caso ocorra uma nova piora clínica perceptível ou se o paciente for atendido posteriormente por outro colega [H, Q5]**.

### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| Ator(es) | Dr. Marcos Andrade (médico clínico, P01); Sr. Ivo Bittencourt (paciente); filho do Sr. Ivo; Dr. César Andrade de Melo (neurologista, P02) |
| Objetivo(s) | Retomar com segurança o acompanhamento de um paciente utilizando o raciocínio clínico de um parecer especializado anterior |
| Contexto | Consultório de atendimento geral; agenda lotada; ausência de interoperabilidade e registro estruturado |
| Recursos/informações | Nota de rodapé no prontuário; exames anteriores (MMSE e MRI); relato verbal recente do filho |
| Ações | Abrir prontuário; tentar contato telefônico com especialista indisponível; ponderar alternativas de conduta |
| Problemas/rupturas | Perda de contexto e justificativa técnica do parecer especializado; prontuário sem suporte a pareceres informais estruturados |
| Consequências | Risco de duplicação desnecessária de exames; decisão clínica tomada sob incerteza |

### 5. Implicações para as próximas entregas

- Levar para a Entrega 5 a necessidade de estruturar o fluxo de **reabertura e atualização de casos encaminhados**, avaliando como manter visíveis os pareceres de especialistas de forma integrada à interface do médico clínico (apoio à H06).

---

## Cenário C03 — O exame que precisou ser refeito

**Autor(a):** Nathan Gabriel da Fonseca Leite — 221230287  
**Persona(s) relacionada(s):** P04 — Bruno Tavares Lima (técnico em radiologia)  
**Necessidade relacionada:** Conferir a qualidade da imagem e os dados clínicos obrigatórios antes de liberar o exame (Entrega 3); atividade A01 (Entrega 1, item 3.2).  
**Situação concreta da Entrega 1 relacionada:** Item 4.1 (aquisição de MRI e armazenamento no PACS) e item 4.2 (variabilidade de protocolos e inconsistência de qualidade).  
**Hipóteses ainda presentes:** H07  

### 1. Cenário inicial

Numa segunda-feira de manhã, Bruno Tavares Lima, técnico em radiologia, recebe no setor de imagem a Sra. Aparecida Souza, 74 anos, acompanhada do filho, Rogério. O pedido médico diz apenas "RM de crânio — investigação de déficit cognitivo". Bruno usa o protocolo padrão de crânio que o setor aplica na maioria dos casos. Durante o exame, Dona Aparecida fica inquieta e mexe a cabeça várias vezes. Bruno repete uma das sequências, mas ela pede para sair e ele encerra o exame. Na tela, as imagens parecem aceitáveis. Depois que a paciente vai embora, Bruno envia o exame ao PACS e copia do prontuário as informações clínicas que encontra para a requisição de laudo. Três dias depois, o laudo volta com a observação "exame limitado por artefato de movimento; ausência de sequência volumétrica; dados clínicos incompletos". Dona Aparecida precisa ser chamada de novo, e o diagnóstico atrasa algumas semanas.

### 2. Questões de refinamento

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
|---|---|---|---|
| Q1 | **(Ambiente)** Como a central de agendamento distribui os horários para pacientes idosos com suspeita de declínio cognitivo na escala diária do equipamento? | Identifica se há folga de tempo alocada para manejo de pacientes com movimentação restrita | [H] Normas operacionais do setor de imagem |
| Q2 | **(Atores)** Qual é o nível de autonomia formal do técnico para alterar o protocolo padrão de aquisição quando o pedido médico está genérico? | Esclarece se a decisão de incluir sequências avançadas depende exclusivamente de autorização médica prévia | [F] Entrega 1, item 2.4; [?] diretrizes do corpo clínico |
| Q3 | **(Planejamento)** Quais alternativas operacionais Bruno possui no console para mitigar artefatos de movimento antes de decidir encerrar o exame? | Mapeia o conjunto de ações de contenção disponíveis na rotina técnica | [H] Manuais de operação de ressonância magnética |
| Q4 | **(Ação)** Como o técnico realiza a transferência manual dos dados clínicos do prontuário para a requisição, e quais erros de digitação são mais frequentes? | Evidencia a vulnerabilidade do processo de cópia manual de informações | [F] Entrega 1, item 5.3; [H] registros de divergência de prontuário |
| Q5 | **(Avaliação)** Existe algum mecanismo automatizado de alerta precoce de qualidade de imagem no PACS antes que o paciente deixe as dependências do hospital? | Verifica se o fluxo atual possui pontos intermediários de checagem ou se depende exclusivamente da leitura final do laudo | [?] Arquitetura de software do PACS do serviço |

### 3. Cenário refinado

Numa segunda-feira de manhã, Bruno Tavares Lima, técnico em radiologia, recebe no setor de imagem a Sra. Aparecida Souza, 74 anos, acompanhada do filho, Rogério. O pedido médico diz apenas "RM de crânio — investigação de déficit cognitivo". Bruno usa o protocolo padrão de crânio que o setor aplica na maioria dos casos. **Como a escala do aparelho opera com intervalos curtos entre pacientes [H, Q1]**, a margem de manobra para lidar com imprevistos é reduzida. 

Durante o exame, Dona Aparecida fica inquieta e mexe a cabeça várias vezes. **Diante da movimentação, Bruno pondera as alternativas técnicas disponíveis em seu treinamento — como tentar orientar a paciente novamente ou aplicar contenções leves [H, Q3]** —, mas, percebendo o desconforto dela e pressionado pela agenda, Bruno repete apenas uma das sequências e encerra o exame. Na tela do console, as imagens parecem visualmente aceitáveis. Depois que a paciente vai embora, Bruno envia o exame ao PACS e transcreve manualmente do prontuário as informações clínicas para a requisição de laudo — **um procedimento sujeito a lapsos devido à digitação manual sob ritmo acelerado [H, Q4]**. 

Três dias depois, o laudo volta com a observação "exame limitado por artefato de movimento; ausência de sequência volumétrica; dados clínicos incompletos". **Como o fluxo operacional do serviço carece de um validador automatizado de qualidade de imagem no PACS logo após o escaneamento [H, Q5]**, a falha só é descoberta após a saída da paciente, tornando indispensável a reconvocação e gerando atraso de semanas no diagnóstico.

### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| Ator(es) | Bruno Tavares Lima (técnico em radiologia, P04); Sra. Aparecida Souza (paciente); Rogério (acompanhante) |
| Objetivo(s) | Realizar a aquisição de imagem de ressonância com qualidade diagnóstica e dados clínicos completos, dentro da agenda |
| Contexto | Setor de imagem hospitalar; agenda com alta ocupação; paciente idosa com dificuldade de cooperação |
| Recursos/informações | Scanner de RM; console de aquisição; protocolo padrão; prontuário eletrônico; requisição |
| Ações | Aplicar protocolo; monitorar varredura; encerrar exame; transcrever dados manuais; enviar ao PACS |
| Problemas/rupturas | Falta de dados clínicos detalhados; ausência de sequência volumétrica; limite de tempo na agenda; ausência de checagem precoce |
| Consequências | Exame inconclusivo detectado dias depois; necessidade de reconvocação; atraso no diagnóstico |

### 5. Implicações para as próximas entregas

- Utilizar as rupturas deste cenário para fundamentar a necessidade de **mecanismos de pré-validação de qualidade de imagem e integridade de dados clínicos** antes da liberação do paciente (suporte à hipótese H07).

---

## Cenário C04 — A dúvida sobre a autonomia do paciente

**Autor(a):** Ana Carolina Lazzuri  
**Persona(s) relacionada(s):** P02 — Dr. César Andrade de Melo (neurologista)  
**Necessidade relacionada:** Avaliar capacidade funcional e tomada de decisão sobre autonomia (dirigir, gerir finanças) diante de evidências clínicas conflitantes (Entrega 3).  
**Situação concreta da Entrega 1 relacionada:** Item 5.6 (impacto de falsos negativos/positivos na qualidade de vida do paciente e familiares); divergência entre laudo de imagem, testes cognitivos e relato de terceiros.  
**Hipóteses ainda presentes:** H01, H05  

### 1. Cenário inicial

Numa tarde de quinta-feira, o Dr. César Andrade de Melo, neurologista, atende o Sr. Roberto Mendes, 76 anos, acompanhado de sua filha. Na consulta anterior, os testes cognitivos (MMSE) e o laudo de ressonância magnética indicavam um quadro limítrofe de declínio leve. No entanto, a filha relata episódios recentes preocupantes: o paciente se perdeu voltando da padaria e apresentou pequenos lapsos ao gerenciar contas domésticas, embora insista veementemente em continuar dirigindo seu automóvel. César precisa decidir se emite um laudo restritivo recomendando a suspensão da CNH e maior supervisão domiciliar. Ele analisa os dados objetivos do prontuário, que mostram pontuação estável, confrontando-os com o relato empírico da família. Diante do conflito, César pondera o impacto de restringir a autonomia de um paciente que ainda preserva lucidez parcial em vários momentos, equilibrando o risco de um acidente de trânsito com o dano psicológico de uma restrição precipitada.

### 2. Questões de refinamento

| # | Questão | Por que precisa ser respondida | Fonte/forma de obter resposta |
|---|---|---|---|
| Q1 | **(Ambiente)** Quais diretrizes legais e normativas o neurologista deve seguir obrigatoriamente ao emitir pareceres de restrição de capacidade civil ou de direção para idosos? | Define o marco regulatório que condiciona a decisão médica | [H] Legislação de trânsito e resoluções do CFM |
| Q2 | **(Atores)** Que grau de peso o médico atribui ao relato do familiar em comparação com o escore numérico dos testes cognitivos padronizados? | Revela a heurística decisória do especialista em casos limítrofes | [F] Entrega 1, item 5.6; [?] entrevistas com neurologistas clínicos |
| Q3 | **(Planejamento)** Quais estratégias alternativas o médico considera antes de impor uma restrição total de autonomia (ex: testes práticos, reavaliação com neuropsicólogo)? | Mostra a gradação de condutas disponíveis no planejamento do caso | [H] Práticas comuns de condução de consultório neurológico |
| Q4 | **(Ação)** Como o médico documenta formalmente o conflito entre a avaliação objetiva e a narrativa familiar no prontuário eletrônico? | Identifica a clareza e a rastreabilidade do registro de condutas sensíveis | [H] Análise de modelos de laudos neurológicos |
| Q5 | **(Avaliação)** Como o médico acompanha se a restrição de autonomia imposta foi efetiva e aceita pelo paciente e pela família sem rupturas graves no vínculo? | Verifica o feedback de longo prazo sobre a decisão tomada | [H] Retornos ambulatoriais subsequentes |

### 3. Cenário refinado

Numa tarde de quinta-feira, o Dr. César Andrade de Melo, neurologista, atende o Sr. Roberto Mendes, 76 anos, acompanhado de sua filha. Na consulta anterior, os testes cognitivos (MMSE) e o laudo de ressonância magnética indicavam um quadro limítrofe de declínio leve. No entanto, a filha relata episódios recentes preocupantes: o paciente se perdeu voltando da padaria e apresentou pequenos lapsos ao gerenciar contas domésticas, embora insista veementemente em continuar dirigindo seu automóvel. César precisa decidir se emite um laudo restritivo recomendando a suspensão da CNH e maior supervisão domiciliar. 

Ele analisa os dados objetivos do prontuário, que mostram pontuação estável, confrontando-os com o relato empírico da filha. **Na ausência de um protocolo padronizado no sistema para ponderar relatos subjetivos de familiares frente a métricas de exames de imagem [H, Q2]**, César precisa ponderar a decisão com base em sua experiência clínica pessoal. **Para mitigar o risco de uma restrição abrupta sem respaldo inequívoco, he considera como alternativa solicitar uma avaliação neuropsicológica complementar antes de emitir um parecer definitivo [H, Q3]**. César pondera o impacto de restringir a autonomia de um paciente que ainda preserva lucidez parcial, equilibrando o risco severo de um acidente de trânsito com o dano psicológico de uma limitação precipitada, **sabendo que a aceitação dessa conduta por parte da família e do paciente só poderá ser avaliada com segurança nos retornos dos meses seguintes [H, Q5]**.

### 4. Elementos extraídos

| Elemento | Evidência no cenário |
|---|---|
| Ator(es) | Dr. César Andrade de Melo (neurologista, P02); Sr. Roberto Mendes (paciente); filha do paciente |
| Objetivo(s) | Avaliar capacidade funcional e autonomia cotidiana diante de evidências clínicas contraditórias |
| Contexto | Consultório neurológico especializado; decisão de alto impacto ético e pessoal |
| Recursos/informações | Prontuário eletrônico; escores MMSE; laudo de MRI; relato da família |
| Ações | Confrontar dados objetivos e subjetivos; ponderar riscos e autonomia; considerar exames complementares |
| Problemas/rupturas | Conflito entre testes numéricos estáveis e relato de incidentes cotidianos; ausência de ferramentas de suporte para autonomia |
| Consequências | Risco de permitir condutor inapto versus o risco de restringir injustamente a liberdade civil |

### 5. Implicações para the próximas entregas

- Integrar a discussão deste cenário no escopo de suporte à decisão clínica, demonstrando como a explicabilidade multimodal da IA pode auxiliar especialistas a visualizar discrepâncias entre biomarcadores e manifestações funcionais relatadas.

---

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
