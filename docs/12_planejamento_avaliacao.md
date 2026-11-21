# Entrega 12 — Planejamento da avaliação de usabilidade (DECIDE)

**Data:** 21/11/2026  
**Status:** 🟩 concluída  
**Responsabilidade:** 1 solução por equipe.

## O que está sendo avaliado

A interface foi ampliada na disciplina a partir do aplicativo previsto no TCC. **Esta avaliação investiga a qualidade da interação com o protótipo, não a validade científica nem o desempenho do modelo M-XAI.**

| A avaliação **responde** | A avaliação **não responde** |
|---|---|
| Se o médico distingue a probabilidade da classe da confiabilidade da estimativa | Se a probabilidade está correta para aquele paciente |
| Se o médico reconstitui o raciocínio de um parecer anterior a partir do caso | Se o parecer estava certo |
| Se o neurologista decide sobre a autonomia sem atribuí-la ao modelo | Se o modelo deveria avaliar autonomia |
| Se a radiologista usa a pergunta clínica e registra método e dúvida | Se o volume hipocampal foi bem medido |
| Se o técnico resolve as pendências antes de liberar a paciente | Se a leitura automática do cabeçalho é tecnicamente viável |
| Se o técnico se recupera de uma falha sem redigitar dados | Por que a análise falha |

**Dados e processamentos simulados.** Sugestões, probabilidades, confiabilidades, contribuições por variável e mapas de atenção são valores fixos por caso. A conferência do arquivo, as pendências, o reenvio com dados mantidos, o parecer, a linha do tempo, a fila de laudos e a pergunta ao solicitante só existem no protótipo. Os pacientes são fictícios e a ressonância é uma ilustração esquemática. Os problemas que o técnico encontra (série FLAIR, teste cognitivo ausente, volume intracraniano errado, arquivo T2 no reenvio) são **plantados** para observar a reação a eles. A seção "O que é simulado e o que é integrado" da [Entrega 11](11_figma.md) detalha cada item.

## A. Método DECIDE

| Etapa | Aplicação no projeto |
|---|---|
| **D — Determine the goals** | Verificar se o protótipo permite a cada perfil alcançar o objetivo da sua conversa MoLIC com segurança: o médico retoma o parecer e decide com a sugestão entendida como apoio (M02, H03, H06); o neurologista confronta as evidências sem delegar ao modelo a decisão sobre dirigir (M04); a radiologista lauda o caso limítrofe registrando método e dúvida (M01, H08); o técnico resolve as pendências antes de liberar a paciente e se recupera de uma falha sem redigitar (M03, H07, H13). Os critérios são as metas MU01–MU06 da Entrega 8, sem alteração de valores |
| **E — Explore the questions** | Quinze perguntas de avaliação (QA01–QA15, seção B), cada uma com método, evidência e critério definidos antes da coleta. As de compreensão (QA01–QA04, QA06, QA07) só podem ser respondidas pelo que o participante diz que entendeu, não por inspeção |
| **C — Choose the evaluation paradigm and techniques** | **Inspeção heurística** (Nielsen, H1–H10) por cada integrante, sobre as 51 telas, na Entrega 13: é barata, vem primeiro e acha problemas de consistência e de feedback sem gastar participante. Depois, **observação de usuários com tarefas e pensar em voz alta** na Entrega 14, porque as perguntas centrais são de compreensão e só a fala do participante as responde. Questionário pós-tarefa de 1 a 5 (MU04) e perguntas de verificação com gabarito (MU05, MU06). Sem teste A/B nem medição remota não moderada: com quatro participantes, o valor está no qualitativo |
| **I — Identify the practical issues** | Quatro participantes, **um por perfil**, como pede a Entrega 14 (número de participantes igual ao número de integrantes). Profissionais reais são difíceis de recrutar; estudantes avançados entram como *proxy* declarado. Sessões remotas ou presenciais na FEI, com o protótipo no modo de apresentação. Piloto com integrante da equipe antes da primeira sessão. Riscos: link pedindo login, participante médico que tenta avaliar o diagnóstico, preenchimento simulado que confunde. Seção C |
| **D — Decide how to deal with ethical issues** | Consentimento livre e esclarecido antes de qualquer registro (seção E.1). Avaliação de interface com profissionais, sem dados de pacientes reais, sem intervenção clínica e sem coleta de dados sensíveis, no espírito da Resolução CNS 510/2016 e da LGPD (Lei 13.709/2018). Gravação só com autorização e pelo tempo da disciplina. Participantes identificados como U01–U04. No encerramento, o participante é informado de que o protótipo **não** é ferramenta clínica e de quais problemas foram plantados |
| **E — Evaluate, interpret and present the data** | Sucesso, tempo, erros (críticos e não críticos), ajudas e avaliação pós-tarefa por tarefa e participante, comparados às metas MU. Falas codificadas por pergunta QA. Problemas consolidados com os da inspeção, classificados por severidade (0–4), e cada um ligado à tela, à QA, à hipótese e à linha R da `RASTREABILIDADE.md`. Seção F |

## Metas de usabilidade aplicadas

As metas são as da [Entrega 8](08_engenharia_usabilidade.md), seção 3.2, **sem mudança de valores**. Esta seção diz só como cada uma será medida com o protótipo e a amostra desta avaliação.

| Meta (Entrega 8) | Critério | Onde se mede | Como se aplica aqui |
|---|---|---|---|
| MU01 — eficácia | ≥ 80% concluem a tarefa atribuída sem orientação e atendem aos critérios essenciais | tarefa principal de cada perfil: UT01, UT02, UT03, UT05 | Ver "Denominador da MU01" abaixo |
| MU02 — prevenção de erros | 0 erros críticos | todas as tarefas | Erros críticos da Entrega 8, traduzidos para o protótipo na seção E.6 |
| MU03 — eficiência | tempo mediano ≤ 10 min para interpretar a sugestão e registrar a avaliação | P01, UT01, do momento em que o caso é aberto até a decisão gravada (UI09) | Com um participante P01, a "mediana" é o tempo dele |
| MU04 — satisfação | mediana ≥ 4 em cada item (escala de 1 a 5) | após cada tarefa, por perfil | Três itens da Entrega 8: clareza das informações, facilidade para concluir, satisfação geral. Apresentados como distribuição e mediana, sem média |
| MU05 — compreensão do papel da IA | 100% dos P01 identificam que a saída é sugestão, não diagnóstico | P01, após UT01 (QA04) | Com um P01, a meta exige a resposta certa dele. A mesma pergunta é feita ao P02, mas o resultado do P02 não entra na MU05, que a Entrega 8 restringe ao P01 |
| MU06 — compreensão da explicação | ≥ 80% dos P01 interpretam corretamente ≥ 2 de 3 elementos | P01, após UT01 (QA01, QA02, QA03) | Com um P01, a meta exige que ele acerte pelo menos dois dos três |

**Denominador da MU01.** A `RASTREABILIDADE.md` registrou que o exemplo de 3/4 da Entrega 8 equivale a 75% e não atinge 80%. Esta entrega **não altera o limite**. Para aplicá-lo, propõe: o denominador é o número de participantes (4), cada um com a tarefa principal do seu perfil (UT01, UT02, UT03, UT05). Com isso, **só 4/4 atinge a meta**, e 3/4 é registrado como "não atingida" com a tarefa e o perfil que falharam. As tarefas de recuperação (UT04, UT06) são apresentadas à parte, na mesma tabela, porque dependem de a tarefa principal ter sido concluída. A equipe confirma essa leitura no piloto; se decidir outra, registra na seção 5 da `RASTREABILIDADE.md` antes da primeira sessão.

> Com um participante por perfil, nenhum resultado é generalizável. As metas servem para dizer, antes da coleta, o que será considerado problema; os números são lidos junto das falas.

## B. Perguntas de avaliação

| ID | Pergunta | Perfil / tarefa | Método | Métrica / evidência | Critério esperado | Hipótese / meta |
|---|---|---|---|---|---|---|
| QA01 | O médico distingue a probabilidade da classe da confiabilidade da estimativa? | P01 / UT01 | pergunta pós-tarefa com gabarito | resposta a "o que significa 'Moderada' neste caso?" | diz que é o quanto a probabilidade pode ser levada em conta, não a chance de estar certo | H03; MU06 (elemento 1) |
| QA02 | O médico lê o mapa de atenção como onde o modelo se apoiou, e não como lesão? | P01 / UT01 | pergunta pós-tarefa com gabarito | resposta a "o que a área destacada na imagem indica?" | "onde o modelo se apoiou"; não fala em lesão | H03; MU06 (elemento 2) |
| QA03 | O médico interpreta o peso das modalidades e a contribuição das variáveis como explicação do modelo? | P01 / UT01 | pergunta pós-tarefa com gabarito | resposta a "o que mais pesou nesta sugestão, e o que isso diz sobre o paciente?" | cita o volume do hipocampo e a ressonância; trata como algo do modelo, que pode levar a confiar ou desconfiar dele, e não como causa da doença | H01, H03; MU06 (elemento 3) |
| QA04 | O médico identifica a saída como sugestão de apoio? | P01 / UT01 (e P02 / UT02, à parte) | pergunta pós-tarefa | resposta a "o que este resultado permite concluir, e quem decide?" | sugestão; a decisão é do médico | MU05 |
| QA05 | O médico reconstitui o raciocínio do parecer anterior a partir do caso? | P01 / UT01 | observação + pergunta pós-tarefa | resposta a "o que o neurologista concluiu em agosto, com base em quê, e o que mudou desde então?"; uso do parecer na justificativa | cita especialista, data, conclusão e pelo menos um critério, e a queda do MMSE | H06; meta qualitativa "recuperar o raciocínio de um parecer anterior" |
| QA06 | O profissional entende que o contexto clínico não entra no cálculo da sugestão? | P01 / UT01; P02 / UT02 | pergunta pós-tarefa | resposta a "o MMSE influenciou a sugestão?" | não | correção 7 da Entrega 6 |
| QA07 | O neurologista percebe a confiabilidade baixa e que o modelo não avalia aptidão para dirigir, e decide sem atribuir ao modelo a decisão sobre autonomia? | P02 / UT02 | observação + pergunta pós-tarefa | fala; justificativa registrada; resposta a "a plataforma ajudou a decidir sobre a direção? Como?" | menciona a confiabilidade baixa e o limite; não diz que o modelo indica se ele pode dirigir | H03 (calibração); MU02 (erro crítico) |
| QA08 | O neurologista registra a divergência e uma justificativa que vai além do modelo? | P02 / UT02 | observação | conteúdo do registro (UI09b) e reação ao aviso de UI05c | divergência preenchida ou mencionada; justificativa cita os episódios | meta qualitativa "comparar evidências conflitantes" |
| QA09 | A radiologista usa a pergunta clínica e o contexto, e trata o volume do modelo como referência? | P03 / UT03 | observação + pergunta pós-tarefa | caminho (abre ou não a segunda leitura), fala, resposta a "o que o solicitante vai receber deste laudo?" | menciona a pergunta clínica; diz que o solicitante recebe método e dúvida; não trata o volume como conclusão | H08; meta qualitativa de P03 |
| QA10 | A radiologista retoma o laudo após a interrupção sem perder a etapa? | P03 / UT04 | observação | caminho até UI16; fala sobre a dúvida anotada | retoma pelo laudo suspenso, sem ajuda | meta qualitativa "legibilidade e continuidade diante de interrupções" |
| QA11 | O técnico percebe e resolve as pendências antes de liberar a paciente? | P04 / UT05 | observação | reação a UI06c, UI06g e UI06b; ações seguintes | resolve as três pendências sem ajuda e não tenta enviar com pendência | H07; MU02 (erro crítico) |
| QA12 | O técnico entende quando pode liberar a paciente? | P04 / UT05 | pergunta pós-tarefa | resposta a "a paciente já pode ir embora?" | é melhor aguardar o resultado da análise | H07, H09 |
| QA13 | O técnico se recupera da falha pelo próprio caso, sem redigitar dados? | P04 / UT06 | observação | caminho, tempo, fala sobre "dados mantidos", reação ao arquivo errado (UI08c) | reenvia pelo caso, sem procurar criar outro | H13; F04 |
| QA14 | O profissional precisaria corrigir ou complementar uma decisão já registrada? | P01 e P02, pós-teste | entrevista | resposta e exemplos | sem critério: coleta exploratória | H15 |
| QA15 | Quais violações das heurísticas de Nielsen as telas têm, e com que severidade? | inspeção (Entrega 13) | inspeção heurística | violações H1–H10, severidade 0–4 | nenhuma violação de severidade 4 nas telas das tarefas UT01–UT06 | — |

## C. Escopo e participantes

| Item | Planejamento |
|---|---|
| Perfis | **U01 — P01, médico clínico:** clínico geral, generalista ou residente de clínica médica. **U02 — P02, neurologista:** neurologista ou residente de neurologia. **U03 — P03, radiologista:** radiologista ou residente de radiologia. **U04 — P04, técnico em radiologia:** técnico ou tecnólogo que opere ressonância |
| Critérios de inclusão | Atuar (ou ter estágio) no perfil; P01 e P02: atender pacientes com queixa cognitiva; P03: já ter laudado RM de crânio; P04: já ter realizado RM de crânio. Todos: usar navegador em computador |
| Critérios de exclusão | Integrantes da equipe; quem já viu o protótipo (inclusive o participante da simulação da Entrega 6); quem participou das coletas da Entrega 7 como co-autor dos instrumentos |
| *Proxy*, se não houver profissionais | P01 e P02: estudante de Medicina no internato (P02 com estágio em neurologia). P03: residente de outra área com rodízio em radiologia, ou estudante de Medicina com estágio em imagem. P04: estudante de curso técnico ou tecnólogo em radiologia com estágio em RM. A condição de *proxy* é registrada e entra como limitação |
| Recrutamento | Contatos das coletas da Entrega 7 e rede pessoal da equipe. Convite por mensagem, com duração e formato. Sem incentivo financeiro |
| Nº de participantes | 4, um por perfil |
| Ambiente | Remoto (videochamada com o participante compartilhando a tela) ou presencial (laboratório da FEI) |
| Dispositivo | Computador com tela de pelo menos 1366 px de largura; protótipo no modo de apresentação, em tela cheia, com "ajustar à largura" |
| Protótipo/versão | <https://www.figma.com/proto/wQIeoySFfUvRdhjPRIj1HJ?node-id=9-3&starting-point-node-id=9-3>, versão de 21/11/2026 (51 telas, 116 ligações). Cada tarefa começa num fluxo nomeado (seção D) |
| Duração | 30 a 40 minutos por sessão |
| Papéis em cada sessão | Um moderador (conduz e lê as instruções) e um observador (preenche a planilha e cronometra) |
| Responsáveis (proposta) | U01: Paulo Hudson (autor do M02) · U02: Ana Carolina Lazzuri (M04) · U03: Raphael Garavati Erbert (M01) · U04: Nathan Gabriel da Fonseca Leite (M03). O observador de cada sessão é outro integrante |
| Teste piloto | Antes da primeira sessão, com um integrante da equipe em cada perfil (não conta na amostra). Valida: link sem login, todas as ligações das tarefas, clareza das instruções, duração, gravação e a leitura do denominador da MU01. Mudanças após o piloto são registradas na Entrega 14 |
| Riscos e mitigação | Link pede login → testar em janela anônima no piloto. Participante tenta avaliar se o diagnóstico está certo → a abertura diz que o modelo não está sendo avaliado e o moderador redireciona uma vez, com frase padronizada. Preenchimento simulado confunde ("cliquei e o campo se preencheu") → a abertura avisa que os campos se preenchem ao clicar. Queda de conexão → retomar da tarefa interrompida e registrar |

## D. Lista de tarefas de avaliação

| ID | Perfil | Cenário neutro entregue ao participante | Objetivo oculto | Começa no fluxo | Critério de sucesso | Tempo-limite |
|---|---|---|---|---|---|---|
| UT01 | P01 | "Você é o Dr. Marcos. O Sr. Ivo Bittencourt, 71 anos, voltou hoje; o filho diz que a memória piorou nas últimas semanas. Em agosto você conversou por telefone com um neurologista sobre ele, e uma ressonância nova ficou pronta. Entre na plataforma, retome o caso dele e deixe registrado o que você decidiu." | M02 inteiro (O01, O02, O07, O06, O11, O12); T01; QA01–QA06 | 1 · Médico clínico (UI01) | **Total:** chega a UI09 com uma decisão cuja justificativa cita o parecer anterior ou a queda do MMSE, sem ajuda. **Parcial:** chega a UI09 com uma ajuda, ou a justificativa não usa nenhuma evidência do caso. **Falha:** não grava | 10 min (MU03) |
| UT02 | P02 | "Você é o Dr. César. A filha do Sr. Roberto Mendes, 76 anos, contou na consulta que em 02/11 ele se confundiu ao pagar as contas da casa, e ela se preocupa porque ele insiste em dirigir. Acrescente o que ela contou, veja o que a plataforma tem sobre ele e registre a sua conduta." | M04 (O09, O06, O11, O12); T04; QA06–QA08 | 2 · Neurologista (UI12) | **Total:** inclui o episódio, chega a UI09b e, na fala ou no registro, não atribui ao modelo a decisão sobre dirigir. **Parcial:** chega a UI09b com uma ajuda. **Falha:** não grava, ou atribui ao modelo a decisão sobre dirigir (erro crítico) | 10 min |
| UT03 | P03 | "Você é a Dra. Helena e está na fila do dia. Laude o próximo exame. Se faltar alguma informação para concluir, resolva como faria no seu serviço." | M01 (O02, O10, O06); T02; QA09 | 5 · Radiologista (UI13) | **Total:** libera o laudo (UI13c) e diz que o solicitante recebe o método e a dúvida; se precisar de dado do solicitante, usa a pergunta pelo exame. **Parcial:** libera com uma ajuda. **Falha:** não libera | 8 min |
| UT04 | P03 | "Enquanto você laudava, chegou um exame urgente. Resolva e depois termine o laudo que estava fazendo." | M01, ruptura de urgência e retomada; QA10 | 6 · Radiologista — urgência (UI16b) | **Total:** suspende, encontra o laudo suspenso na fila e volta a UI16 sem ajuda. **Falha:** não encontra o laudo suspenso | 3 min |
| UT05 | P04 | "Você é o Bruno. A Sra. Aparecida Souza, 74 anos, acabou de fazer a ressonância e ainda está no setor. Mande o exame para análise." *(a ficha impressa mostra MMSE 22 de 28/10 e ICV 1.200.000 mm³)* | M03 (O03, O04, O05); T03; QA11, QA12 | 3 · Técnico (UI06) | **Total:** chega a UI07 tendo resolvido as pendências (série, teste cognitivo, ICV) sem ajuda. **Parcial:** chega a UI07 com uma ajuda. **Falha:** não envia, ou declara a paciente liberada com pendência aberta (erro crítico) | 8 min |
| UT06 | P04 | "Chegou um aviso de que a análise do exame da Sra. Aparecida não foi concluída. Ela ainda está no setor. Resolva para que o exame seja analisado." | M03, rupturas de falha e de arquivo errado no reenvio; QA13 | 4 · Técnico — falha (UI08) | **Total:** chega a UI07 pelo reenvio no próprio caso, sem ajuda. **Falha:** procura criar um caso novo e não encontra outro caminho, ou desiste | 4 min |

**Ordem:** cada participante faz as tarefas do seu perfil na ordem da tabela. UT04 e UT06 vêm depois das principais porque são continuações delas.

> Nenhuma instrução diz onde clicar nem usa os rótulos dos controles avaliados ("Registrar decisão", "Registrar parecer", "Confiabilidade", "Perguntar ao solicitante", "Reenviar exame", "Suspender o laudo").

**O que fica de fora do teste e vai para a inspeção.** Registrar o parecer (UI11, O08) aparece no protótipo, mas o parecer de agosto já está no caso de UT01; pedir que o médico o registre de novo seria artificial. Os estados abertos pelos fluxos "Estado · …" (UI01b, UI02d, UI05f, UI11b, UI14b, UI16c, UI16d, UI17b) e a identidade que não confere (UI06f) também não têm gatilho natural numa tarefa. Todos entram na inspeção heurística da Entrega 13.

**Sobre os problemas plantados em UT05 e UT06.** O protótipo sempre oferece primeiro o arquivo FLAIR, depois aponta o teste cognitivo ausente na requisição e o volume intracraniano digitado como 120.000 mm³; no reenvio, oferece primeiro um arquivo T2. O participante não sabe disso antes. O que se observa é **se** ele percebe e **como** reage, não se ele cometeria o erro por conta própria. Isso é dito no encerramento.

## E. Instrumentos

Modelos do repositório, adaptados abaixo:

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
| O que será solicitado | uma ou duas tarefas no protótipo, comentando em voz alta o que pensa, mais perguntas curtas depois de cada tarefa e no final; 30 a 40 minutos |
| Registros | gravação de tela e áudio, somente se autorizada; uso exclusivo da equipe; descarte ao fim do semestre |
| Privacidade | identificação apenas por U01–U04; nenhuma informação de pacientes reais é mostrada ou pedida |
| Esclarecimento adicional | "O protótipo usa dados fictícios. Ele não é uma ferramenta clínica e não deve orientar decisões sobre pacientes" |

### E.2 Abertura padronizada (lida pelo moderador)

> "Obrigado por participar. Estamos testando um protótipo de plataforma que mostra a sugestão de um modelo de inteligência artificial sobre exames de ressonância. **Não estamos testando você nem o modelo**: os resultados são fictícios e fixos, e a imagem do exame é só um desenho. Queremos saber se a tela comunica bem o que precisa comunicar. Vou te pedir uma ou duas tarefas. Enquanto faz, fale em voz alta o que está pensando, o que procura e o que espera que aconteça. Nos formulários, os campos se preenchem quando você clica neles. Eu não vou poder te ajudar durante a tarefa, porque queremos ver onde a tela não se explica sozinha. Se travar, me diga. Você pode parar a qualquer momento."

**Frase padronizada para quem tenta avaliar o diagnóstico:** "Neste teste o resultado é fictício; o que importa é como você usaria essa informação na tela."

### E.3 Pré-teste (perfil mínimo)

1. Profissão, especialidade e tempo de atuação (menos de 2 anos, 2 a 5, mais de 5).
2. Com que frequência atende pacientes com queixa de memória (P01, P02), lauda RM de crânio (P03) ou realiza RM de crânio (P04)?
3. Já usou alguma ferramenta que mostra sugestão de inteligência artificial em exames? (sim/não; qual)
4. *(proxy)* Ano do curso e contato prático com o tema.

### E.4 Pós-tarefa

Após **cada** tarefa, os três itens da MU04, de 1 (discordo totalmente) a 5 (concordo totalmente): "as informações estavam claras"; "foi fácil concluir a tarefa"; "estou satisfeito com como a tarefa foi feita". Em seguida: "o que tornou a tarefa fácil ou difícil?".

Perguntas de compreensão, só depois da tarefa correspondente, para não induzir. O gabarito é o critério da seção B; repetir o rótulo sem explicação coerente não conta como acerto (Entrega 8, MU06).

| Após | Pergunta | Responde |
|---|---|---|
| UT01 | "O que significa 'Moderada' ao lado da probabilidade?" | QA01 |
| UT01 | "O que a área destacada na imagem indica?" | QA02 |
| UT01 | "O que mais pesou nesta sugestão, e o que isso diz sobre o paciente?" | QA03 |
| UT01, UT02 | "O que este resultado permite concluir, e quem decide?" | QA04 |
| UT01 | "O que o neurologista concluiu em agosto, com base em quê, e o que mudou desde então?" | QA05 |
| UT01, UT02 | "O MMSE influenciou a sugestão da plataforma?" | QA06 |
| UT02 | "A plataforma ajudou a decidir sobre a direção? Como?" | QA07 |
| UT03 | "O que o solicitante vai receber deste laudo?" | QA09 |
| UT05 | "A paciente já pode ir embora?" | QA12 |

### E.5 Pós-teste

1. "O que mais te ajudou e o que mais atrapalhou?"
2. *(P01, P02)* "Depois de registrar uma decisão, você já precisou corrigir ou complementar o que registrou? Como faria aqui?" — QA14, para H15.
3. *(P04)* "No seu setor, o paciente costuma esperar alguns minutos depois do exame? Isso seria possível?" — evidência para H09.
4. *(P03)* "Um pedido de RM chega com a pergunta clínica? Como você pede o que falta hoje?" — evidência para H08.
5. Encerramento: explicar os problemas plantados (UT05, UT06), reforçar que o protótipo não é ferramenta clínica e agradecer.

### E.6 Definições para a planilha de observação

| Termo | Definição adotada |
|---|---|
| Sucesso total | atinge o critério da tarefa sem ajuda do moderador |
| Sucesso parcial | atinge o critério com uma ajuda, ou só parte dele (definida por tarefa na seção D) |
| Falha | não atinge o critério no tempo-limite, desiste, precisa de mais de uma ajuda ou comete erro crítico |
| **Erro crítico** (MU02) | os quatro da Entrega 8, traduzidos para o protótipo: (1) **paciente errado:** registrar decisão, parecer ou episódio no caso de outro paciente, ou confirmar a identidade em UI06e sem comparar os dois lados quando ela não confere; (2) **dado obrigatório ausente sem perceber:** declarar a paciente liberada ou o exame "pronto" com pendência aberta em UI06c/UI06g/UI06b, ou liberar o laudo sem conclusão; (3) **sugestão como diagnóstico:** dizer que o resultado é o diagnóstico ou que "a IA confirmou"; (4) **autonomia atribuída ao modelo:** dizer que a plataforma indica se o paciente pode dirigir |
| Erro não crítico | ação que afasta o participante do objetivo e que ele mesmo desfaz (abrir o caso errado e voltar, procurar criar um caso novo em UT06) |
| Dúvida | fala de incerteza ("será que é aqui?") ou pausa maior que 10 s sem ação |
| Ajuda | qualquer intervenção do moderador além de repetir a instrução |
| Abandono | o participante declara que desistiu |
| Tempo | da última palavra da instrução até o critério de sucesso ou o abandono. Em UT01, também o intervalo da abertura do caso até UI09 (MU03) |

## F. Plano de análise

1. **Por tarefa e participante:** sucesso (total/parcial/falha), tempo, erros críticos e não críticos, ajudas e os três itens da MU04, preenchidos a partir da planilha e conferidos na gravação.
2. **Comparação com as metas:** tabela MU01–MU06 com meta, numerador/denominador, resultado e "atingida?". MU01 com o denominador definido na seção "Metas de usabilidade aplicadas"; MU05 e MU06 só com o P01. Meta não atingida não é reprovação: vira problema a investigar, com as falas que explicam o porquê.
3. **Falas:** trechos de cada tarefa codificados pela QA a que respondem, mais duas categorias livres: "expectativa não atendida" e "termo não compreendido".
4. **Consolidação com a inspeção (Entrega 13):** cada problema observado é cruzado com as violações heurísticas. Problema que aparece nas duas fontes ganha prioridade; problema só da inspeção é mantido com severidade revista.
5. **Severidade:** escala de Nielsen, de 0 a 4. Prioridade = severidade, com desempate por bloquear ou não a tarefa e por envolver erro crítico.
6. **Apresentação na Entrega 14:** tabela de resultados por tarefa, tabela das metas, lista de problemas priorizados (tela, evidência, heurística, QA, recomendação) e limitações (um participante por perfil, *proxy*, dados simulados, problemas plantados, preenchimento simulado).
7. **Retorno ao projeto:** cada recomendação aceita vai para a `RASTREABILIDADE.md` (coluna "Decisão/melhoria" da seção 3) e, quando afetar uma hipótese (H03, H06, H07, H08, H09, H13, H15), para a coluna "Evidência obtida" da seção 2.

## Checklist

- [x] As seis etapas DECIDE foram contextualizadas, não apenas expandidas por sigla.
- [x] Perguntas de avaliação têm método e evidência correspondentes.
- [x] O plano distingue avaliação de IHC de avaliação técnica/científica do TCC.
- [x] Dados ou processamentos simulados no protótipo estão declarados.
- [x] Tarefas vêm de objetivos/cenários relevantes. *(uma ou duas por diagrama MoLIC)*
- [x] Critérios de sucesso foram definidos antes da coleta. *(metas da Entrega 8; leitura do denominador da MU01 a confirmar no piloto)*
- [ ] Questões práticas e éticas estão resolvidas. *(faltam datas, confirmação dos responsáveis e recrutamento dos quatro participantes)*
- [ ] Instrumentos estão prontos antes da Entrega 13/14. *(conteúdo pronto; falta montar o termo e os questionários no formato de aplicação e passar pelo piloto)*
- [x] Plano diz como dados serão analisados e apresentados.
