# Entrega 2 — Público-alvo e análise de concorrência

- **Data:** 03/09/2026
- **Status:** 🟩 em andamento  
- **Responsabilidade mínima:** cada integrante analisa pelo menos 1 concorrente/interface representativa; a equipe produz síntese comparativa.

## Objetivo da atividade

Compreender soluções do mesmo domínio **e também interfaces familiares ao público-alvo**. O objetivo não é copiar telas, mas identificar convenções, padrões, affordances percebidas, problemas recorrentes, expectativas e oportunidades de design.

> **Concorrente não precisa ser idêntico ao produto.** Pode atuar na mesma área, resolver objetivo semelhante ou disputar a mesma necessidade. Quando não houver concorrente direto, use produtos análogos e softwares que o público já utiliza.

### Para TCCs que não previam interface

Não procure apenas um “concorrente do algoritmo”. Investigue **interfaces profissionais que materializam atividades semelhantes** às que o usuário escolhido precisaria realizar.

Exemplos:

- TCC de banco de dados → consoles de administração, ferramentas para DBA, monitoramento e análise de consultas;
- TCC de LLM/ML → painéis de experimentos, gestão de modelos/datasets, comparação de métricas, revisão de resultados;
- TCC de análise de dados → dashboards, ferramentas de BI, filtros, relatórios e exploração;
- TCC de infraestrutura/API → portais administrativos, observabilidade, logs, gestão de credenciais e uso;
- TCC de cibersegurança → consoles de alertas, triagem, histórico e auditoria.

A pergunta é: **“que convenções esse perfil já conhece para executar tarefas equivalentes?”**

## Entrada obrigatória da Entrega 1

Retome o mapa inicial de alternativas e produtos citado na Entrega 1. Aqui a equipe deixa de trabalhar apenas com impressão inicial e passa a **investigar sistematicamente** cada solução.

| Item citado na Entrega 1 | Tipo | Por que foi citado | Status inicial | Decisão nesta entrega |
|---|---|---|---|---|
| {{...}} | concorrente / análogo / ferramenta cotidiana / processo manual | {{...}} | F / H / ? | analisar / descartar com justificativa |

Se uma hipótese da Entrega 1 for confirmada ou refutada durante esta análise, atualize `H01`, `H02`... em [`../RASTREABILIDADE.md`](../RASTREABILIDADE.md).

## 1. Público-alvo desta análise

O público-alvo é composto principalmente por profissionais de saúde, com foco no médico clínico/generalista, definido na Entrega 1 como usuário primário da interface. Neurologistas e radiologistas também são considerados, principalmente para validação dos resultados.

A análise de IHC terá como foco compreender as necessidades desses profissionais ao interpretar as explicações geradas pela IA e utilizá-las como apoio ao diagnóstico de Alzheimer, atividade identificada na Entrega 1 como a mais frequente e crítica.

## 2. Concorrentes diretos/indiretos

### Análise C01 — Glass Health

**Autor(a):** Nathan Gabriel da Fonseca Leite - 221230287

**Tipo:** indireto

**Link oficial:** https://glass.health/

**Data de acesso:** 09/09/2026

#### Contexto e proposta

Esta plataforma reconheceu alguns dos problemas que existiam nos ambientes médicos tais como: sobrecarga administrativa, fragmentação e o volume informacional e busca obsoletas (precisa fazer uma pesquisa bastante específica para achar uma informação útil). Para resolver isso, ela traz a IA para automatizar o preenchimento de relatórios e outros documentos, direciona a atenção do profissional para o diagnósticos de 3 níveis (Mais provável, expandido e não pode perder).

#### Funcionalidades relevantes

| Funcionalidade | Como é realizada | Evidência/print | Observação de IHC |
|---|---|---|---|
| Upload de dados tabulares | Botão que abre uma janela para upload de arquivos | `../assets/02_concorrencia/glasshealth_upload_chat.png` |---|
| Chat com LLM para relatórios automáticos e direcionamento de diagnóstico | Aba na esquerda da tela com uma barra inferior onde pode digitar | `../assets/02_concorrencia/glasshealth_upload_chat.png` | Uso de fundo claro e preenchimento da altura completa da tela |
| Dashboard de exibição de dados | Ao subir dados do paciente, há o preenchimento automático do dashboard exibindo estes mesmos | `../assets/02_concorrencia/glasshealth_upload_chat.png` | Elementos arredondados, informações importantes em negrito |

#### Experiência do usuário e opiniões

Excelente "Parceiro de Raciocínio": Diferente de plataformas que funcionam apenas como mecanismos de busca estruturada, o Glass Health funciona como uma "lousa digital inteligente". Ele ajuda o clínico a mapear possibilidades e estruturar o pensamento frente a casos complexos. 
Inteligência Ambiental Integrada (Ambient Scribing): A plataforma evoluiu para capturar consultas em tempo real, gerando notas clínicas estruturadas e planos de manejo diretamente a partir da conversa. 
Transparência em Citações: O Glass Health é elogiado por embutir referências e links diretos para a literatura médica em seus planos de tratamento recomendados. 

Foco no Modelo Americano/Global: A iatroX alerta que o Glass Health possui uma base de dados predominantemente voltada para as diretrizes dos EUA. Por conta disso, ele pode sugerir condutas ou antibióticos que conflitam com protocolos locais de outros países (como as diretrizes do NICE no Reino Unido ou protocolos do SUS no Brasil). 
Risco no Processamento de Dados: Como o Glass Health ingere dados clínicos e áudios de consultas em tempo real, há uma fricção regulatória maior quanto à privacidade de dados locais dos pacientes se comparado a ferramentas de consulta estática.

#### Preço/modelo de negócio

O Glass Health opera sob um modelo freemium baseado em assinaturas SaaS abordando individualmente o profissional ou institucionalmente o hospital.

| Plano | Preço Mensal | Principais Recursos Incluídos |
|---|---:|---|
| Glass Lite | Gratuito ($0) | Uso limitado de gravação de consultas (scribe) e suporte a decisões clínicas. Inclui anúncios. |
| Glass Starter | $20 / mês | Capacidade expandida de gravação de consultas e suporte clínico aprimorado. |
| Glass Pro | $90 / mês | Transcrição de consultas ilimitada, suporte clínico completo e acesso ao modo de Deep Reasoning (Raciocínio Clínico Profundo). |
| Glass Max | $200 / mês | Tudo do plano Pro + Integração com prontuários eletrônicos (EHR) como Epic, athenahealth, eClinicalWorks e Elation. |

#### Padrões e tendências percebidos

Uso de cores claras, elementos arredondados, ícones de acordo com a tarefa ou contexto do elemento, informações importantes em destaque por negrito, diferentes cores de fundo de acordo com a funcionalidade geral(Azul para exibição dos dados no dashboard e branco para o chat LLM, por exemplo).

#### Pontos positivos, limitações e lições

| Ponto | Evidência | Implicação para nosso projeto |
|---|---|---|
| Variar cores de fundo de acordo com o funcionalidade geral | `../assets/02_concorrencia/glasshealth_upload_chat.png` | Usar a mesma ideia para facilitar o olhar intuitivo do médico |
| Uso de cores claras | `../assets/02_concorrencia/glasshealth_upload_chat.png` | Usar a mesma ideia para evitar um estranhamento inicial do usuário com a interface |

### Análise C02 — BrainSee (Darmiyan, Inc.)

**Autor(a):** Paulo Hudson - 22.222.013-9

**Tipo:** indireto / análogo

**Link oficial:** https://brainsee.ai

**Data de acesso:** 09/09/2026

BrainSee é um software de IA, desenvolvido pela Darmiyan Inc. É o produto de mercado mais próximo do M-XAI que encontramos: combina MRI cerebral de rotina com testes cognitivos (MMSE e CDR-SB) e dados demográficos (idade, sexo) para gerar um score de 0 a 100 que indica a probabilidade de um paciente com comprometimento cognitivo leve progredir para demência de Alzheimer em 5 anos. O score reflete o grau de similaridade do paciente com duas populações de referência: quem progrediu ("converters") e quem não progrediu ("non-converters") dentro desse período.

É oferecido como plataforma em nuvem, acessada via portal web por médicos (neurologistas, geriatras, psiquiatras, clínicos gerais e médicos internistas), tipicamente em atenção primária — exatamente o perfil que priorizamos na Entrega 1 (médico clínico sem acesso imediato a especialista).

#### Funcionalidades relevantes

| Funcionalidade | Como é realizada | Evidência/print | Observação de IHC |
|---|---|---|---|
| Upload de dados do paciente | Médico faz upload do arquivo de MRI e insere manualmente os scores de MMSE e CDR-SB no portal web | Fonte: brainsee.ai/doctors ("Upload brain MRI scan files... Enter MMSE & CDRSB scores") — sem print, portal fechado a cadastro profissional | Fluxo de entrada muito próximo ao nosso F01 (abrir caso com MRI + dados clínicos) |
| Geração de score de risco (0–100) | Processamento automático no servidor; resultado no mesmo dia; score <50 = baixo risco, >50 = alto risco | Fonte: brainsee.ai/doctors + BioSpace (release oficial) — sem print, portal fechado | Análogo ao nosso F04 (ver grau de confiança) — mas aqui é um único número de risco, não uma explicação de features |
| Relatório de saída visualizável/baixável/imprimível (PDF) | "View/download BrainSee the analysis report (PDF)" dentro do próprio portal | Fonte: brainsee.ai/doctors — sem print, portal fechado | Relaciona-se a F06 (registrar decisão com justificativa) |
| Tutorial e guia de interpretação | Material de apoio fornecido junto ao software, tanto para médicos quanto para pacientes/cuidadores | Fonte: Alzforum ("comes with a tutorial and interpretation guide for physicians, as well as a guide for patients and caregivers") — sem print | Reforça diretamente F08 (glossário/ajuda contextual) |

> **Nota metodológica**: o portal do BrainSee é fechado com acesso liberado após formulário de verificação profissional (CRM/licença, instituição), aprovado pela Darmiyan. Não há demo público do lado do médico (só um vídeo de imprensa sobre a aprovação da FDA, sem imagens da tela). Por isso as evidências acima são citações de fonte primária (site oficial + imprensa), não capturas de tela. Isso em si é um dado de IHC: o produto não expõe transparência de interface ao público, o que dificulta benchmarking externo — algo que podemos citar como diferencial se o nosso protótipo/documentação for mais aberta.

#### Experiência do usuário e opiniões

 O que existe publicado é a validação clínica do escore: em estudo clínico, médicos não afiliados à Darmiyan usaram o software para prever o prognóstico de 107 pacientes com aMCI amnéstico, comparando a predição com os desfechos clínicos 5 anos depois;

#### Preço/modelo de negócio

- Preço de tabela: US$ 1.500 por teste.
- Preço praticado enquanto aguarda cobertura pelo Medicare: US$ 300 por teste.
- A ressonância em si já é coberta pelo Medicare separadamente (custo médio de US$ 1.000 fora do bolso, quando não coberta).
- Desde set/2024, existe também o "BrainSee Platform", que amplia o produto para incluir consultas remotas, agendamento de MRI e acompanhamento — não é mais só o teste isolado, é uma jornada completa do paciente.

#### Padrões e tendências percebidos

- Saída como **score único e objetivo (0–100)**, não como explicação multi-camada (sem heatmap visual sobre a MRI, ao que tudo indica) — é mais parecido com uma pontuação de risco tipo "score de crédito" do que com uma explicação Grad-CAM/SHAP.
- Uso de **duas populações de referência** (quem progrediu vs. quem não progrediu) como base de comparação — um tipo de explicação por analogia/exemplo, diferente da explicação por atribuição de features do M-XAI.
- Fornecimento de **material de apoio à interpretação** junto ao produto (tutorial + guia), reconhecendo que o número sozinho não basta.
- Modelo de precificação por teste (não assinatura), alinhado ao fato de ser usado pontualmente por caso, não como ferramenta de uso contínuo.

#### Pontos positivos, limitações e lições

| Ponto | Evidência | Implicação para nosso projeto |
|---|---|---|
| Fluxo de entrada simples (upload de MRI + 2 scores clínicos) já validado no mercado e aprovado pela FDA | Documentação regulatória FDA DEN220066; fluxo descrito em múltiplas fontes de imprensa especializada | Valida que nosso F01 (upload de MRI + dados clínicos) é um padrão realista e aceito clinicamente, não uma invenção nossa |
| Saída como score único, sem explicação visual sobre a imagem | Ausência de menção a heatmap/overlay em toda a cobertura encontrada | Aqui está uma diferença real e defensável do M-XAI: nosso projeto vai além do BrainSee ao oferecer explicação visual (Grad-CAM) + explicação de features clínicas (SHAP), não apenas um número — isso pode virar argumento de originalidade **verificado**, ao contrário do "Feature-Augmented" (ver observação da pesquisa anterior) |
| Empresa fornece guia de interpretação junto ao produto | Confirmado em fonte jornalística (Alzforum) | Reforça a prioridade de F08 (ajuda/glossário) — mesmo um produto aprovado pela FDA sentiu necessidade de "traduzir" o resultado para o médico |
| Preço alto de tabela (US$1.500) pode ser barreira de adoção, mesmo com desconto temporário | Fonte: Alzforum | Não é um problema de IHC diretamente, mas é contexto de mercado relevante para justificar por que uma alternativa mais acessível (como a proposta do M-XAI) tem valor de negócio, não só técnico |

### Análise C03 — OHIF Viewer

**Autor(a):** Ana Carolina Lazzuri - 22.123.001-4

**Tipo:** análogo / ferramenta cotidiana

**Link oficial:** https://ohif.org / https://viewer.ohif.org/

**Data de acesso:** 09/09/2026

#### Contexto e proposta

O OHIF Viewer é o visualizador web de exames DICOM mais usado para integrar modelos de IA à práticas médicas. Ele permite navegar por imagens 3D (como ressonâncias magnéticas) e aplicar mapas de calor e segmentações direto no navegador, sem precisar de instalações na máquina do hospital.

#### Funcionalidades relevantes

| Funcionalidade | Como é realizada | Evidência/print | Observação de IHC |
|---|---|---|---|
| Visualização de MRI em diferentes formatos (Axial, Sagital, Coronal) | *Viewports* divididos e sincronizados para navegar pelos planos da imagem. | pendente | O médico já espera usar o *scroll* do mouse para trocar de corte e arrastar para dar zoom/pan. |
| Controle de Overlays de IA | Botão para ligar/desligar a camada de IA e barra para ajustar a transparência (0 a 100%). | pendente | O usuário precisa conseguir esconder o Grad-CAM para conferir a anatomia real por baixo. |
| Painel de Dados do Paciente | Barra lateral retrátil com dados do paciente e métricas do exame. | pendente| Manter as informações na lateral evita poluição visual no centro da tela. |
| Ajuste de Contraste (*Windowing*) | Arrastar o ponteiro sobre a imagem para alterar brilho e contraste em tempo real. |pendente | A sobreposição da IA não pode quebrar a ajuste de contraste feito pelo médico. |

#### Experiência do usuário e opiniões

O OHIF se destaca pelo desempenho rápido no navegador e por usar o padrão *dark mode*, que reduz o cansaço visual e melhora a leitura das imagens de ressonância. Por outro lado, médicos que não são radiologistas costumam achar a tela inicial carregada com muitas ferramentas técnicas de medição que não usam no dia a dia.

#### Preço/modelo de negócio

Gratuito e open-source (licença MIT). É financiado pelo *National Cancer Institute* (NCI) e mantido pela comunidade, servindo de base para diversas startups e hospitais criarem suas próprias interfaces.

#### Padrões e tendências percebidos

- **Tema Escuro Nativo:** Padrão absoluto em radiologia para dar contraste às imagens em tom de cinza.
- **Controle de Transparência:** A interface nunca deixa o destaque da IA fixo; o médico sempre pode suavizar ou ocultar a marcação.
- **Painéis Retráteis:** Ferramentas e dados adicionais ficam escondidos nas laterais para priorizar o exame na tela principal.

#### Pontos positivos, limitações e lições

| Ponto | Evidência | Implicação para nosso projeto |
|---|---|---|
| Ajuste de transparência do destaque visual | Slider de opacidade presente nas ferramentas de IA do OHIF | O M-XAI deve ter um controle simples para o médico ajustar a opacidade do Grad-CAM sobre a ressonância. |
| Foco central na imagem com fundo escuro | Design nativo do OHIF em tom escuro  | Usar tema escuro na tela do exame para evitar fadiga visual e destacar o hipocampo. |
| Poluição visual para o clínico geral | Excesso de botões de medição e calibração no topo da tela | Como nosso foco são profissionais da área da saúde, devemos manter apenas o básico: zoom, contraste, cortes e transparência da IA. |
| Pouco espaço para dados clínicos fora da imagem | OHIF foca 100% na imagem e joga os dados em abas secundárias | O M-XAI é multimodal; precisamos dar o mesmo destaque visual para a explicação SHAP (dados do paciente) e para o Grad-CAM (imagem). |

### Análise C04 — iatroX

**Autor(a):** Raphael Garavati Erbert

**Tipo:** indireto

**Link oficial:** https://iatrox.com/

**Data de acesso:** 15/09/2026

#### Contexto e proposta

O iatroX é uma plataforma de IA clínica, registrada como dispositivo médico Classe I pela MHRA (agência reguladora do Reino Unido) para seu componente de referência em guidelines. Diferente do Glass Health (chat de raciocínio diagnóstico amplo) e do BrainSee/Neuroreader (ferramentas de diagnóstico por imagem), o iatroX não faz diagnóstico nem processa exames de paciente: ele resolve o problema de sobrecarga informacional do clínico, respondendo perguntas clínicas em linguagem natural com respostas ancoradas em diretrizes oficiais do Reino Unido (NICE, CKS, SIGN, BNF), sempre citando a fonte. Além do "askiatroX", a plataforma inclui bancos de questões adaptativos para mais de 40 exames médicos (UK, EUA, Canadá, Austrália, Itália), calculadoras clínicas e um "Tutor Socrático" para estudo. É, portanto, mais um concorrente indireto pela atenção do médico do que um concorrente direto do M-XAI — mas extremamente relevante pelo padrão de **transparência de citação** que estabelece.

#### Funcionalidades relevantes

| Funcionalidade | Como é realizada | Evidência/print | Observação de IHC |
|---|---|---|---|
| Chat de perguntas clínicas com citação de fontes (askiatroX) | Campo de texto (ou voz) onde o médico faz a pergunta; resposta estruturada aparece com "pills" de referência clicáveis que levam direto à guideline original | `../assets/02_concorrencia/pergunta_askiatroX.png` | Uso de citações como elementos de UI (não só texto corrido) parece ser o maior diferencial de confiança da plataforma |
| Acesso gratuito sem login (20 perguntas de teste) | Botão de "perguntas grátis" que libera uso imediato da IA sem formulário ou verificação profissional | `../assets/02_concorrencia/gratis_askiatroX.png`| Contrasta diretamente com o portal fechado do BrainSee/Neuroreader — reduz fricção de primeiro uso |
| Calculadoras clínicas dinâmicas (NEWS2, SOFA, Wells etc.) | Formulário de inputs específicos por calculadora, com conversão de unidade automática e faixa de interpretação clínica exibida junto ao resultado | `../assets/02_concorrencia/calculadora_ask.png`| Resultado numérico sempre vem acompanhado de banda de interpretação (ex.: "risco baixo/moderado/alto"), nunca um número isolado |
| Expansão de raciocínio ("reasoning steps") por resposta | Botão para expandir a resposta padrão e ver passos de raciocínio, diagnósticos diferenciais e marcadores de confiança | `../assets/02_concorrencia/expansao_ask.png` | Camada opcional de profundidade (resposta curta por padrão, detalhe sob demanda) evita sobrecarregar o médico em consultas rápidas |


#### Experiência do usuário e opiniões

O material disponível é majoritariamente autopublicado, mas há um dado mais robusto: um estudo formativo (preprint, abril–julho de 2025) com dados reais de uso de ~19 mil usuários web e uma pesquisa com 1.223 clínicos do Reino Unido, medindo adoção, usabilidade e valor clínico percebido do iatroX. A hipótese testada — que uma ferramenta rápida, gratuita e ancorada em guidelines nacionais seria adotada rapidamente por um corpo clínico diverso — foi reportada como confirmada pelos próprios autores. Vale registrar que o estudo foi conduzido pela própria equipe do produto, o que exige cautela na leitura dos números de adoção e satisfação. Em conteúdo de blog institucional, o iatroX se posiciona explicitamente contra assistentes generalistas (ChatGPT, Gemini) para uso clínico, argumentando que a "alucinação" desses modelos é o principal risco que a arquitetura RAG (Retrieval-Augmented Generation) do iatroX evita.

#### Preço/modelo de negócio

Modelo freemium, com plano gratuito genuinamente funcional (não apenas trial):

| Plano | Preço | Principais recursos incluídos |
|---|---:|---|
| Gratuito | £0 | askiatroX ilimitado + bancos de questões de 4 exames específicos (MRCP Part 1, MRCEM SBA, PSA, PARA), sem cartão de crédito |
| Assinatura completa | £29/mês ou £99/ano | Todos os bancos de questões (UKMLA, PLAB 1, MSRA, MRCGP AKT, SCEs, exames dos EUA/Canadá/Austrália/Itália), Tutor Socrático, planejador de estudos por IA e simulados completos |

Modelo de negócio focado em educação médica/exame (assinatura B2C individual), enquanto a ferramenta de referência clínica (askiatroX) permanece gratuita como isca de aquisição e, provavelmente, fonte de dados de uso para o produto educacional pago.

#### Padrões e tendências percebidos

- **Citação como elemento de interface, não rodapé**: as referências aparecem como "pills" clicáveis dentro da própria resposta, não como lista de fontes ao final — reforça a rastreabilidade em tempo real.
- **Resposta em camadas (short-answer-first)**: resposta direta por padrão, com expansão opcional para raciocínio detalhado — evita "paredes de texto" na tela.
- **Bandas de interpretação em vez de números isolados**: toda saída numérica (calculadora, score) vem com uma faixa de risco/interpretação ao lado, nunca um valor cru.
- **Gratuidade real como estratégia de confiança**: ausência de paywall na função clínica central (diferente de Glass Health, que restringe funcionalidades avançadas ao plano pago) é usada como argumento de adoção e transparência.
- **Escopo geográfico explícito**: a plataforma é clara sobre ser "UK-gated" — resposta ancorada em guidelines do Reino Unido — o que evita o problema que a própria iatroX apontou no Glass Health (viés para diretrizes dos EUA aplicadas fora de contexto).

#### Pontos positivos, limitações e lições

| Ponto | Evidência | Implicação para nosso projeto |
|---|---|---|
| Citações como "pills" clicáveis dentro da resposta, não em lista separada | [iatrox.com/ask-iatrox](https://www.iatrox.com/ask-iatrox) | O M-XAI pode adotar o mesmo princípio para a explicação SHAP: cada feature destacada podendo levar a uma nota explicativa, em vez de um glossário separado da tela principal |
| Acesso público sem barreira de cadastro reduz fricção de primeiro uso | [iatrox.com/free-questions](https://www.iatrox.com/free-questions) | Reforça a lição já registrada no C02/C04: documentação e protótipo abertos do M-XAI são um diferencial real frente ao padrão fechado do mercado de diagnóstico por imagem |
| Resposta em camadas (resumo primeiro, detalhe sob demanda) | [iatrox.com/how-it-works](https://www.iatrox.com/how-it-works) | Aplica-se diretamente ao nosso F04: mostrar o grau de confiança/resultado principal primeiro, com Grad-CAM e SHAP detalhados disponíveis por expansão, não tudo de uma vez |
| Escopo geograficamente delimitado e declarado (UK-gated) | Material institucional ("iatroX is a UK-gated RAG pipeline") | Reforça a necessidade de o M-XAI declarar explicitamente os limites de generalização do modelo (dataset ADNI, predominantemente norte-americano) — um paralelo direto ao aviso que o próprio iatroX fez sobre o viés do Glass Health |


## 3. Softwares que o público-alvo usa no cotidiano

| Software | Por que o público usa | Padrões relevantes | Prints | O que aprender |
|---|---|---|---|---|
| **OHIF Viewer** | Visualizar exames de ressonância (MRI) e camadas de IA no navegador. | Tela escura, navegação por cortes (*scroll*), zoom e ajuste de transparência da IA. | | O médico já está acostumado a ver imagens em telas escuras e controlar a opacidade dos destaques da IA. |
| **BrainSee (Darmiyan)** | Consultar o risco de progressão de Alzheimer para apoiar o diagnóstico. | Formulário simples de envio de dados, score numérico de risco e relatório em PDF. | | A entrada de dados precisa ser rápida e o resultado deve vir acompanhado de um guia fácil de interpretar. |
| **Glass Health** | Auxiliar no raciocínio diagnóstico e agilizar relatórios médicos. | Diagnósticos organizados por prioridade (*Mais provável*, *Expandido*, *Não pode perder*) e chat. | | Mostrar hipóteses bem categorizadas sem sobrecarregar o médico com blocos longos de texto. |
| **iatroX** | Tirar dúvidas clínicas rápidas com resposta ancorada em guidelines oficiais (NICE, CKS, SIGN, BNF). | Chat com citações clicáveis, resposta curta por padrão com detalhe sob demanda, acesso gratuito sem cadastro. | | O médico confia mais na resposta quando a fonte está visível e clicável dentro da própria resposta, não em rodapé separado. |

## 3.1 Padrões de interface relevantes ao escopo de IHC

| Padrão observado | Produto(s) | Para qual tarefa serve | Vantagem percebida | Risco/limitação | Aplicável ao nosso escopo? |
|---|---|---|---|---|---|
| **Destaque Visual com Transparência** | OHIF Viewer | Analisar o cérebro e conferir a marcação (Grad-CAM) da IA. | Permite ver a imagem original e o destaque da IA sem esconder o cérebro. | Se a barra de transparência for ruim, a marcação pode cobrir detalhes da imagem. | **Sim** (Usar no visualizador do Grad-CAM). |
| **Score Numérico de Risco** | BrainSee | Resumir a chance do paciente evoluir para Alzheimer (0 a 100). | Entendimento rápido em consultas curtas. | O médico pode confiar no número sem checar os motivos. | **Talvez** (Usar como resumo, mas acompanhado da explicação). |
| **Painéis Laterais Dobráveis** | OHIF Viewer / Glass Health | Mostrar dados e testes do paciente sem cobrir o exame. | Mantém o foco no cérebro e deixa a tela limpa. | Se ficar escondido, o médico pode não ver dados importantes. | **Sim** (Ideal para os dados do paciente e o gráfico SHAP). |
| **Relatório Baixável (PDF)** | BrainSee / Glass Health | Salvar o diagnóstico no prontuário ou entregar ao paciente. | Facilita guardar o histórico e explicar o caso para a família. | Texto muito técnico pode confundir o paciente. | **Sim** (Permitir baixar o laudo explicativo). |
| **Citação Embutida na Resposta (referência clicável)** | iatroX | Rastrear a origem de uma afirmação clínica gerada por IA sem sair da tela principal. | Aumenta a confiança do médico na saída da IA por permitir verificação imediata da fonte. | Se a citação for genérica ou mal vinculada, pode dar falsa sensação de rastreabilidade. | **Sim** (Ligar cada feature do SHAP a uma referência/nota explicativa clicável). |

## 4. Síntese comparativa da equipe

| Critério | C01 (Glass Health) | C02 (BrainSee) | C03 (OHIF Viewer) | C05 (iatroX) | Oportunidade para o projeto |
|---|---|---|---|---|---|
| **Navegação** | Baseada em chat e abas de documentos. | Passo a passo direto: Envio → Análise → Relatório. | Telas divididas com navegação de imagens pelo *scroll* do mouse. | Chat de pergunta única, sem etapas — resposta aparece na mesma tela em segundos. | Usar o envio simples do C02 com a tela de visualização direta do C03. |
| **Feedback/estado** | Respostas de texto em tempo real no chat. | Avisa quando o resultado do score está pronto. | Resposta imediata ao mexer no contraste e botão claro de IA ligada/desligada. | Tempo de resposta declarado abaixo de 20 segundos; resposta curta aparece primeiro, detalhe expande sob clique. | Mostrar na hora o ajuste de transparência e o status de carregamento da IA. |
| **Prevenção de erro** | Campo de texto livre pode aceitar dados incompletos. | Bloqueia o envio se faltar algum teste ou imagem. | Avisa se o arquivo de imagem estiver corrompido. | Sistema recusa responder ("abstenção segura") quando a confiança é baixa ou a pergunta foge do escopo de guidelines do Reino Unido. | Validar os arquivos e exames antes de enviar para a IA não errar; considerar também abstenção do modelo em casos de baixa confiança, como o C05. |
| **Terminologia** | Termos médicos do dia a dia da clínica geral. | Linguagem direta focada em probabilidade e testes. | Termos muito técnicos e avançados de radiologia. | Linguagem clínica direta, sempre amarrada ao nome da guideline de origem (NICE, CKS, SIGN, BNF). | Usar termos simples para o clínico geral e explicar nomes difíceis de IA em um glossário. |
| **Acessibilidade** | Tela clara e focada em leitura de texto. | Visual limpo com opção de relatório fácil de ler e imprimir. | Tela escura nativa para não cansar a vista e destacar detalhes da imagem. | Acesso público, sem cadastro nem paywall na função clínica central. | Adotar tela escura na imagem do cérebro para não cansar a vista do médico; considerar também reduzir a barreira de primeiro acesso ao protótipo, como o C05. |
| **Eficiência** | Agiliza a criação de relatórios. | Leitura rápida por meio de um score único. | Imagens carregam rápido no navegador. | Resposta média em menos de 20 segundos, otimizada para consulta rápida entre atendimentos. | Juntar a rapidez de resposta do C05 com a facilidade do mouse do C03. |

## 5. Recomendações derivadas

- **RC01:** Usar um controle de transparência (0% a 100%) no mapa de calor da ressonância — derivada do C03 (OHIF Viewer), permitindo que o médico veja a imagem real do cérebro por baixo do destaque da IA.
- **RC02:** Adotar fundo escuro (*dark mode*) na tela do exame — derivada do C03 (OHIF Viewer), para não cansar a vista do médico e destacar as nuances de cinza da imagem.
- **RC03:** Exibir a chance de diagnosticada em um score de risco simples — derivada do C02 (BrainSee), agilizando a leitura do caso durante consultas curtas.
- **RC04:** Incluir um guia ou glossário explicativo junto com o resultado — derivada do C02 (BrainSee) e C01 (Glass Health), para ajudar o clínico geral a entender os termos da IA e explicar o quadro para o paciente.
- **RC05:** Criar um formulário de envio de dados simples e em etapas (imagem + testes) — derivada do C02 (BrainSee), evitando que o sistema receba dados incompletos.
- **RC06:** Colocar as informações do paciente e os gráficos em painéis laterais dobráveis — derivada do C03 (OHIF Viewer), mantendo a tela limpa e o foco principal no cérebro.
- **RC07:** Manter apenas os botões essenciais na tela (zoom, contraste, cortes e transparência) — derivada de limitação do C03 (OHIF Viewer), evitando poluição visual para o clínico geral.

## Referências

- **Glass Health:** Disponível em: <https://glass.health/>. Acesso em: 09 set. 2026.
- **BrainSee (Darmiyan, Inc.):** Disponível em: <https://brainsee.ai>. Acesso em: 09 set. 2026.
- **OHIF Viewer (Open Health Imaging Foundation):** Disponível em: <https://ohif.org/> e <https://viewer.ohif.org/>. Acesso em: 09 set. 2026.
- **FDA Regulation (BrainSee):** U.S. Food and Drug Administration. De Novo Classification Order DEN220066 (BrainSee).
- **BARBOSA, S. D. J.; SILVA, B. S.** Interação Humano-Computador. Rio de Janeiro: Elsevier, 2010.

## Checklist

- [x] O mapa inicial de alternativas da Entrega 1 foi revisitado e aprofundado.
- [x] Hipóteses relevantes sobre mercado/padrões foram atualizadas na rastreabilidade quando surgiram evidências.
- [x] Há pelo menos uma análise completa por integrante.
- [x] Cada análise contém prints legíveis da interface.
- [x] Prints mostram telas/estados relevantes, não apenas logos/homepage.
- [x] Foram analisados concorrentes e/ou interfaces representativas ao público.
- [x] Em TCC sem interface original, foram investigadas ferramentas profissionais análogas às atividades do usuário escolhido.
- [x] Padrões como dashboard, relatório, filtros e CRUD foram analisados como soluções para tarefas, não como requisitos automáticos.
- [x] Opiniões de UX têm fonte.
- [x] A síntese compara critérios comuns e produz recomendações.
- [x] Não há “copiar porque o concorrente faz”; há justificativa de adequação ao público/contexto.
