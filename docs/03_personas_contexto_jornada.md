# Entrega 3 — Personas, mapa de empatia, contexto de uso e jornada

- **Data:** 09/09/2026
- **Status:** 🟨 em andamento
- **Responsabilidade:** 1 persona por integrante; 1 mapa de empatia, 1 contexto de uso consolidado e 1 jornada por equipe.

## Objetivo da atividade

Representar grupos de usuários de forma útil para decisões de design. Persona não é personagem decorativo: suas características devem alterar requisitos, prioridades, linguagem, fluxos ou critérios de avaliação.

## Atenção a projetos técnicos

Em TCCs sem interface original, a persona pode representar um **profissional que se apropria da contribuição técnica**: DBA, analista, cientista de dados, administrador, pesquisador, técnico, operador, gestor ou especialista de domínio.

Não escolha um perfil apenas porque “parece combinar” com a tecnologia. Explique **qual objetivo esse perfil teria e qual parte da contribuição do TCC produziria valor para ele**. Se ainda for hipótese, mantenha como hipótese/proto-persona a validar.

Também considere papéis diferentes quando houver tarefas distintas, por exemplo:

- operador que executa análises;
- administrador que configura e gerencia permissões;
- especialista que interpreta resultados;
- gestor que consulta relatórios e decide;
- auditor que revisa histórico.

## Entradas da Entrega 1

Antes de criar personas, retome os tipos de usuários, características relevantes, objetivos e hipóteses registradas na Entrega 1. A persona **não deve transformar uma hipótese inicial em fato por meio de uma história fictícia**.

| Item da Entrega 1 | Status inicial | Evidência disponível agora | Como será tratado nesta entrega |
|---|---|---|---|
| Médico Clínico como perfil priorizado (item 7.2) | [F] | Entrega 1, itens 2.2, 2.4, 7.2 | incorporar como P01 (persona primária) |
| Objetivo priorizado: diagnosticar com confiança e rapidez (item 7.3) | [F] | Entrega 1, item 7.3 | incorporar como objetivo central de P01 e da jornada |
| H03 — médico entende score de confiança sem treinamento extenso | [H] aberta | Rastreabilidade; reforçada indiretamente pelo estudo Al-bakri et al. 2025 (Entrega 2, C02) — 80% dos médicos relataram confiança apenas "condicional" | mantida como hipótese; incorporada como dor/necessidade de P01, não tratada como fato |
| Neurologista, Radiologista, Técnico de Laboratório, Pesquisador (item 2.2) | [F] | Entrega 1, item 2.2 | manter como personas secundárias (P02, P03, P04) — a preencher pelos demais integrantes |
| Caso Maria Silva (item 4.5) | [F] (narrativa ilustrativa) | Entrega 1, item 4.5 | usada como evidência da dor "discordância entre pareceres", não convertida em fato genérico |
| Contexto de uso (item 5.1–5.6) | [F]/[H] | Entrega 1, seção 5 | incorporado na consolidação da seção 3 abaixo |

## 1. Personas

### Persona P01 — Dr. Marcos Andrade

- **Autor(a):** Paulo Hudson — 22.222.013-9
- **Tipo:** primária
- **Base de evidências:** combinação de Entrega 1 (itens 2.2, 2.4, 4.5, 5.x, 7.2, 7.3) com literatura citada na Entrega 2 (Al-bakri et al., 2025)
- **Hipóteses da Entrega 1 relacionadas:** H03 (confiança sem treinamento extenso)

![Persona P01](../assets/03_personas/persona_p01..svg)

| Campo | Descrição |
|---|---|
| Faixa etária / contexto relevante | 30–45 anos; clínico em início/meio de carreira, ainda sem grande volume de casos complexos de AD |
| Ocupação/papel | Médico clínico / generalista, atuando em atenção primária ou hospital geral |
| Conhecimento do domínio | Médio — conhece critérios clínicos de Alzheimer (MMSE, MoCA, história clínica), mas não tem formação para interpretar MRI tecnicamente |
| Experiência tecnológica | Média — usa prontuário eletrônico e sistemas clínicos padrão no dia a dia; não é usuário avançado de ferramentas técnicas |
| Objetivos | Diagnosticar Alzheimer com confiança e rapidez, sem depender de um especialista que pode levar meses para atender |
| Necessidades | Explicação clara combinando imagem e dados clínicos; score de confiança compreensível; forma simples de documentar a decisão; caminho fácil para encaminhar a um especialista quando necessário |
| Dores/frustrações | Fila de espera longa por especialista; discordância entre pareceres (radiologista vs. neurologista); falta de justificativa técnica no relatório de imagem; medo de errar o diagnóstico |
| Motivadores | Cuidar bem do paciente; evitar erro que prejudique alguém (como no caso Maria Silva); ter respaldo documental em caso de questionamento |
| Restrições/acessibilidade | Tempo curto por consulta; iluminação de consultório nem sempre ideal; possível uso de estação de trabalho compartilhada |
| Ambiente típico de uso | Consultório de atenção primária ou hospital geral; computador desktop padrão, integrado ao prontuário eletrônico |
| Comportamentos relevantes | Consulta MMSE/MoCA como parte da rotina; liga para colega quando tem dúvida; documenta a decisão no prontuário; pode encaminhar a um especialista em casos incertos |

**Decisões de design influenciadas por P01:**

- Explicação deve ser traduzida para linguagem clínica — nunca expor apenas termos técnicos de ML (Grad-CAM, SHAP) sem contexto.
- O score de confiança nunca deve aparecer isolado — precisa vir acompanhado de explicação textual/visual, já que a literatura (Al-bakri et al., 2025) mostra confiança "condicional" mesmo com explicação combinada.
- A ação de encaminhar a um especialista deve estar sempre visível na interface, não escondida em um submenu — é a válvula de escape para os casos em que H03 se confirmar (médico não entende o suficiente para decidir sozinho).
- O fluxo de documentação da decisão deve aproveitar o que já foi mostrado na explicação (não pedir que o médico redigite tudo do zero), para não virar um obstáculo que ele acaba pulando.

### Persona P02 — Dr. César Andrade de Melo

- **Autor(a):** Ana Carolina Lazzuri
- **Tipo:** secundária
- **Base de evidências:** Entrega 1 (itens 2.2, 2.4, 4.5, 5.x) e análise de concorrência da Entrega 2 (OHIF Viewer e BrainSee)
- **Hipóteses da Entrega 1 relacionadas:** H03 (validação de casos complexos ou divergentes com explicação aprofundada)


| Campo | Descrição |
|---|---|
| **Faixa etária / contexto** | 45–60 anos; neurologista especialista em demências. |
| **Ocupação/papel** | Neurologista em centro de referência ou hospital universitário. |
| **Conhecimento do domínio** | Alto — domínio total de neuroimagem (MRI) e testes cognitivos. |
| **Experiência tecnológica** | Média-Alta — usa PACS e visualizadores DICOM; cético a IAs "caixa-preta". |
| **Objetivos** | Confirmar a suspeita em casos difíceis e resolver dúvidas entre médicos. |
| **Necessidades** | Visualizar destaques anatômicos (Grad-CAM), pesos dos dados (SHAP) e exportar laudo. |
| **Dores/frustrações** | Receber diagnósticos prévios inconsistentes e ter que reavaliar a MRI do zero. |
| **Motivadores** | Garantir a precisão diagnóstica precoce e ter respaldo técnico para a decisão. |
| **Restrições/acessibilidade** | Alta carga de casos por turno; necessita de navegação ágil por atalhos. |
| **Ambiente típico de uso** | Consultório especializado; desktop com tela de alta resolução integrada ao PACS. |
| **Comportamentos** | Analisa cortes da MRI, cruza com testes cognitivos e emite o parecer final. |

**Decisões de design influenciadas por P02:**

- **Controle de transparência no heatmap:** Permitir ajustar a opacidade do Grad-CAM (0% a 100%) para inspecionar o cérebro original.
- **Exibição multimodal detalhada:** Exibir gráficos explicativos dos atributos clínicos (SHAP) além do score de risco.
- **Navegação rápida por cortes:** Manter o scroll do mouse e ajustes de contraste padrão do fluxo de radiologia.
- **Laudo de auditoria:** Permitir a geração de relatório em PDF com as explicações da IA para anexar ao prontuário.

### Persona P03 — Regina Albuquerque Marins

- **Autor(a):** Raphael Garavati Erbert
- **Tipo:** secundária (stakeholder, não usuária direta da tela de diagnóstico)
- **Base de evidências:** Entrega 1 (item 2.3 — caracterização como stakeholder realocado; item 9.1 — benefício "reduzir divergência de interpretação" tem impacto institucional)
- **Hipóteses da Entrega 1 relacionadas:** **H04** — Gestores aprovariam a adoção se houver ganho comprovado

![Persona P03](../assets/03_personas/persona_03.png)

| Campo | Descrição |
|---|---|
| Faixa etária / contexto relevante | 45–58 anos; gestora com formação médica ou em administração hospitalar, atuando há anos em cargo de gestão |
| Ocupação/papel | Diretora clínica ou gestora hospitalar responsável por decisões de adoção de novas ferramentas/tecnologias no serviço |
| Conhecimento do domínio | Alto sobre gestão clínica, indicadores de qualidade e processos hospitalares; médio-baixo sobre detalhes técnicos de IA/XAI — precisa que o ganho seja traduzido em métricas de gestão (tempo, custo, risco), não em termos de ML |
| Experiência tecnológica | Média — usa dashboards de BI e sistemas de gestão hospitalar; não opera a ferramenta clínica diretamente |
| Objetivos | Decidir, com base em evidência agregada, se a ferramenta deve ser adotada, expandida ou descontinuada no serviço |
| Necessidades | Relatório agregado (não caso a caso) com indicadores objetivos: tempo médio de diagnóstico antes/depois, taxa de concordância entre médicos, volume de casos processados, incidentes/erros registrados |
| Dores/frustrações | Falta de evidência quantitativa para justificar investimento perante a diretoria; risco de adotar ferramenta que gere passivo legal (item 5.6 — falso negativo/positivo); dificuldade de comparar ganho real vs. custo de implementação |
| Motivadores | Reduzir fila de espera e custo com diagnóstico especializado (item 1.4 — benefício para organizações); evitar risco legal associado a "caixa-preta" clínica; melhorar indicadores de qualidade do serviço |
| Restrições/acessibilidade | Pouco tempo dedicado a analisar ferramenta caso a caso; decisão tomada em reuniões periódicas de gestão, não no fluxo clínico do dia a dia |
| Ambiente típico de uso | Escritório administrativo do hospital (citado no item 5.1); acesso a dashboard de BI, não à tela de diagnóstico |
| Comportamentos relevantes | Revisa relatórios agregados periodicamente; compara indicadores antes/depois da adoção; discute com equipe clínica e compliance antes de decidir |

**Decisões de design influenciadas por P03:**

- É preciso existir uma camada de relatório agregado/institucional (dashboard com métricas de uso, não só o laudo por paciente) — algo que nenhuma tela pensada até agora (focada no médico clínico) cobre, e que fica fora do escopo de IHC da disciplina (item "Delimitação: fora do escopo — auditoria em nível de sistema"), mas deve ser registrado como necessidade real de P03 para eventual trabalho futuro.
- Os indicadores expostos a Regina devem ser de gestão (tempo, custo, concordância, incidentes), nunca métricas técnicas de ML (AUC, F1-score) — reforça a distinção de linguagem técnica por perfil já mapeada no item 2.4.
- A trilha de auditoria (item 5.5, já prevista para o médico) deve ser agregável em relatório de gestão, evitando duplicar esforço de registro — o log criado para rastreabilidade médica é a mesma fonte de dado que sustenta a decisão de adoção de P03.
- Reforça, por contraste, por que o **recorte de IHC da disciplina exclui esse perfil da interface principal** (item "Fora do escopo de IHC": auditoria em nível de sistema) — P03 existe para deixar isso explícito e justificado, não para virar tela nova.

### Persona P04 — Otávio Rezende Prado (persona negativa)
 
- **Autor(a):** Nathan Gabriel da Fonseca Leite - 221230287
- **Tipo:** negativa
- **Base de evidências:** Entrega 1 (item 1.4 — "redução de custos com diagnósticos especializados"; item 2.3 — gestor hospitalar como stakeholder sem uso da tela de diagnóstico; item 5.4 — responsabilidade legal é do médico; item 5.6 — consequências de falso negativo/positivo; item 9.3 — LGPD e "sugestão, não diagnóstico"); Entrega 2 (BrainSee — preço de tabela como barreira de adoção)
- **Hipóteses relacionadas:** H04 (adoção por gestores); **H06 (nova)** — há pressão institucional para usar a ferramenta como substituta do especialista, e não como apoio à decisão

![Persona 04](../assets/03_personas/persona_04.png)
  
**Otávio Rezende Prado, diretor financeiro — "se a IA já diz o resultado, por que pagar o especialista?"**
 
Otávio tem 52 anos e é diretor financeiro de um hospital geral privado há seis anos. Formado em Ciências Contábeis, com MBA em gestão de saúde, ele acompanha diariamente planilhas de custo por procedimento, glosas de convênios e tempo de ocupação de agenda. Ele não tem formação clínica e vê a IA como uma forma de "fazer mais com menos": sua expectativa é que, uma vez adotado o sistema, o hospital possa reduzir os encaminhamentos ao neurologista, cortar pedidos de ressonância "desnecessários" e medir quais médicos são mais produtivos. Ele gostaria de ter acesso à tela de cada caso para cruzar o resultado da IA com o faturamento do paciente e com a negociação junto às operadoras de saúde. Para ele, o score de confiança é um número que deveria bastar para encerrar o caso.
 
| Campo | Descrição |
|---|---|
| Faixa etária / contexto relevante | 48–60 anos; executivo da área financeira, sem formação clínica |
| Ocupação/papel | Diretor financeiro (CFO) do hospital; participa da decisão de compra, mas **não** é quem decide sobre conduta clínica |
| Conhecimento do domínio | Baixo em Alzheimer, neuroimagem e XAI; alto em custos, faturamento, contratos com operadoras e indicadores financeiros |
| Experiência tecnológica | Média-alta em ERP, BI e planilhas; nenhuma em sistemas clínicos de apoio à decisão |
| Objetivos pessoais | Mostrar à diretoria redução de custo e aumento de produtividade no curto prazo |
| Objetivos (que a interface **não** atenderá) | Usar o resultado da IA para dispensar o parecer do especialista; restringir encaminhamentos e exames com base no score; ranquear médicos por "casos fechados"; acessar dados de pacientes individuais para faturamento e negociação com operadoras |
| Necessidades declaradas | Número único e "definitivo" por paciente; painel de produtividade por médico; exportação livre de dados por paciente; bloqueio automático de encaminhamento quando o score é alto |
| Dores/frustrações | Custo alto de especialistas e de ressonância; fila longa que ocupa agenda sem gerar receita proporcional; ferramentas cujo retorno sobre investimento não aparece rápido (ex.: preço de tabela do BrainSee, Entrega 2) |
| Motivadores | Metas de margem e redução de despesas; pressão da diretoria e dos convênios |
| Relacionamentos | Responde à diretoria executiva; negocia com operadoras de saúde; costuma entrar em conflito com a diretora clínica (P03) e com o corpo médico (P01, P02) sobre autonomia clínica |
| Expectativas sobre o produto | Acredita que a IA "dá o diagnóstico" e que o médico só precisa confirmar — expectativa **incompatível** com o item 9.3 da Entrega 1 (responsabilidade legal é do médico; a interface deve mostrar "sugestão", não "diagnóstico") |
| Ambiente típico | Escritório administrativo; reuniões de diretoria; acesso a ERP e BI, não ao consultório |
| Comportamentos relevantes | Pede relatórios por profissional; propõe metas de volume; questiona pedidos de exame e encaminhamentos que "não se pagam" |

**Decisões de design influenciadas por P04**
 
- A ação "Encaminhar a especialista" (F07) nunca será bloqueada, ocultada ou condicionada ao valor do score de confiança.
- O resultado continuará sendo apresentado como **sugestão** acompanhada de explicação (F02–F04); a interface não terá um modo "somente score" nem encerrará o caso automaticamente.
- Não haverá ranking, meta ou painel de produtividade por médico dentro do sistema clínico, para não induzir pressa na atividade mais crítica (A03).
- Nenhuma informação de custo, faturamento ou convênio aparecerá durante a interpretação e o registro da decisão, para não enviesar a conduta clínica.
- O controle de acesso por perfil (item 8 da Entrega 1 — usuários/perfis/permissões) não dará à área financeira acesso a casos, imagens ou explicações individuais; relatórios institucionais, se existirem no futuro, serão agregados e anonimizados.
- A exportação de dados por paciente ficará restrita ao laudo clínico destinado ao prontuário (necessidade de P02), sem exportação livre em massa.

### Síntese das personas

Explique diferenças entre os perfis e qual persona é prioritária. Evite personas duplicadas que só mudam nome/foto.

## 2. Mapa de empatia — equipe

**Persona escolhida:** {{P01}}  
**Justificativa:** {{por que esse perfil é relevante}}

![Mapa de empatia](../assets/03_personas/mapa_empatia.svg)

Documente também em texto: o que vê; ouve; diz/faz; pensa/sente; dores; ganhos. Diferencie **evidência** de **hipótese**.

## 3. Contexto de uso — consolidação

| Dimensão | Descrição | Implicação de design |
|---|---|---|
| Usuários | {{...}} | {{...}} |
| Tarefas | {{...}} | {{...}} |
| Equipamentos | {{...}} | {{...}} |
| Ambiente físico | {{...}} | {{...}} |
| Ambiente social/organizacional | {{...}} | {{...}} |
| Papéis/permissões/governança | {{...}} | {{...}} |
| Volume de dados/histórico | {{...}} | {{...}} |

## 4. Jornada do usuário — equipe

**Persona:** {{P01}}  
**Objetivo da jornada:** {{...}}  
**Início e fim da jornada:** {{...}}

| Etapa | Situação/ação | Objetivo | Pensamento/emoção | Dor | Oportunidade de design | Evidência |
|---|---|---|---|---|---|---|
| 1 | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |

> A jornada pode incluir etapas **antes, durante e depois** do uso do produto. Não transforme a jornada em lista de telas.

## Síntese

Quais necessidades e objetivos devem obrigatoriamente aparecer nos cenários e nas tarefas seguintes?

## Checklist

- [ ] Existe pelo menos uma persona por integrante.
- [ ] As personas não são apenas diferenças demográficas superficiais.
- [ ] Está claro o que é dado real e o que é hipótese/proto-persona.
- [ ] A persona não “validou por ficção” uma hipótese da Entrega 1; afirmações continuam marcadas como hipótese quando não há evidência.
- [ ] Objetivos e dores têm consequência para o design.
- [ ] Contexto de uso está coerente com a Entrega 1.
- [ ] Em TCC sem interface original, a persona possui relação explícita com a contribuição técnica.
- [ ] Papéis administrativos, técnicos e decisórios só foram criados quando possuem objetivos/tarefas diferentes.
- [ ] Jornada possui etapas, dores e oportunidades e não é apenas wireflow.
- [ ] IDs das personas foram adicionados à rastreabilidade.
