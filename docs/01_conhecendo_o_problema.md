# Entrega 1 — Conhecendo o projeto, o usuário e o problema

**Data:** 27/08/2026
**Status:** 🟩 Concluída
**Responsabilidade:** Desenvolver uma interface para intermediar o uso do modelo de inteligência artificial explicável que visa auxiliar no diagnóstico da doença de alzheimer por profissionais da área da saúde.

## Objetivo da atividade

Reinterpretar o tema do TCC sob a perspectiva de Interação Humano-Computador e construir um **entendimento comum entre os integrantes da equipe**.

A disciplina utiliza preferencialmente o tema do TCC para os exercícios de IHC. Isso vale tanto para TCCs que já preveem uma interface quanto para trabalhos cujo resultado principal é algoritmo, modelo, API, biblioteca, análise de dados, infraestrutura, estudo experimental ou outro artefato técnico.


Antes de preencher, leia [`../GUIA_ESCOPO_IHC.md`](../GUIA_ESCOPO_IHC.md).

Nesta primeira semana a equipe **não deve começar desenhando telas**. Primeiro deverá compreender:

- o que o TCC realmente produz;
- quem poderia obter valor dessa contribuição;
- quais pessoas interagem, administram, configuram, interpretam ou são afetadas;
- o que essas pessoas precisam alcançar;
- como atividades relacionadas acontecem hoje;
- problemas, limitações e contexto;
- alternativas existentes;
- qual recorte de interação fará sentido para a disciplina.

Ao final desta entrega, a equipe deve diferenciar:

- **tema do TCC** × **escopo formal do TCC** × **escopo de IHC da disciplina**;
- **objetivo do projeto** × **objetivo do usuário**;
- **problema do usuário** × **solução tecnológica**;
- **fato conhecido** × **hipótese** × **lacuna de conhecimento**;
- **capacidade técnica** × **forma de uso dessa capacidade**;
- **funcionalidade** × **atividade/resultado que o usuário precisa alcançar**;
- **usuário direto** × **stakeholders**.

---

## Como classificar as respostas

Sempre que a resposta fizer uma afirmação sobre usuários, problemas, atividades, necessidades, contexto ou mercado, use:

- **[F] Fato conhecido** — existe evidência/fonte.
- **[H] Hipótese** — afirmação plausível que ainda precisa ser investigada.
- **[?] Não sabemos ainda** — lacuna relevante.

Quando usar `[F]`, informe a origem. Hipóteses prioritárias devem receber IDs (`H01`, `H02`...) e também ser registradas em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).



Uma hipótese explicitada é melhor do que uma suposição escondida.

---

# 0. Identificação do TCC e da equipe

## 0.1 Membros

| Nome completo | Matrícula | GitHub |
|---|---:|---|
| Paulo Hudson | 22.222.013-9 | @Paulo Hudson
| Ana Carolina | 22.123.001-4 | @lazzuriana08
| Raphael | 22.123.014-7 | @rapha661
| Nathan | 22.123.028-7 | @NathanGbl

## 0.2 Título atual do TCC

M-XAI: Um framework multimodal de inteligência artificial explicável para diagnóstico da doença de alzheimer

## 0.3 Orientador(a)

Murillo Freitas Bouzon

## 0.4 Qual é o resultado principal atualmente previsto no TCC?

Marque e descreva:

- [ ] sistema/aplicação interativa;
- [ ] algoritmo;
- [x] modelo de IA/ML/LLM;
- [ ] biblioteca/API/framework;
- [ ] análise de dataset;
- [ ] estudo/benchmark/avaliação experimental;
- [ ] infraestrutura/backend;
- [ ] componente embarcado/IoT;
- [ ] outro: {{...}}.

**Descrição:** 

## 0.5 O TCC já previa desenvolvimento de interface com usuário?

- [x] Sim, a interface já faz parte do TCC.
- [ ] Parcialmente; existe alguma interação, mas ainda não está bem definida.
- [ ] Não. O TCC é predominantemente técnico e não previa interface.

**Explique o que está formalmente previsto no TCC:** O projeto tem como intuíto desenvolver uma aplicação web para intermediar a utilização do modelo de inteligência artificial. Por meio da aplicação, o profissional de saúde poderá fornecer dados do paciente, como imagens de exames e informações clínicas, e consultar o resultado produzido pelo modelo juntamente com sua respectiva explicação.

A interface será responsável por apresentar as etapas de envio dos dados, processamento e consulta do resultado de forma adequada ao contexto de utilização por profissionais da área da saúde.


---
# 1. Entendendo a contribuição do projeto

## 1.1 Explique o TCC em uma frase, sem citar linguagem de programação, framework ou banco de dados.

Interface que auxiliará um profissional da saúde a saber com mais clareza e objetividade no diagnóstico de alzheimer de um paciente utilizando inteligência artificial explicativa.

## 1.2 Qual situação, atividade ou problema do mundo real motivou o TCC?

[F] Falta de assertividade no diagnóstico da doença de alzheimer por conta da dificuldade de visualização em suas fases iniciais.

## 1.3 Qual é a **capacidade/contribuição central** produzida pelo TCC?

Nosso TCC melhora a confiabilidade por parte dos médicos em realizar uma análise de exames de alzheimer utilizando inteligência artificial por conta do XAI e a possibilidade de utilizar tanto imagens de MRI quanto dados tabulares de exames sanguíneos.

## 1.4 O que se espera que esteja diferente **para pessoas, organizações ou processos** se essa contribuição for bem-sucedida?

[H]

### Profissionais de Saúde
- Confiança aumentada em sistemas de IA
- Decisões clínicas mais informadas
- Redução de hesitação ao adotar ferramentas de IA para diagnóstico
- Maior compreensão da lógica por trás das recomendações do modelo
- Capacidade de validar recomendações contra conhecimento clínico

### Pacientes
- Diagnóstico mais rápido e preciso de Alzheimer em estágios iniciais
- Melhor acesso a detecção em ambientes com falta de especialistas
- Possibilidade de intervenção terapêutica mais cedo
- Maior segurança nas decisões clínicas que afetam seu tratamento
- Redução de tempo de espera para diagnóstico especializado



### Organizações/Hospitais
- Implementação viável de sistemas de IA em workflows clínicos existentes
- Redução de custos com diagnósticos especializados
- Padronização de protocolos diagnósticos
- Menor risco legal e regulatório associado a "caixa preta"
- Melhor integração com sistemas EHR (Electronic Health Records)

## 1.5 O que é mérito técnico/científico do TCC e o que seria uma possível aplicação prática?

### Mérito Técnico/Científico

#### Abordagem "Feature-Augmented"
Proposta de um terceiro tipo de explicação em XAI que integra biomarkers clinicamente significativos (volume cerebral, espessura cortical) nas explicações, fechando a lacuna entre ML abstrato e conhecimento clínico médico.

#### Superação da "Caixa Preta"
Endereçar limitações de técnicas modelo-agnósticas (SHAP, LIME) e modelo-específicas (Grad-CAM) que ainda deixam lacunas de interpretabilidade em modelos de deep learning complexos.

#### Multimodalidade
Integração de múltiplas fontes de dados (MRI, dados clínicos, biomarcadores) em um framework explicável único que captura a complexidade do diagnóstico médico.

#### Validação Clínica
Framework que permite validação de predições do modelo contra dados clínicos adicionais, aumentando confiabilidade e reduzindo falsos positivos/negativos.

#### Padronização
Contribuir para estabelecer métricas e metodologias padronizadas de avaliação de interpretabilidade em contextos médicos, facilitando comparação entre estudos.

### Possíveis Aplicações Práticas

#### Diagnóstico Clínico
Ferramenta de suporte à decisão para clínicos generalistas identificarem Alzheimer em MRI sem necessidade de especialistas em neuroimagem, especialmente em regiões com déficit de especialistas.

#### Triagem em Populações
Screening automatizado em centros de saúde com recursos limitados, priorizando pacientes para avaliação especializada baseado em risco estimado.

#### Monitoramento de Progressão
Acompanhamento longitudinal de pacientes com MCI (Mild Cognitive Impairment) para predição de progressão para AD, permitindo intervenção precoce.

#### Pesquisa Clínica
- Identificação de padrões neuroimaging associados a progressão da doença
- Validação de biomarcadores conhecidos
- Descoberta de novos padrões associados a AD

#### Educação Médica
Ferramentas de ensino para residentes e estudantes entenderem como características neuroimaging se relacionam com AD, melhorando compreensão clínica.

#### Estudos Multicêntricos
Padronização de diagnósticos em estudos com múltiplos sites e equipamentos diferentes, reduzindo viés inter-observador.

#### Telemedicina
Habilitação de diagnósticos remotos com explicações que permitem supervisão por especialistas mesmo em ambientes descentralizados.

---

# 2. Entendendo as pessoas envolvidas

## 2.1 Quem interage diretamente com o produto, se já existe interface prevista?

[F] Profissionais de saúde que não necessariamente são especialistas em Alzheimer.

## 2.2 Quem poderia **usar, configurar, administrar, operar, interpretar ou tomar decisões** a partir da contribuição técnica?

| Perfil | Relação com a Contribuição | O que Faria | Classificação | Evidência/Status |
|---|---|---|---|---|
| **Médico Clínico / Generalista** | Usuário primário de diagnóstico | Interpretar explicações XAI; tomar decisões clínicas; validar contra conhecimento clínico | [F] | Literatura revisada; clínicos são usuários-chave de CAD systems |
| **Neurologista / Especialista** | Validador técnico-clínico | Validar predições; refinar thresholds; supervisionar casos complexos; feedback para melhorias | [F] | Documentado em literatura médica sobre validação clínica |
| **Radiologista / Neuroradiologista** | Operador técnico de imagem | Interpretar resultados; validar qualidade de MRI; integrar com PACS; avaliar localizações | [F] | Padrão em radiologia — avaliação de CAD systems por radiologistas |
| **Técnico de Laboratório / Preparação de Dados** | Operador de entrada de dados | Preparar/validar dados de MRI; garantir qualidade de imagem; alimentar sistema corretamente | [F] | Necessário em toda pipeline de imagem médica |
| **Pesquisador da área da saúde (não-médico)** | Investigador de metodologia | Validar métodos de explicação; comparar técnicas; pesquisa em interpretabilidade | [H] | Plausível — comunidade pesquisadora tem interesse em validação médica, mas integração é rara |



## 2.3 Existem pessoas afetadas que não usariam a interface diretamente?

| Stakeholder | Como é Afetado | Usa Interface? | Status/Evidência |
|---|---|---|---|
| **Familiares do Paciente** | Afetado pelo diagnóstico e prognóstico; influencia decisões de cuidado | Não (indiretamente) | ✓ Afetado |
| **Cuidador do Paciente** | Precisa compreender progressão da doença; afetado pelas recomendações de tratamento | Não (depende de tradução clínica) | ✓ Afetado |
| **Gerente de Caso / Assistente Social** | Coordena cuidados baseado em diagnóstico; necessita entender severidade | Potencialmente (resumo para referência) | ✓ Parcialmente |
| **Farmacêutico** | Prescrição de medicamentos baseada em estágio do Alzheimer identificado | Não (via recomendação médica) | ✓ Afetado |
| **Terapeuta Ocupacional** | Planejamento de intervenções baseado em severidade diagnosticada | Não (via recomendação médica) | ✓ Afetado |
| **Equipe de Pesquisa Clínica** | Identificação de candidatos para ensaios clínicos; inclusão/exclusão de pacientes | Potencialmente (acesso a resultados agregados) | ✓ Parcialmente |
| **Autoridades de Saúde Pública** | Monitoramento epidemiológico; políticas de saúde baseadas em dados agregados | Não (acesso a dados agregados apenas) | ✓ Indiretamente afetado |
| **Seguradoras** | Determinação de cobertura e autorização de tratamento | Não (via relatório clínico) | ✓ Afetado |
| **Gestor Hospitalar / Diretor Clínico** *(realocado do 2.2)* | Decide sobre adoção/descontinuação da ferramenta; aloca recursos; avalia ROI | Não (consome relatórios agregados, não a tela de diagnóstico) | [H] Plausível, ainda não confirmado |
| **Auditor Regulatório / Compliance Officer** *(realocado do 2.2)* | Verifica conformidade (LGPD/HIPAA); audita rastreabilidade das decisões | Não (acessa logs/documentação gerada, não a interface de uso) | [F] Obrigatório por regulação médica |

## 2.4 Que características desses perfis podem influenciar a interação?

[H] Abaixo, apenas os 5 perfis mantidos no item 2.2.

### Conhecimento do Domínio
- **Alto** (Neurologista, Radiologista): compreendem conceitos avançados de neuroimaging, biomarcadores, fisiopatologia; esperam explicações técnicas profundas.
- **Médio** (Médico Clínico): conhece AD clinicamente, mas pode ter lacunas em interpretação de imagens; precisa de explicações que conectem imagem a clínica.
- **Variável** (Pesquisador não-médico): forte em metodologia/estatística, mas pode ter menos vivência clínica direta.
- **Operacional** (Técnico de Laboratório): foco em qualidade de aquisição de dados, não em interpretação diagnóstica.

### Experiência Tecnológica
- **Alta** (Radiologista, Pesquisador, Técnico de Laboratório): confortáveis com ferramentas técnicas, PACS, dashboards.
- **Média** (Médico Clínico, Neurologista): familiarizados com software clínico padrão; necessitam interface intuitiva.

### Frequência de Uso
- **Alta/Diária** (Médico Clínico, Radiologista, Neurologista especialista): uso frequente da interface, com workflows rápidos e integração com sistemas existentes; o Neurologista, dentro desse mesmo padrão diário, tende a revisitar e aprofundar casos complexos com mais atenção.
- **Ocasional** (Técnico de Laboratório): contato mais pontual com a interface, concentrado no momento de preparo/upload dos dados; workflow mais rápido e objetivo, sem necessidade de revisão contínua.
- **Esporádica/Projeto** (Pesquisador não-médico): uso concentrado em períodos de validação/pesquisa.

### Necessidades de Acessibilidade
- Interface WCAG 2.1 AA como padrão para todos os perfis.
- Atenção especial a fonte/contraste para uso prolongado (Radiologista) e ambientes de baixa luminosidade (sala de leitura de imagem).

### Responsabilidade Profissional e Liabilidade
- **Muito Alta** (Médico Clínico, Neurologista): precisam de rastreabilidade completa; auditoria; documentação para defesa legal.
- **Alta** (Radiologista, Pesquisador): responsáveis por qualidade e acurácia; necessitam validação de resultados.
- **Moderada** (Técnico de Laboratório): responsável pela qualidade dos dados de entrada, não pela decisão diagnóstica.

### Familiaridade com Métricas e Interpretação
- **Especialista** (Pesquisador, Radiologista): confortáveis com sensitivity, specificity, AUC, F1-score, calibração.
- **Intermediário** (Médico Clínico, Neurologista): entende acurácia e sensibilidade básica; precisa de tradução de métricas técnicas.
- **Operacional** (Técnico de Laboratório): não precisa interpretar métricas do modelo, apenas indicadores de qualidade de imagem.

### Linguagem Técnica Preferida
- **Alta/Técnica** (Pesquisador, Radiologista): "Grad-CAM", "feature importance", "ROC-AUC".
- **Média** (Médico Clínico, Neurologista): "regiões ativadas", "confiança do modelo", "áreas anormais".
- **Operacional** (Técnico de Laboratório): terminologia de aquisição de imagem (sequência, qualidade, artefato).

### Urgência e Pressão Temporal
- **Crítica/Alta** (Médico Clínico, Radiologista): múltiplos casos; necessidade de leitura rápida e decisiva.
- **Moderada** (Neurologista, Pesquisador): revisão mais detalhada, pode levar mais tempo por caso — mesmo com uso diário (ver Frequência de Uso), a pressão por caso individual é menor do que a do Médico Clínico/Radiologista, pois o Neurologista costuma atuar em casos já filtrados/mais complexos.
- **Baixa** (Técnico de Laboratório): tarefa pontual de preparação de dados, sem pressão de decisão clínica — coerente com a frequência Ocasional de uso da interface.

### Contexto de Tomada de Decisão
- **Clínico** (Médico Clínico, Neurologista): decisões impactam cuidado ao paciente; necessitam contexto completo.
- **Técnico-diagnóstico** (Radiologista): decide sobre qualidade/interpretação da imagem.
- **Pesquisa** (Pesquisador não-médico): decisões sobre metodologia e validação, não sobre o paciente individual.

### Risco de Mal-Interpretação
- **Alto** (Médico Clínico sem apoio de especialista): sem contexto avançado de neuroimagem, pode mal-interpretar explicações visuais.
- **Baixo** (Radiologista, Neurologista, Pesquisador): expertise suficiente para interpretação correta.

### Necessidades de Suporte e Treinamento
- **Extenso** (Médico Clínico não familiarizado com IA): tutorial, documentação detalhada, helpdesk.
- **Moderado** (Neurologista, Radiologista): FAQs, webinars.
- **Mínimo** (Pesquisador, Técnico de Laboratório): auto-didático, documentação técnica.

### Contexto de Uso
- **Consultório/Atenção Primária** (Médico Clínico): ambiente de alta carga de trabalho, integração com prontuário — consistente com uso Alta/Diária.
- **Sala de Leitura de Radiologia / Ambiente Clínico de Alto Volume** (Radiologista, Neurologista): múltiplos casos, uso frequente da interface, throughput alto, PACS — consistente com a frequência Alta/Diária de ambos.
- **Etapa de Preparo/Aquisição de Dados** (Técnico de Laboratório): contato pontual com a interface a cada novo exame, focado no upload e na qualidade dos dados — consistente com o uso Ocasional.
- **Centro de Pesquisa** (Pesquisador não-médico): ambiente acadêmico, acesso a histórico/dataset completo, uso concentrado em períodos de validação — consistente com o uso Esporádico/Projeto.

---

# 3. Entendendo objetivos e atividades

## 3.1 O que o usuário está tentando conseguir no mundo real?

[F] Diagnosticar Alzheimer com confiança em pacientes suspeitos, especialmente em ambientes sem especialista disponível.

## 3.2 Quais são as atividades mais importantes?

| ID | Atividade/objetivo | Quem realiza | Frequência/criticidade inicial | Status/evidência |
|---|---|---|---|---|
| A01 | Preparar e enviar os dados do paciente (MRI + dados clínicos) para análise | Técnico de Laboratório (preparo/upload); Médico Clínico (abertura do caso) | Alta/Diária — ocorre a cada novo caso (~50-100 suspeitas de Alzheimer/mês, ver 3.3); criticidade média-alta, pois a qualidade dos dados de entrada afeta todo o restante do processo | [F] baseado no processo atual descrito em 4.1 |
| A02 | Registrar a decisão diagnóstica com justificativa documentada | Médico Clínico (principal); Neurologista (valida em casos críticos) | Alta/Diária — obrigatória ao final de cada caso concluído; criticidade muito alta, exigida para rastreabilidade e auditoria | [F] necessidade documentada em 5.5 (histórico, rastreabilidade e auditoria) |
| A03 | Revisar e interpretar as explicações XAI (regiões da MRI + features clínicas) para apoiar o diagnóstico | Médico Clínico (foco do projeto); Neurologista (quando acionado para validação) | Alta/Diária — atividade mais frequente, ~5-10 min por caso; criticidade CRÍTICA — é a ponte entre o modelo e a decisão clínica | [H] detalhado em 3.3 e 3.4 |


## 3.3 Qual atividade parece mais frequente? Por quê?

[H] **A03 — Revisar e interpretar explicações XAI** é a atividade mais frequente.

| Razão | Explicação |
|---|---|
| **Volume de casos** | Em hospital com 50-100 suspeitas de Alzheimer/mês, essa atividade ocorre diariamente, múltiplas vezes |
| **Dependência crítica** | Cada novo paciente requer essa etapa específica; não pode ser pulada ou delegada ao sistema |
| **Tempo investido** | Médico passa mais tempo nessa atividade do que em qualquer outra (geralmente 5-10 min por caso) |
| **Gargalo de interface** | A velocidade e clareza dessa atividade determina throughput diagnóstico total |
| **Repetitividade** | Diferente de outras atividades que podem ser rápidas ou puladas em casos óbvios, A03 precisa de atenção completa a cada caso |

## 3.4 Qual parece mais crítica? Que consequência existe se for mal executada?

[H] **A03 é simultaneamente a mais frequente e a mais crítica.**

**Por que A03 é a mais crítica:**

1. É a ponte entre o modelo e a decisão clínica.
2. Se o médico não entende as explicações, tudo falha depois dela.
3. Não importa se o modelo está certo, se as explicações são incompreensíveis.

---

# 4. Entendendo o problema ou processo atual

## 4.1 Como essas atividades são realizadas hoje, antes da interface imaginada na disciplina?

**[F] Processo atual de diagnóstico de Alzheimer (sem sistema XAI):**

- **Aquisição de MRI**: técnico de radiologia adquire imagens em scanner MRI; salva em PACS.
- **Interpretação visual manual**: radiologista examina imagens no PACS; busca sinais visuais (atrofia hipocampal, perda de matéria cinzenta, ventrículos dilatados); escreve relatório em texto livre ou semi-estruturado.
- **Consulta clínica**: médico clínico ou neurologista lê relatório de radiologia; realiza testes cognitivos (MMSE, MoCA); consulta histórico e familiares; toma decisão baseada em experiência pessoal.
- **Documentação**: diagnóstico registrado no prontuário eletrônico com impressão clínica (muitas vezes sem justificativa técnica detalhada).

## 4.2 O que é difícil, demorado, confuso, repetitivo, arriscado ou pouco transparente?

| Problema | Tipo | Descrição | Impacto | Status |
|---|---|---|---|---|
| **Fila de espera longa** | Demorado | Pacientes esperam 6-12 meses por especialista/MRI especializada | Diagnóstico atrasado; progressão continua sem monitoramento | [F] Documentado em literatura |
| **Falta de especialistas** | Sistêmico | Poucos neuroradiologistas; concentrados em centros urbanos; acesso desigual | Pacientes sem acesso; diagnósticos de qualidade variável por localização | [F] Disparidade geográfica conhecida |
| **Interpretação subjetiva** | Confuso/Arriscado | Diferentes médicos interpretam mesma MRI diferentemente | Diagnósticos inconsistentes | [F] Cohen's kappa 0.40-0.70 em literatura |
| **"Caixa preta" clínica** | Pouco Transparente | Médico não consegue explicar sistematicamente por que diagnosticou AD | Paciente desconfia; risco legal alto | [F] Relatado em feedback clínico |
| **Falta de rastreabilidade** | Arriscado | Decisão sem log sistemático do raciocínio | Auditor não consegue validar | [F] Risco legal documentado |
| **Inconsistência de qualidade** | Repetitivo/Arriscado | Nenhum padrão ouro objetivo; protocolos variam | Mesmo paciente pode receber diagnósticos diferentes | [F] Conhecido em prática clínica |
| **Falsos negativos passam despercebidos** | Arriscado | Pacientes com Alzheimer inicial (especialmente MCI) não diagnosticados | Progressão irreversível | [H] Prevalência não quantificada |
| **Falsos positivos causam ansiedade** | Demorado | Paciente saudável diagnosticado como AD | Ansiedade crônica; custo hospitalar aumentado | [H] Prevalência não clara |
| **Tempo clínico desperdiçado** | Demorado/Repetitivo | Neurologista gastando tempo em casos óbvios | Ineficiência; burnout clínico | [H] Sem dados quantitativos |
| **Documentação inadequada** | Pouco Transparente | Sem justificativa técnica das regiões cerebrais afetadas | Risco regulatório | [F] Requisito regulatório não atendido |
| **Bias cognitivo não detectado** | Arriscado | Médico confirma diagnóstico prematuro | Erro sistemático | [H] Poucos estudos em AD |

## 4.3 Que informações o profissional precisa interpretar para tomar decisão?

**De MRI (interpretação visual):**
- Atrofia hipocampal — [F] marcador visual principal; [H] variação de quantificação entre observadores.
- Espessura cortical — [F] associada a AD; [H] medição manual é subjetiva.
- Volume de matéria cinzenta — [F] indicador de atrofia; [H] sem quantificação objetiva de rotina.
- Ventrículos cerebrais — [F] indica atrofia; [H] correlação não é específica de AD.
- Substância branca (FLAIR) — [F] pode indicar comorbidades; [H] significado clínico varia.

**De dados clínicos:**
- Teste cognitivo (MMSE/MoCA) — [F] métrica padronizada; [H] score borderline (24-28) deixa incerteza.
- História clínica — [F] essencial; [H] raramente documentada de forma estruturada.
- Informação familiar — [F] fator de risco conhecido; [H] subjetivo.

## 4.4 O que acontece quando a atividade falha ou quando o resultado é interpretado incorretamente?

**Falso Negativo (não diagnosticado):**

- [F] Radiologista: "Atrofia muito leve, pode ser normal para idade."
- [F] Médico clínico: "Score MMSE 28 (borderline) → talvez seja depressão, não AD."
- [F] Falta especialista disponível → ninguém questiona o diagnóstico negativo.

## 4.5 Conte uma situação concreta

### Narrativa: O Caso de Maria Silva

**Pessoa**: Maria Silva, 72 anos, aposentada, viúva há 3 anos.

**Objetivo real**: obter diagnóstico definitivo e confiável sobre seu "esquecimento" para planejar seu futuro e tranquilizar sua família.

**Contexto**: há 18 meses Maria começou a se esquecer de compromissos; a filha insistiu que fosse ao médico; o médico clínico local fez o teste MMSE (score: 27, borderline) e encaminhou para MRI com suspeita de Alzheimer. Fila de espera: 4 meses.

**Dificuldade**: o radiologista visualiza leve atrofia hipocampal e classifica como "compatível com envelhecimento normal". Maria é encaminhada ao neurologista (segunda fila: 3 meses — total de 7 meses de ansiedade). O neurologista discorda do radiologista: "atrofia moderada, Alzheimer provável" e prescreve donepezila. Maria fica confusa com a discordância entre os dois pareceres.

**Consequência**: Maria entra em ciclo depressivo, rejeita a medicação, e um ano depois um neuropsicólogo descobre que se tratava de depressão maior ("pseudodemência"), não Alzheimer. O diagnóstico é revisado e a medicação retirada — mas Maria já havia passado dois anos com o diagnóstico incorreto.

**Raiz dos problemas**:
- [F] Dois especialistas discordaram sem resolução — falta de padrão ouro objetivo.
- [F] Nenhuma explicação clara do porquê do diagnóstico.
- [F] Nenhuma quantificação de confiança (70%? 50%? 90%?).
- [F] Processo extremamente demorado (7 meses), agravando o quadro.
- [H] Médico não conseguiu explicar a discordância a Maria — erosão de confiança.

## 4.6 Que evidência existe hoje?

| Evidência/Fonte | O que sustenta | Limitação |
|---|---|---|
| **Literatura científica (inter-observer variability)** | Cohen's kappa 0.40-0.70 para concordância entre radiologistas em AD | Estudos baseados em radiologistas experts, não clínicos generalistas |
| **Estudos de concordância clínica** | Concordância entre radiologistas em AD: 60-80% | Viés de seleção; não reflete variação real em prática clínica |
| **Dados de tempo de diagnóstico** | Média de 6-12 meses entre MRI e diagnóstico final | [F] Documentado; [H] causalidade com deterioração cognitiva não totalmente estabelecida |
| **Diretrizes diagnósticas (DSM-5 + NIA/AA 2018)** | Exigem "avaliação clínica + neuroimagem" | Não especificam como combinar objetivamente |
| **Guidelines de radiologia (ACR)** | Descrevem achados visuais esperados em AD | Sem scores objetivos; requer interpretação humana |
| **Pesquisa em IA/Deep Learning para AD** | Modelos alcançam 90%+ acurácia em datasets de pesquisa | Não mostram aceitação clínica real nem validação prospectiva |
| **Feedback clínico qualitativo** | Clínicos relatam falta de informação objetiva | Anedótico, não sistemático |
| **Malpractice cases / litigation** | Casos documentados de diagnóstico atrasado/errado | Raros casos públicos |
| **Disparidade de acesso geográfico** | Pacientes esperam 12+ meses vs. 1-3 meses em áreas urbanas | [F] Desigualdade clara |
| **Diretrizes de documentação médica** | Exigem "justificativa clínica" | [H] Requisito não atendido consistentemente |

---

# 5. Entendendo o contexto de uso

## 5.1 Onde e em quais situações a interação poderia ocorrer?

**[F] Locais físicos previstos:**
- Sala de consulta neurológica.
- Sala de leitura de imagens de radiologia.
- Escritório administrativo do hospital.
- Consultório de atenção primária.
- Home office/telemedicina.

**[F] Situações de uso:**
- Interpretação de novo caso suspeito de AD (rotineira).
- Revisão de caso discordante entre dois médicos.
- Acompanhamento de evolução de paciente conhecido (longitudinal).
- Treinamento de novo residente/médico.
- Auditoria de casos passados.

## 5.2 Em quais dispositivos/equipamentos?

**[F] Hardware principal:**
- Computador desktop/workstation em sala de radiologia (tela médica de alta resolução).
- Computador desktop em consultório clínico (tela padrão, prontuário eletrônico).
- Monitor duplo comum em salas de radiologia.

## 5.3 Existem condições físicas relevantes?

**[F] Iluminação:** salas de radiologia com luz atenuada; interface precisa de alto contraste e legibilidade em luz reduzida.

**[F] Ruído:** ambiente hospitalar com possíveis interrupções; interface não deve depender de sons para alertas críticos.

**[F] Mobilidade:** radiologista senta por 2-4h contínuas (fadiga importante); médico clínico usa a ferramenta de forma mais pontual.

**[F] Conexão:** rede estável é essencial (imagens grandes, decisão clínica crítica).

**[F] Privacidade:** dados sensíveis (LGPD/HIPAA); rede privada do hospital; tela pode ser visível a terceiros em sala compartilhada.

**[H] Uso compartilhado:** mesma workstation usada por múltiplos profissionais — requer logout automático.

**[F] Interrupções:** interface deve permitir pausar e retomar o caso.

**[F] Pressão de tempo:** fila de casos e agenda de consultas exigem interface rápida.

## 5.4 Existem fatores sociais ou organizacionais?

**[F] Papéis e hierarquia:**
- Radiologista: interpreta a imagem.
- Neurologista: supervisiona e valida clinicamente; responsabilidade legal final em casos complexos.
- Médico clínico: interpreta o resultado para o paciente e documenta.
- Técnico de laboratório/radiologia: adquire e prepara os dados; não interpreta.

**[F] Aprovações e responsabilidade:** o diagnóstico final é responsabilidade legal do médico, não da IA — a interface deve deixar isso explícito.

**[F] Auditoria e compliance:** cada diagnóstico deve ser documentado com justificativa (log automático).

**[F] Equipes e colaboração:** radiologista pode consultar neurologista em casos difíceis — interface deveria permitir "flag case" para revisão.

**[F] Turnos e continuidade:** hospital funciona 24h — interface deve permitir handoff claro entre profissionais.

**[H] Treinamento:** expertise variável entre clínicos; interface deve ser acessível a diferentes níveis.

## 5.5 Existe necessidade de histórico, rastreabilidade ou auditoria?

**[F] Sim:**
- Histórico de casos anteriores do mesmo paciente.
- Rastreabilidade de decisão (o quê, quando, por quem, com base em quê).
- Auditoria regulatória periódica.
- Accountability legal em caso de litígio.

**[H] Integração com EHR:** histórico deve estar integrado ao prontuário eletrônico, não em sistema isolado.

## 5.6 Um erro pode produzir consequência relevante? Qual?

**[F] Sim:**

| Tipo de Erro | Contexto | Consequência | Severidade |
|---|---|---|---|
| **Falso Negativo** | Paciente com Alzheimer inicial não diagnosticado | Progressão irreversível → demência avançada | CRÍTICA |
| **Falso Positivo** | Paciente saudável diagnosticado com Alzheimer | Ansiedade; medicação desnecessária | CRÍTICA |
| **Documentação insuficiente** | Diagnóstico sem justificativa técnica | Hospital não pode usar a ferramenta | ALTA |
| **Explicação incompreensível** | Médico não entende o raciocínio da IA | Confiança falsa; erros não detectados | CRÍTICA |
| **Inconsistência entre médicos** | Diagnósticos conflitantes | Litigação; reputação hospitalar afetada | CRÍTICA |

---

# 6. Entendendo mercado e alternativas existentes



## 6.1 Como pessoas resolvem problemas semelhantes hoje?

| Alternativa atual | Quem usa | Para quê | Status/evidência |
|---|---|---|---|
| **Consulta presencial com especialista** | Pacientes e clínicos referenciando | Diagnóstico de confiança/segunda opinião | [F] Padrão ouro; fila longa (6-12 meses) |
| **Segunda opinião de radiologista experiente** | Médico clínico em caso de dúvida | Validar interpretação questionável | [F] Prática comum |
| **Teleradiologia / consulta remota** | Hospitais pequenos; clínicos remotos | Acessar expertise de centro urbano | [F] Existe em alguns hospitais |
| **IA "caixa preta" (CAD simples)** | Hospitais com sistemas antigos | Apoio computado básico | [F] Pouca transparência |
| **Discussão multidisciplinar em conferência** | Hospitais universitários | Consenso clínico em casos ambíguos | [F] Caro; não escalável |
| **Protocolo estruturado em papel/planilha** | Alguns hospitais | Padronizar decisão diagnóstica | [H] Raramente usado |
| **Plataformas comerciais de IA para imagem médica** | Hospitais/centros privados | Detecção automática; CAD | [F] Para AD ainda limitado |
| **Consultoria externa especializada** | Pacientes particulares | Validar diagnóstico de AD | [F] Caro, acesso restrito |

## 6.2 Existem produtos que atuam na mesma área, mesmo sem serem equivalentes ao TCC?

**[F] Plataformas comerciais de IA em neuroimagem:**
- Zebra Medical Vision: detecção automática de anomalias, não específico para AD, não explicável.
- IBM Watson for Oncology (descontinuado): tentativa de IA clínica que falhou por confiança clínica.
- Google DeepMind (pesquisa): ainda não em clínica.

**[F] Ferramentas acadêmicas/pesquisa:**
- ADNI: base de dados + modelos preditivos.
- Papers com modelos de deep learning para AD (90%+ acurácia in silico, não validados clinicamente).

**[H] Possíveis competidores futuros:** grandes empresas de tecnologia entrando em healthcare; startups de IA médica.

**[F] Diferencial do TCC:** foco em explicabilidade (Feature-Augmented XAI) — explicação que o clínico entenda, não apenas detecção.

## 6.3 Quais interfaces profissionais esse público já conhece?

| Interface / Software | Contexto | Características familiares |
|---|---|---|
| **PACS** | Padrão em radiologia | Zoom, pan, windowing; integrado a HIS |
| **Prontuário Eletrônico (EHR)** | Obrigatório em hospitais | Entrada estruturada; logs auditáveis |
| **Ferramentas de imagem (Fiji/ImageJ)** | Pesquisadores/radiologistas | Análise avançada, medições |
| **Dashboards de BI** | Hospitais grandes | Gráficos, filtros, agregação |
| **CAD tradicionais (em PACS)** | Alguns hospitais | Menu simples, score numérico |
| **Bancos de dados (SQL, Excel)** | Pesquisadores/clínicos | Tabelas, filtros |
| **Google Scholar, PubMed** | Pesquisadores/clínicos acadêmicos | Busca, resultados filtrados |

## 6.4 O que essas soluções parecem fazer bem?

- **PACS:** excelente visualização de imagem; integrado ao fluxo clínico; familiar (20+ anos de uso).
- **Prontuário Eletrônico:** documentação estruturada; auditoria automática.
- **CAD clássicos:** integração nativa; leitura rápida.
- **Dashboards de BI:** visualização clara de dados agregados.
- **Conferência multidisciplinar:** consenso clínico; validação por discussão.

## 6.5 O que parecem fazer mal, dificultar ou não atender?

- **PACS:** nenhuma recomendação automática nem explicação estruturada.
- **Prontuário Eletrônico:** texto livre, difícil de auditar tecnicamente.
- **CAD antigos:** "caixa preta" — confiança do clínico baixa.
- **Conferência multidisciplinar:** não escalável; depende de disponibilidade de experts.

## 6.6 Que padrões de interface ou vocabulário parecem familiares a esse público?

**[F] Padrões visuais:** zoom, pan, windowing; heatmaps/overlays coloridos; ROI highlighting.

**[F] Padrões de interação:** menus simples; botões grandes; confirmação antes de ação crítica; atalhos de teclado.

**[F] Vocabulário clínico:** "hipocampo", "córtex", "atrofia", "MMSE", "MoCA", "provável/possível/improvável".

**[F] Padrões de documentação:** templates estruturados; checkboxes/dropdowns; texto livre para notas.

---

# 7. Derivando o escopo de IHC da disciplina

## 7.1 Escolha o caminho do projeto

### Resposta: Caminho B — TCC não possui interface prevista para o recorte de IHC

**Justificativa**: o TCC é um projeto de pesquisa em Explainable AI (algoritmo + validação); a interface clínica de uso das explicações não estava detalhada no escopo técnico original — esta disciplina projeta esse recorte.

**Exercício de Transferência de Uso:**

1. **Quem poderia contratar/adotar a solução?**
   - [F] Hospitais com neuroimagem.
   - [F] Centros de pesquisa em Alzheimer.
   - [H] Clínicas de neurologia especializadas; telemedicina em localidades rurais.

2. **Quem seria o usuário direto?**
   - [F] Radiologista, Médico clínico, Neurologista especialista.

3. **Quem administraria/configuraria?**
   - [F] Técnico de TI do hospital/fornecedor; [H] administrador clínico define protocolos.


4. **Quem interpretaria resultados?**
   - [F] Médico clínico → paciente; Neurologista → equipe.
   - [F] Auditor → hospital, para fins de compliance.


5. **Quem tomaria decisões?**
   - [F] Médico clínico (responsabilidade legal do diagnóstico); Neurologista valida casos críticos.
   - [H] Gestor decide sobre adotar/descontinuar a ferramenta (papel de negócio, listado em 2.3, não como persona de IHC).

6. **Quais dados/entradas seriam necessários?**
   - [F] Imagem MRI (T1, T2, FLAIR); dados clínicos (MMSE/MoCA, história clínica); dados do paciente (idade, escolaridade, comorbidades).
   - [H] Informação familiar (história de demência).

7. **Quais resultados deveriam ser compreendidos?**
   - [F] Diagnóstico sugerido; explicação (regiões/features críticas); confiança/incerteza do modelo; comparação com casos anteriores.
   - [H] Recomendação de ação (chamar especialista? follow-up?).

8. **Que erros/rupturas seriam possíveis?**
   - [F] Falso positivo; falso negativo; explicação incompreensível; falta de documentação.
   - [H] Bias sistemático do modelo por grupo demográfico.

## 7.2 Qual perfil será priorizado no projeto de IHC?

**Perfil escolhido:** Médico Clínico em contexto de atenção primária ou hospital geral, sem expertise em neuroimagem, sem acesso imediato a especialista.

**Por que esse perfil foi escolhido?**

1. Maior volume de usuários em relação a radiologistas especializados.
2. Ponto crítico de confiança: se o médico clínico não entender as explicações XAI, o sistema falha.
3. É justamente o perfil para o qual o Feature-Augmented XAI foi pensado (melhorar compreensão de não especialistas em imagem).
4. Reduz o tempo de diagnóstico ao não depender de especialista.
5. Corresponde à atividade mais crítica identificada (A03 — interpretar explicações XAI).

## 7.3 Qual objetivo desse usuário será priorizado?

**Objetivo escolhido:** tomar decisão diagnóstica de Alzheimer com confiança, rapidamente, sem esperar especialista, baseado em compreensão clara das explicações do sistema.

**Por que esse objetivo?**
- [F] Resolve problema real (tempo de diagnóstico).
- [F] Alinhado ao objetivo real do usuário (item 3.1).
- [H] Depende criticamente de IHC — se as explicações não forem compreendidas, o objetivo falha.
- [F] Mensurável por meio de testes/feedback.

## 7.4 Que interface será explorada na disciplina?

> Para fins da disciplina de IHC, será projetada uma interface que permita ao **médico clínico** utilizar as **explicações do modelo Feature-Augmented XAI** para **diagnosticar Alzheimer com confiança**, no contexto de **sala de consulta/escritório do hospital, com tempo limitado, sem acesso imediato a especialista**.

**O que a interface deve permitir:**
1. Visualizar MRI + explicações sobrepostas.
2. Entender quais regiões/features foram críticas para o diagnóstico.
3. Entender o porquê (raciocínio clínico traduzido das features do modelo).
4. Comparar com casos anteriores (quando disponível).
5. Registrar decisão com justificativa documentada.
6. Solicitar revisão por especialista, se necessário.

## 7.5 Qual é a relação dessa interface com o TCC?

- [x] É uma extensão conceitual criada para a disciplina.

**Declaração de Aprendizagem:** a interface desenvolvida nesta disciplina de IHC é um artefato de aprendizagem baseado no tema do TCC. Sua inclusão ou implementação efetiva no TCC somente ocorrerá se posteriormente decidido pela equipe de pesquisa e orientador, após validação clínica preliminar.

---

# 8. Levantando possibilidades de interação — sem desenhar ainda

A equipe pode registrar possibilidades para investigação. Cada uma corresponde a uma tarefa identificada em seções anteriores.

| Possibilidade | Faz sentido? | Objetivo/tarefa que justificaria | Evidência atual |
|---|---|---|---|
| **Dashboard/visão geral de casos** | SIM | Médico vê lista de pacientes pendentes de diagnóstico; prioriza casos mais críticos | [F] Consulta histórico; [H] workflow comum em PACS |
| **Configuração/parametrização do modelo** | NÃO | Médico clínico não deve configurar o modelo | [F] Fora do escopo — responsabilidade de pesquisador/TI, ambos fora da lista de personas priorizadas (2.2) |
| **Entrada/upload/seleção de dados (MRI)** | SIM | Médico ou técnico faz upload de MRI para análise | [F] Padrão em PACS; envolve o Técnico de Laboratório (2.2) |
| **Acompanhamento de processamento** | TALVEZ | Mostrar progresso se processamento levar mais que ~30s | [H] Depende da velocidade do algoritmo |
| **Relatório/resultados formatado** | SIM | Diagnóstico em linguagem clínica clara; scores numéricos | [F] Padrão clínico |
| **Histórico com busca/filtros** | SIM | Médico busca MRI anterior do mesmo paciente | [F] Crítico para continuidade |
| **Comparação de resultados** | SIM | Lado a lado: exame atual vs. anterior; progressão de atrofia | [H] Auxilia detecção de progresso |
| **Explicabilidade/detalhamento** | SIM (CRÍTICA) | Mostrar regiões/features importantes para o diagnóstico | [F] Atividade A03; diferencial central do TCC |
| **Administração/configurações globais** | TALVEZ | Definir protocolo de uso, limiares de confiança | [H] Papel de administração não modelado como persona nesta disciplina (ver 2.2); registrado apenas como possibilidade futura |
| **Usuários/perfis/permissões** | SIM | Controle de acesso por perfil; auditoria de quem fez o quê | [F] Requisito legal/compliance |
| **CRUD de entidade do domínio** | NÃO | Médico clínico não edita diagnósticos retrospectivamente | [F] Fora do escopo — trilha de auditoria é imutável |
| **Auditoria/logs** | SIM | Registro automático de quem abriu o caso, quando, qual diagnóstico | [F] Crítico para compliance regulatório |
| **Alertas/ocorrências** | TALVEZ | Notificar quando um caso de baixa confiança recebe nova interpretação | [H] Possível, mas requisito não explícito ainda |
| **Ajuda/documentação** | SIM | Tutorial interativo; glossário de termos técnicos | [H] Reduz curva de aprendizado, especialmente para o Médico Clínico |

---

# 9. Benefícios e ações iniciais

## 9.1 Qual benefício concreto o projeto de IHC pretende oferecer?

| Benefício esperado | Problema/necessidade | Usuário | Status/evidência |
|---|---|---|---|
| Reduzir tempo até uma decisão diagnóstica inicial | Fila de meses por especialista | Médico clínico | [F] |
| Explicar o "porquê" da sugestão, não só o resultado | "Caixa preta" clínica, falta de justificativa técnica | Médico clínico | [F] |
| Gerar documentação/justificativa automática da decisão | Falta de rastreabilidade para auditoria | Médico clínico / Hospital | [F] |
| Mostrar grau de confiança para apoiar decisão de escalonar | Casos ambíguos sem critério objetivo | Médico clínico | [H] |
| Reduzir divergência de interpretação entre profissionais | Baixa concordância inter-observador | Médico clínico / Neurologista | [F] |

## 9.2 Que ações o usuário deverá conseguir realizar?

| ID | O usuário precisa conseguir... | Para alcançar... | Prioridade inicial |
|---|---|---|---|
| F01 | Abrir um caso com MRI e dados clínicos | Iniciar a análise | alta |
| F02 | Ver a MRI com regiões destacadas pela explicação | Entender onde o modelo "olhou" | alta |
| F03 | Ver as features (imagem + clínicas) em linguagem clara | Entender o "porquê" da sugestão | alta |
| F04 | Ver o grau de confiança da predição | Calibrar quanto confiar no resultado | alta |
| F05 | Comparar com exames anteriores do mesmo paciente | Avaliar progressão | média |
| F06 | Registrar a decisão final com justificativa | Documentar de forma auditável | alta |
| F07 | Encaminhar o caso a um especialista | Lidar com casos ambíguos | média |
| F08 | Consultar glossário/ajuda contextual | Reduzir a barreira de interpretação | baixa |


## 9.3 Tecnologias/restrições já definidas no TCC

A tecnologia aparece **agora**, depois do entendimento do uso.

| Tecnologia/restrição | Por que existe | Possível impacto na interação |
|---|---|---|
| Modelo multimodal (MRI + dados tabulares) | Definição central do TCC | Interface precisa integrar imagem e dados clínicos |
| Abordagem Feature-Augmented XAI | Diferencial científico do TCC | Explicação precisa ir além de heatmap, incluindo biomarcadores |
| Saída probabilística (score, não binária) | Natureza do modelo de ML | Precisa comunicar incerteza sem gerar falsa certeza |
| LGPD/HIPAA, rede hospitalar privada | Sensibilidade dos dados | Sem exportação livre; exige logout/controle de sessão |
| Responsabilidade legal é do médico, não da IA | Regulação médica | Interface deve deixar isso explícito ("sugestão", não "diagnóstico") |

---

# 10. Hipóteses e dúvidas prioritárias

| ID | Hipótese/dúvida | Por que importa | Como poderá ser investigada |
|---|---|---|---|
| H01 | Explicação Feature-Augmented aumenta a confiança do médico vs. um score isolado | É a premissa central de valor do TCC | Entrega 7 |
| H02 | Explicação combinada (imagem + biomarcadores) reduz o tempo de decisão | Sustenta o benefício de rapidez (9.1) | Entrega 7 |
| H03 | Médico entende o score de confiança sem treinamento extenso | Risco de má interpretação já identificado | Entrega 6/7 |
| H04 | Gestores aprovariam a adoção se houver ganho comprovado | Impacta viabilidade real, fora do escopo direto | Não priorizado nesta disciplina |
| H05 | Pacientes/familiares não são usuários diretos nesta fase | Delimita escopo | Reavaliar em versões futuras |

Registre em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

---

# 11. Síntese da equipe

| Pergunta | Síntese atual |
|---|---|
| Qual é a contribuição central do TCC? | Modelo de IA explicável que combina MRI e dados clínicos tabulares para apoiar o diagnóstico de Alzheimer |
| O TCC já previa interface? | Sim — aplicação web para envio de dados e consulta de resultado |
| Quem é o usuário prioritário de IHC? | Rede médica |
| O que ele precisa alcançar? | Diagnosticar com confiança e rapidez, entendendo o porquê da sugestão |
| Qual problema/atividade será estudado? | Interpretar as explicações XAI para apoiar a decisão diagnóstica |
| Como isso acontece hoje? | Radiologista interpreta a MRI visualmente; médico combina com MMSE/histórico e julgamento pessoal, sem explicação estruturada |
| Qual é o contexto de uso? | Hospital/consultório, tempo limitado, requisitos de privacidade e rastreabilidade |
| Que interface/recorte será explorado? | Visualizar MRI + explicação + confiança, comparar histórico, registrar decisão, encaminhar especialista |
| Como a interface se relaciona ao TCC? | Extensão conceitual do app já previsto, com foco no médico clínico |
| Quais pontos ainda são hipóteses? | H01, H02, H03, H04 |

### Delimitação

**Dentro do escopo de IHC:** interação do médico com MRI, explicação, score de confiança, histórico e registro de decisão.
**Fora do escopo de IHC:** configuração do modelo, infraestrutura, interface para pacientes, integração completa com EHR, auditoria em nível de sistema.
**Dentro do escopo formal do TCC:** modelo multimodal M-XAI e app web básica.
**Interface da disciplina será implementada no TCC?** não definido — depende de validação clínica preliminar e decisão da equipe/orientador.

---

# 12. Como esta entrega alimenta as próximas

- **Entrega 2:** verifica mercado, concorrentes e interfaces profissionais representativas.
- **Entrega 3:** detalha perfis e contexto.
- **Entrega 4:** aprofunda situações problemáticas.
- **Entrega 5:** modela tarefas centrais.
- **Entrega 6:** experimenta alternativas em baixa fidelidade.
- **Entrega 7:** investiga hipóteses com dados.
- **Entrega 8:** define restrições e metas de usabilidade.
- **Entregas 9–11:** transformam o recorte em modelo de interação e protótipo.
- **Entregas 12–14:** avaliam a interface construída na disciplina.

A Entrega 1 é uma **fotografia inicial do conhecimento**. Ela pode e deve ser revisada quando surgirem evidências.

---

# 13. Relação com INOVA e comunicação do projeto

Prepare uma explicação de até três frases:

1. **Problema/atividade humana:** {{...}}
2. **Contribuição técnica do TCC:** {{...}}
3. **Como uma pessoa poderia utilizar essa contribuição:** {{...}}

Essa síntese ajuda a apresentar o projeto para público não especializado sem reduzir seu mérito técnico.

---

# Checklist de qualidade

- [ ] Está clara a diferença entre tema do TCC, escopo formal do TCC e escopo de IHC.
- [ ] A equipe declarou se o TCC já previa interface.
- [ ] Se não previa, foi derivado um usuário plausível e um objetivo de uso.
- [ ] A interface de IHC não foi apresentada como obrigação automática do TCC.
- [ ] A contribuição do TCC foi descrita sem começar por tecnologias de implementação.
- [ ] Usuários diretos e stakeholders foram diferenciados.
- [ ] Foram considerados profissionais que configuram, administram, interpretam ou decidem, quando pertinente.
- [ ] Objetivo do usuário não foi confundido com objetivo do projeto.
- [ ] Processo/problema atual foi descrito antes da solução.
- [ ] Existe situação concreta de uso/problema.
- [ ] Contexto físico, social/organizacional, dispositivos e consequências de erro foram considerados.
- [ ] Mercado/alternativas existentes foram levantados inicialmente.
- [ ] Possibilidades como dashboard, relatório, histórico, filtros e CRUD foram tratadas como hipóteses de solução, não como requisitos automáticos.
- [ ] Cada possibilidade de interface tem um objetivo/tarefa que poderia justificá-la.
- [ ] Afirmações relevantes estão marcadas `[F]`, `[H]` ou `[?]`.
- [ ] Hipóteses prioritárias receberam IDs e foram para a rastreabilidade.
- [ ] O recorte de IHC é viável para modelar, prototipar e avaliar no semestre.
- [ ] A equipe consegue explicar problema humano → contribuição computacional → forma de uso.
