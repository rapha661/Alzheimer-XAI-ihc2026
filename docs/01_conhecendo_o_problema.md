# Entrega 1 — Conhecendo o projeto, o usuário e o problema

**Data:** 27/08/2026
**Status:** 🟩 Concluída
**Responsabilidade:** Desenvolver uma interface para intermediar o uso do modelo de inteligência artificial explicável que visa auxiliar no diagnóstico da doença de alzheimer por profissionais da área da saúde.

## Objetivo da atividade

Reinterpretar o tema do TCC sob a perspectiva de Interação Humano-Computador e construir um **entendimento comum entre os integrantes da equipe**.

A disciplina utiliza preferencialmente o tema do TCC para os exercícios de IHC. Isso vale tanto para TCCs que já preveem uma interface quanto para trabalhos cujo resultado principal é algoritmo, modelo, API, biblioteca, análise de dados, infraestrutura, estudo experimental ou outro artefato técnico.

> **Importante:** a interface projetada na disciplina é um artefato de aprendizagem de IHC. Ela **não se torna automaticamente uma obrigação do TCC**. Sua incorporação ao trabalho de conclusão depende de decisão da equipe e do orientador.

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

> **Exemplo:** `[H] H01 — DBAs considerariam útil comparar automaticamente o plano atual de execução com uma recomendação produzida pelo algoritmo.`

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

Nosso TCC, melhora a confiabilidade por parte dos médicos em realizar uma analise de exames de alzheimer utilizando inteligência artificial por conta do XAI e a possibilidade de utilizar tanto imagens de MRI e dados tabulares de exames sanguíneos.


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

[F] Profissionais de saúde que não necessáriamente são especilialistas em Alzheimer

## 2.2 Quem poderia **usar, configurar, administrar, operar, interpretar ou tomar decisões** a partir da contribuição técnica?

| Perfil | Relação com a Contribuição | O que Faria | Classificação | Evidência/Status |
|---|---|---|---|---|
| **Médico Clínico / Generalista** | Usuário primário de diagnóstico | Interpretar explicações XAI; tomar decisões clínicas; validar contra conhecimento clínico | [F] | Literatura revisa (papers 1.2, 1.3); Clínicos são usuários-chave de CAD systems |
| **Neurologista / Especialista** | Validador técnico-clínico | Validar predições; refinar thresholds; supervisionar casos complexos; feedback para melhorias | [F] | Documentado em literatura médica (papers sobre clinical validation) |
| **Radiologista / Neuroradiologista** | Operador técnico de imagem | Interpretar resultados; validar qualidade de MRI; integrar com PACS; avaliar localizações | [F] | Padrão em radiologia - avaliação de CAD systems por radiologistas |
| **Pesquisador / Cientista de Dados** | Desenvolvedor do modelo XAI | Treinar/refinar modelo; validar metodologia XAI; investigar bias/fairness; documentar decisões técnicas | [F] | Direto - equipe de desenvolvimento do TCC |
| **Administrador de TI / DevOps** | Operador de infraestrutura | Configurar/manter infraestrutura; gerenciar atualizações; garantir segurança HIPAA; monitorar performance | [F] | Requisito técnico necessário para deployment hospitalar |
| **Gestor Hospitalar / Diretor Clínico** | Tomador de decisão estratégica | Aprovar implementação; alocar recursos; decidir sobre deployment; avaliar ROI; integração em workflows | [H] | Plausível - gestores decidem sobre adoção de tecnologia, mas depende de démonstração de valor |
| **Patient Advocate / Paciente Informado** | Stakeholder informado | Compreender resultados; questionar recomendações; consentimento informado; feedback sobre usabilidade | [H] | Emergente - patient engagement é tendência, mas não é padrão em sistemas atuais |
| **Auditor Regulatório / Compliance Officer** | Avaliador de conformidade | Verificar GDPR/HIPAA/FDA; auditar transparência; garantir rastreabilidade; validar explicabilidade | [F] | Obrigatório - regulação médica exige conformidade |
| **Usuário Final (Paciente)** | Beneficiário do diagnóstico | Receber diagnóstico em tempo hábil; entender explicações acessíveis; confiança no sistema | [?] | Lacuna - como pacientes interagem com XAI explicações não é bem documentado; estudos de usabilidade necessários |
| **Técnico de Laboratório / Preparação de Dados** | Operador entrada de dados | Preparar/validar dados de MRI; garantir qualidade de imagem; alimentar sistema corretamente | [F] | Necessário - toda pipeline médica requer controle de qualidade |
| **Enfermeira / Coordenador Clínico** | Intermediário clínico | Coordenar fluxo de pacientes; explicar resultados básicos; agendamento de follow-up | [H] | Plausível - necessário em workflows, mas depende de treinamento específico |
| **Bioético / Comitê de Ética** | Avaliador de impacto ético | Avaliar fairness; risco de bias; questões de consentimento; impacto social | [H] | Emergente - há crescente preocupação com ética em IA, mas ainda não é mandatório para todos |
| **Paciente com Deficiência Cognitiva / Familiar Próximo** | Beneficiário com necessidade especial | Receber diagnóstico; compreender em linguagem acessível; | [?] | Lacuna crítica - como sistema funciona com comprometimento cognitivo não é investigado |
| **Pesquisador de XAI (não-médico)** | Investigador de metodologia | Validar métodos de explicação; comparar técnicas XAI; pesquisa em interpretabilidade | [H] | Plausível - comunidade XAI tem interesse em validação médica, mas integração é rara |

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

## 2.4 Que características desses perfis podem influenciar a interação?

[H]
### Conhecimento do Domínio
- **Alto** (Neurologista, Radiologista): Compreendem conceitos avançados de neuroimaging, biomarcadores, fisiopatologia. Esperam explicações técnicas profundas.
- **Médio** (Médico Clínico): Conhecem AD clinicamente mas podem ter lacunas em interpretação de imagens. Precisam de explicações que conectem imagem a clínica.
- **Baixo** (Pacientes, Familiares): Requerem explicações simplificadas com contexto não-técnico.
### Experiência Tecnológica
- **Alta** (Pesquisador, DevOps, Radiologista): Confortável com ferramentas complexas, APIs, dashboards avançados, visualizações técnicas.
- **Média** (Médico Clínico, Gestor): Familiarizado com software clínico padrão. Necessita interface intuitiva.
- **Baixa** (Paciente, Familiar): Requer interface simplificada, bem documentada, com suporte.
### Frequência de Uso
- **Alta/Diária** (Médico Clínico, Radiologista): Workflows rápidos; atalhos; integração com sistemas existentes.
- **Ocasional** (Neurologista especialista): Precisa de ferramentas mais detalhadas; pode revisitar casos complexos.
- **Rara** (Gestor Hospitalar): Precisa de relatórios de alto nível; métricas agregadas.
### Necessidades de Acessibilidade
- **Críticas** (Médicos com deficiência visual): Alt text em imagens médicas; modo contraste alto; navegação via teclado.
- **Importantes** (Idade avançada de usuários clínicos): Fonte grande; contraste adequado; navegação simples.
- **Padrão**: Interface WCAG 2.1 AA compliant.
### Responsabilidade Profissional e Liabilidade
- **Muito Alta** (Médico, Neurologista): Precisam de rastreabilidade completa de decisões; auditoria; documentação para defesa legal.
- **Alta** (Radiologista, Pesquisador): Responsáveis por qualidade e acurácia. Necessitam validação de resultados.
- **Moderada** (DevOps, Admin TI): Responsáveis por disponibilidade e conformidade.
- **Baixa** (Paciente): Confiança mas sem responsabilidade legal.
### Familiaridade com Métricas e Interpretação
- **Especialista** (Pesquisador, Radiologista): Confortável com sensitivity, specificity, AUC, F1-score, confusion matrix, calibração.
- **Intermediário** (Médico Clínico): Entende acurácia, sensibilidade básica, precisa de tradução de métricas técnicas.
- **Básico** (Paciente): Requer frases como "90% de precisão" ou "risco baixo/médio/alto".
### Linguagem Técnica Preferida
- **Alta/Técnica** (Pesquisador, Radiologista, DevOps): "Grad-CAM", "feature importance SHAP", "ROC-AUC", "overfitting", "regularization".
- **Média** (Médico Clínico): "Regiões ativadas", "confiança do modelo", "explicação visual", "áreas anormais".
- **Simplificada** (Paciente, Familiar): "Áreas do cérebro anormais", "risco de doença", "próximos passos".
### Urgência e Pressão Temporal
- **Crítica** (Médico em pronto-socorro): Necessita diagnóstico em minutos; interface rápida; resultados claros e decisivos.
- **Alta** (Radiologista em hospital ocupado): Múltiplos casos simultâneos; eficiência importante.
- **Moderada** (Pesquisador): Revisão detalhada; pode levar mais tempo.
- **Flexível** (Gestor administrativo): Sem pressão temporal; foco em relatórios aggregados.
### Contexto de Tomada de Decisão
- **Clínico** (Médico, Neurologista): Decisões impactam cuidado ao paciente; necessita contexto completo e alternativas.
- **Administrativo** (Gestor): Decisões sobre recursos e política; necessita agregação de dados.
- **Pesquisa** (Pesquisador): Decisões sobre metodologia e publicação; necessita reprodutibilidade.
- **Compliance** (Auditor): Decisões sobre conformidade regulatória; necessita rastreabilidade completa.
### Risco de Mal-Interpretação
- **Alto** (Médico não-especialista, Paciente): Sem contexto neuroimaging, pode mal-interpretar explicações visuais.
- **Médio** (Médico Clínico generalista): Conhece AD mas pode não entender nuances técnicas de XAI.
- **Baixo** (Radiologista, Especialista, Pesquisador): Expertise suficiente para interpretação correta.
### Necessidades de Suporte e Treinamento
- **Extenso** (Médico não-familiar com ferramenta): Workshop presencial; documentação detalhada; helpdesk.
- **Moderado** (Médico familiarizado com IA): Tutorial online; FAQs; webinars.
- **Mínimo** (Pesquisador experiente): Auto-didático; acesso a documentação técnica.
### Contexto de Uso
- **Consultório/Clínica** (Médico Clínico): Precisa ser funcional em ambiente com alta carga de trabalho; integração com prontuário eletrônico.
- **Laboratório Diagnóstico** (Radiologista): Múltiplos casos; throughput alto; PACS integration.
- **Hospital Pesquisa** (Pesquisador): Ambiente acadêmico; acesso a datasets completos; flexibilidade para customização.
- **Remoto** (Paciente, Familiar): Interface web responsiva; segurança de dados.

---

# 3. Entendendo objetivos e atividades

## 3.1 O que o usuário está tentando conseguir no mundo real?

[F] Diagnosticar Alzheimer com confiança em pacientes suspeitos, especialmente em ambientes sem especialista disponível

## 3.2 Quais são as atividades mais importantes?

| ID | Atividade/objetivo | Quem realiza | Frequência/criticidade inicial | Status/evidência |
|---|---|---|---|---|
| A01 | {{...}} | {{...}} | {{...}} | {{...}} |
| A02 | {{...}} | {{...}} | {{...}} | {{...}} |
| A03 | {{...}} | {{...}} | {{...}} | {{...}} |

## 3.3 Qual atividade parece mais frequente? Por quê?

[H]
**A03 - Revisar e interpretar explicações XAI** é a atividade mais frequente
| Razão | Explicação |
|---|---|
| **Volume de casos** | Em hospital com 50-100 suspeitas de Alzheimer/mês, essa atividade ocorre diariamente, múltiplas vezes |
| **Dependência crítica** | Cada novo paciente requer ESSA etapa específica; não pode ser pulada ou delegada ao sistema |
| **Tempo investido** | Médico passa mais tempo nessa atividade do que em qualquer outra (geralmente 5-10 min por caso) |
| **Gargalo de interface** | A velocidade e clareza dessa atividade determina throughput diagnóstico total |
| **Repetitividade** | Diferente de A04 (validação) que pode ser rápida ou pulada em casos óbvios, A03 precisa de atenção completa a cada caso |
 

## 3.4 Qual parece mais crítica? Que consequência existe se for mal executada?

[H]
### Análise: A03 é SIMULTANEAMENTE a mais frequente E a mais crítica
 
#### **Por quê A03 é a MAIS crítica:**
 
1. **É a ponte entre modelo e decisão clínica**
- Se o médico não entende as explicações, tudo falha depois dela
- Não importa se modelo está certo se explicações são incompreensíveis

---

# 4. Entendendo o problema ou processo atual

## 4.1 Como essas atividades são realizadas hoje, antes da interface imaginada na disciplina?
 
**[F] Processo atual de diagnóstico de Alzheimer (sem sistema XAI):**
 
- **Aquisição de MRI**: Técnico de radiologia adquire imagens em scanner MRI; salva em PACS (Picture Archiving and Communication System)
- **Interpretação visual manual**: Radiologista examina imagens no PACS; busca sinais visuais (atrofia hipocampal, perda de matéria cinzenta, ventrículos dilatados); escreve relatório em texto livre ou semi-estruturado
- **Consulta clínica**: Médico clínico ou neurologista lê relatório de radiologia; realiza testes cognitivos (MMSE, MoCA); consulta histórico e familiares; toma decisão baseada em experiência pessoal
- **Documentação**: Diagnóstico registrado no prontuário eletrônico com impressão clínica (muitas vezes sem justificativa técnica detalhada)

## 4.2 O que é difícil, demorado, confuso, repetitivo, arriscado ou pouco transparente?
 
| Problema | Tipo | Descrição | Impacto | Status |
|---|---|---|---|---|
| **Fila de espera longa** | Demorado | Pacientes esperam 6-12 meses por especialista/MRI especializada | Diagnóstico atrasado; progressão continua sem monitoramento | [F] Documentado em literatura |
| **Falta de especialistas** | Sistêmico | Poucos neuroradiologistas; concentrados em centros urbanos; acesso desigual | Pacientes rurais sem acesso; diagnósticos de qualidade variável por localização | [F] Disparidade geográfica conhecida |
| **Interpretação subjetiva** | Confuso/Arriscado | Diferentes médicos interpretam mesma MRI diferentemente (variação inter-observador alta) | Diagnósticos inconsistentes; pacientes recebem diagnósticos conflitantes em hospitais diferentes | [F] Cohen's kappa 0.40-0.70 em literatura |
| **"Caixa preta" clínica** | Pouco Transparente | Médico não consegue explicar sistematicamente POR QUÊ diagnosticou AD; apenas impressão clínica | Paciente desconfia; difícil documentar para auditoria regulatória; risco legal alto | [F] Relatados em feedback clínico |
| **Falta de rastreabilidade** | Arriscado | Decisão está no "julgamento" do médico; sem log sistemático do raciocínio; sem escores objetivos documentados | Malpractice cases: impossível provar que decisão foi justificada; auditor não consegue validar | [F] Risco legal documentado |
| **Inconsistência de qualidade** | Repetitivo/Arriscado | Alguns médicos mais cuidadosos que outros; nenhum padrão ouro objetivo; protocolos variam | Mesmo paciente pode receber 2 diagnósticos diferentes em 2 hospitais; qualidade impredizível | [F] Conhecido em prática clínica |
| **Falsos negativos passam despercebidos** | Arriscado | Pacientes com Alzheimer inicial (especialmente MCI) não diagnosticados | Anos sem acompanhamento → progressão irreversível → diagnóstico tardio com demência avançada | [H] Relatado mas prevalência não quantificada |
| **Falsos positivos causam ansiedade** | Demorado | Paciente saudável diagnosticado como AD; leva meses de testes adicionais para descartar | Ansiedade crônica; possível medicação desnecessária; qualidade de vida afetada; custo hospitalar aumentado | [H] Casos relatados mas prevalência não clara |
| **Tempo clínico desperdiçado** | Demorado/Repetitivo | Neurologista gastando tempo em casos óbvios em vez de investigar casos complexos/ambíguos | Ineficiência operacional; casos complexos ficam sem atenção adequada; burnout clínico | [H] Relatado por clínicos mas sem dados quantitativos |
| **Documentação inadequada** | Pouco Transparente | Apenas impressão clínica; sem justificativa técnica das regiões cerebrais afetadas; sem scores objetivos | Auditor não consegue validar decisão; risco regulatório; impossível rastrear raciocínio clínico | [F] Requisito regulatório não atendido |
| **Bias cognitivo não detectado** | Arriscado | Médico "vê" o que espera ver; confirma diagnóstico prematuro (ex: "é velho, deve ser AD") | Erro sistemático; falsos positivos especialmente em idosos saudáveis; disparidade de diagnóstico por idade/sexo | [H] Conhecido em psicologia clínica; poucos estudos em AD |

## 4.3 Que informações o profissional precisa interpretar para tomar decisão?
 
### Informações que médico INTERPRETA HOJE (manualmente)
 
**De MRI (Interpretação Visual):**
- **Atrofia hipocampal**: Redução de volume visual (semiquantitativo: leve/moderado/severo, ou volume em mm³ em alguns centros)
  - [F] Marcador visual principal em AD
  - [H] Variação de como quantificar entre observadores
- **Espessura cortical**: Redução em córtex (avaliada visualmente; raramente medida de forma objetiva)
  - Regiões críticas: lobo temporal medial, parietal
  - [F] Associada a AD
  - [H] Medição manual é subjetiva
- **Volume de matéria cinzenta**: Perda generalizada (avaliada visualmente como "preservado" vs "reduzido")
  - [F] Indicador de atrofia cerebral
  - [H] Sem quantificação objetiva de rotina
- **Ventrículos cerebrais**: Dilatação (avaliada visualmente)
  - [F] Indica atrofia cerebral
  - [H] Correlação com AD não é específica (outras patologias também dilatam ventrículos)
- **Substância branca**: Lesões (sequences FLAIR)
  - Avaliação qualitativa: "normal", "minimal", "moderate", "extensive"
  - [F] Pode indicar comorbidades (doença cerebrovascular)
  - [H] Significado clínico varia
**De Dados Clínicos:**
- **Teste cognitivo** (MMSE, MoCA): Score numérico (objetivo)
  - Interpretação: AD provável se < 24 MMSE + achados MRI
  - [F] Métrica padronizada
  - [H] Score borderline (24-28) deixa incerteza
- **História clínica**: Duração dos sintomas, progressão (lenta vs rápida), comorbidades (depressão, hipotireoidismo, deficiência B12)
  - [F] Informação clínica essencial
  - [H] Raramente documentada de forma estruturada
- **Informação familiar**: História familiar de demência (aumenta risco), observações de declínio funcional
  - [F] Fator de risco conhecido
  - [H] Subjetivo; depende de quanto família consegue observar

## 4.4 O que acontece quando a atividade falha ou quando o resultado é interpretado incorretamente?
 
### Falso Negativo (Não diagnosticado)
 
**Situação**: Paciente com MCI/Alzheimer inicial não é diagnosticado
 
**Como acontece**:
- [F] Radiologista: "Atrofia muito leve, pode ser normal para idade"
- [F] Médico clínico: "Score MMSE 28 (borderline) → talvez seja depressão, não AD"
- [F] Falta especialista disponível → ninguém questiona o diagnóstico negativo

## 4.5 Conte uma situação concreta
 
### Narrativa: O Caso de Maria Silva
 
**Pessoa**: Maria Silva, 72 anos, aposentada, viúva há 3 anos
 
**Objetivo real**: Obter diagnóstico definitivo e confiável sobre seu "esquecimento" para planejar seu futuro e tranquilizar sua família
 
**Atividade**: Realizar MRI neurológica e consulta com especialista para diagnóstico de Alzheimer vs. envelhecimento normal
 
**Contexto**:
- Há 18 meses Maria começou a se esquecer de compromissos (consultas médicas, datas de medicações)
- Filha insistiu que fosse ao médico
- Médico clínico local fez teste MMSE (score: 27 = borderline)
- Encaminhou para MRI com suspeita de Alzheimer
- Fila de espera: 4 meses (até conseguir MRI)
**Dificuldade** (o ponto crítico):
- MRI finalmente realizada
- Radiologista visualiza leve atrofia hipocampal
- Relatório radiológico: "Atrofia leve, compatível com envelhecimento normal — achados não específicos de demência"
- Maria encaminhada para neurologista especialista
- SEGUNDA fila de espera: 3 meses
- **Total: 7 meses de ansiedade** (Maria ficar 7 meses pensando que tinha Alzheimer)
- Neurologista examina Maria
- **DISCORDAM do radiologista**: "Atrofia moderada; Alzheimer provável"
- Prescreve donepezila (medicação para Alzheimer)
- **Maria fica confusa**: Radiologista disse "normal", neurologista disse "doença"
**Consequência**:
- Maria passa 7 meses em ansiedade extrema → depressão começa
- Medicação (donepezila) causa efeitos colaterais (náusea, falta de apetite)
- Maria rejeita medicação após 2 semanas
- Filha e netos "veem" esquecimento porque Maria agora está deprimida (ciclo)
- **1 ano depois**: MRI de follow-up mostra atrofia SEM progressão (mesmo tamanho)
- Neuropsicólogo especializado descobre: Maria tem depressão maior, não Alzheimer ("pseudodementia")
- Diagnóstico revisado; medicação de Alzheimer retirada
- **Dano total**: Maria passou 2 anos com diagnóstico de Alzheimer; perdeu confiança em medicina; custo: múltiplas consultas extras, testes desnecessários, ansiedade crônica, tentativa de suicídio leve (pior caso mas possível)
**Raiz dos problemas**:
- [F] Dois especialistas discordaram sem resolução → falta de padrão ouro objetivo
- [F] Nenhuma explicação clara do PORQUÊ do diagnóstico (quais critérios foram usados?)
- [F] Nenhuma quantificação de confiança (70%? 50%? 90%?)
- [F] Processo extremamente demorado (7 meses) → ansiedade contribui ao fenótipo de "esquecimento" (depressão causa perda de memória)
- [H] Médico não conseguiu explicar a discordância a Maria → erosão de confiança

## 4.6 Que evidência existe hoje?
 
| Evidência/Fonte | O que sustenta | Limitação |
|---|---|---|
| **Literatura Científica (inter-observer variability)** | Cohen's kappa 0.40-0.70 para concordância entre radiologistas em AD (moderado, não excelente) | Estudos antigos; baseados em radiologistas experts, não clínicos generalistas; dados selecionados |
| **Estudos de Concordância Clínica** | Concordância entre radiologistas em AD: 60-80% (não é 100%) | Estudos de pesquisa com dados de repositórios (ADNI, OASIS); viés de seleção; não reflete variação real em prática clínica |
| **Dados de Tempo de Diagnóstico** | Média de 6-12 meses entre MRI e diagnóstico final em alguns centros; demora correlacionada com deterioração cognitiva | [F] Documentado; [H] Causalidade (demora causa piora?) não totalmente estabelecida |
| **Diretrizes Diagnósticas (DSM-5 + NIA/AA 2018)** | Critérios oficiais requerem "avaliação clínica MAIS neuroimagem" | SEM especificar COMO combinar objetivamente; deixa espaço para interpretação subjetiva |
| **Guidelines de Radiologia (ACR - American College of Radiology)** | Descreve achados visuais esperados em AD | SEM scores objetivos; REQUER interpretação humana; exemplos visuais deixam margem para variação |
| **Pesquisa em IA/Deep Learning para AD** | Papers mostram: modelos de deep learning alcançam 90%+ acurácia em detecção de AD em datasets de pesquisa | Modelos NÃO mostram: aceitação clínica real; usabilidade em prática clínica; confiança de clínicos; validação prospectiva |
| **Feedback Clínico Qualitativo** | Clínicos relatam: "Falta informação objetiva; confio principalmente em experiência pessoal; difícil explicar decisão" | Anedótico; não sistemático; poucos estudos qualitativos formais |
| **Malpractice Cases / Litigation** | Alguns casos documentados de pacientes processando hospitais por diagnóstico atrasado ou errado de AD | Raros casos públicos; pouco dados acessíveis; mas indicam risco real |
| **Disparidade de Acesso Geográfico** | Pacientes rurais/periféricos: 12+ meses de espera por MRI; pacientes urbanos: 1-3 meses | [F] Desigualdade clara; impacto em outcomes documentado |
| **Diretrizes de Documentação Médica** | Prontuários eletrônicos requerem "justificativa clínica"; mas não há padrão de como documentar raciocínio diagnóstico | [H] Requisito existe mas não é atendido consistentemente |

---

# 5. Entendendo o contexto de uso


## 5.1 Onde e em quais situações a interação poderia ocorrer?
 
**[F] Locais físicos previstos:**
- Sala de consulta neurológica (clínico/neurologista consulta com paciente)
- Sala de leitura de imagens de radiologia (radiologista interpreta MRI)
- Escritório administrativo do hospital (médico clínico registra diagnóstico)
- Consultório de atendimento em atenção primária (clínico generalista suspeita de AD)
- Home office/telemedicina (clínico revisa casos remotamente)
**[F] Situações de uso:**
- Interpretação de novo caso suspeito de AD (rotineira)
- Revisão de caso discordante entre dois médicos (investigação)
- Acompanhamento de evolução de paciente conhecido (longitudinal)
- Treinamento de novo residente/médico (educacional)
- Auditoria de casos passados (compliance)

## 5.2 Em quais dispositivos/equipamentos?

**[F] Hardware principal:**
- Computador desktop/workstation em sala de radiologia (típico: PACS conectado a tela médica de alta resolução 21"-27")
- Computador desktop em consultório clínico (tela padrão, prontuário eletrônico)
- Monitor duplo comum em salas de radiologia (uma tela para PACS, outra para interface de decisão)

## 5.3 Existem condições físicas relevantes?
 
**[F] Iluminação:**
- Salas de radiologia: iluminação atenuada (low ambient light) para melhor leitura de imagens
- Interface deve ser legível em luz reduzida; alto contraste importante
- Consultórios variados (alguns bem iluminados, outros com luz artificial)
**[F] Ruído:**
- Ambiente hospitalar: possível interrupção (telefones, alarmes, colegas)
- Interface não deve depender de sons para alertas críticos
**[F] Mobilidade:**
- Radiologista: senta durante 2-4 horas de uso contínuo (RSI/fadiga importante)
- Médico clínico: frequentemente em pé em rondas; uso ocasional; pode consultar rapidamente
- Design deve considerar sessões longas vs consultas rápidas
**[F] Conexão:**
- Essencial: conectividade de rede estável (imagens grandes, decisão clínica crítica)
- Falha de conexão = interrupção de diagnóstico (risco clínico)
**[F] Privacidade:**
- Dados de paciente são sensíveis (LGPD, HIPAA)
- Interface deve rodar em rede privada do hospital; sem acesso externo
- Tela de diagnóstico pode ser visível a terceiros em sala compartilhada (risco)
**[H] Uso compartilhado:**
- Mesma workstation usada por múltiplos médicos (manhã: radiologista A, tarde: radiologista B)
- Requisito: logout automático, sem dados de paciente anterior visível
**[F] Interrupções:**
- Médico pode ser chamado durante interpretação (emergência, telefone)
- Interface deve permitir pausa e retorno ao caso (save state)
**[F] Pressão de tempo:**
- Radiologista: fila de casos aguardando (pressão para conclusão rápida)
- Médico clínico: agenda limitada de consultas (tempo por paciente restrito)
- **Implicação**: interface deve ser rápida; explicações devem ser consumidas rapidamente

## 5.4 Existem fatores sociais ou organizacionais?
 
**[F] Papéis e hierarquia:**
- Radiologista: responsável pela interpretação de imagem; senior em prioridade
- Neurologista: supervisor clínico; valida diagnóstico; tem responsabilidade legal final
- Médico clínico: interpreta resultado para paciente; documenta
- Técnico de radiologia: adquire imagens; não interpreta
**[F] Aprovações e responsabilidade:**
- Diagnóstico final é responsabilidade legal do MÉDICO (não da IA)
- IA é "segundo parecer" ou "apoio"; não substitui julgamento clínico
- Implicação: interface deve deixar claro que médico é responsável final; IA é sugestão
**[F] Auditoria e compliance:**
- Hospital tem obrigação regulatória de rastrear decisões diagnósticas
- Cada diagnóstico deve ser documentado com justificativa
- **Implicação**: interface deve gerar log automático de decisão; justificativa deve ser explícita
**[F] Equipes e colaboração:**
- Radiologista pode precisar consultar neurologista em casos difíceis
- Interface deveria permitir "flag case" para review por especialista
- Possível: comentários entre profissionais
**[F] Turnos e continuidade:**
- Hospital funciona 24h; diferentes médicos cobrem plantões
- Caso iniciado por médico A pode ser finalizado por médico B
- **Requisito**: interface deve permitir handoff claro entre profissionais
**[H] Treinamento:**
- Novos residentes precisam aprender a usar ferramenta
- Expertise variável entre clínicos (alguns muito experientes, outros novatos)
- Interface deve ser acessível a níveis diferentes de expertise

## 5.5 Existe necessidade de histórico, rastreabilidade ou auditoria?
 
**[F] SIM:**
 
- **Histórico de casos anteriores**: Médico precisa comparar novo caso com casos passados de mesmo paciente ou casos similares
  - Exemplo: "MRI de Maria em 2023 vs MRI de Maria em 2024; progrediu atrofia?"
  - Requisito: sistema deve guardar estudos anteriores com metadata
- **Rastreabilidade de decisão**: Cada diagnóstico deve ter "trilha de auditoria"
  - O quê foi decidido? Quando? Por quem? Com base em quais evidências?
  - Requisito: log automático de todas as ações; não confiar em memória de médico
- **Auditoria regulatória**: Hospital é auditado periodicamente por órgãos reguladores
  - Auditor quer ver: diagnóstico A foi justificado? Quais achados MRI? Qual score MMSE?
  - Requisito: cada decisão documentada de forma que auditor possa rastrear
- **Accountability legal**: Se paciente processa hospital por diagnóstico errado
  - Advogado quer provar: "Diagnóstico de Alzheimer foi irresponsável; faltaram evidências"
  - Requisito: documentação robusta que mostre raciocínio clínico na época
**[H] Integração com EHR:**
- Histórico deve estar integrado ao prontuário eletrônico (não em sistema separado)
- Requisito: XAI interface deve se comunicar com EHR para contexto clínico completo

## 5.6 Um erro pode produzir consequência relevante? Qual?
 
**[F] SIM:**
 
| Tipo de Erro | Contexto | Consequência | Severidade |
|---|---|---|---|
| **Falso Negativo (missed diagnosis)** | Paciente com Alzheimer inicial não diagnosticado | 2-5 anos sem acompanhamento → progressão irreversível → demência avançada → qualidade vida destruída |  CRÍTICA |
| **Falso Positivo (overdiagnosis)** | Paciente saudável diagnosticado com Alzheimer | Anos de ansiedade → medicação desnecessária → ciclo depressivo → risco psicológico |  CRÍTICA |
| **Documentação insuficiente** | Diagnóstico registrado sem justificativa técnica | Auditoria retira aprovação de sistema → hospital não pode usar ferramenta → impacto operacional |  ALTA |
| **Explicação incompreensível** | Médico não entende raciocínio da IA | Confiança falsa → médico usa IA sem validar → erros sistemáticos não detectados |  CRÍTICA |
| **Inconsistência entre médicos** | Um médico usa ferramenta, outro não; diagnósticos conflitantes | Paciente confuso → litigação → reputação hospitalar afetada |  CRÍTICA |

---

# 6. Entendendo mercado e alternativas existentes

> Nesta entrega faça apenas um **levantamento inicial**. A análise aprofundada ocorre na Entrega 2.

## 6.1 Como pessoas resolvem problemas semelhantes hoje?
 
| Alternativa atual | Quem usa | Para quê | Status/evidência |
|---|---|---|---|
| **Consulta presencial com especialista (neuroimagem)** | Pacientes e clínicos referenciando | Obter diagnóstico de confiança; segunda opinião | [F] Padrão ouro atualmente; mas fila longa (6-12 meses) |
| **Segunda opinião de radiologista experiente** | Médico clínico em caso de dúvida | Validar interpretação questionável | [F] Prática comum; custa tempo e recursos |
| **Teleradiologia / consulta remota** | Hospitais pequenos; clínicos remotos | Acessar expertise de centro urbano | [F] Existe em alguns hospitais; melhora acesso geográfico |
| **IA "caixa preta" (CAD simples)** | Alguns hospitais com sistemas antigos | Apoio computado básico (ex: detecção de regiões) | [F] Utilizado; mas pouca transparência |
| **Discussão multidisciplinar em conferência** | Hospitais universitários; casos complexos | Consenso clínico em casos ambíguos | [F] Gold standard em ensino; cara (tempo médico); não escalável |
| **Protocolo estruturado em papel/planilha** | Alguns hospitais | Padronizar decisão diagnóstica | [H] Raramente usado; não automatizado |
| **Plataformas comerciais de AI para imagem médica** | Alguns hospitais; centros privados | Detecção automática; CAD | [F] Existem (ex: Zebra Medical Vision, IBM Watson for Oncology antigo); para AD ainda limitado |
| **Consultoria externa especializada** | Pacientes particulares; segundas opiniões | Validar diagnóstico de AD | [F] Acessível apenas a ricos; caro |

## 6.2 Existem produtos que atuam na mesma área, mesmo sem serem equivalentes ao TCC?
 
**[F] Plataformas comerciais de AI em neuroimagem:**
- Zebra Medical Vision: detecção automática de anomalias em imagens (não específico para AD; não explicável)
- IBM Watson for Oncology (descontinuado): foi tentativa de AI clínica; falhou por confiança clínica
- Google DeepMind (pesquisa): modelos de deep learning para diagnóstico; ainda não em clínica
**[F] Ferramentas acadêmicas/pesquisa:**
- ADNI (Alzheimer's Disease Neuroimaging Initiative): base de dados + alguns modelos preditivos
- Papers publicados com modelos de deep learning para AD detection (90%+ acurácia in silico; não validados clinicamente)
**[H] Possíveis competidores futuros:**
- Grandes tech companies entrando em healthcare (Apple, Google, Amazon) — ainda não focado em AD diagnóstico
- Startups de AI médica em fase de funding
**[F] Diferencial do TCC:**
- Foco em **explainabilidade** (Feature-Augmented XAI): não é apenas detecção, mas EXPLICAÇÃO que clínico entenda
- Validação clínica: propósito do TCC é demonstrar que explicabilidade melhora confiança clínica (ainda não comprovado para AD)

## 6.3 Quais interfaces profissionais esse público já conhece?
 
**[F] Experiência existente de radiologistas/médicos:**
 
| Interface / Software | Contexto | Características familiares |
|---|---|---|
| **PACS (Picture Archiving and Communication System)** | Padrão em todas radiologias | Visualização de imagens; zoom, pan, janela de cor (windowing); interface médica; integrado a HIS |
| **Prontuário Eletrônico (EHR)** | Obrigatório em hospitais | Entrada de texto; templates; estruturado; segurança; logs auditáveis |
| **Ferramentas de imagem (Photoshop, Fiji/ImageJ)** | Pesquisadores; alguns radiologistas | Ferramentas de análise avançada; histogramas; medições |
| **Dashboards de BI (Tableau, Power BI)** | Hospitais grandes; auditar performance | Gráficos; filtros; agregação de dados |
| **Sistemas de CAD tradicionais (em PACS)** | Alguns hospitais; radiology CAD | Menu simples; checkbox; score numérico; pouca interatividade |
| **Bancos de dados (SQL, Excel)** | Pesquisadores; clínicos administrativos | Tabelas; filtros; sorting; familiares |
| **Google Scholar, PubMed** | Pesquisadores; clínicos acadêmicos | Busca; resultados filtrados; interface web simplificada |
 
**[H] Experiência limitada:**
- Prototipagem de UX/design
- Prototipagem de interações exploratórias
- Interfaces altamente customizadas

## 6.4 O que essas soluções parecem fazer bem?
 
**[F] Força: PACS**
- Excelente visualização de imagem médica
- Integrado ao fluxo clínico (HIS)
- Familiar a radiologistas (20+ anos de uso)
- Rápido
**[F] Força: Prontuário Eletrônico**
- Documentação estruturada
- Auditoria automática
- Integração legal/compliance
**[F] Força: Sistemas CAD clássicos (em PACS)**
- Integração nativa em workflow radiológico
- Leitura rápida (score numérico)
- Familiaridade
**[F] Força: Dashboards de BI**
- Visualização clara de dados agregados
- Filtros intuitivos
- Comparação entre casos/periodos
**[F] Força: Conferência multidisciplinar**
- Consenso clínico
- Explicação verbal clara entre especialistas
- Validação através discussão

## 6.5 O que parecem fazer mal, dificultar ou não atender?
 
**[F] Fraqueza: PACS**
- Nenhuma recomendação automática; puramente visual
- Nenhuma explicação estruturada do raciocínio
**[F] Fraqueza: Prontuário Eletrônico**
- Texto livre (sem estrutura); difícil auditar justificativa técnica
- Não integra raciocínio diagnóstico automaticamente
**[F] Fraqueza: Sistemas CAD antigos**
- "Caixa preta": não explica POR QUÊ chegou naquele score
- Confiança do clínico baixa (não compreende recomendação)
**[F] Fraqueza: Conferência multidisciplinar**
- **Não escalável**: demanda tempo de múltiplos experts (caro)
- Apenas para casos difíceis (casos óbvios não passam por conferência)
- Dependente de disponibilidade de experts (raro em cidades pequenas)

## 6.6 Que padrões de interface ou vocabulário parecem familiares a esse público?
 
**[F] Padrões visuais familiares:**
- Visualização de imagem médica: zoom, pan, windowing (ajuste de contraste/brilho)
- Heatmaps/overlays coloridos (radiologistas conhecem "color mapping" de CT/MRI)
- Medições de distância/área em imagens (ferramenta de ruler)
- ROI (Region of Interest) highlighting
**[F] Padrões de interação:**
- Menu simples com opções claras (não abusado)
- Botões de ação grandes (não clicáveis pequenos)
- Confirmação antes de ação crítica ("Tem certeza?")
- Atalhos de teclado (radiologistas querem rapidez)
**[F] Vocabulário clínico familiar:**
- Termos anatômicos: "hipocampo", "córtex", "matéria cinzenta", "ventrículos"
- Termos de radiologia: "atrofia", "dilatação", "lesão", "normal", "anormal"
- Escalas/scores conhecidos: MMSE, MoCA, CDR
- Probabilidades/likelihoods: "provável", "possível", "improvável"
**[F] Padrões de documentação:**
- Templates estruturados (radiologistas usam templates em PACS)
- Checkboxes e dropdowns (rápido)
- Texto livre para notas adicionais

---

# 7. Derivando o escopo de IHC da disciplina

## 7.1 Escolha o caminho do projeto
 
### Resposta: Caminho B — TCC não possui interface prevista
 
**Justificativa**: O TCC atual é um projeto de **pesquisa em Explainable AI** (algoritmo + validação). A interface clínica (como médicos interagem com as explicações) **não está prevista** no escopo técnico original. Esta disciplina de IHC é oportunidade para projetar essa interface.
 
**Exercício de Transferência de Uso:**
 
> O TCC foi concluído com sucesso. Um hospital ou centro de pesquisa quer transformar o método Feature-Augmented XAI em ferramenta utilizável na prática. Quem interage com ela e para quê?
 
**Respostas específicas:**
 
1. **Quem poderia contratar/adotar a solução?**
   - [F] Hospitais com neuroimagem (públicos ou privados)
   - [F] Centros de pesquisa em Alzheimer
   - [H] Clínicas de neurologia especializadas
   - [H] Telemedicina em localidades rurais
2. **Quem seria o usuário direto?**
   - [F] Radiologista (interpreta imagens; primeiro contato com ferramenta)
   - [F] Médico clínico (recebe relatório; usa para diagnóstico)
   - [F] Neurologista especialista (valida e supervisiona)
   - [H] Paciente (possível acesso futuro a explicações; ainda não previsto)
3. **Quem administraria/configuraria?**
   - [F] Técnico TI do hospital ou fornecedor
   - [H] Adminitrador clínico (define protocolos de uso)
4. **Quem interpretaria resultados?**
   - [F] Médico clínico → paciente (comunicação de diagnóstico)
   - [F] Neurologista → equipe (supervisão)
   - [F] Auditor → hospital (compliance)
5. **Quem tomaria decisões?**
   - [F] Médico clínico: diagnóstico final é responsabilidade legal seu (não da IA)
   - [F] Neurologista: valida em casos críticos
   - [H] Gestor: decisão de adotar/descontinuar ferramenta
6. **Quais dados/entradas seriam necessários?**
   - [F] Imagem MRI (T1, T2, FLAIR sequences)
   - [F] Dados clínicos: teste cognitivo (MMSE/MoCA), história clínica
   - [H] Informação familiar (história de demência)
   - [F] Informação de paciente: idade, escolaridade, comorbidades
7. **Quais resultados deveriam ser compreendidos?**
   - [F] Diagnóstico sugerido (Alzheimer provável? sim/não/incerto)
   - [F] **Explicação**: Quais regiões da MRI foram críticas? Qual peso para cada feature?
   - [F] Confiança/incerteza do modelo (70%? 50%?)
   - [F] Comparação com casos anteriores (evoluiu?)
   - [H] Recomendação de ação (chamar especialista? fazer follow-up?)
8. **Que erros/rupturas seriam possíveis?**
   - [F] Falso positivo (saudável → diagnóstico de AD)
   - [F] Falso negativo (AD → não diagnosticado)
   - [F] Explicação incompreensível → confiança falsa
   - [F] Falta de documentação → risco regulatório
   - [H] Bias do modelo (sistemáticos em grupo de idade/sexo/escolaridade)

## 7.2 Qual perfil será priorizado no projeto de IHC?
 
**Perfil Escolhido: Médico Clínico em contexto de atenção primária ou hospital geral**
 
**Subtipo específico**: Médico clínico sem expertise em neuroimagem; que precisa tomar decisão diagnóstica rápida; sem acesso imediato a especialista.
 
**Por que esse perfil foi escolhido?**
 
1. **Volume de usuários**: Maior número de médicos clínicos que radiologistas especializados
2. **Ponto de crítico de confiança**: Se médico clínico não entender explicações XAI, sistema falha (ele é quem toma decisão final)
3. **Diferencial do TCC**: Feature-Augmented XAI foi proposto justamente para melhorar compreensão de NÃO-EXPERTS em imagem
4. **Impacto**: Médico clínico sem acesso a especialista reduz tempo de diagnóstico (6 meses → semanas)
5. **Correspondência com 3.2 A03**: "Revisar e interpretar explicações XAI" — atividade mais crítica do sistema — é feita pelo médico clínico

## 7.3 Qual objetivo desse usuário será priorizado?
 
**Objetivo escolhido**: *Tomar decisão diagnóstica de Alzheimer com confiança, rapidamente, sem esperar especialista, baseado em COMPREENSÃO CLARA das explicações do sistema*
 
**Por que esse objetivo?**
 
- [F] Resolve problema real: reduz tempo de diagnóstico
- [F] Alinhado com 3.1 "Objetivo real": diagnóstico rápido + confiança + sem dependência de especialista
- [H] Depende criticamente de IHC: se explicações não forem compreendidas, objetivo falha
- [F] Mensurável: pode avaliar se médico realmente compreendeu através de testes/feedback

## 7.4 Que interface será explorada na disciplina?
 
### Declaração de Escopo de IHC:
 
> **Para fins da disciplina de IHC, será projetada uma interface que permita ao `médico clínico` utilizar as `explicações do modelo Feature-Augmented XAI` para `diagnosticar Alzheimer com confiança`, no contexto de `sala de consulta/escritório do hospital, com tempo limitado, sem acesso imediato a especialista`.**
 
**Especificação dos elementos:**
 
- **Perfil**: Médico clínico (não especialista em imagem; variação de expertise)
- **Capacidade/resultado do TCC**: Explicações Feature-Augmented que combinam (1) features do modelo, (2) features clinicamente significativas, (3) contexto do paciente
- **Objetivo**: Diagnosticar Alzheimer com confiança sem dependência de especialista
- **Contexto**: Ambiente hospitalar; tempo limitado; pressão de fila de pacientes; necessidade de rastreabilidade
**O que a interface deve permitir:**
1. Visualizar MRI + explicações sobrepostas
2. Entender QUAIS regiões/features foram críticas para diagnóstico
3. Entender O PORQUÊ (raciocínio clínico traduzido de features do modelo)
4. Comparar com casos anteriores (quando disponível)
5. Registrar decisão com justificativa documentada
6. Solicitar revisão por especialista (se necessário)

## 7.5 Qual é a relação dessa interface com o TCC?

- [ ] Já fazia parte do TCC.
- [ ] É um aprofundamento de algo parcialmente previsto.
- [X] É uma extensão conceitual criada para a disciplina.
- [ ] É um protótipo demonstrativo de aplicação potencial.
- [ ] Outra: {{...}}.

**Declaração de Aprendizagem:**
 
> A interface desenvolvida nesta disciplina de IHC é um artefato de aprendizagem baseado no tema do TCC. Sua inclusão ou implementação efetiva no TCC somente ocorrerá se posteriormente decidido pela equipe de pesquisa e orientador, após validação clínica preliminar.

---

# 8. Levantando possibilidades de interação — sem desenhar ainda

# 8. Levantando possibilidades de interação — sem desenhar ainda
 
A equipe pode registrar possibilidades para investigação. Cada uma corresponde a uma tarefa identificada em seções anteriores.
 
| Possibilidade | Faz sentido? | Objetivo/tarefa que justificaria | Evidência atual |
|---|---|---|---|
| **Dashboard/visão geral de casos** | SIM | Médico vê lista de pacientes pendentes de diagnóstico; prioriza casos mais críticos | [F] A01, A06: consulta histórico; [H] workflow comum em PACS |
| **Configuração/parametrização do modelo** | NÃO | Médico clínico não deve configurar modelo (responsabilidade de pesquisador/admin TI) | [F] Fora do escopo (admin responsibility) |
| **Entrada/upload/seleção de dados (MRI)** | SIM | Médico ou técnico faz upload de MRI para análise; seleciona study type (T1, T2, FLAIR) | [F] A01: preparação de dados; [F] Padrão em PACS |
| **Acompanhamento de processamento** | TALVEZ | Se processamento levar > 30 segundos, mostrar progresso (barra de carregamento); caso contrário não necessário | [H] Depende de velocidade do algoritmo |
| **Relatório/resultados formatado** | SIM | Diagnóstico em linguagem clínica clara; scores numéricos; comparação com treshold | [F] A05, A07: documentação e comunicação ao paciente; [F] Padrão clínico |
| **Histórico com busca/filtros** | SIM | Médico busca MRI anterior de mesmo paciente; compara evolução (atrofia progressiva?) | [F] A06: consultar histórico; [F] Crítico para continuidade |
| **Comparação de resultados** | SIM | Lado-a-lado: MRI 2023 vs MRI 2024; visualizar progressão de atrofia; mudanças em features explicáveis | [H] A06: comparação com casos; [H] Auxilia detecção de progresso |
| **Explicabilidade/detalhamento** | SIM (CRÍTICA) | Mostrar quais regiões/features foram importantes para diagnóstico; visualizar importância relativa de cada feature; saliency maps/heatmaps | [F] A03: interpretar explicações XAI; [F] DIFERENCIAL do TCC; [H] "Como Feature-Augmented melhora compreensão?" |
| **Administração/configurações globais** | TALVEZ | Admin define: protocolo de uso, limiares de confiança para flag specialist, permissões por role | [H] A11, A12: uso periódico por admin; não prioridade para médico clínico |
| **Usuários/perfis/permissões** | SIM | Controle de acesso: radiologista vs clínico vs especialista veem coisas diferentes (ex: especialista vê mais detalhes); auditoria de quem fez quê | [F] A04, A05: documentação e rastreabilidade; [F] Requisito legal/compliance |
| **CRUD de entidade do domínio** | NÃO | Médico clínico não cria/edita diagnósticos retrospectivamente; dados são imutáveis por compliance | [F] Fora do escopo (audit trail crítica) |
| **Auditoria/logs** | SIM | Sistema registra automaticamente: quem abriu caso? quando? qual diagnóstico? qual justificativa? sem dependência de digitação manual | [F] A05: documentação; [F] CRÍTICO para compliance regulatório |
| **Alertas/ocorrências** | SIM | Notificação quando: paciente anteriormente diagnosticado com incerteza baixa recebe nova interpretação | [H] A08: revisar métricas; [H] Possível mas requisito não explícito em 3.2 |
| **Ajuda/documentação** | SIM | Tutorial interativo; explicação sobre o que significa cada metrica/feature; glossário de termos técnicos | [H] A05: treinamento de usuários; [F] Reduz curva de aprendizado |
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
