# Entrega 12 — Planejamento da avaliação de usabilidade (DECIDE)

**Data:** 14/11/2026  
**Status:** 🟨 entrega parcial: metas provisórias até a Entrega 8; versão do protótipo pendente da montagem no Figma (Entrega 11)  
**Responsabilidade:** 1 solução por equipe. Redação desta versão: Nathan Gabriel da Fonseca Leite — 22.123.028-7.

## Situação desta entrega

O plano depende de três entregas anteriores, e só uma delas está pronta:

| Depende de | Situação | Como o plano lida com isso |
|---|---|---|
| Metas de usabilidade (Entrega 8) | não iniciada | A seção [Metas de usabilidade provisórias](#metas-de-usabilidade-provisórias) define seis metas, MU01 a MU06, só para este plano ter critério de sucesso **antes** da coleta. A Entrega 8 deve adotá-las, ajustá-las ou substituí-las; se mudarem, as perguntas QA e os critérios das tarefas UT mudam junto |
| Protótipo (Entrega 11) | parcial: telas prontas, falta montar o arquivo no Figma | As tarefas usam as telas e ligações da Entrega 11. O link entra no item "Protótipo/versão" quando o arquivo existir |
| MoLIC (Entrega 10) | não iniciada | As tarefas são ligadas aos fluxos da Entrega 6 e às tarefas da Entrega 5. Quando o MoLIC existir, a coluna "objetivo oculto" ganha a referência M0x |

## O que está sendo avaliado

A interface foi ampliada na disciplina a partir do aplicativo previsto no TCC. **Esta avaliação investiga a qualidade da interação com o protótipo, não a validade científica nem o desempenho do modelo M-XAI.**

| A avaliação **responde** | A avaliação **não responde** |
|---|---|
| Se o médico distingue a probabilidade da classe da confiabilidade da estimativa | Se a probabilidade está correta para aquele paciente |
| Se o médico percebe o aviso de confiabilidade baixa antes de concordar | Se a confiabilidade foi bem calculada |
| Se o médico entende que o contexto clínico não entra no modelo | Se o modelo deveria usar MMSE e MoCA |
| Se o médico lê "o que mais pesou" como explicação do modelo, e não como causa da doença | Se as contribuições SHAP e o mapa Grad-CAM estão corretos |
| Se o técnico percebe e corrige um arquivo errado ou um valor fora da faixa antes de enviar | Se a conferência automática do arquivo é tecnicamente viável |
| Se o técnico se recupera de uma falha sem recomeçar o caso | Por que a análise falha |

**Dados e processamentos simulados.** Todas as sugestões, probabilidades, confiabilidades, contribuições por variável e mapas Grad-CAM do protótipo são valores fixos por caso. A conferência do arquivo, a validação de faixa e o reenvio com dados mantidos não existem na plataforma, só no protótipo. Os pacientes são fictícios, e as imagens são recortes dos prints da plataforma. Os erros que o técnico encontra (série FLAIR, volume intracraniano digitado errado) são **plantados** no protótipo para observar a reação a eles. A seção "O que é simulado e o que é integrado" da [Entrega 11](11_figma.md) detalha cada item.

## A. Método DECIDE

| Etapa | Aplicação no projeto |
|---|---|
| **D — Determine the goals** | Verificar se as correções da Entrega 6 que viraram tela na Entrega 11 resolvem os problemas que as motivaram: (1) o médico lê probabilidade e confiabilidade como coisas diferentes e calibra a confiança pela segunda (H03); (2) o médico não registra um "concordo" automático num caso de confiabilidade baixa; (3) o técnico detecta erros do exame **antes** de liberar o paciente (H07); (4) o técnico se recupera de uma falha sem redigitar dados (H13). Metas MU01 a MU06, provisórias até a Entrega 8 |
| **E — Explore the questions** | Doze perguntas de avaliação (QA01 a QA12, seção B). Cada uma tem método, evidência e critério definidos agora, antes da coleta. As perguntas sobre interpretação (QA01 a QA03, QA11) não podem ser respondidas só por inspeção: dependem do que o participante diz que entendeu |
| **C — Choose the evaluation paradigm and techniques** | **Inspeção heurística** (Nielsen, H1–H10) por cada integrante, sobre as 21 telas, na Entrega 13. Ela vem primeiro porque é barata e acha problemas de consistência e de feedback sem gastar participante. Depois, **observação de usuários com tarefas e pensar em voz alta** na Entrega 14, porque as perguntas centrais são de compreensão (o que o médico entende do número e do aviso), e só a fala do participante mostra isso. Questionários curtos (SEQ após cada tarefa, SUS no fim) dão a medida de satisfação. Não se usa teste A/B nem medição remota não moderada: com quatro participantes, o valor está no qualitativo |
| **I — Identify the practical issues** | Quatro participantes externos à equipe: dois no perfil médico (P01) e dois no perfil técnico em radiologia (P04). Recrutar profissionais reais é difícil, então estudantes avançados entram como *proxy* declarado. Sessões remotas por videochamada, com o protótipo aberto no navegador do participante, ou presenciais na FEI. Um piloto com integrante da equipe antes da primeira sessão. Cada integrante conduz um participante. Riscos: link do Figma pedindo login, ligação faltando numa tarefa, participante médico que tenta avaliar o diagnóstico em vez de usar a interface. Detalhes na seção C |
| **D — Decide how to deal with ethical issues** | Consentimento livre e esclarecido antes de qualquer registro, com o modelo do repositório adaptado (seção E). Avaliação de interface com profissionais, sem dados de pacientes reais, sem intervenção clínica e sem coleta de dados sensíveis, no espírito da Resolução CNS 510/2016 e da LGPD (Lei 13.709/2018). Gravação de tela e áudio só com autorização e pelo tempo da disciplina. Participantes identificados como U01 a U04. Ao fim, o participante é informado de que o protótipo **não** é ferramenta clínica validada, para que não saia da sessão achando que o modelo pode ser usado em pacientes |
| **E — Evaluate, interpret and present the data** | Sucesso, tempo, erros, ajudas, SEQ e SUS por tarefa e participante, comparados às metas MU. Falas codificadas por pergunta QA. Problemas consolidados com os da inspeção heurística, classificados por severidade (0–4) e frequência, e cada um ligado à tela, à pergunta QA e à hipótese que afeta. Resultado apresentado em tabelas na Entrega 14 e registrado na `RASTREABILIDADE.md` (coluna "Tarefa no teste" e "Decisão/melhoria"). Seção F |

## Metas de usabilidade provisórias

> Provisórias até a Entrega 8. Com dois participantes por perfil, metas quantitativas são **indicativas**: um único participante muda o resultado em 50%. Por isso elas são escritas como "os dois participantes" e lidas junto das falas.

| ID | Dimensão | Métrica | Tarefa | Meta | Justificativa |
|---|---|---|---|---|---|
| MU01 | compreensão | participantes que descrevem probabilidade e confiabilidade como informações diferentes | UT01 | 2 de 2 médicos | É a correção 8 da Entrega 6. Se um dos dois ainda misturar, a separação visual não bastou |
| MU02 | eficácia | participantes que registram a decisão com justificativa, sem ajuda, e reconhecem o registro em UI09 | UT02 | 2 de 2 médicos | Registrar é o fim de T01 e T04; reconhecer o registro é o operador de verificação do GOMS T01 (OP. 4.4) |
| MU03 | prevenção de erro | participantes que trocam a série errada **e** corrigem o volume fora da faixa antes de enviar | UT04 | 2 de 2 técnicos | É a correção 5 e o núcleo de H07: o erro precisa ser resolvido com o paciente ainda no setor |
| MU04 | recuperação de erro | participantes que reenviam pelo próprio caso, sem criar um caso novo | UT05 | 2 de 2 técnicos | É a correção 6. Na sessão da Entrega 6, o participante não concluiu essa tarefa |
| MU05 | eficiência | tempo da tela de falha até o reenvio | UT05 | ≤ 90 s | O reenvio deveria ser trocar um arquivo; mais que isso sugere que o caminho não está claro |
| MU06 | satisfação | SEQ (1–7) por tarefa; SUS (0–100) no fim | todas | SEQ ≥ 5 em todas as tarefas; SUS ≥ 68 | 68 é a média de referência do SUS. SEQ abaixo de 5 indica que a tarefa foi percebida como difícil |

## B. Perguntas de avaliação

| ID | Pergunta | Método | Métrica/evidência | Critério esperado |
|---|---|---|---|---|
| QA01 | O médico distingue a probabilidade da classe da confiabilidade da estimativa? | observação + pergunta pós-tarefa | resposta à pergunta "o que significa 'Confiabilidade: alta'?"; fala durante UT01 | MU01 |
| QA02 | O médico percebe o aviso de confiabilidade baixa e o leva em conta antes de concordar? | observação (UT02) | menção ao aviso, em fala ou na justificativa; tempo parado em UI05c | os dois médicos mencionam a confiabilidade baixa na fala ou na justificativa |
| QA03 | O médico entende que o contexto clínico não entra no cálculo da sugestão? | pergunta pós-tarefa (UT01) | resposta a "o MMSE deste paciente influenciou a sugestão?" | os dois respondem que não |
| QA04 | O médico encontra rapidamente os casos que aguardam revisão? | observação (UT03) | sucesso, tempo, caminho usado (contador, busca ou rolagem) | sucesso sem ajuda em até 60 s |
| QA05 | O médico registra a decisão completa e reconhece que ela foi gravada? | observação (UT02) | sucesso, erros (campos pendentes), fala diante de UI09 | MU02 |
| QA06 | O técnico percebe que escolheu a série errada e sabe o que fazer? | observação (UT04) | reação a UI06c; fala; ação seguinte | MU03 |
| QA07 | O técnico corrige um valor fora da faixa antes de enviar? | observação (UT04) | reação a UI06b; se procura o laudo de volumetria | MU03 |
| QA08 | O técnico se recupera de uma falha sem recriar o caso nem redigitar dados? | observação (UT05) | caminho, tempo, fala sobre os dados mantidos | MU04 e MU05 |
| QA09 | O técnico entende o estado do processamento e quando pode liberar o paciente? | pergunta pós-tarefa (UT04) | resposta a "a paciente já pode ir embora?" | os dois respondem que é melhor aguardar a análise |
| QA10 | Quais violações das heurísticas de Nielsen as telas têm, e com que severidade? | inspeção heurística (Entrega 13) | violações H1–H10, severidade 0–4 | nenhuma violação de severidade 4 nas telas das tarefas UT01–UT05 |
| QA11 | O médico lê "o que mais pesou neste caso" como explicação do modelo, e não como causa da doença? | pergunta pós-tarefa (UT02) | resposta a "o estado civil pesou contra Alzheimer neste caso; o que você conclui disso?" | os dois tratam como algo do modelo, que pode levar a desconfiar dele, e não como achado clínico |
| QA12 | O médico precisaria corrigir ou complementar uma decisão já registrada? | entrevista pós-teste | resposta e exemplos | sem critério: é coleta exploratória para H15 |

## C. Escopo e participantes

| Item | Planejamento |
|---|---|
| Perfis | **Médico** (P01): médico clínico ou generalista, ou residente de clínica médica. **Técnico** (P04): técnico ou tecnólogo em radiologia que opere ressonância magnética |
| Critérios de inclusão | Médico: atende ou já atendeu pacientes com queixa cognitiva. Técnico: já realizou exame de ressonância de crânio. Ambos: conseguem usar navegador em computador |
| Critérios de exclusão | Integrantes da equipe; quem já viu o protótipo (inclusive o participante da simulação da Entrega 6); neurologistas e radiologistas (são outro perfil: P02 e P03) |
| *Proxy*, se não houver profissionais | Médico: estudante de Medicina no internato. Técnico: estudante de curso técnico ou tecnólogo em radiologia com estágio em ressonância. A condição de *proxy* é registrada e entra como limitação na análise |
| Recrutamento | Contatos da coleta da Entrega 7 e da rede pessoal da equipe. Convite por mensagem, com duração e formato. Sem incentivo financeiro |
| Nº de participantes | 4, como pede a Entrega 14: U01 e U02 (médicos), U03 e U04 (técnicos) |
| Ambiente | Remoto (videochamada com compartilhamento de tela do participante) ou presencial (laboratório da FEI). O formato é o mesmo para os dois participantes do mesmo perfil |
| Dispositivo | Computador com tela de pelo menos 1366 px de largura; protótipo do Figma no modo de apresentação, em tela cheia |
| Protótipo/versão | {{link do protótipo da Entrega 11 e data da versão}}. Pontos de partida: **Médico** (UI01) para UT01–UT03; **Técnico — envio** (UI06) para UT04; **Técnico — falha** (UI08) para UT05 |
| Duração | 30 a 40 minutos por sessão |
| Papéis em cada sessão | Um moderador (conduz e lê as instruções) e um observador (preenche a planilha e cronometra) |
| Responsáveis (proposta, a confirmar pela equipe) | U01: Paulo Hudson · U02: Ana Carolina Lazzuri · U03: Raphael Garavati Erbert · U04: Nathan Gabriel da Fonseca Leite |
| Teste piloto | {{data}}, antes da primeira sessão, com um integrante da equipe no papel de cada perfil (não conta na amostra). Valida: link sem pedir login, todas as ligações das tarefas, clareza das instruções, duração, gravação. Mudanças após o piloto são registradas na Entrega 14 |
| Riscos e mitigação | Link pede login → testar em janela anônima no piloto. Ligação faltando → percorrer as cinco tarefas no piloto. Participante médico tenta avaliar se o diagnóstico está certo → a abertura explica que o modelo não está sendo avaliado, e o moderador redireciona uma vez, com frase padronizada. Queda de conexão → retomar da tarefa interrompida e registrar |

## D. Lista de tarefas de avaliação

| ID | Cenário neutro entregue ao participante | Objetivo oculto da avaliação | Critério de sucesso | Tempo-limite |
|---|---|---|---|---|
| UT01 | **(médico)** "O Sr. Ivo Bittencourt, 71 anos, voltou ao seu consultório. Ele fez uma ressonância nova esta semana. Veja o que a plataforma diz sobre o exame dele e me conte, com suas palavras, o que ela sugere e o quanto você levaria isso em conta." | PF01; T01 (HTA 1.2, 2.2); QA01, QA03 | **Total:** abre o caso e descreve a sugestão **e** a confiabilidade como coisas distintas. **Parcial:** abre o caso, mas só fala do percentual. **Falha:** não chega ao caso | 5 min |
| UT02 | **(médico)** "A filha do Sr. Roberto Mendes, 76 anos, está preocupada porque ele continua dirigindo. O exame dele já foi analisado. Revise o caso e registre a sua conclusão sobre ele." | PF02; T04 (HTA 4.2); QA02, QA05, QA11 | **Total:** registra a decisão com justificativa e reconhece em UI09 que ela foi gravada. **Parcial:** registra, mas precisa de ajuda ou não reconhece o registro. **Falha:** não registra | 7 min |
| UT03 | **(médico)** "Você tem alguns minutos entre duas consultas e quer saber quais exames ainda esperam a sua avaliação." | PF05; T01 (HTA 2.1); QA04 | **Total:** chega a uma lista só com os casos que aguardam revisão (UI02b) ou os identifica corretamente na lista. **Falha:** não identifica | 2 min |
| UT04 | **(técnico)** "A Sra. Aparecida Souza, 74 anos, acabou de fazer a ressonância e ainda está no setor. Os dados dela estão nesta ficha. Envie o exame para análise." *(ficha impressa ou em tela com nome, código, volumes e escores)* | PF03; T03 (GOMS GOAL 3 e 4); QA06, QA07, QA09 | **Total:** chega a UI07 tendo trocado o arquivo e corrigido o volume sem ajuda. **Parcial:** chega a UI07 com uma ajuda. **Falha:** não envia | 6 min |
| UT05 | **(técnico)** "Você recebeu um aviso de que a análise do exame da Sra. Aparecida não foi concluída. Ela ainda está no setor. Resolva a situação para que o exame seja analisado." | PF04; T03; QA08 | **Total:** chega a UI07 pelo reenvio no próprio caso, sem ajuda. **Falha:** procura criar um caso novo e não encontra outro caminho, ou desiste | 3 min |

**Ordem de aplicação:** médicos fazem UT03, UT01 e UT02, nessa ordem; técnicos fazem UT04 e UT05. UT03 vem antes porque o protótipo é estático: depois do registro em UT02, a lista continuaria mostrando o Sr. Roberto como "aguardando revisão", o que confundiria o participante.

> Nenhuma instrução diz onde clicar nem usa os rótulos dos controles avaliados ("Registrar decisão", "Reenviar exame", "Confiabilidade", "Aguardando revisão").

**Sobre os erros plantados em UT04.** O protótipo sempre oferece primeiro o arquivo FLAIR e preenche o volume intracraniano com 120.000 mm³, enquanto a ficha entregue ao participante mostra 1.200.000 mm³. O participante não sabe disso antes. O que se observa é **se** ele percebe e **como** reage, e não se ele cometeria o erro por conta própria. Isso é dito ao participante no encerramento.

## E. Instrumentos

Modelos genéricos do repositório, adaptados abaixo:

- [Modelo de termo de consentimento](../instrumentos/termo_consentimento_modelo.md)
- [Roteiro de teste](../instrumentos/roteiro_teste_usabilidade.md)
- [Planilha de observação](../instrumentos/planilha_observacao_modelo.md)
- [Formulário de avaliação heurística](../instrumentos/formulario_heuristica_modelo.md)
- Questionários pré-teste, pós-tarefa e pós-teste: abaixo

### E.1 Adaptações do termo de consentimento

| Campo do modelo | Preenchimento |
|---|---|
| Projeto | Interface de Apoio ao Diagnóstico Explicável de Alzheimer (M-XAI), disciplina CC8122, Centro Universitário FEI |
| Atividade | teste de usabilidade de protótipo |
| Objetivo | "avaliar se a interface de um protótipo é fácil de entender e de usar. Estamos avaliando o protótipo, não você nem os seus conhecimentos médicos ou técnicos" |
| O que será solicitado | três tarefas (médico) ou duas tarefas (técnico) no protótipo, comentando em voz alta o que pensa, mais dois questionários curtos; 30 a 40 minutos |
| Registros | gravação de tela e áudio, somente se autorizada; uso exclusivo da equipe para análise; descarte ao fim do semestre |
| Privacidade | identificação apenas por U01–U04; nenhuma informação de pacientes reais é mostrada ou pedida |
| Esclarecimento adicional | "O protótipo usa dados fictícios. Ele não é uma ferramenta clínica e não deve orientar decisões sobre pacientes" |

### E.2 Abertura padronizada (lida pelo moderador)

> "Obrigado por participar. Estamos testando um protótipo de plataforma que mostra a sugestão de um modelo de inteligência artificial sobre exames de ressonância. **Não estamos testando você nem o modelo**: os resultados que aparecem são fictícios e fixos. Queremos saber se a tela comunica bem o que precisa comunicar. Vou te pedir algumas tarefas. Enquanto faz, fale em voz alta o que está pensando, o que procura e o que espera que aconteça. Eu não vou poder te ajudar durante a tarefa, porque queremos ver onde a tela não se explica sozinha. Se travar, me diga. Você pode parar a qualquer momento."

**Frase padronizada para participante médico que tenta avaliar o diagnóstico:** "Neste teste o resultado é fictício; o que importa é como você usaria essa informação na tela."

### E.3 Pré-teste (perfil mínimo)

1. Profissão e tempo de atuação (faixas: menos de 2 anos, 2 a 5, mais de 5).
2. Com que frequência atende pacientes com queixa de memória (médico) ou realiza ressonância de crânio (técnico)?
3. Já usou alguma ferramenta que mostra sugestão de inteligência artificial em exames? (sim/não; qual)
4. *(proxy)* Ano do curso e se já teve contato prático com o tema.

### E.4 Pós-tarefa

Após **cada** tarefa: SEQ — "No geral, essa tarefa foi: 1 (muito difícil) a 7 (muito fácil)" — e "o que tornou a tarefa fácil ou difícil?".

Perguntas de compreensão, aplicadas só depois da tarefa correspondente, para não induzir o participante:

| Após | Pergunta | Responde |
|---|---|---|
| UT01 | "O que significa 'Confiabilidade: alta' neste caso?" | QA01 |
| UT01 | "O MMSE deste paciente influenciou a sugestão da plataforma?" | QA03 |
| UT02 | "No caso do Sr. Roberto, o estado civil pesou contra Alzheimer. O que você conclui disso?" | QA11 |
| UT04 | "A paciente já pode ir embora?" | QA09 |

### E.5 Pós-teste

1. SUS (10 itens, versão em português), aplicado ao fim da sessão.
2. "O que mais te ajudou e o que mais atrapalhou?"
3. *(médico)* "Depois de registrar uma decisão, você já precisou corrigir ou complementar o que registrou? Como faria aqui?" — QA12, para H15.
4. *(técnico)* "No seu setor, o paciente costuma esperar alguns minutos depois do exame? Isso seria possível?" — evidência para H09.
5. Encerramento: explicar os erros plantados (UT04), reforçar que o protótipo não é ferramenta clínica e agradecer.

### E.6 Definições para a planilha de observação

| Termo | Definição adotada |
|---|---|
| Sucesso total | atinge o critério da tarefa sem ajuda do moderador |
| Sucesso parcial | atinge o critério com uma ajuda, ou atinge só parte do critério (definida por tarefa na seção D) |
| Falha | não atinge o critério no tempo-limite, desiste ou precisa de mais de uma ajuda |
| Erro | ação que afasta o participante do objetivo e que ele precisa desfazer (por exemplo, abrir o caso errado, procurar criar um caso novo em UT05) |
| Dúvida | fala de incerteza ("será que é aqui?") ou pausa maior que 10 s sem ação |
| Ajuda | qualquer intervenção do moderador além de repetir a instrução |
| Abandono | o participante declara que desistiu |
| Tempo | da última palavra da instrução até o critério de sucesso ou o abandono, medido pelo observador e conferido na gravação |

## F. Plano de análise

1. **Por tarefa e participante:** tabela com sucesso (total/parcial/falha), tempo, erros, ajudas e SEQ, preenchida a partir da planilha e conferida na gravação.
2. **Comparação com as metas:** tabela MU01–MU06 com "meta / resultado / atingida?". Meta não atingida não é tratada como reprovação: vira problema a investigar, com as falas que explicam o porquê.
3. **Falas:** transcrever os trechos de cada tarefa e codificá-los pela pergunta QA a que respondem, mais duas categorias livres: "expectativa não atendida" e "termo não compreendido".
4. **Consolidação com a inspeção (Entrega 13):** cada problema observado é cruzado com as violações heurísticas. Problema que aparece nas duas fontes ganha prioridade; problema só da inspeção, que nenhum participante encontrou, é mantido com severidade revista.
5. **Severidade:** escala de Nielsen, de 0 (não é problema) a 4 (catástrofe). Prioridade = severidade, com desempate pela quantidade de participantes afetados e por bloquear ou não a tarefa.
6. **Apresentação na Entrega 14:** tabela de resultados por tarefa, tabela das metas, lista de problemas priorizados (com tela, evidência, heurística, QA e recomendação) e as limitações (amostra de 4, *proxy*, dados simulados, erros plantados).
7. **Retorno ao projeto:** cada recomendação aceita é registrada na `RASTREABILIDADE.md` (coluna "Decisão/melhoria" da seção 3) e, quando afetar uma hipótese (H03, H07, H09, H13, H15), na coluna "Evidência obtida" da seção 2.

## Checklist

- [x] As seis etapas DECIDE foram contextualizadas, não apenas expandidas por sigla.
- [x] Perguntas de avaliação têm método e evidência correspondentes.
- [x] O plano distingue avaliação de IHC de avaliação técnica/científica do TCC.
- [x] Dados ou processamentos simulados no protótipo estão declarados.
- [x] Tarefas vêm de objetivos/cenários relevantes.
- [x] Critérios de sucesso foram definidos antes da coleta. *(metas provisórias até a Entrega 8)*
- [ ] Questões práticas e éticas estão resolvidas. *(faltam datas, confirmação dos responsáveis e recrutamento)*
- [ ] Instrumentos estão prontos antes da Entrega 13/14. *(conteúdo pronto; falta montar o termo e os questionários no formato de aplicação e passar pelo piloto)*
- [x] Plano diz como dados serão analisados e apresentados.
