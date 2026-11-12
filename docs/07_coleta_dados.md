# Entrega 7 — Coleta de dados, necessidades e aspectos éticos

**Data:** 05/11/2026  
**Status:** 🟡 em andamento

## Objetivo da atividade

Planejar dados necessários para compreender usuários e requisitos de IHC, escolher técnicas adequadas e documentar instrumentos de modo que a aplicação possa ser reproduzida por pessoas diferentes.

## Para escopos de IHC derivados de TCC técnico

Quando o usuário e a interface foram propostos pela disciplina, uma prioridade da coleta é investigar se esse **cenário de uso realmente faz sentido**. Não trate o exercício de comercialização da Entrega 1 como validação de mercado.

Perguntas úteis incluem:

- esse perfil realmente realiza a atividade imaginada?
- quais ferramentas usa hoje?
- quais informações consulta?
- quais decisões toma?
- que vocabulário utiliza?
- quais parâmetros compreende e quais deveriam ser abstraídos?
- precisa de dashboard, histórico, filtros, relatórios ou comparação? Por quê?
- quais erros são frequentes e quais são críticos?
- existem papéis/permissões diferentes?
- que resultados do algoritmo/modelo seriam úteis ou difíceis de interpretar?

Quando o acesso ao perfil profissional for difícil, discuta com o docente alternativas metodológicas (especialistas próximos, dados secundários, literatura, participantes proxy) e registre as limitações. **Não esconda a limitação da amostra.**

## Hipóteses e lacunas prioritárias herdadas da Entrega 1

Antes de decidir “que dados coletar”, retome os itens `[H]` e `[?]` da Entrega 1 e o registro de hipóteses em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md). A coleta deve responder perguntas reais do projeto, e não apenas produzir um formulário porque a técnica foi solicitada.

| ID | Hipótese/lacuna | Evidência atual | Decisão que depende da resposta | Prioridade |
|---|---|---|---|---|
| H01 | A explicação combinada (mapa de atenção na imagem e peso da imagem e dos dados clínicos) ajuda o profissional a compreender a sugestão do modelo e a calibrar sua confiança melhor do que um score isolado | [H] Premissa central da Entrega 1, item 1.3. As personas P01 e P02 e os cenários C01 e C04 mostram necessidades e situações ilustrativas, mas ainda não há evidência primária com profissionais | Definir quais explicações devem ser apresentadas, em que nível de detalhe e como comunicar limitações sem induzir confiança excessiva | alta |
| H02 | A explicação combinada pode reduzir o tempo necessário para avaliar um caso em comparação com a consulta de um score isolado ou com o fluxo atual | [H] Entrega 1, hipótese H02; a estimativa de 5 a 10 minutos para A03 é uma estimativa da equipe, ainda não medida | Verificar se a apresentação multimodal agiliza a tarefa; a redução efetiva de tempo deverá ser medida posteriormente com protótipo e tarefa comparável | média |
| H03 | O médico clínico compreende o score de confiança e as explicações sem treinamento extenso | [H] Entrega 1, hipótese H03, e necessidades atribuídas à P01 na Entrega 3; ainda não houve teste direto de compreensão com o público priorizado | Definir linguagem, explicações auxiliares, avisos, exemplos e necessidade de treinamento | alta |
| H06 | O raciocínio de um especialista consultado informalmente precisa ser preservado e recuperável quando o caso retorna ao médico que acompanha o paciente | [H] Persona P01 e cenário C02 da Entrega 4 descrevem a perda de contexto após um parecer telefônico resumido; T01 da Entrega 5 modela a retomada do caso. São situações construídas pela equipe, não relatos observados | Definir quais informações de um parecer precisam ser registradas, como identificar sua origem e como recuperar o histórico na retomada do caso | média |
| H07 | Problemas de qualidade da MRI e dados clínicos incompletos só são percebidos depois que o paciente sai do setor, gerando reconvocação e atraso no diagnóstico | Nenhuma evidência primária. O cenário C03 é construído a partir dos itens 4.1 e 4.2 da Entrega 1 (variabilidade de protocolos e inconsistência de qualidade), não de relato de campo | Se sustentada, justifica deslocar a conferência de qualidade e completude para antes da liberação do paciente (F03) e torna essa a tarefa do protótipo de T03. Se refutada, o problema central de P04 deixa de existir e a persona precisa ser revista | **alta** |
| H09 | Serviços de imagem não reservam tempo adicional na escala para pacientes idosos com suspeita de declínio cognitivo | `[H]`, suposta a partir de normas operacionais genéricas de setor de imagem (origem: C03, questão de refinamento Q1) | Define se "dentro da agenda" é de fato uma restrição concreta do objetivo de T03 ou um pressuposto nosso. Afeta a meta de usabilidade da Entrega 8, que hoje prevê tempo de tarefa | alta |
| H10 | O técnico não tem autonomia formal para alterar o protocolo padrão quando o pedido médico vem genérico | `[F]` parcial (Entrega 1, item 2.4); `[?]` quanto às diretrizes do corpo clínico (origem: C03 Q2) | Decide se o método 2.B do GOMS (encurtar o protocolo preservando a sequência crítica) é um caminho real ou inviável. Se for inviável, a recomendação de indicar a sequência crítica muda de destinatário | **alta** |
| H11 | As decisões do fluxo de aquisição — protocolo, aceitação da qualidade e completude dos dados — estão distribuídas entre técnico, radiologista e sistema sem documentação, variando de serviço para serviço | Lacuna apontada no feedback da Entrega 5; a H10 cobre só a autonomia do técnico | Delimita o que a interface pode propor automatizar sem invadir decisão de outro profissional. Condiciona o modelo conceitual (Entrega 9) e os perfis de permissão | **alta** |
| H12 | Não existe repertório padronizado de contenção de movimento; cada técnico usa o que aprendeu na prática, sem critério escrito de aceitação de artefato | `[H]`, suposta a partir de manuais de operação de RM (origem: C03 Q3) | Valida os operadores de `METHOD 2.A` do GOMS (orientar novamente, aplicar contenções leves). Se o repertório for outro, o método precisa ser reescrito | média |
| H13 | A transferência dos dados clínicos do prontuário para a requisição é manual, e é nela que o resultado do teste cognitivo se perde | `[F]` parcial (Entrega 1, item 5.3); `[H]` quanto à frequência de erro (origem: C03 Q4) | Sustenta ou derruba o `METHOD 3.B` do GOMS e o requisito de trazer os dados sem redigitação | média |
| H14 | Não existe mecanismo automatizado de alerta de qualidade de imagem ou de campo obrigatório faltando antes de o paciente deixar o hospital | `[?]`, depende da arquitetura do PACS de cada serviço (origem: C03 Q5) | Se já existir em parte dos serviços, o projeto deixa de propor algo inédito e passa a ter referência concreta de comparação (Entrega 2) | média |

> Os demais integrantes preenchem aqui as hipóteses de suas tarefas (H06, H08 e as lacunas de C01 e C02).

## Parte A — necessidades e requisitos de IHC

> **Responsabilidade:** solução individual por integrante.

### A01 — Paulo Hudson Josué da Silva

**Autor(a):** Paulo Hudson Josué da Silva — 22.222.013-9  
**Persona/cenário:** P01 — Dr. Marcos Andrade / C02 — "O parecer que se perdeu" / tarefa T01  
**Hipóteses sob investigação:** H01, H02, H03 e H06

#### Que dados coletar?

| Dado/informação | Hipótese/lacuna relacionada | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Área de atuação, tempo de experiência e frequência com que atende pessoas com queixas cognitivas ou suspeita de demência | H03 | Verifica se o perfil de médico clínico/generalista previsto na Entrega 1 realiza de fato a atividade imaginada e qual é sua familiaridade com o domínio | Nível de linguagem clínica, quantidade de explicações e necessidade de orientação inicial |
| Ferramentas utilizadas para consultar MRI, laudos, testes cognitivos, histórico e pareceres de outros profissionais | H02, H06 | Identifica o fluxo atual, os sistemas acessados e as eventuais trocas entre prontuário, PACS, telefone e registros livres | Organização do fluxo, ponto de entrada das informações e necessidade real de integração |
| Informações consultadas antes de decidir: laudo/imagem, MMSE ou MoCA, histórico clínico, relato familiar e parecer especializado | H01, H06 | Mostra quais evidências participam da decisão e quais costumam faltar ou chegar tarde | Hierarquia e agrupamento das informações clínicas e explicativas |
| Interpretação das probabilidades, da faixa de confiança e dos limites de uma sugestão de IA apresentada no exemplo sintético (telas P03 e P04 da Entrega 6) | H01, H03 | Verifica o que o médico entende espontaneamente e quais interpretações equivocadas podem surgir | Vocabulário, apresentação do score, avisos e explicações auxiliares |
| Compreensão do mapa de atenção sobre o corte da MRI (Grad-CAM) e do peso da imagem e dos dados clínicos na sugestão (SHAP) | H01, H03 | Investiga se a explicação multimodal é compreensível e útil para quem não é especialista em neuroimagem | Nível de detalhe, legenda, tradução para linguagem clínica e possibilidade de consultar detalhes adicionais |
| Etapas e tempo que o médico estima gastar para reunir evidências e avaliar um caso | H02 | Verifica a percepção de esforço e de demora do fluxo atual; a entrevista não mede objetivamente eventual ganho de tempo | Priorização das informações e definição posterior de tarefa e métrica para teste com protótipo |
| Como o parecer de outro profissional é recebido, registrado e recuperado quando o paciente retorna | H06 | Testa se a ruptura descrita em C02 ocorre e quais informações do raciocínio especializado precisam ser preservadas | Histórico do caso, registro da origem do parecer e mecanismo de retomada/encaminhamento |
| Erros considerados críticos e situações em que o médico decide não seguir uma sugestão automatizada ou solicitar revisão | H01, H03 | Identifica riscos de confiança excessiva, falsa segurança e limites de atuação do sistema | Avisos, apresentação de incerteza e acesso à revisão por especialista |

#### De quem coletar?

| Perfil/stakeholder | Critério de inclusão | Relação com persona/público |
|---|---|---|
| Médico(a) clínico(a) ou generalista em atenção primária ou hospital geral | Atende adultos/idosos e já participou de avaliação de queixas cognitivas ou investigação de suspeita de demência; não é exigida experiência prévia com IA explicável | Corresponde à P01, perfil priorizado na Entrega 1 |
| Médico(a) de área próxima, como geriatria ou medicina de família, caso autorizado pelo docente | Atua na avaliação de queixas cognitivas, mas não corresponde exatamente ao perfil primário | Participante proxy; seus dados serão identificados separadamente e não serão apresentados como fala de P01 |

O instrumento foi preparado para 3 a 5 profissionais, por conveniência; sua aplicação depende de acesso a médicos clínicos, que a equipe não tem por via institucional. A amostra pequena e não probabilística permite aprofundar práticas e dificuldades, mas não representa todos os médicos clínicos.

#### Aspectos éticos

A participação será voluntária, mediante explicação do objetivo, duração e uso acadêmico das informações e aceite antes da entrevista. A conduta segue as Resoluções CNS 466/2012 e 510/2016 e a LGPD (Lei 13.709/2018). O participante poderá deixar de responder qualquer pergunta ou encerrar a conversa sem justificativa. A entrevista não avaliará competência profissional nem desempenho individual.

Não serão solicitados nomes, iniciais, datas, números de prontuário, imagens, laudos reais ou qualquer dado que permita identificar pacientes. Ao descrever um caso anterior, o profissional será orientado a retirar detalhes identificadores e a relatar apenas o fluxo e o tipo de informação consultada. Para discutir a interpretação de uma explicação, será utilizado somente exemplo sintético, identificado como fictício, sem finalidade diagnóstica.

A gravação de áudio será opcional e dependerá de autorização específica; na ausência de autorização, serão feitas apenas anotações. Não serão gravadas telas nem imagens clínicas. Os registros serão codificados, sem associação com nome ou instituição, e o acesso ficará restrito aos integrantes da equipe e ao docente. Trechos eventualmente citados serão revisados para remover elementos identificadores. Os arquivos de trabalho serão descartados ao término da disciplina. Há risco de desconforto ao relatar dificuldades ou erros do fluxo profissional; por isso, as perguntas serão formuladas sobre a rotina e não sobre culpa individual.

### A03 — Nathan Gabriel da Fonseca Leite

**Autor(a):** Nathan Gabriel da Fonseca Leite — 22.123.028-7  
**Persona/cenário:** P04 — Bruno Tavares Lima / C03 — "O exame que precisou ser refeito" / tarefa T03  
**Hipóteses sob investigação:** H07 e H09 a H14 (derivadas das questões de refinamento do C03)

A persona P04 e o cenário C03 foram construídos sem contato com técnicos em radiologia: derivam dos itens 4.1 e 4.2 da Entrega 1 e de inferência da equipe sobre o funcionamento de um setor de imagem. Por isso, a coleta não busca confirmar o que foi escrito, e sim verificar se esse profissional, essa tarefa e esse problema existem como foram descritos. A resposta pode ser negativa.

#### Que dados coletar?

Organizado pelas cinco categorias de Barbosa e Silva (2010). Cada linha aponta a hipótese que investiga e a decisão de design que depende dela; dados que não afetam nenhuma decisão deste projeto foram **deliberadamente deixados de fora**, e a omissão está justificada ao final de cada categoria.

**1. Dados sobre o próprio usuário**

| Dado/informação | Hipótese | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Tempo de atuação com ressonância magnética (em faixas) | todas | Separa quem fala da rotina consolidada de quem está em formação; a autonomia percebida tende a variar com a experiência | Define se P04 é um perfil representativo ou um caso particular |
| Formação específica em protocolos de investigação de demência (formal, informal ou inexistente) | H10, H12 | Testa se o conhecimento do caso vem de norma ou de prática pessoal | Indica se a interface deve apresentar o protocolo exigido ou apenas apoiar quem já o conhece |
| **Jargão** usado para nomear o problema de imagem causado por movimento | H12 | A Entrega 1 (item 2.4) determina que a qualidade seja expressa em linguagem de aquisição, nunca em métricas do modelo. Só sabemos qual é essa linguagem perguntando | Vocabulário dos rótulos de qualidade na interface (Entregas 9 e 11) |

*Deixados de fora:* idade, sexo e status socioeconômico. A categoria existe na referência, mas nenhum deles altera qualquer decisão de design deste projeto, e coletá-los contraria o princípio de minimização adotado nos aspectos éticos. Grau de instrução não é coletado porque o exercício da função já pressupõe formação técnica registrada.

**2. Dados sobre a relação com tecnologia**

| Dado/informação | Hipótese | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Quais sistemas o técnico opera na rotina (console, PACS, RIS, prontuário eletrônico, requisição em papel) | H13, H14 | Define onde a interface proposta teria de se encaixar e quantas janelas o técnico já alterna hoje | Integração e ponto de entrada da solução (Entrega 9); se já há quatro sistemas abertos, propor um quinto é inviável |
| Existência de sinalização automática de qualidade ou de campo obrigatório nos sistemas atuais | H14 | Verifica se o que propomos já existe em algum serviço | Se existir, deixa de ser contribuição inédita e entra como referência de comparação (Entrega 2) |
| Como a qualidade da imagem é avaliada hoje: a olho, por critério escrito ou por recurso do equipamento | H12, H07 | O cenário afirma que é "a olho"; isso precisa ser verificado | Justifica ou derruba a recomendação de indicar qualidade em linguagem de aquisição |

**3. Dados sobre o conhecimento do domínio**

| Dado/informação | Hipótese | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Frequência com que o pedido médico informa a suspeita clínica | H10 | O cenário parte de um pedido genérico ("RM de crânio"); se isso for raro, o problema muda | Se o pedido normalmente traz a suspeita, a recomendação de derivar requisitos a partir dela perde objeto |
| Quem define, na prática, quais sequências serão adquiridas | H10, H11 | Determina se o técnico é o decisor que a persona supõe | Se a decisão não for dele, P04 deixa de ser persona primária e T03 precisa ser substituída |
| Existência de protocolo escrito para investigação de demência no serviço | H10, H12 | Distingue conhecimento institucionalizado de conhecimento tácito | Define se a interface apresenta uma referência existente ou precisa construí-la |

**4. Dados sobre as tarefas**

| Dado/informação | Hipótese | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Momento em que um problema de qualidade ou de dado clínico é percebido | **H07** | É a afirmação central do C03 e a única que, se falsa, derruba a tarefa T03 inteira | Define se existe a "janela de correção" que o protótipo pretende aproveitar |
| Frequência de reconvocação nos últimos 6 meses | H07 | Mede o tamanho real do problema. Um caso por semestre e um por semana levam a prioridades opostas | Prioridade do requisito F03 na Entrega 8 e a meta de usabilidade associada |
| Tempo reservado na agenda e existência de folga para pacientes com dificuldade de cooperação | H09 | O objetivo de T03 inclui "dentro da agenda"; sem pressão real de tempo, o critério sai do objetivo | Mantém ou remove a restrição temporal do objetivo e da meta de usabilidade |
| Repertório de ações diante de movimento e o que limita a repetição de uma sequência | H12 | Testa se os operadores de `METHOD 2.A` do GOMS correspondem à prática | Reescreve ou confirma os operadores do GOMS e o ponto de seleção 2.1.3 do HTA |
| Quais dados clínicos acompanham o exame e por qual caminho chegam à requisição | H13 | Testa se a transcrição manual existe e onde ela falha | Sustenta ou derruba o `METHOD 3.B` e o requisito de trazer dados sem redigitação |
| **Gravidade dos erros**: impacto atribuído pelo próprio técnico a artefato fora da região de interesse, sequência faltante, dado clínico ausente e reconvocação | H07, H13 | Barbosa e Silva tratam gravidade do erro como dado de tarefa. Nós presumimos que reconvocação é o pior desfecho — quem faz o trabalho pode ordenar diferente | Define o que a interface deve impedir com mais firmeza e o que basta sinalizar (Entregas 8 e 9) |

**5. Dados sobre motivações e valores**

| Dado/informação | Hipótese | Por que é necessário | Qual decisão de design pode afetar |
|---|---|---|---|
| Autonomia percebida para conduzir a aquisição quando o paciente não colabora | H10, H11 | Autonomia formal (norma) e autonomia percebida (prática) podem divergir, e é a segunda que governa o comportamento | Se o técnico não se sente autorizado, uma interface que ofereça a decisão a ele não será usada |
| Percepção de tempo disponível para conferir o exame antes de liberar o paciente | H07, H09 | Testa pelo ângulo da atitude a mesma restrição que H09 testa pelo ângulo da norma | Viabilidade de inserir uma conferência antes da liberação sem que ela seja ignorada |
| **Atitude diante de mudança de sistema**: preferência por seguir o protocolo padrão e percepção sobre mudanças anteriores nas ferramentas | H11 | Barbosa e Silva chamam de atitudes e valores: o usuário explora novas formas de trabalhar ou evita? | Grau de mudança que a solução pode propor sem ser rejeitada; necessidade de treinamento |

#### De quem coletar?

As quatro perguntas de investigação de público (Barbosa e Silva, 2010) respondidas para este recorte:

**Quem utilizará o sistema?** Na tarefa T03, o técnico em radiologia que opera a RM — a persona P04. Nas demais tarefas do projeto, o médico clínico (P01) e a radiologista (P03), cobertos pelos instrumentos dos outros integrantes.

**Quem será afetado por ele?** O **paciente**, que é quem arca com a reconvocação e com o atraso no diagnóstico, e que não é usuário nem será consultado nesta coleta — a decisão de não envolvê-lo está registrada em H05, e o ônus que ele carrega é o principal argumento de relevância social deste projeto. Também são afetados a radiologista que recebe o estudo, o médico solicitante que aguarda o laudo e a central de agendamento, que absorve a vaga extra.

**Quem é responsável por decidir quais objetivos o sistema deve apoiar e quais funcionalidades ter?** Hoje, a própria equipe, a partir de inferência; é essa lacuna que a coleta busca reduzir. Os objetivos de T03 foram definidos pela equipe a partir de inferência, sem nenhum profissional do setor de imagem na decisão. Num projeto real, esse papel caberia à coordenação do setor de imagem junto ao corpo clínico. Enquanto isso não existir, qualquer funcionalidade proposta é hipótese nossa, não requisito levantado.

**Quem definiu os processos a serem apoiados?** Ainda não se sabe; é o que a H11 investiga. O protocolo de aquisição é presumivelmente definido pelo corpo clínico ou pela radiologia; a escala do equipamento, pela central de agendamento; o fluxo de laudo, pelo serviço. Enquanto essa distribuição não estiver clara, não há como saber que decisões a interface pode propor automatizar sem invadir a competência de outro profissional.

| Perfil/stakeholder | Critério de inclusão | Relação com persona/público |
|---|---|---|
| Técnico(a) em radiologia que opera ressonância magnética | Atua com RM há pelo menos 6 meses e realiza exames de crânio com indicação de investigação de declínio cognitivo ao menos raramente | É a própria P04 (Bruno). Público primário do instrumento |
| Subgrupo: técnicos de serviços **sem** radiologista no local | Mesmo critério, com laudo feito remotamente ou em outra unidade | Reproduz a condição específica do C03, em que o retorno sobre o exame demora dias. É onde H07 tem mais chance de se sustentar |
| Subgrupo: serviço público × serviço privado | Mesmo critério, segmentado pela pergunta de caracterização | A autonomia sobre protocolo e a folga de agenda tendem a variar; permite ver se o problema é estrutural ou local |

**Quem não é público deste instrumento:** radiologistas e médicos solicitantes. A visão do radiologista sobre quem decide o protocolo pertence ao instrumento do integrante responsável por P03/T02, e as duas coletas devem ser cruzadas na análise para responder a H11 pelos dois lados.

**Recrutamento e limitação da amostra.** Não temos acesso institucional a um setor de imagem. O recrutamento será por conveniência, em grupos profissionais de técnicos em radiologia (associações de classe, grupos em redes sociais e contatos indicados pelo corpo docente), com meta de **n ≥ 20**. Isso significa: amostra **não probabilística**, autosseleção de quem responde, e respostas **autorrelatadas** — não observadas. Quem se dispõe a responder um questionário sobre qualidade de exame pode ser justamente quem tem mais interesse no tema. Nenhuma conclusão desta coleta pode ser apresentada como representativa dos técnicos em radiologia em geral, e essa limitação será registrada junto de qualquer resultado na `RASTREABILIDADE.md`. Caso n < 10, os dados serão tratados apenas como indício qualitativo, sem percentuais.

#### Aspectos éticos

Sim, o projeto precisa considerar aspectos éticos: a coleta envolve pessoas diretamente (os técnicos que respondem) e indiretamente (pacientes e colegas mencionados nos relatos). A análise segue os quatro princípios da **Resolução 196/96 do Conselho Nacional de Saúde**, citada em aula, hoje substituída pelas Resoluções CNS 466/2012 e 510/2016, que mantêm esses princípios. O tratamento dos dados também observa a Lei Geral de Proteção de Dados (Lei 13.709/2018). Trata-se de pesquisa com objetivo técnico e didático, não de pesquisa científica submetida a comitê de ética — a resolução orienta a conduta, e esse limite está declarado ao final.

**Princípio da não maleficência — evitar danos previsíveis, imediatos e tardios.** O dano previsível aqui não é físico nem clínico: é **profissional**. Várias perguntas tocam em falha de trabalho — exame refeito, dado clínico trocado, ausência de conferência antes de liberar o paciente. Se uma resposta puder ser ligada a quem a deu, o participante fica exposto diante do empregador, e o dano é tardio. Por isso: não são coletados nome, e-mail, telefone, número de registro profissional, nome do serviço, cidade ou cargo específico; o formulário **não coleta e-mail**, e o Google Forms não fornece o endereço IP aos responsáveis; as perguntas de caracterização ficam em faixas amplas, nunca em valores que permitam cruzamento identificador; e as perguntas sobre erro são formuladas como **frequência na rotina do serviço**, não como culpa individual. Os relatos abertos podem conter, sem intenção, nome de pessoa ou de serviço, e passam por revisão manual de anonimização antes de qualquer citação — o que não puder ser anonimizado não é citado.

**Princípio da justiça e equidade — relevância social e minimização do ônus.** O ônus para o participante é de 12 minutos, sem deslocamento e sem exposição. A relevância social está do outro lado da cadeia: quem paga pelo problema que investigamos é o paciente idoso que precisa voltar ao hospital e esperar semanas a mais pelo diagnóstico. O participante não recebe benefício direto, e isso é dito a ele com franqueza no convite — não prometemos que o trabalho mudará a rotina dele. O retorno oferecido é concreto e modesto: os resultados agregados ficam públicos no repositório do projeto.

**Princípio da autonomia — consentimento livre e esclarecido e proteção a grupos vulneráveis.** A primeira seção do formulário traz o termo adaptado de [`../instrumentos/termo_consentimento_modelo.md`](../instrumentos/termo_consentimento_modelo.md), com disciplina, equipe, objetivo, duração, ausência de gravação, destino dos dados e contato; o avanço só é liberado após aceite explícito, e quem recusa é encaminhado ao encerramento sem registro. Nenhuma pergunta é obrigatória além do aceite, e o participante pode abandonar a qualquer momento — respostas parciais não enviadas não são armazenadas. Sobre vulnerabilidade: a resolução cita subordinados como grupo a proteger, e isso é pertinente aqui, porque o participante é empregado de um serviço e as perguntas tratam de falhas desse serviço. Por isso o recrutamento **não passa por chefias** — a divulgação é aberta, em grupos profissionais, sem intermediação do empregador, para que ninguém responda por sentir-se obrigado.

**Princípio da beneficência — máximo de benefício, mínimo de risco.** A ponderação é explícita: o benefício é conhecimento sobre uma rotina que a equipe só conhece por inferência, e o risco é a exposição profissional descrita acima. Como o benefício para o participante individual é baixo, o risco precisa ser mantido próximo de zero — daí a ausência total de identificadores, que é desproporcional para um trabalho de disciplina e deliberada.

**Na prática, isto significa:** objetivos explicados no convite; confidencialidade dos dados brutos, com acesso restrito aos quatro integrantes e ao docente; anonimato nos dados divulgados, que são apenas agregados e trechos revisados; **nenhuma gravação** de áudio, vídeo ou tela, por ser instrumento autoaplicado; consentimento registrado antes de qualquer pergunta; e liberdade de recusar ou desistir a qualquer momento.

**Minimização.** Só entram perguntas que respondem a H07 ou a uma das hipóteses H09 a H14 — o mapeamento está na seção "Que dados coletar?" acima, e as omissões estão justificadas lá. Não são coletados idade, sexo, raça, faixa salarial nem instituição de formação.

**Armazenamento e descarte.** As respostas ficam em planilha de acesso restrito aos quatro integrantes e ao docente. O repositório público recebe apenas **dados agregados** e trechos já anonimizados — nunca a base bruta. A base é descartada ao término da disciplina.

**Limite declarado.** Este instrumento foi desenhado para uso didático e **não passou por comitê de ética**. Se qualquer parte do material for reaproveitada no TCC ou em publicação, a coleta precisa ser refeita sob as normas do comitê da instituição.

> Repita A02, A03...

## Parte B — ferramentas de coleta

> Cada integrante deve preparar uma técnica/instrumento completo. As técnicas devem ser diferentes entre si e **questionário deve estar entre as técnicas escolhidas**, conforme o enunciado da disciplina.

### Instrumento I01 — Entrevista semiestruturada com médicos clínicos

**Autor(a):** Paulo Hudson Josué da Silva — 22.222.013-9  
**Técnica:** entrevista semiestruturada  
**Objetivo:** compreender como médicos clínicos/generalistas avaliam atualmente casos com suspeita de declínio cognitivo, quais informações e ferramentas utilizam e como interpretariam uma sugestão multimodal explicada por IA. Investigar H01, H02, H03 e H06.  
**Público:** médicos clínicos/generalistas de atenção primária ou hospital geral que já tenham participado da avaliação de queixas cognitivas.  
**Duração estimada:** 30 a 40 minutos por participante.

#### Procedimento padronizado de aplicação

1. **Preparação.** Convidar de 3 a 5 profissionais que atendam aos critérios de inclusão. Preparar roteiro, ficha de anotações e um exemplo sintético de resultado (sem dados de paciente real). Fazer um pré-teste do roteiro para verificar clareza e duração.
2. **Apresentação/consentimento.** Explicar o objetivo acadêmico, a duração, a voluntariedade, o uso dos registros e a possibilidade de não responder. Solicitar consentimento antes de iniciar, com o termo adaptado de [`../instrumentos/termo_consentimento_modelo.md`](../instrumentos/termo_consentimento_modelo.md). Explicar que a entrevista não avalia a competência do profissional.
3. **Aplicação.** Seguir os blocos do roteiro, começando pelo processo atual sem apresentar a solução. Somente depois, mostrar o exemplo sintético de explicação XAI e perguntar o que o participante entende, o que considera útil e o que permanece incerto. Usar perguntas de aprofundamento sem sugerir respostas.
4. **Encerramento.** Perguntar se há algum aspecto importante não abordado, resumir os principais pontos entendidos pelo entrevistador e permitir que o participante corrija a interpretação.
5. **Armazenamento/anonimização.** Registrar as respostas por código (M01, M02 etc.). Gravar áudio somente com autorização específica; caso contrário, utilizar anotações. Remover referências a pacientes, instituições e profissionais antes da análise.

#### Instrumento

**Abertura ao participante**

“Obrigado por participar. Esta entrevista faz parte de uma atividade acadêmica de Interação Humano-Computador. Nosso objetivo é compreender como ocorre a avaliação de pacientes com queixas cognitivas e como profissionais interpretam informações clínicas, exames de imagem e possíveis explicações geradas por IA. Não estamos avaliando sua atuação e não há respostas certas ou erradas. Não compartilhe dados que identifiquem pacientes ou colegas. Sua participação é voluntária e você pode interromper a entrevista quando desejar.”

**Bloco 1 — Perfil e contexto de atuação**

1. Qual é sua área de atuação e em que tipo de serviço trabalha?
2. Há quanto tempo atua nessa área?
3. Com que frequência participa da avaliação de pessoas com queixa de memória, declínio cognitivo ou suspeita de demência?
4. Qual costuma ser sua participação no processo: avaliação inicial, solicitação de exames, interpretação de resultados, acompanhamento ou encaminhamento?

**Bloco 2 — Processo atual**

5. Sem mencionar dados identificáveis, descreva como costuma conduzir a avaliação de um caso com suspeita de declínio cognitivo, desde a primeira consulta até a decisão ou encaminhamento.
6. Quais informações costuma consultar antes de tomar uma decisão? Como utiliza MRI/laudo, MMSE ou MoCA, histórico clínico e relatos de familiares?
7. Quais ferramentas ou sistemas utiliza para acessar essas informações? Há necessidade de alternar entre sistemas, documentos ou contatos com outros profissionais?
8. Quais informações costumam estar ausentes ou ser difíceis de localizar?
9. Em que situações procura a opinião de um neurologista ou outro especialista? Como recebe e registra esse parecer?
10. Quando o paciente retorna após uma avaliação especializada anterior, como recupera o raciocínio e os dados que fundamentaram o parecer?

**Bloco 3 — Interpretação de uma explicação sintética**

*Apresentar as telas P03 e P04 da Entrega 6, identificadas como material de estudo com dados simulados: probabilidade de cada classe (CN × DA) com a faixa de confiança, mapa de atenção sobre um corte axial da MRI, peso da imagem e dos dados clínicos na sugestão e limites do modelo.*

11. O que você entende a partir das informações apresentadas? O que considera que o resultado está sugerindo?
12. O que a probabilidade e a faixa de confiança significam para você? Que informação adicional seria necessária para interpretá-lo adequadamente?
13. O que você entende pelo mapa de atenção sobre a imagem? O destaque permite concluir algo por si só? O que ainda precisaria ser verificado?
14. Ao observar quanto a sugestão veio da imagem e quanto veio dos dados clínicos, o que fica claro e o que precisa de explicação?
15. Quais informações do exemplo ajudariam sua avaliação? Quais seriam pouco úteis ou poderiam induzir a uma interpretação equivocada?
16. Que limitações ou incertezas você gostaria de conhecer antes de considerar a sugestão do modelo?

**Bloco 4 — Uso, tempo e continuidade**

17. Em qual etapa do seu fluxo atual uma explicação como essa poderia ser consultada? Em que situação não seria apropriado utilizá-la?
18. Em sua percepção, essa forma de apresentação poderia alterar o tempo gasto para avaliar o caso? O que poderia acelerar ou tornar o processo mais demorado?
19. Quais informações deveriam permanecer registradas para que você ou outro profissional pudesse compreender a decisão em um retorno futuro?
20. Há alguma situação em que a explicação deveria levar o médico a solicitar revisão de um especialista, em vez de tomar uma decisão com as informações disponíveis?

**Encerramento**

21. Existe alguma informação, dificuldade ou prática da rotina que não foi abordada e que você considera importante para esse projeto?

#### Como os dados serão analisados

As respostas serão organizadas por código de participante e analisadas por codificação temática. Os temas iniciais serão: perfil e contexto de atuação; fluxo e ferramentas atuais; informações consultadas e ausentes; interpretação do score; compreensão do mapa de atenção e do peso de cada modalidade; percepção de tempo; continuidade do parecer; riscos e situações de encaminhamento.

Será feita uma matriz que relacione cada tema às hipóteses H01, H02, H03 e H06. Respostas divergentes serão mantidas e comparadas, sem forçar consenso. A entrevista permite investigar percepção de tempo, mas não comprova redução objetiva; H02 precisará ser medida em teste posterior com protótipo e tarefa comparável.

### Instrumento I03 — Questionário sobre a rotina de aquisição de RM de crânio
 
**Autor(a):** Nathan Gabriel da Fonseca Leite — 22.123.028-7  
**Técnica:** questionário autoaplicado, assíncrono, em formulário on-line (Google Forms)  
**Objetivo:** verificar H07 — se problemas de qualidade de imagem e de dados clínicos só são percebidos depois que o paciente deixa o setor — e testar as hipóteses H09 a H14, mapeando o que o técnico pode fazer e o que ele decide no momento da aquisição.  
**Público:** técnicos(as) em radiologia que operam RM há pelo menos 6 meses e realizam exames de crânio com indicação de investigação de declínio cognitivo.  
**Duração estimada:** 12 minutos.
 
**Método correto para o objetivo.** Das sete técnicas apresentadas em aula, a escolha se justifica por eliminação:
 
| Técnica | Por que não foi escolhida |
|---|---|
| Entrevista | Dá profundidade, mas com dois ou três participantes não distingue problema estrutural de caso isolado — e H07 é uma afirmação de **frequência** |
| Grupo de foco | Exigiria reunir de 3 a 10 técnicos no mesmo horário, fora do nosso alcance; e falar de falha de trabalho diante de colegas inibe a resposta |
| *Brainstorming* de necessidades | Levanta desejos, não verifica se a rotina descrita existe. Útil depois de H07 resolvida, não antes |
| Classificação de cartões | Serve a arquitetura de informação, que ainda não temos — cabe na Entrega 9 |
| Estudo de campo / investigação contextual | **Tecnicamente a melhor opção**: tornaria explícito o conhecimento tácito que a Entrega 5 tentou modelar por inferência. Inviável por falta de acesso institucional a um setor de imagem, e a limitação está registrada |
| **Questionário** | Escolhido. H07 pede frequência; H09, H10 e H14 dependem de normas e sistemas que **variam entre serviços**, e só a variação entre muitos respondentes revela isso. Não exige acesso presencial |
 
A contrapartida é conhecida e aceita: questionário é mais superficial que entrevista. Ela é compensada por três perguntas abertas ao final e pela previsão de que, se algum resultado ficar ambíguo, a equipe solicite ao docente autorização para uma entrevista de aprofundamento com um ou dois respondentes voluntários.
 
A `RASTREABILIDADE.md` registrava "entrevista com técnicos e radiologistas" como forma de investigar H07; a mudança está anotada lá.
 
#### Procedimento padronizado de aplicação
 
O **protocolo de execução** descrito abaixo é o instrumento mais importante desta coleta: é ele que garante que qualquer integrante da equipe aplique o questionário do mesmo modo e que os dados sejam comparáveis.
 
1. **Preparação.** Montar o formulário no Google Forms com a coleta de e-mail **desativada** (o Google Forms não fornece o endereço IP aos responsáveis), respostas não obrigatórias (exceto o aceite) e lógica de encerramento para quem não atende ao critério de inclusão. Aplicar pré-teste com 2 respondentes do perfil, cronometrando o tempo e marcando termos ambíguos ou perguntas que induzam; ajustar e registrar no repositório o que mudou entre a versão pré-teste e a final.
2. **Apresentação e consentimento.** A Seção 0 traz o termo adaptado de `../instrumentos/termo_consentimento_modelo.md`. O formulário só avança após aceite explícito; quem recusa é direcionado ao encerramento sem registro de resposta.
3. **Aplicação.** Divulgação do link em grupos profissionais de técnicos em radiologia e por indicação do corpo docente, **sem intermediação de chefias**, com texto de convite padronizado — o mesmo em todos os canais, para não enviesar quem responde. Janela de coleta de 15 dias corridos, com um único lembrete no oitavo dia.
4. **Encerramento.** Tela de agradecimento com contato da equipe e informação de que os resultados agregados ficarão disponíveis no repositório público do projeto.
5. **Armazenamento e anonimização.** Exportar as respostas para planilha de acesso restrito aos quatro integrantes e ao docente. Revisar manualmente as respostas abertas, removendo nomes de pessoas e de serviços antes de qualquer citação. Publicar apenas dados agregados e trechos anonimizados. Descartar a base ao término da disciplina.
#### Instrumento
 
> Cópia textual integral. A marcação entre colchetes ao final de cada pergunta indica a hipótese investigada e a categoria de dados correspondente (C1 a C5, conforme a seção "Que dados coletar?"). **Essas marcações não aparecem para o respondente.**
 
---
 
**Seção 0 — Convite e consentimento**
 
Você está sendo convidado(a) a responder um questionário sobre a rotina de aquisição de ressonância magnética de crânio. Ele faz parte de um trabalho acadêmico da disciplina de Interação Humano-Computador do Centro Universitário FEI, em um projeto que estuda apoio computacional ao diagnóstico de Alzheimer.
 
Queremos entender **como o trabalho acontece hoje**, no seu serviço. Não estamos avaliando você nem o seu serviço, e não há resposta certa ou errada.
 
- A participação é voluntária e você pode encerrar a qualquer momento fechando a página.
- Nenhuma pergunta é obrigatória, além deste aceite.
- **Não coletamos** seu nome, e-mail, telefone, número de registro profissional nem o nome do serviço onde você trabalha. O formulário não coleta e-mail, e o endereço IP não é fornecido à equipe.
- Não há gravação de áudio, vídeo ou tela.
- Tempo estimado: 12 minutos.
- As respostas ficam em arquivo de acesso restrito à equipe e ao professor da disciplina, e são descartadas ao fim do semestre. No repositório público do projeto publicamos apenas resultados agregados e trechos de resposta já anonimizados.
- Você não recebe benefício direto por participar. O que buscamos é entender uma rotina que só conhecemos de fora.
- Dúvidas: paulo.hudson012345awd6@gmail.com, rgaravatierbert@gmail.com, nathangabriel.f.leite@gmail.com ou lazzurianacarolina@gmail.com.
**0.1** Li as informações acima e concordo em participar. *(única pergunta obrigatória)*
☐ Sim, concordo  ☐ Não desejo participar → *encerra o formulário*
 
---
 
**Seção 1 — Sobre a sua atuação**
 
**1.1** Há quanto tempo você atua com ressonância magnética? *[C1]*
☐ Menos de 6 meses → *encerra*  ☐ 6 meses a 1 ano  ☐ 1 a 3 anos  ☐ 4 a 10 anos  ☐ Mais de 10 anos
 
**1.2** Em que tipo de serviço você atua atualmente? *[C1]*
☐ Público  ☐ Privado  ☐ Ambos  ☐ Outro  ☐ Prefiro não responder
 
**1.3** Durante os exames, há radiologista presente no local? *[C1 — reproduz a condição do C03]*
☐ Sim, sempre  ☐ Na maior parte do tempo  ☐ Raramente  ☐ Não; o laudo é feito remotamente ou em outra unidade  ☐ Não sei
 
**1.4** Com que frequência você realiza RM de crânio com indicação de investigação de declínio cognitivo, demência ou Alzheimer? *[critério de inclusão]*
☐ Diariamente  ☐ Algumas vezes por semana  ☐ Algumas vezes por mês  ☐ Raramente  ☐ Nunca → *encerra*
 
**1.5** Você recebeu alguma formação específica sobre protocolos de investigação de demência? *[C1, H10, H12]*
☐ Sim, treinamento formal  ☐ Sim, orientação informal de colegas ou do radiologista  ☐ Não  ☐ Não sei
 
---
 
**Seção 2 — Sistemas que você usa**
 
**2.1** Quais sistemas você utiliza na rotina de um exame de crânio? *(pode marcar mais de uma)* *[C2, H13]*
☐ Console do equipamento  ☐ PACS  ☐ RIS ou sistema de agendamento  ☐ Prontuário eletrônico  ☐ Requisição em papel  ☐ Outro: ____
 
**2.2** Como a qualidade da imagem é avaliada no seu serviço, antes de o exame seguir para laudo? *(pode marcar mais de uma)* *[C2, H12]*
☐ Avaliação visual do técnico no console  ☐ Critério escrito do serviço  ☐ Recurso do próprio equipamento que sinaliza problemas  ☐ Conferência por radiologista antes do envio  ☐ Não há avaliação antes do laudo  ☐ Não sei
 
---
 
**Seção 3 — Antes do exame: pedido e protocolo**
 
**3.1** Nesses exames, com que frequência o pedido médico informa a suspeita clínica (por exemplo, "investigação de Alzheimer")? *[C3, H10]*
☐ Sempre  ☐ Na maioria das vezes  ☐ Em cerca de metade  ☐ Raramente  ☐ Nunca  ☐ Não sei
 
**3.2** Na prática, quem define quais sequências serão adquiridas? *(pode marcar mais de uma)* *[C3, H10, H11]*
☐ Eu mesmo(a)  ☐ Radiologista do serviço  ☐ Médico solicitante, por contato prévio  ☐ Protocolo fixo do equipamento, sem escolha  ☐ Outro: ____  ☐ Não sei
 
**3.3** No seu serviço, o técnico pode alterar o protocolo padrão — incluir ou retirar sequências — sem autorização prévia de um médico? *[C3, H10]*
☐ Sim, livremente  ☐ Sim, em situações previstas em norma  ☐ Somente com autorização caso a caso  ☐ Não  ☐ Não sei
 
**3.4** Existe no seu serviço um protocolo **escrito** específico para investigação de demência? *[C3, H10, H12]*
☐ Sim, escrito e disponível na rotina  ☐ Existe, mas não é consultado na prática  ☐ Não existe  ☐ Não sei
 
**3.5** Quanto tempo é reservado na agenda para uma RM de crânio no seu serviço? *[C4, H09]*
☐ Menos de 20 minutos  ☐ 20 a 30 minutos  ☐ 31 a 45 minutos  ☐ Mais de 45 minutos  ☐ Varia muito  ☐ Não sei
 
**3.6** Pacientes idosos ou com dificuldade de cooperação recebem tempo adicional na agenda? *[C4, H09]*
☐ Sim, sempre  ☐ Sim, quando isso é sinalizado antes  ☐ Não  ☐ Não sei
 
---
 
**Seção 4 — Durante o exame: movimento e qualidade**
 
**4.1** Em exames de crânio de pacientes idosos, com que frequência o movimento do paciente compromete ao menos uma sequência? *[C4, H12]*
☐ Em quase todos  ☐ Na maioria  ☐ Em cerca de metade  ☐ Em poucos  ☐ Raramente ou nunca  ☐ Não sei
 
**4.2** Quando percebe movimento durante a aquisição, quais recursos você usa na prática? *(pode marcar mais de uma)* *[C4, H12]*
☐ Orientar novamente o paciente pelo interfone  ☐ Pedir que um acompanhante permaneça na sala  ☐ Usar coxins, faixas ou contenções leves  ☐ Trocar por uma sequência mais rápida  ☐ Usar recurso de correção de movimento do equipamento  ☐ Repetir a sequência  ☐ Encerrar o exame como está  ☐ Outro: ____
 
**4.3** O que costuma limitar a decisão de repetir uma sequência? *(pode marcar mais de uma)* *[C4, H09, H12]*
☐ Tolerância do paciente  ☐ Horário do próximo paciente na agenda  ☐ Orientação do serviço  ☐ Nada limita; repito quantas vezes for necessário  ☐ Outro: ____
 
**4.4** Existe no seu serviço algum critério **escrito** para decidir se uma imagem com artefato é aceitável? *[C4, H12]*
☐ Sim, há critério escrito  ☐ Não; é julgamento do técnico  ☐ Não; quem decide é o radiologista  ☐ Não sei
 
**4.5** Como você e seus colegas costumam se referir, no dia a dia, à imagem prejudicada por movimento do paciente? Escreva o termo que vocês realmente usam. *[C1 — jargão]* *(aberta curta, opcional)*
 
---
 
**Seção 5 — Dados clínicos que acompanham o exame**
 
**5.1** Quais informações clínicas costumam acompanhar o exame até quem vai laudar? *(pode marcar mais de uma)* *[C4, H13]*
☐ Idade  ☐ Queixa ou motivo do exame  ☐ Resultado de teste cognitivo (MMSE, MoCA ou similar)  ☐ Medicações em uso  ☐ Histórico familiar  ☐ Nenhuma além do que está no pedido  ☐ Não sei
 
**5.2** Como essas informações chegam à requisição de laudo? *[C4, H13]*
☐ Eu as digito a partir do prontuário  ☐ Já vêm preenchidas pelo médico solicitante  ☐ São importadas automaticamente do prontuário  ☐ Não são registradas  ☐ Outro: ____  ☐ Não sei
 
**5.3** Quando precisa buscar uma informação clínica no prontuário, com que frequência você não consegue localizá-la? *[C4, H13]*
☐ Sempre  ☐ Frequentemente  ☐ Às vezes  ☐ Raramente  ☐ Nunca  ☐ Não faço esse tipo de busca
 
**5.4** Já aconteceu de um exame seguir para laudo com dado clínico faltando ou trocado? *[C4, H13]* *(opcional)*
☐ Sim, em exames que realizei  ☐ Já vi acontecer no serviço  ☐ Não que eu saiba  ☐ Não sei  ☐ Prefiro não responder
 
---
 
**Seção 6 — Depois do exame: como o problema aparece**
 
**6.1** Quando um exame de crânio sai com problema — artefato, sequência faltante ou dado clínico incompleto —, em que momento isso **costuma** ser percebido? *[C4, **H07** — pergunta central]*
☐ Ainda durante o exame, com o paciente no aparelho  ☐ Logo depois, com o paciente ainda no setor  ☐ Depois que o paciente saiu, mas antes do laudo  ☐ Somente quando o laudo aponta o problema  ☐ Varia muito  ☐ Não sei
 
**6.2** Nos últimos 6 meses, com que frequência um paciente precisou ser chamado de volta para refazer ou completar uma RM de crânio? *[C4, H07]* *(opcional)*
☐ Nenhuma vez  ☐ 1 a 2 vezes  ☐ 3 a 5 vezes  ☐ Mais de 5 vezes  ☐ Não sei  ☐ Prefiro não responder
 
**6.3** Quando isso acontece, quanto tempo costuma passar até o paciente ser reconvocado? *[C4, H07]*
☐ No mesmo dia  ☐ Alguns dias  ☐ Algumas semanas  ☐ Mais de um mês  ☐ Varia muito  ☐ Não sei
 
**6.4** O console do equipamento ou o PACS sinaliza automaticamente algo sobre a qualidade da imagem ou sobre campos obrigatórios não preenchidos? *[C2, H14]*
☐ Sim  ☐ Não  ☐ Não sei
 
**6.5** Se respondeu "sim", descreva brevemente o que o sistema sinaliza. *[C2, H14]* *(aberta, opcional)*
 
**6.6** Antes de o paciente deixar o setor, existe alguma conferência do exame? *[C4, H07]*
☐ Sim, feita por mim, de forma estruturada  ☐ Sim, feita por mim, de forma informal  ☐ Sim, feita por outro profissional  ☐ Não há conferência antes da liberação  ☐ Não sei
 
---
 
**Seção 7 — Gravidade e percepções**
 
**7.1** Na sua avaliação, qual é a gravidade de cada situação abaixo para o resultado final do exame? *[C4 — gravidade dos erros; H07, H13]*
 
*(escala por linha: sem impacto · impacto pequeno · impacto moderado · impacto grande · crítico · não sei)*
 
| Situação |
|---|
| Artefato de movimento fora da região de interesse |
| Artefato de movimento sobre a região de interesse |
| Ausência de uma sequência prevista no protocolo |
| Resultado de teste cognitivo ausente na requisição |
| Paciente precisar ser reconvocado para refazer o exame |
 
**7.2** Indique o quanto concorda com cada afirmação. *[C5 — motivações, atitudes e valores; H07, H09, H10, H11]*
 
*(escala por linha: concordo plenamente · concordo parcialmente · não concordo nem discordo · discordo parcialmente · discordo totalmente)*
 
| Afirmação |
|---|
| Tenho autonomia para decidir como conduzir a aquisição quando o paciente não colabora |
| Tenho tempo suficiente para conferir o exame antes de liberar o paciente |
| Prefiro seguir o protocolo padrão a ajustar a aquisição caso a caso |
| As informações de que preciso para preparar o exame chegam até mim de forma completa |
| Mudanças nos sistemas que uso costumam atrapalhar mais do que ajudar |
 
---
 
**Seção 8 — Relato livre**
 
**8.1** Se puder, descreva a última vez em que um exame de crânio precisou ser refeito ou complementado. O que aconteceu e em que momento o problema foi notado? *[H07]* *(aberta, opcional)*
 
**8.2** Na sua experiência, o que poderia ter evitado esse retrabalho? *(aberta, opcional)*
 
**8.3** Há algo sobre essa rotina que as perguntas acima não cobriram e que você considera importante? *(aberta, opcional)*
 
Obrigado pela participação.
 
---
 
#### Como os dados serão analisados
 
**Fechadas de escolha e faixa.** Distribuição de frequência por pergunta, em números absolutos e com percentuais apenas se n ≥ 10. Três cruzamentos estão previstos, porque são eles que separam "problema estrutural" de "problema de um serviço":
 
- **6.1 × 1.3** — o momento de detecção muda conforme haja ou não radiologista no local? É o teste mais direto de H07 no contexto do C03.
- **6.1 × 6.6** — serviços com alguma conferência antes da liberação detectam mais cedo?
- **3.3 × 1.2** — a autonomia sobre o protocolo varia entre serviço público e privado?
**Escalas (7.1 e 7.2).** Distribuição por item e mediana, tratadas como ordinais — sem média aritmética, que não se aplica a Likert. Em 7.1 interessa a **ordenação** de gravidade atribuída pelos próprios técnicos: se "reconvocação" não for o item mais grave na percepção deles, a prioridade que demos ao requisito F03 precisa ser revista. Em 7.2, as respostas de autonomia e de tempo são confrontadas com as perguntas normativas equivalentes (3.3 e 3.5/3.6): divergência entre norma e percepção é achado, não ruído.
 
**Critério de decisão sobre H07, definido antes da coleta** para não ajustar a régua ao resultado:
 
| Resultado em 6.1 | Veredito sobre H07 |
|---|---|
| Maioria responde "depois que o paciente saiu" ou "somente quando o laudo aponta" | **sustentada** — a janela de correção existe e é perdida; T03 e F03 seguem |
| Maioria responde "ainda durante o exame" ou "com o paciente ainda no setor" | **refutada** — o problema do C03 não é geral; P04 e T03 precisam ser revistos |
| Respostas divididas, ou "varia muito" como maioria | **refinada** — identificar na análise cruzada qual condição separa os dois grupos, e reescrever H07 com essa condição |
 
As demais hipóteses seguem a mesma lógica: H09 é respondida por 3.5, 3.6 e pelo item de tempo em 7.2; H10 por 3.1, 3.2 e 3.3; H11 por 3.2 (cruzada com o instrumento do integrante de P03/T02); H12 por 2.2, 4.1 a 4.4; H13 por 5.1 a 5.4; H14 por 6.4 e 6.5.
 
**Abertas (4.5, 6.5, 8.1 a 8.3).** Codificação temática em dois passos: primeiro marcar, em cada relato, o momento em que o problema foi notado e a causa atribuída; depois agrupar os códigos e contar ocorrências. A 4.5 recebe tratamento à parte: os termos coletados formam um pequeno glossário do vocabulário real do técnico, que alimenta os rótulos de qualidade nas Entregas 9 e 11. Os relatos servem para explicar os números das fechadas e para encontrar causas que não previmos — e é nesse segundo ponto que eles podem derrubar o cenário, não só confirmá-lo.
 
**O que a análise não pode fazer.** Amostra de conveniência e autorrelatada: os resultados descrevem quem respondeu, não a categoria profissional. Nenhum número daqui vai para o repositório sem a nota de limitação de amostra ao lado.

## Síntese

> Cada integrante acrescenta aqui o parágrafo da sua coleta.

**A01 / I01 (Paulo) — P01, médico clínico.** A entrevista investigará se o médico clínico/generalista participa da avaliação descrita, quais dados e ferramentas utiliza e como interpreta as probabilidades, a faixa de confiança, o mapa de atenção e o peso de cada modalidade. H01 deverá ser sustentada, refutada ou refinada conforme a explicação ajude, não ajude ou ajude apenas em determinadas condições a compreender e calibrar a confiança. H03 será avaliada pela compreensão espontânea e pelas dúvidas relatadas. H06 será sustentada, refutada ou refinada conforme a prática de registro e recuperação de pareceres corresponda ao cenário C02. H02 será apenas refinada nesta etapa: a entrevista recolhe percepção sobre tempo, mas a redução efetiva deverá ser medida posteriormente com protótipo.

**A03 / I03 (Nathan) — P04, técnico em radiologia.** O conjunto P04 + C03 + T03 foi construído inteiramente por inferência a partir dos itens 4.1 e 4.2 da Entrega 1: nenhum técnico em radiologia foi ouvido até aqui. O questionário cobre as cinco categorias de dados de Barbosa e Silva e ataca quatro lacunas nesta ordem de prioridade: (1) **se o problema existe** — em que momento uma falha de qualidade ou de dado clínico é percebida, e com que frequência isso gera reconvocação; (2) **se o técnico é o decisor** que a persona supõe, isto é, quem define o protocolo, se há autonomia formal para alterá-lo e se ele se sente autorizado a usá-la; (3) **qual o repertório real** de ações diante de movimento, com que vocabulário o técnico nomeia o problema e qual gravidade ele próprio atribui a cada tipo de falha; (4) **se parte da solução já existe**, na forma de sinalização automática no console ou no PACS.

Depois da análise, estes são os desfechos esperados por hipótese:

| Hipótese/lacuna | Desfecho esperado | O que muda no projeto em cada caso |
|---|---|---|
| **H07** | sustentada, refutada ou refinada, pelo critério definido em I03 | Sustentada: T03 e F03 seguem para o protótipo. Refutada: P04 deixa de ser persona primária e T03 precisa ser substituída. Refinada: H07 é reescrita com a condição que separar os grupos (provavelmente a presença ou não de radiologista no local) |
| **H09** | sustentada ou refutada | Se não houver pressão real de agenda, o critério "dentro da agenda" sai do objetivo de T03 e a meta de usabilidade da Entrega 8 deixa de ser tempo de tarefa |
| **H10 / H11** | refinada | Define se o método 2.B do GOMS é caminho real; delimita o que a interface pode automatizar sem invadir decisão do radiologista. A resposta completa exige cruzar com o instrumento do integrante de P03/T02 |
| **H12** | refinada | Confirma ou reescreve os operadores de `METHOD 2.A` e o ponto de seleção 2.1.3 do HTA |
| **H13** | sustentada ou refutada | Sustenta ou derruba o `METHOD 3.B` e o requisito de trazer dados sem redigitação |
| **H14** | sustentada ou refutada | Se a sinalização já existir em parte dos serviços, ela entra como referência de comparação na Entrega 2 e o recorte da contribuição muda |

A refutação de H07 é um desfecho aceitável e previsto, não um fracasso da coleta: significaria que o recorte precisa mudar antes de a equipe investir em protótipo e teste. Os resultados — inclusive a limitação de amostra — serão registrados na coluna "Evidência obtida" da `RASTREABILIDADE.md`, preservando o enunciado original de cada hipótese.

## Checklist

- [ ] Hipóteses/lacunas prioritárias da Entrega 1 foram revisitadas.
- [ ] Se o escopo de IHC foi derivado de TCC técnico, a coleta investiga a plausibilidade do usuário, tarefa e contexto adotados.
- [ ] Perguntas não pressupõem que dashboard, CRUD, filtros ou relatórios sejam necessários; investigam a necessidade.
- [ ] Cada dado a coletar responde uma dúvida concreta do projeto ou justifica outra necessidade de informação.
- [ ] Parte A identifica dados e perfis de coleta de forma específica.
- [ ] Aspectos éticos são contextualizados para o projeto.
- [ ] Há uma técnica completa por integrante e técnicas distintas.
- [ ] Questionário está incluído entre as técnicas.
- [ ] Cada instrumento possui objetivo, público, procedimento e conteúdo integral.
- [ ] Perguntas evitam indução e coletam apenas dados necessários.
- [ ] Está claro como os dados serão analisados e usados no design.
