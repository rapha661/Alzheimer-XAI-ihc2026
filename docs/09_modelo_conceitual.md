# Entrega 9 — Modelo conceitual e design centrado na comunicação

**Data:** 16/11/2026  
**Status:** 🟨 em andamento  
**Responsabilidade:** soluções individuais, com consolidação da equipe para mapa de objetivos e esquema de signos.

## Objetivo da atividade

Passar do cenário de problema para uma concepção da interação, explicitando objetivos, tópicos de conversa, falas e signos que a interface deverá comunicar/manipular.

## Transformando resultados técnicos em conceitos compreensíveis

Em TCCs algorítmicos ou orientados a dados, esta entrega deve evitar que a interface exponha apenas estruturas internas do código. Identifique os **conceitos e signos que fazem sentido para o usuário**.

Exemplos:

- `query plan`, custo estimado, recomendação e impacto para um DBA;
- modelo, dataset, versão, execução e métrica para engenheiro de IA;
- período, indicador, grupo, tendência e filtro para gestor/analista;
- alerta, severidade, evidência, responsável e status para analista de segurança.

Se um termo técnico for necessário, modele como será comunicado, explicado e relacionado à tarefa.

Dashboards, relatórios, filtros e CRUDs devem aparecer no modelo conceitual por meio dos **objetivos, signos e conversas** que justificam sua existência.

## 1. Cenários de interação

Para cada cenário de problema, produza uma versão em que a solução já pode ser descrita. **Destaque claramente o texto alterado** em relação ao cenário original.

### CI01 — O laudo que registrou o que foi avaliado

**Autor(a):** Raphael Garavati Erbert — 22.123.014-7  
**Origem:** cenário problema C01 — "O laudo que não disse nada" (P03, tarefa T02)

*Em **negrito**, o texto novo ou alterado em relação ao cenário refinado C01 da Entrega 4; em ~~tachado~~, o texto retirado.*

Numa quarta-feira à tarde, a Dra. Helena Siqueira Prado, radiologista de um serviço de telerradiologia, tem 41 exames na fila de laudos, vindos de hospitais diferentes. O serviço opera sob metas estritas de prazo por exame, monitoradas por relatórios de produtividade. Ela abre a ressonância de crânio de um paciente idoso. ~~O pedido diz apenas "RM de crânio — investigação de déficit cognitivo", e o campo de dados clínicos traz só a idade. Esses dados clínicos foram repassados de forma resumida pelo técnico do hospital de origem.~~ **Junto das imagens, o caso traz a pergunta clínica escrita pelo solicitante ("queixa de memória há cerca de um ano; distinguir declínio esperado para a idade de doença de Alzheimer") e um bloco de contexto clínico com idade, escolaridade e o MMSE mais recente, com a data de aplicação.** Helena percorre os cortes e nota que os hipocampos parecem um pouco reduzidos, mas não o suficiente para afirmar atrofia com segurança. Não há exame anterior para comparar. ~~Ela pensa em medir, mas fazer a medição à mão levaria um tempo que a fila não permite; o PACS do serviço dispõe apenas de ferramentas de medidas lineares, carecendo de volumetria automática para o hipocampo.~~ **Ela abre a análise do modelo, apresentada como segunda leitura: o volume hipocampal enviado ao modelo aparece com a proporção em relação ao volume intracraniano (ou marcado como "imputado", quando não foi informado), e o mapa de atenção aparece sobreposto a um corte axial. A tela informa que o mapa mostra onde o modelo se apoiou, e não uma lesão, e que o modelo não foi validado na população brasileira.** Enquanto analisa o caso, chegam exames de urgência (como suspeita de AVC) que ganham prioridade imediata na fila. **Helena suspende o laudo e, ao voltar, encontra o caso no ponto em que parou, com a anotação de dúvida que tinha deixado.** ~~Sem ferramentas objetivas e sem contexto clínico, Helena opta por escrever uma frase cautelosa ("Redução volumétrica hipocampal discreta... Correlacionar com dados clínicos") para se proteger de falsos positivos, sem dispor de um canal ágil para sanar a dúvida com o solicitante ou de auditoria interna que avalie o impacto dessa inconclusão no destino do paciente.~~ **Com a pergunta clínica e uma referência objetiva à mão, Helena descreve o achado e preenche, em campos próprios do laudo, o que avaliou, por qual método (inspeção visual e volume informado) e a dúvida que permanece. A conclusão continua sendo dela. Como a dúvida depende de um dado que só o solicitante tem, ela envia uma pergunta ligada ao próprio exame, sem travar a fila.** Libera o laudo e abre o próximo exame.

### Diferenças relevantes

| Alteração | Por que foi necessária | Evidência/artefato que justifica |
|---|---|---|
| A pergunta clínica e o contexto clínico mínimo acompanham o exame | Sem eles, a seleção de T02 recai em "prosseguir só com os dados recebidos", e a dúvida passa para a conclusão | H08; T02 HTA 1.2 e 1.3 (Entrega 5); C01 Q3 |
| O volume hipocampal e o mapa de atenção aparecem como segunda leitura, sem regiões nomeadas nem percentil | A medida manual não cabe no prazo da fila; a referência objetiva não pode afirmar mais do que o modelo calcula | T02 HTA 2.3.3 e GOMS GOAL 2.6; Entrega 6, seção 5.2 (o que o modelo produz) |
| O laudo suspenso preserva a etapa e a dúvida registrada | A urgência interrompe o laudo, e a dúvida não fica registrada em lugar nenhum | T02 CTT, operador `\|>`; C01 Q5 |
| Campos do laudo para método e dúvida | A frase cautelosa devolve a dúvida ao médico clínico, que não interpreta RM | T02 HTA 3.3 (recomendação); P01 (Entrega 3) |
| Pergunta ao solicitante ligada ao exame | Não há canal ágil com o solicitante | T02 HTA 1.3.1 (recomendação); C01 Q6 |

### CI02 — O parecer que ficou no caso

**Autor(a):** Paulo Hudson Josué da Silva — 22.222.013-9  
**Origem:** cenário problema C02 — "O parecer que se perdeu" (P01, tarefa T01)

*Em **negrito**, o texto novo ou alterado em relação ao cenário refinado C02 da Entrega 4; em ~~tachado~~, o texto retirado.*

Dois meses atrás, o Dr. Marcos Andrade encaminhou informalmente o Sr. Ivo Bittencourt, 71 anos, ao neurologista Dr. César Andrade de Melo, após identificar um MMSE limítrofe e um laudo de MRI pouco conclusivo. Como a fila oficial de encaminhamento levaria meses e o quadro não parecia grave o suficiente para justificar a espera, Marcos preferiu resolver por conhecimento pessoal. Ligou para César, que atendeu o caso como favor entre colegas. César respondeu que os achados eram "compatíveis com comprometimento cognitivo leve, sem elementos fortes para Alzheimer neste momento" e sugeriu reavaliação em seis meses. ~~Marcos anotou rapidamente "neuro: sem AD por ora, reavaliar" numa nota de rodapé do prontuário. Como o prontuário eletrônico atual não possui campos estruturados para distinguir pareceres informais de anotações comuns, os critérios técnicos exatos utilizados por César para afastar Alzheimer não foram gravados no sistema.~~ **Ainda durante a ligação, Marcos registrou o parecer no caso do paciente, em campos próprios: quem deu o parecer, a data, o canal ("telefone"), a conclusão, os critérios citados por César (redução hipocampal discreta para a idade, MMSE compatível com a escolaridade, autonomia preservada), os exames que ele revisou e a recomendação de reavaliar em seis meses. O registro ficou identificado como parecer de especialista, separado das anotações de rotina.**

Hoje, o Sr. Ivo retorna à consulta acompanhado do filho, relatando piora perceptível da memória nas últimas semanas. ~~Marcos abre o prontuário e encontra apenas essa anotação breve. Ele não lembra quais exames o neurologista revisou, nem por que descartou Alzheimer naquele momento.~~ **Marcos localiza o caso pela busca e encontra o parecer de César no topo, com os critérios e os exames que o sustentaram. Ele reaplica o MMSE, e o bloco de contexto clínico mostra o escore anterior e o atual lado a lado, separado dos dados que entram no modelo.** A agenda do dia está cheia. ~~Tenta ligar para César, mas ele está em cirurgia e não retorna a tempo da consulta. Na ausência de um canal estruturado para resgatar o histórico, Marcos estima que gastaria preciosa parte da consulta tentando auditar papéis físicos ou registros dispersos.~~ **César está em cirurgia, mas Marcos não precisa ligar: confronta a piora relatada com os critérios registrados. Ele também consulta a sugestão do modelo para o exame mais recente, que mostra separadamente a probabilidade da classe e a confiabilidade dessa estimativa, as variáveis que mais pesaram e os limites do modelo.** Marcos precisa decidir se pede um novo exame do zero, se reencaminha o paciente ao mesmo neurologista — sobrecarregando a fila oficial — ou se toma uma conduta sozinho, ~~sem o contexto completo da avaliação anterior~~ **agora com o contexto da avaliação anterior. Ele registra a decisão, marca como evidências consideradas o parecer de César e os dois escores, e confere o registro gravado com seu nome e horário, ligado ao parecer anterior.** ~~Qualquer que seja a conduta tomada nesta consulta, Marcos só saberá se ela foi adequada caso ocorra uma nova piora clínica perceptível ou se o paciente for atendido posteriormente por outro colega.~~ **Qualquer que seja a conduta, quem abrir o caso depois encontrará, em ordem, o raciocínio de César e o de Marcos.**

### Diferenças relevantes

| Alteração | Por que foi necessária | Evidência/artefato que justifica |
|---|---|---|
| Parecer de especialista registrado em campos próprios (autor, data, canal, conclusão, critérios, exames, recomendação) | O raciocínio do especialista existia só na ligação; o método de reconstrução pelos exames termina numa inferência que o clínico não domina | H06; T01 HTA 2.2 e 2.3, GOMS M2 (Entrega 5); feedback da Entrega 5: preservar a continuidade do raciocínio, não reduzir a solução a "reabrir caso" |
| Parecer identificado como tal, separado das anotações de rotina | A nota de rodapé se mistura às anotações comuns | T01 HTA 2.2 (recomendação); C02 Q1 |
| Escores anterior e atual lado a lado, fora dos dados do modelo | O novo escore só tem valor se comparado ao anterior; MMSE e MoCA não entram no modelo, mas são contexto da decisão | T01 HTA 1.2; Entrega 6, seção 5.2 (bloco "Contexto clínico") |
| Probabilidade da classe e confiabilidade da estimativa como signos separados | Um percentual alto com confiabilidade baixa é o caso perigoso, e os dois eram lidos como uma coisa só | H03; Entrega 6, seção 5.2; Entrega 8, MU06 |
| Decisão ligada ao parecer anterior, com as evidências marcadas | Sem a ligação, a próxima retomada repete o problema | T01 HTA 4; F05 (`RASTREABILIDADE.md`); H15 em aberto (correção por adendo) |

### CI04 — A decisão com as evidências lado a lado

**Autor(a):** Ana Carolina Lazzuri — 22.123.001-4  
**Origem:** cenário problema C04 — "A dúvida sobre a autonomia do paciente" (P02, tarefa T04)

*Em **negrito**, o texto novo ou alterado em relação ao cenário refinado C04 da Entrega 4; em ~~tachado~~, o texto retirado.*

Numa tarde de quinta-feira, o Dr. César Andrade de Melo, neurologista, atende o Sr. Roberto Mendes, 76 anos, acompanhado de sua filha. Na consulta anterior, os testes cognitivos (MMSE) e o laudo de ressonância magnética indicavam um quadro limítrofe de declínio leve. No entanto, a filha relata episódios recentes preocupantes: o paciente se perdeu voltando da padaria e apresentou pequenos lapsos ao gerenciar contas domésticas, embora insista veementemente em continuar dirigindo seu automóvel. César precisa decidir se emite um laudo restritivo recomendando a suspensão da CNH e maior supervisão domiciliar. **Durante a consulta, ele registra no caso cada episódio relatado pela filha, com a data aproximada e a atividade afetada (deslocamento, finanças, direção).**

~~Ele analisa os dados objetivos do prontuário, que mostram pontuação estável, confrontando-os com o relato empírico da filha. Na ausência de um protocolo padronizado no sistema para ponderar relatos subjetivos de familiares frente a métricas de exames de imagem, César precisa ponderar a decisão com base em sua experiência clínica pessoal.~~ **A tela de evidências mostra lado a lado a evolução do MMSE, a conclusão do laudo de MRI, a sugestão do modelo — com a probabilidade da classe e a confiabilidade da estimativa — e os episódios relatados em uma linha do tempo. Um aviso fixo junto da sugestão informa que o modelo analisa padrões de imagem e dados clínicos e não avalia capacidade funcional nem aptidão para dirigir. Com as fontes reunidas, César percebe que os episódios são posteriores ao último teste; a ponderação continua sendo dele.** Para mitigar o risco de uma restrição abrupta sem respaldo inequívoco, ele considera como alternativa solicitar uma avaliação neuropsicológica complementar antes de emitir um parecer definitivo. César pondera o impacto de restringir a autonomia de um paciente que ainda preserva lucidez parcial, equilibrando o risco severo de um acidente de trânsito com o dano psicológico de uma limitação precipitada. **Ele registra a conduta, as evidências que considerou e a divergência encontrada entre o relato e os escores.** ~~sabendo que a aceitação dessa conduta por parte da família e do paciente só poderá ser avaliada com segurança nos retornos dos meses seguintes~~ **A aceitação da conduta continua a ser acompanhada nos retornos, mas agora cada retorno parte do que foi decidido e por quê, e os novos episódios entram na mesma linha do tempo.**

### Diferenças relevantes

| Alteração | Por que foi necessária | Evidência/artefato que justifica |
|---|---|---|
| Episódios relatados registrados com data e atividade afetada | O relato era oral e ficava em texto livre, sem data | T04 HTA 1.1; Entrega 7, A02; `RASTREABILIDADE.md`, R04 |
| Escores, laudo, sugestão e relato lado a lado | O confronto entre as fontes acontecia só no raciocínio do médico | T04 HTA 2.1 e CTT ("Confrontar as evidências" como tarefa do usuário) |
| Aviso fixo de que o modelo não avalia autonomia | A sugestão não pode ser lida como resposta sobre dirigir ou morar sozinho | Feedback da Entrega 5 sobre T04; Entrega 8, restrições e MU02 |
| Registro da conduta com evidências consideradas e divergência | O conflito entre avaliação objetiva e relato era registrado em texto livre | T04 HTA 4.2; C04 Q4 |
| Retornos partem da decisão registrada | A aceitação da conduta só aparece nos retornos seguintes | C04 Q5; T04 HTA 3.3 |

## 2. Design centrado na comunicação

**Nome do cenário:** CI01 — O laudo que registrou o que foi avaliado (Raphael Garavati Erbert)

| Tópico > subtópico | Falas e signos envolvidos | Intenção/efeito esperado |
|---|---|---|
| Laudar com contexto clínico e referência | `D: "Fila de laudos — 41 exames; urgências no topo"` / `U: abre o próximo exame` | Começar pelo exame sem perder a visão da fila |
| > Ler a pergunta clínica | `D: "Pergunta clínica: distinguir declínio esperado para a idade de doença de Alzheimer"` · `D: "Contexto clínico: 72 anos · 11 anos de escolaridade · MMSE 25, aplicado em 03/09"` | A leitura do caso limítrofe parte da dúvida de quem pediu o exame |
| > Consultar a referência objetiva | `U: abre "Análise do modelo (segunda leitura)"` / `D: "Hipocampo: 5.900 mm³ · 0,39% do volume intracraniano"` ou `D: "Hipocampo: imputado — valor estimado pelo modelo"` | Dar uma referência objetiva sem substituir a leitura; deixar claro quando o número foi estimado |
| > Ver o mapa de atenção | `D: corte axial com o mapa de atenção sobreposto` · `D: "O mapa mostra onde o modelo se apoiou, não uma lesão"` / `U: compara o mapa com a própria leitura dos cortes` | Evitar que o destaque seja lido como achado anatômico |
| > Retomar após interrupção | `D: "Urgência na fila — suspender este laudo?"` / `U: "Suspender"` · `D: "Laudo suspenso · dúvida anotada: volume limítrofe para a idade"` | Voltar ao caso no ponto em que parou |
| > Registrar método e dúvida | `U: preenche "Método: inspeção visual + volume informado"` e `"Dúvida: redução discreta, sem exame anterior"` / `D: "Esses campos acompanham o laudo para o solicitante"` | O laudo diz o que foi avaliado, em vez de só pedir correlação clínica |
| > Perguntar ao solicitante | `U: "Enviar pergunta ao solicitante"` / `D: "Pergunta enviada pelo exame — a resposta aparece neste caso"` | Resolver a dúvida sem travar a fila |

**Nome do cenário:** CI02 — O parecer que ficou no caso (Paulo Hudson Josué da Silva)

| Tópico > subtópico | Falas e signos envolvidos | Intenção/efeito esperado |
|---|---|---|
| Registrar parecer de especialista | `U: "Registrar parecer"` / `D: campos "Especialista", "Data", "Canal", "Conclusão", "Critérios considerados", "Exames revisados", "Recomendação"` | Transformar a ligação em um registro recuperável, com a origem explícita |
| > Confirmar o registro | `D: "Parecer de Neurologia — Dr. César Andrade de Melo · 29/08 · por telefone"` | O parecer fica identificado como tal, separado das anotações de rotina |
| Retomar o raciocínio do parecer anterior | `U: busca "Ivo"` / `D: lista com o caso, o status e a data do último registro` | Localizar o caso sem percorrer evoluções |
| > Consultar o parecer | `D: "Compatível com comprometimento cognitivo leve, sem elementos fortes para Alzheimer neste momento" · "Critérios: …" · "Reavaliar em 6 meses"` | Recuperar o raciocínio sem depender da memória nem do telefone |
| > Comparar escores | `D: "Contexto clínico (não entra no cálculo da sugestão): MMSE 26 em 29/08 · 23 hoje"` | Ver a variação sem misturar contexto clínico com entrada do modelo |
| Interpretar a sugestão explicada | `D: "Probabilidade da classe: 64% — padrão compatível com Alzheimer"` · `D: "Confiabilidade desta estimativa: moderada"` | Ler os dois números como coisas diferentes |
| > Ver o que mais pesou | `D: "O que mais pesou neste caso: volume do hipocampo, em direção a Alzheimer"` · `D: "Mostra o que pesou no modelo, não a causa da doença"` | Julgar se a sugestão se apoia em algo clinicamente plausível ou em algo que deve gerar desconfiança |
| > Conhecer os limites | `D: "Treinado na ADNI; não validado no Brasil" · "Distingue só normal e Alzheimer; não avalia comprometimento leve"` | Calibrar a confiança antes de decidir |
| Registrar decisão e justificativa | `U: escolhe "Concordo parcialmente", escreve a conduta e marca as evidências "Parecer de Neurologia" e "MMSE"` / `D: "A decisão será gravada com seu nome e horário e ficará ligada ao parecer de 29/08"` | Tornar a decisão rastreável e conectada ao raciocínio anterior |
| > Conferir o registro | `U: "Registrar decisão"` / `D: "Decisão registrada · Dr. Marcos Andrade · 13/11, 10:42"` | Verificar que o objetivo foi atingido (operador de verificação do GOMS T01) |

**Nome do cenário:** CI04 — A decisão com as evidências lado a lado (Ana Carolina Lazzuri)

| Tópico > subtópico | Falas e signos envolvidos | Intenção/efeito esperado |
|---|---|---|
| Confrontar evidências divergentes | `U: abre o caso do Sr. Roberto` / `D: "Evidências do caso"` | Reunir as fontes num só lugar |
| > Registrar episódio relatado | `U: "Adicionar episódio"` / `D: campos "Data aproximada", "Atividade afetada (deslocamento, finanças, direção, outra)", "Relatado por", "Descrição"` | Tirar o relato do texto livre e datá-lo |
| > Ver as fontes lado a lado | `D: linha do tempo com "MMSE 27 (02/06) · 27 (13/11)", "Laudo de MRI: alterações limítrofes", episódios de 20/10 e 02/11` | Mostrar que os episódios são posteriores ao último teste |
| Interpretar a sugestão explicada | `D: "Probabilidade da classe: 58% — padrão compatível com Alzheimer · Confiabilidade desta estimativa: baixa"` | Ler a sugestão com a confiabilidade ao lado |
| > Reconhecer o que o modelo não avalia | `D: "O modelo analisa padrões de imagem e dados clínicos. Não avalia capacidade funcional nem aptidão para dirigir."` | Evitar que o score determine a conduta sobre a autonomia |
| Registrar decisão e justificativa | `U: escreve a conduta "solicitar avaliação neuropsicológica antes de parecer sobre direção"` e marca as evidências | A decisão fica com as fontes que a sustentaram |
| > Registrar a divergência | `U: preenche "Divergência: escores estáveis × episódios recentes relatados"` / `D: "A divergência aparecerá no próximo retorno"` | O retorno parte do conflito já identificado |
| > Conferir o registro | `D: "Decisão registrada · Dr. César Andrade de Melo · 13/11, 15:20"` | Verificar que o registro foi gravado |

**Convenção:** `U` = usuário; `D` = preposto do designer/sistema, conforme a abordagem de Engenharia Semiótica adotada na disciplina.

## 3. Mapa de objetivos

Cada integrante apresenta seu mapa e a equipe cria um **mapa consolidado**, eliminando duplicidades e resolvendo conflitos de nomenclatura.

![Mapa de objetivos — Raphael Garavati Erbert (P03, CI01)](../assets/09_modelo_conceitual/mapa_objetivos_p03.svg)

![Mapa de objetivos — Paulo Hudson (P01, CI02)](../assets/09_modelo_conceitual/mapa_objetivos_p01.svg)

![Mapa de objetivos — Ana Carolina Lazzuri (P02, CI04)](../assets/09_modelo_conceitual/mapa_objetivos_p02.svg)

![Mapa consolidado](../assets/09_modelo_conceitual/mapa_objetivos.svg)

### Dicionário de objetivos

| ID | Objetivo | Persona(s) | Cenário(s) | Prioridade |
|---|---|---|---|---|
| O01 | {{...}} | {{P01}} | {{CI01}} | {{...}} |

## 4. Esquema conceitual de signos

Consolide as informações em **uma tabela única**.

| Grupo | Signo | Origem | Observações/semântica | Tipo de conteúdo | Restrição | Valor padrão | Prevenção | Recuperação |
|---|---|---|---|---|---|---|---|---|
| Credenciais | usuário | domínio | {{...}} | texto | não nulo | — | {{...}} | {{...}} |

### Regras para os signos

- Use o vocabulário do domínio do usuário.
- Evite duplicar o mesmo conceito com nomes diferentes.
- Diferencie informação fornecida pelo usuário, produzida pelo sistema e derivada do domínio.
- Registre prevenção e recuperação apenas quando fizer sentido; explique as siglas usadas.

## Síntese

Quais objetivos/tópicos/signos deverão necessariamente aparecer nos diagramas MoLIC?

## Checklist

- [ ] Cenários de interação mostram alterações em relação aos cenários de problema.
- [ ] Cada solução individual identifica autor e cenário de origem.
- [ ] Tópicos/falas/signos são coerentes com objetivos do usuário.
- [ ] Mapas individuais foram consolidados.
- [ ] O esquema de signos está em uma tabela única e sem duplicações conceituais.
- [ ] Nomes de objetivos/signos serão reutilizados na Entrega 10.
- [ ] Em TCC técnico, signos representam conceitos do domínio compreensíveis ao usuário, não apenas variáveis/estruturas internas.
- [ ] Padrões como dashboard, relatório, filtros, administração e CRUD possuem objetivos e signos correspondentes.
- [ ] A interface comunica não só o resultado técnico, mas também seu significado para a tarefa.
