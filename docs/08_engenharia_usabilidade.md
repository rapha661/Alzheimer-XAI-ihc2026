# Entrega 8 — Ciclo de vida e engenharia de usabilidade

**Data:** 11/11/2026  
**Status:** 🟩 concluída  
**Responsabilidade:** 1 solução por equipe

## Objetivo da atividade

Transformar o conhecimento acumulado sobre usuários, tarefas, plataforma e contexto em princípios e **metas de usabilidade verificáveis**, mantendo o caráter iterativo do projeto.

## Delimitação do sistema interativo

| Camada | O que pertence ao projeto | O que será avaliado em IHC |
|---|---|---|
| contribuição técnica do TCC | Modelo multimodal de IA/ML com MRI e dados clínicos tabulares da ADNI; resultados atuais binários (CN × DA); explicabilidade por Grad-CAM e SHAP. | Acurácia, sensibilidade, especificidade, AUC e validade técnica das explicações permanecem na avaliação científica do TCC. |
| camada de interação da disciplina | Aplicação web de apoio ao fluxo profissional, com envio de dados, visualização da sugestão explicada e registro da decisão. | Compreensão, eficácia, eficiência, satisfação, prevenção de erros, acessibilidade e adequação aos papéis profissionais. |
| integrações/dados simulados | Protótipo sem backend, com API simulada e dados sintéticos; integrações hospitalares completas ainda não definidas. | Serão avaliadas a interação e a compreensão. Não serão comprovadas integração real, segurança de produção, validade clínica ou desempenho diagnóstico. |

### Contribuição técnica do TCC

O modelo multimodal utiliza imagens de ressonância magnética (MRI) e dados clínicos tabulares da ADNI. O TCC prevê três estágios (CN/MCI/AD), mas os resultados atuais são binários (CN × DA), porque a classe MCI ainda não é separada de forma confiável. A explicabilidade combina Grad-CAM sobre um corte axial da MRI e SHAP, que hoje separa a contribuição da imagem e a dos dados clínicos na sugestão.

O desempenho técnico do modelo — por exemplo, acurácia, sensibilidade, especificidade, AUC e validade das explicações — não será substituído por testes de IHC. Esses resultados pertencem à avaliação técnica e científica do TCC.

### Camada de interação da disciplina

O recorte é uma aplicação web de apoio ao fluxo profissional. O protótipo navegável da Entrega 6 já cobre:

- envio de MRI e dados clínicos com validação;
- acompanhamento do processamento e da falha;
- visualização da MRI com o mapa de atenção;
- interpretação da sugestão, da faixa de confiança e dos limites do modelo;
- registro da decisão profissional, sem edição posterior.

A consulta de pareceres anteriores, o encaminhamento ou solicitação de revisão e a conferência de qualidade e completude antes da liberação do paciente são funções propostas, ainda não presentes no protótipo. O foco prioritário permanece no médico clínico P01, sem excluir os fluxos de apoio atribuídos a P02, P03 e P04.

A avaliação em IHC considerará a compreensão da sugestão e de suas limitações; a eficácia na execução das tarefas T01–T04; eficiência, satisfação, prevenção de erros, acessibilidade, clareza dos dados e adequação aos diferentes papéis profissionais. A interface deve apoiar a decisão, não emitir diagnóstico definitivo nem decidir sobre a autonomia do paciente.

### Integrações e dados simulados

O TCC prevê uma aplicação web para intermediar o uso do modelo. Entretanto, a integração completa com prontuário eletrônico (EHR), PACS, RIS e equipamentos de MRI não está definida no escopo de IHC.

O protótipo da disciplina (Entrega 6) funciona sem backend, com uma API simulada que guarda os dados no navegador. Casos, imagens de MRI, dados clínicos, probabilidades, mapas de atenção e pesos por modalidade são sintéticos, e o processamento tem duração fixa. O contrato com a futura API de inferência já está definido no repositório do front-end.

Serão avaliados os passos de interação e a compreensão das informações apresentadas. O protótipo não comprova integração real com sistemas hospitalares, tempo de inferência, segurança operacional, validade clínica ou desempenho diagnóstico do modelo. A simulação deverá estar identificada como tal e não poderá ser confundida com resultado de paciente real.

## 1. Características da plataforma

| Característica | Condição identificada | Consequência para IHC |
|---|---|---|
| Software | Aplicação web; front-end em React e TypeScript, publicado na Vercel; backend de inferência inexistente. | Não pressupor integração automática com PACS ou prontuário; deixar claros os caminhos de entrada e transferência de informações. |
| Hardware/dispositivos | Desktop em consultórios e hospitais; workstations de alta resolução na radiologia; console de MRI no setor de imagem. | Priorizar desktop e legibilidade da MRI, das informações clínicas e do resultado. |
| Capacidades | Receber MRI e dados tabulares; apresentar classe/probabilidades CN × DA, Grad-CAM e SHAP; apoiar registro da decisão; funções de histórico, revisão e conferência ainda propostas. | Separar dados de entrada, resultado, explicações e decisão; adequar linguagem e profundidade ao papel profissional. |
| Restrições | A IA não substitui a avaliação médica; qualidade da sugestão depende da identificação, da MRI e da completude dos dados. Integrações completas e interface para pacientes estão fora do recorte. | Identificar o caso e dados inválidos/ausentes; diferenciar sugestão de decisão profissional; não automatizar decisões sobre autonomia. |
| Conectividade/latência | Rede estável é necessária para arquivos de MRI; arquitetura, largura de banda e limites de latência não definidos. | Informar estados de envio, carregamento e processamento; apresentar mensagens claras de falha, sem prometer tempos não medidos. |
| Segurança/privacidade | MRI e dados clínicos são dados pessoais sensíveis; protótipo utiliza dados sintéticos; segurança de produção não especificada. | Restringir o protótipo a dados fictícios; prever proteção, controle de acesso e minimização para eventual uso real. |
| Volume de dados/histórico | Tamanho dos exames, número de casos, usuários e retenção não medidos; necessidade de histórico ainda vinculada à hipótese H06. | Não dimensionar busca, filtros ou paginação sem dados de volume; priorizar identificação do caso e recuperação do parecer relevante. |
| Tempo de processamento | Tempo real não medido; protótipo simula processamento com duração fixa. | Diferenciar tempo computacional de tempo do usuário; apresentar progresso, estado e falha; não exibir estimativas não medidas. |
| Papéis/permissões | P01 clínico; P02 neurologista; P03 radiologista; P04 técnico em radiologia. H11 mantém em aberto a divisão formal de responsabilidades na aquisição. | Mostrar ações pertinentes a cada papel; não atribuir decisão diagnóstica ao técnico; definir permissões após esclarecimento de H11. |

### Detalhamento das características da plataforma

**Software e ambiente de execução.** A aplicação é acessada por navegador. O front-end do protótipo foi implementado em React e TypeScript e publicado na Vercel; o backend de inferência ainda não existe (o repositório do modelo contém só o código de treino). Navegadores homologados, banco de dados e arquitetura de implantação ainda não foram especificados. O fluxo profissional atual envolve ferramentas como console de MRI, PACS, RIS e prontuário eletrônico. A compatibilidade com navegadores e sistemas operacionais deverá ser definida quando a arquitetura técnica for especificada.

**Hardware e dispositivos.** O contexto prevê computadores desktop em consultórios e hospitais, workstations com monitores de alta resolução, eventualmente duplos, no ambiente de radiologia, além do console do equipamento de MRI e da estação de trabalho no setor de imagem. Não foi estabelecido requisito de uso em celular ou tablet. O protótipo foi conferido em desktop e em largura de 390 px apenas para evitar quebra de layout. No ambiente de radiologia, devem ser considerados monitores de alta resolução e iluminação atenuada; no consultório, tela padrão e interrupções durante o atendimento.

**Capacidades e restrições funcionais.** A plataforma deve receber e apresentar MRI e dados clínicos tabulares, apresentar a classe sugerida e a probabilidade de cada classe retornada pelo modelo (atualmente CN × DA), exibir Grad-CAM e SHAP, e apoiar o registro da decisão e a solicitação de revisão. A conferência de completude e qualidade da imagem é necessária ao fluxo de P04, mas permanece condicionada à investigação de H07. A interface deve separar dados de entrada, resultado do modelo, explicações e decisão profissional. Deve utilizar linguagem clínica para P01, maior profundidade técnica para P02 e P03 e terminologia operacional de aquisição para P04. O score não deve aparecer isolado, e o mapa de atenção ou a contribuição SHAP não devem ser tratados como prova diagnóstica.

O sistema não substitui a avaliação médica nem transforma a classificação do modelo em diagnóstico definitivo. A decisão clínica permanece sob responsabilidade do profissional. A qualidade da sugestão depende da identificação correta do paciente, da qualidade da MRI e da completude dos dados de entrada. A integração completa com EHR/PACS, a configuração administrativa do modelo e uma interface para pacientes/familiares estão fora do recorte atual de IHC. Por isso, a interface deve indicar dados ausentes ou inválidos, diferenciar claramente sugestão do modelo e decisão profissional e não permitir que a saída seja interpretada como autorização automática para restringir autonomia, dirigir ou morar sozinho. Funções administrativas ou destinadas a pacientes não devem ser acrescentadas sem evidência de necessidade.

**Conectividade, volume e processamento.** A rede estável é necessária principalmente pelo tamanho dos arquivos de MRI e pela criticidade do uso, mas arquitetura de rede, largura de banda mínima e limites de latência não foram definidos. Cada caso pode conter arquivos de MRI, dados clínicos tabulares, resultados e explicações; as entregas não informam tamanho médio dos exames, quantidade esperada de casos, volume de usuários ou período de retenção. A consulta de pareceres e informações anteriores aparece como necessidade a investigar em H06, mas não há volume longitudinal medido.

O tempo de execução do modelo e de carregamento das MRI não foi medido nem especificado. No protótipo, o processamento é simulado com duração fixa e não representa o tempo real. A estimativa de 5 a 10 minutos registrada na Entrega 1 refere-se à hipótese da equipe sobre a atividade A03 do médico, e não ao tempo computacional do modelo. A interface deve informar o estado de envio, carregamento e processamento, indicar falhas e permitir compreender como retomar a tarefa. Não se deve estabelecer tempo máximo de resposta nem exibir duração estimada sem medição. A possibilidade de cancelar ou repetir processamento dependerá da implementação técnica.

**Segurança, privacidade e papéis.** MRI, dados clínicos, resultados e registros associados a um paciente podem revelar informações de saúde, classificadas como dados pessoais sensíveis pela LGPD. O protótipo desta disciplina utilizará dados sintéticos. Não há arquitetura de segurança ou política de retenção/armazenamento de produção especificada nas entregas. Para futura utilização com dados reais, serão necessários autenticação, acesso conforme papel, transmissão e armazenamento protegidos, registro de acesso e minimização dos dados exibidos. Devem ser evitados identificadores em capturas de tela, demonstrações e materiais públicos.

Os papéis identificados são: P01 — médico clínico, que interpreta a sugestão e toma a decisão; P02 — neurologista, que aprofunda ou valida casos complexos; P03 — radiologista, que interpreta a MRI e emite o laudo; P04 — técnico em radiologia, que prepara e encaminha o exame e os dados. Pacientes e familiares são stakeholders afetados, mas não usuários diretos nesta fase (H05). A distribuição formal de responsabilidades no fluxo de aquisição ainda é uma lacuna (H11). O protótipo atual usa uma única conta, sem perfis. A matriz definitiva de permissões depende do esclarecimento de H11, a ser investigada pelos instrumentos I03 e I04 da Entrega 7 quando aplicados. O técnico não deve receber atribuição de decisão diagnóstica; a interpretação e a decisão clínica cabem aos profissionais médicos.

## 2. Princípios gerais do projeto

| Princípio/norma | Aplicabilidade ao contexto | Decisão/requisito decorrente | Fonte |
|---|---|---|---|
| Contexto de uso | Quatro perfis profissionais, tarefas distintas, tempo limitado, interrupções e ambientes físicos diferentes. | Priorizar desktop, níveis de detalhe por papel, retomada após interrupções e informação que não dependa apenas de cor ou som. | Entregas 1 e 3; cenários C01–C04 da Entrega 4; `RASTREABILIDADE.md`, seções 1 e 3. |
| LGPD — Lei nº 13.709/2018 | MRI, informações clínicas e resultados vinculados a pacientes podem constituir dados pessoais sensíveis. | Usar dados sintéticos no protótipo; em uso real, definir finalidade/base legal, minimizar dados, controlar acessos, proteger armazenamento/transmissão e definir retenção e descarte. | [Lei nº 13.709/2018 — Presidência da República, arts. 5º, 6º, 11 e 46](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm). |
| Acessibilidade — WCAG 2.1, nível AA | Aplicação web com imagens, mapas de atenção, gráficos e controles interativos. | Contraste suficiente, navegação por teclado, foco visível, rótulos claros e alternativas textuais; não transmitir informação apenas por cor. | [W3C — Web Content Accessibility Guidelines (WCAG) 2.1](https://www.w3.org/TR/WCAG21/). |
| ISO 9241-11:2018 — Usabilidade | Usabilidade depende dos usuários, objetivos e contexto; considera eficácia, eficiência e satisfação. | Definir e medir metas por perfil e tarefa, incluindo conclusão correta, tempo/esforço e satisfação. | [ISO 9241-11:2018 — Ergonomics of human-system interaction — Part 11: Usability: Definitions and concepts](https://www.iso.org/standard/63500.html). |
| ISO 9241-210:2019 — Projeto centrado no ser humano | Personas, tarefas e necessidades ainda contêm hipóteses sujeitas a revisão. | Envolver usuários representativos, avaliar protótipos em diferentes etapas e revisar requisitos conforme os resultados. | [ISO 9241-210:2019 — Human-centred design for interactive systems](https://www.iso.org/standard/77520.html). |
| Apoio à decisão com responsabilidade humana | A interface apresenta uma sugestão explicada; o profissional mantém a decisão clínica. | Identificar a saída como sugestão, apresentar probabilidades, explicações e limites e manter a decisão e sua justificativa sob responsabilidade profissional. | Entrega 1, itens 1.1, 1.3 e 7.3–7.4; `RASTREABILIDADE.md`, seção 3, linha R04. |

### Aplicação dos princípios ao projeto

**Contexto de uso.** P01 atua em consultório de atenção primária ou hospital geral, sem expertise em neuroimagem e com tempo limitado. P02 avalia casos complexos; P03 trabalha com leitura de imagens em workstation, frequentemente em ambiente de iluminação atenuada; P04 atua no setor de imagem, entre console, PACS e informações clínicas. Há possibilidade de interrupções e alternância entre ferramentas. Por isso, a interface deve priorizar desktop, oferecer níveis de detalhe adequados ao papel, utilizar linguagem clínica para P01 e linguagem técnica/operacional para os demais, permitir compreender e retomar o caso após interrupções e não depender exclusivamente de alertas sonoros. As necessidades ainda hipotéticas deverão ser revistas quando os instrumentos da Entrega 7 forem aplicados.

**LGPD.** Dados referentes à saúde são dados pessoais sensíveis (art. 5º, II). O tratamento deve observar as hipóteses legais aplicáveis (art. 11), os princípios de finalidade e necessidade e as medidas de segurança técnicas e administrativas (art. 46). No protótipo, serão utilizados somente dados sintéticos. Em uma implantação com dados reais, será necessário definir finalidade e base legal, limitar a coleta ao mínimo necessário, controlar acesso por papel, proteger transmissão e armazenamento e estabelecer procedimentos de retenção, descarte e resposta a incidentes. A interface não deve expor dados de pacientes em telas ou relatórios desnecessários.

**Acessibilidade.** A WCAG 2.1, nível AA, será utilizada como referência. A visualização de MRI e mapas de atenção contém informação visual relevante; contraste inadequado, dependência exclusiva de cores ou controles inacessíveis por teclado podem impedir a compreensão e a operação. Devem ser garantidos contraste suficiente, navegação por teclado, foco visível, identificação textual dos controles, rótulos claros e alternativa textual para informações relevantes dos gráficos e mapas. Classificação, gravidade ou estado não devem ser transmitidos apenas por cor.

**Usabilidade e projeto centrado no ser humano.** A ISO 9241-11:2018 orienta a definição de metas observáveis para cada tarefa e perfil, medindo conclusão correta, tempo/esforço e satisfação no contexto de uso previsto. Uma interface não será considerada utilizável apenas por ser visualmente agradável ou tecnicamente funcional. A ISO 9241-210:2019 fundamenta a participação de usuários representativos, a avaliação de protótipos em diferentes etapas e a revisão de requisitos quando as avaliações revelarem problemas. O primeiro protótipo não será tratado como solução definitiva.

**Apoio à decisão com responsabilidade humana.** O TCC apresenta uma sugestão explicada do modelo; o objetivo da interface é permitir que o profissional compreenda as evidências e limitações e tome sua própria decisão. A Entrega 1 estabelece explicitamente que o sistema sugere e o médico decide. A saída deve ser identificada como sugestão do modelo, com probabilidades, explicações e limitações, sem linguagem de diagnóstico definitivo. A interface não deve usar a classificação para determinar, sozinha, a autonomia do paciente.

## 3. Metas de usabilidade

As metas abaixo são **valores iniciais de projeto**, definidos antes dos testes. Ainda não representam resultados obtidos. Deverão ser revisadas após a avaliação dos protótipos e confrontadas com os achados da Entrega 7, quando seus instrumentos forem aplicados. A usabilidade será avaliada por perfil e tarefa, e não por uma média única que esconda diferenças entre os profissionais.

### 3.1 Metas qualitativas

| Meta | Para quem/tarefa | Evidência desejada | Justificativa |
|---|---|---|---|
| Compreender a saída da IA como sugestão, não diagnóstico definitivo. | P01/T01 e P02/T04 | O profissional explica o que o modelo sugere e reconhece sua própria responsabilidade pela decisão clínica. | Decisão clínica de alto impacto; evitar confiança excessiva. |
| Compreender a relação entre MRI, dados clínicos, probabilidades e explicações. | P01/T01 e P02/T04 | O profissional explica os elementos apresentados, o destaque do Grad-CAM, a contribuição indicada pelo SHAP e os limites do que pode concluir. | H01 e H03 tratam da compreensão e da calibração da confiança. |
| Recuperar o raciocínio de um parecer anterior. | P01/T01 | O profissional identifica a origem do parecer, as evidências consideradas e o que precisa ser reavaliado. | H06 e C02 apontam perda de contexto na retomada do caso. |
| Receber contexto clínico suficiente para interpretar achados limítrofes. | P03/T02 | O radiologista identifica a pergunta clínica e os dados disponíveis, diferencia achados de sugestões automatizadas e comunica limitações. | H08 investiga a relação entre falta de contexto e conclusões genéricas. |
| Conferir qualidade e completude sem assumir decisões de outro profissional. | P04/T03 | O técnico identifica dados ausentes e problemas de aquisição e sabe quando solicitar orientação. | H07 e H09–H14 ainda precisam ser verificadas; o fluxo deve respeitar responsabilidades do serviço. |
| Comparar evidências conflitantes sem delegar ao score a decisão sobre autonomia. | P02/T04 | O neurologista explica como pondera relato familiar, testes, MRI e limites do modelo e justifica a conduta. | C04 envolve segurança e autonomia; o modelo não avalia sozinho aptidão para dirigir ou morar sem supervisão. |
| Manter legibilidade e continuidade diante de interrupções e contextos físicos diferentes. | P01–P04, nas tarefas correspondentes | O profissional localiza a etapa em que estava, retoma o caso e identifica informações importantes sem depender apenas de cores, sons ou memória. | A Entrega 1 descreve interrupções, uso em desktop e ambientes de radiologia com iluminação atenuada. |

### 3.2 Metas quantitativas

| ID | Dimensão | Métrica | Tarefa/população | Critério de aceitação |
|---|---|---|---|---|
| MU01 | eficácia | Conclusão correta sem ajuda | T01–T04; participantes correspondentes a P01–P04 | ≥ 80% concluem a tarefa atribuída sem orientação e atendem aos critérios essenciais. |
| MU02 | prevenção de erros | Número de erros críticos | T01–T04 | 0 erros críticos durante os testes. |
| MU03 | eficiência | Tempo mediano para interpretar a sugestão e registrar a avaliação | A03 de P01 | ≤ 10 minutos por caso, como limite inicial. |
| MU04 | satisfação | Avaliação pós-tarefa em escala de 1 a 5 | T01–T04, por perfil | Mediana ≥ 4 em cada item avaliado. |
| MU05 | compreensão | Identificação correta do caráter de apoio da IA | P01, interpretação da sugestão | 100% identificam que a saída é uma sugestão, não diagnóstico definitivo. |
| MU06 | compreensão | Interpretação correta dos elementos centrais da explicação | P01, probabilidade, Grad-CAM e SHAP | ≥ 80% interpretam corretamente pelo menos dois dos três elementos avaliados. |

#### Critérios de medição das metas quantitativas

**MU01 — eficácia: conclusão correta sem ajuda.**

- **Como medir:** teste observado, checklist de sucesso por tarefa e registro de pedidos de ajuda.
- **Critério de sucesso:** o participante conclui a tarefa atribuída sem orientação do moderador e atende aos critérios essenciais definidos antes do teste.
- **Tratamento dos resultados:** apresentar numerador e denominador por perfil. Com a amostra prevista na Entrega 14, igual ao número de integrantes, o resultado será uma contagem como 3/4, sem generalização. Participantes proxy devem ser identificados separadamente.
- **Justificativa:** verificar se cada profissional consegue alcançar seu objetivo, sem esconder diferenças entre tarefas e perfis.

**MU02 — prevenção de erros críticos.**

- **Como medir:** observação direta, registro de erros e perguntas de verificação após a tarefa. Os erros críticos e não críticos deverão ser classificados previamente.
- **Critério de sucesso:** nenhum erro crítico durante os testes.
- **Erros considerados críticos:** associar informação ao paciente/caso errado; concluir ou encaminhar um caso com dado obrigatório ausente sem perceber; interpretar a sugestão do modelo como diagnóstico definitivo; ou atribuir ao modelo a decisão sobre autonomia do paciente.
- **Justificativa:** a Entrega 1 identifica consequências graves de falsos positivos, falsos negativos, documentação insuficiente e explicação incompreensível.

**MU03 — eficiência: tempo mediano de execução.**

- **Como medir:** cronometrar do momento em que os dados e o resultado estão disponíveis até o profissional concluir a interpretação e registrar sua avaliação. Registrar também erros e pedidos de ajuda.
- **Critério de sucesso:** até 10 minutos por caso, como limite inicial para o teste.
- **Justificativa:** a Entrega 1 apresenta estimativa da equipe de 5 a 10 minutos por caso para A03. Essa estimativa não foi medida e o limite de 10 minutos deverá ser revisto após o primeiro teste. Ela se refere à atividade do médico, não ao tempo computacional do modelo.

**MU04 — satisfação: avaliação pós-tarefa.**

- **Como medir:** questionário breve após cada tarefa, com itens de clareza das informações, facilidade para concluir e satisfação geral.
- **Critério de sucesso:** mediana igual ou superior a 4 em cada item, por perfil/tarefa avaliado.
- **Tratamento dos resultados:** apresentar distribuição e mediana por item, sem média aritmética (a escala é ordinal) e sem misturar perfis diferentes.
- **Justificativa:** verificar se a interação atende às expectativas do profissional, além de apenas concluir a tarefa. A escala é um instrumento do projeto, não uma aplicação de escala padronizada validada.

**MU05 — compreensão do papel de apoio da IA.**

- **Como medir:** ao final da tarefa, perguntar o que o resultado permite concluir, quem toma a decisão clínica e quais limites precisam ser considerados.
- **Critério de sucesso:** todos os participantes P01 identificam que a saída é uma sugestão de apoio, e não um diagnóstico definitivo.
- **Tratamento dos resultados:** resposta incompatível com o papel de apoio será registrada como falha crítica.
- **Justificativa:** a responsabilidade clínica permanece com o médico; a interface não pode induzir a delegação da decisão ao modelo.

**MU06 — compreensão dos elementos centrais da explicação.**

- **Como medir:** três perguntas de compreensão, com gabarito definido antes do teste e justificativa verbal registrada. Não considerar acerto a repetição de rótulos sem explicação coerente.
- **Critério de sucesso:** pelo menos 80% dos participantes P01 interpretam corretamente dois ou mais dos três elementos: (1) probabilidade/classe sugerida com a faixa de confiança; (2) área destacada pelo Grad-CAM no corte axial; (3) peso da imagem e dos dados clínicos apresentado por SHAP.
- **Justificativa:** H01 e H03 investigam se as explicações e o score são compreensíveis para o médico clínico sem expertise em neuroimagem.

### 3.3 Priorização das metas (se exigida na disciplina)

Os materiais de aula disponibilizados definem a especificação de metas qualitativas e quantitativas, mas não estabelecem a atribuição de pesos percentuais que somem 100%. Como o enunciado condiciona esta subseção à exigência da disciplina, não foram atribuídos pesos arbitrários nesta versão. A prioridade de avaliação permanece concentrada na compreensão segura da sugestão, na conclusão correta das tarefas e na prevenção de erros críticos.

## 4. Como o ciclo será iterado

O projeto seguirá a lógica iterativa da Engenharia de Usabilidade de Mayhew apresentada em aula. As metas desta entrega serão utilizadas como critérios de avaliação e poderão ser revistas quando os testes revelarem problemas ou quando as coletas indicarem que uma persona, tarefa ou necessidade foi descrita incorretamente.

1. **Revisão da análise de requisitos.** Retomar personas P01–P04, tarefas T01–T04, cenários C01–C04 e hipóteses da `RASTREABILIDADE.md`. Incorporar os resultados da Entrega 7 quando seus instrumentos forem aplicados, distinguindo evidências obtidas, limitações da amostra e hipóteses ainda abertas. Se uma hipótese for refutada, revisar a tarefa e o requisito correspondente antes de avançar no desenho.
2. **Nível 1 — projeto essencial.** Rever a distribuição do trabalho entre profissionais e sistema; estabelecer o modelo conceitual, os componentes essenciais e a navegação necessária às tarefas. Partir do protótipo navegável da Entrega 6, que foi construído antes do modelo conceitual (Entregas 9 e 10), e revisá-lo onde esses modelos apontarem falhas; realizar avaliações interativas com representantes dos usuários, verificando se as principais dificuldades foram eliminadas.
3. **Nível 2 — padrões de telas e diálogos.** Definir padrões para controles, localização, terminologia, cores, tipografia, mensagens e estados de interação. Construir protótipos dos padrões de tela e avaliá-los com tarefas representativas. Comparar os resultados com as metas MU01–MU06, revisar os padrões que não forem compreendidos ou utilizados corretamente e registrar as decisões aprovadas no guia de estilo do projeto.
4. **Nível 3 — projeto detalhado.** Completar janelas, diálogos, mensagens, caminhos entre telas e conteúdos secundários. Realizar avaliações mais próximas do uso previsto, medindo eficácia, erros, satisfação e tempos de tarefa. Verificar especialmente se a explicação da IA continua compreensível quando integrada ao fluxo completo.
5. **Retorno e refinamento.** Quando uma meta não for atingida, retornar ao nível de projeto pertinente, alterar o modelo conceitual, o padrão de tela ou o detalhe responsável pelo problema e repetir a avaliação. Não considerar a etapa concluída apenas porque todas as telas foram implementadas.
6. **Verificação nas Entregas 12–14.** Utilizar as tarefas T01–T04 e os critérios definidos nesta entrega nos testes previstos. Registrar participantes, perfil, ambiente, resultados, erros, tempos, satisfação e limitações. Atualizar a `RASTREABILIDADE.md` com os problemas encontrados e as decisões de melhoria.

O ciclo não será tratado como uma sequência rígida de etapas sem retorno. Conforme o modelo apresentado por Mayhew, a avaliação poderá levar à revisão do projeto conceitual, dos padrões de tela ou do projeto detalhado, até que as metas de usabilidade sejam atingidas. Para este projeto acadêmico, a instalação em ambiente clínico real não será presumida nem declarada como realizada.

## Checklist

- [x] Capacidades e restrições têm impacto de IHC explicitado.
- [x] Está claro o limite entre contribuição técnica do TCC e camada interativa da disciplina.
- [x] Resultados/processamento simulados no protótipo foram explicitados.
- [x] Metas de usabilidade avaliam a interação, não substituem métricas técnicas do TCC.
- [x] Normas/princípios estão contextualizados, não apenas copiados.
- [x] Metas quantitativas são mensuráveis e associadas a tarefas/público.
- [x] Eficácia, eficiência e satisfação são consideradas quando pertinentes.
- [x] Metas poderão ser verificadas nas Entregas 12–14.
