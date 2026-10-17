# Entrega 3 — Personas, mapa de empatia, contexto de uso e jornada

- **Data:** 09/09/2026
- **Status:** 🟩 Concluído
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

O elenco tem **três personas primárias (P01, P02, P04)** e **uma persona secundária (P03)**, todas usuárias da solução estudada. P02 é primária porque participa diretamente do fluxo principal (validação/escalonamento de casos), com tarefas e decisões de design próprias. P03, a radiologista, é secundária: consulta a mesma visualização de imagem + explicação pensada para P01 e P02, sem exigir um fluxo próprio, mas é quem produz o laudo que os dois leem.

### Persona P01 — Dr. Marcos Andrade

- **Autor(a):** Paulo Hudson — 22.222.013-9
- **Tipo:** primária
- **Base de evidências:** combinação de Entrega 1 (itens 2.2, 2.4, 4.5, 5.x, 7.2, 7.3) com literatura citada na Entrega 2 (Al-bakri et al., 2025)
- **Hipóteses da Entrega 1 relacionadas:** H03 (confiança sem treinamento extenso)

![Persona P01](https://github.com/rapha661/Alzheimer-XAI-ihc2026/blob/main/assets/03_personas/persona_p01_v2.svg)

| Campo | Descrição |
|---|---|
| Faixa etária / contexto relevante | [H] 30–45 anos; clínico em início/meio de carreira, ainda sem grande volume de casos complexos de AD |
| Ocupação/papel | [F] Médico clínico / generalista, atuando em atenção primária ou hospital geral (Entrega 1, item 7.2) |
| Conhecimento do domínio | [F]/[H] Médio — conhece critérios clínicos de Alzheimer (MMSE, MoCA, história clínica), mas não tem formação para interpretar MRI tecnicamente |
| Experiência tecnológica | [H] Média — usa prontuário eletrônico e sistemas clínicos padrão no dia a dia; não é usuário avançado de ferramentas técnicas |
| Objetivos | [F] Compreender a sugestão da IA e decidir com confiança proporcional à evidência, sem depender de um especialista que pode levar meses para atender (Entrega 1, item 7.3) |
| Necessidades | [H] Explicação clara combinando imagem e dados clínicos; score de confiança compreensível; forma simples de documentar a decisão; caminho fácil para encaminhar a um especialista quando necessário |
| Dores/frustrações | [H] Fila de espera longa por especialista; discordância entre pareceres (radiologista vs. neurologista); falta de justificativa técnica no relatório de imagem; medo de errar o diagnóstico |
| Motivadores | [H] Cuidar bem do paciente; evitar erro que prejudique alguém (como no caso Maria Silva); ter respaldo documental em caso de questionamento |
| Restrições/acessibilidade | [F]/[H] Tempo curto por consulta; iluminação de consultório nem sempre ideal; possível uso de estação de trabalho compartilhada |
| Ambiente típico de uso | [F] Consultório de atenção primária ou hospital geral; computador desktop padrão, integrado ao prontuário eletrônico |
| Comportamentos relevantes | [H] Aplica MMSE/MoCA como parte da rotina; pode pedir opinião informal a um colega quando tem dúvida; documenta a decisão no prontuário; pode encaminhar a um especialista em casos incertos |

**Decisões de design influenciadas por P01:**

- Explicação deve ser traduzida para linguagem clínica — nunca expor apenas termos técnicos de ML (Grad-CAM, SHAP) sem contexto.
- O score de confiança nunca deve aparecer isolado — precisa vir acompanhado de explicação textual/visual, já que a literatura (Al-bakri et al., 2025) mostra confiança "condicional" mesmo com explicação combinada.
- [H] O caminho para encaminhar a um especialista deve permanecer acessível durante a decisão — é a válvula de escape para os casos em que H03 se confirmar (médico não entende o suficiente para decidir sozinho). A forma exata (sempre visível, em quantos cliques) ainda é hipótese de design.
- [H] O fluxo de documentação da decisão deve aproveitar o que já foi mostrado na explicação (não pedir que o médico redigite tudo do zero), para não virar um obstáculo que ele acaba pulando.

### Persona P02 — Dr. César Andrade de Melo

- **Autor(a):** Ana Carolina Lazzuri
- **Tipo:** **primária** — participa diretamente do fluxo principal de interação, nos casos em que P01 encaminha/escalona (ver Jornada, etapa 9, e Entrega 4, C02)
- **Base de evidências:** Entrega 1 (itens 2.2, 2.4, 4.5, 5.x) e análise de concorrência da Entrega 2 (OHIF Viewer e BrainSee)
- **Hipóteses da Entrega 1 relacionadas:** H03 (validação de casos complexos ou divergentes com explicação aprofundada)

![Persona P02](https://github.com/rapha661/Alzheimer-XAI-ihc2026/blob/main/assets/03_personas/persona_p02_v2.svg)

| Campo | Descrição |
|---|---|
| **Faixa etária / contexto** | [H] 45–60 anos; neurologista especialista em demências — faixa etária hipotética, não verificada. |
| **Ocupação/papel** | [F] Neurologista em centro de referência ou hospital universitário — papel já listado na Entrega 1 (item 2.2). |
| **Conhecimento do domínio** | [H] Alto conhecimento de neuroimagem (MRI) e testes cognitivos, dentro de suas especializações — mesmo especialistas experientes têm limites; o conhecimento relevante para a tarefa ainda precisa ser detalhado por investigação. |
| **Experiência tecnológica** | [H] Média-Alta — usa PACS e visualizadores DICOM; ceticismo a IAs "caixa-preta" é hipótese de atitude, não medida. |
| **Objetivos** | [H] Avaliar casos incertos e dar a palavra final quando há opiniões diferentes. |
| **Necessidades** | [H] Visualizar destaques anatômicos (Grad-CAM), pesos dos dados (SHAP) e exportar laudo. |
| **Dores/frustrações** | [H] Receber diagnósticos prévios inconsistentes e ter que reavaliar a MRI do zero. |
| **Motivadores** | [H] Garantir a precisão diagnóstica precoce e ter respaldo técnico para a decisão. |
| **Restrições/acessibilidade** | [H] Alta carga de casos por turno — hipótese, não medida. Uma navegação ágil por atalhos pode ajudar, mas isso é inferência da equipe, não uma necessidade confirmada ainda. |
| **Ambiente típico de uso** | [F]/[H] Consultório especializado; desktop com tela de alta resolução integrada ao PACS — plausível por analogia ao contexto já registrado em 5.2 da Entrega 1. |
| **Comportamentos** | [H] Analisa cortes da MRI, cruza com testes cognitivos e emite o parecer final. |

---

**Decisões de design influenciadas por P02 (todas como hipóteses de design a validar, não decisões fechadas):**

- **[H] Controle de transparência no heatmap:** permitir ajustar a opacidade do Grad-CAM (0% a 100%) para inspecionar o cérebro original. **Nota:** esta ideia nasceu da observação do OHIF Viewer na Entrega 2 (concorrente), não de uma necessidade de P02 comprovada por investigação — "o concorrente usa" não significa "P02 precisa"; permanece como candidato a testar.
- **[H] Exibição multimodal detalhada:** exibir gráficos explicativos dos atributos clínicos (SHAP) além do score de risco, como camada adicional de detalhe para quem tem mais conhecimento técnico.
- **[H] Navegação por cortes:** considerar scroll do mouse e ajustes de contraste como no fluxo de radiologia (também herdado do OHIF/Entrega 2) — resta verificar se é relevante para o volume de casos real de P02, e não apenas copiado do concorrente.

### Persona P03 — Dra. Helena Siqueira Prado

- **Autor(a):** Raphael Garavati Erbert
- **Tipo:** secundária — usa a mesma visualização de imagem + explicação pensada para P01 e P02, sem exigir um fluxo próprio na interface; é mantida como persona porque produz o laudo que P01 e P02 leem, e a forma como descreve casos limítrofes afeta diretamente o problema estudado
- **Base de evidências:** Entrega 1 (item 2.2 — Radiologista / Neuroradiologista; item 2.4 — conhecimento alto de imagem, linguagem técnica, uso prolongado; item 4.1 — radiologista examina no PACS e escreve relatório em texto livre; item 4.2 — interpretação subjetiva, falta de especialistas, inconsistência; item 4.3 — atrofia hipocampal sem quantificação objetiva de rotina; itens 5.1 a 5.3 — sala de leitura, monitor duplo, luz atenuada) e Entrega 4 (C03 e C04 — laudo feito em outra unidade; laudo "normal para a idade")
- **Hipóteses relacionadas:** H01; **H08** — laudos de MRI para investigação de demência tendem a ser genéricos quando o pedido chega sem contexto clínico e a atrofia é limítrofe

![Persona P03](https://github.com/rapha661/Alzheimer-XAI-ihc2026/blob/main/assets/03_personas/persona_p03_v2.svg)

**Dra. Helena Siqueira Prado, radiologista — "Sem a pergunta clínica, eu descrevo a imagem; não consigo responder ao que o médico quer saber."**

*A frase acima é hipótese da equipe sobre o perfil (H08).*

| Campo | Descrição |
|---|---|
| Faixa etária / contexto relevante | [H] 35–50 anos; radiologista geral com experiência em neuroimagem de rotina, sem subespecialização em neurorradiologia |
| Ocupação/papel | [F] Radiologista que interpreta a MRI e emite o laudo (Entrega 1, itens 2.2 e 4.1); [H] atua em serviço de telerradiologia, laudando exames de mais de um hospital |
| Conhecimento do domínio | [F] Alto em interpretação de imagem — atrofia hipocampal, ventrículos, substância branca (Entrega 1, item 4.3); [H] conhece pouco de IA/ML e de como um modelo chega a uma sugestão |
| Experiência tecnológica | [F] Alta — trabalha o dia todo no PACS, com zoom, windowing e medições (Entrega 1, itens 2.4 e 6.3) |
| Objetivos | [H] Emitir um laudo útil para quem vai decidir, com segurança sobre o que afirma, sem atrasar a fila |
| Necessidades | [H] Receber a pergunta clínica e dados mínimos junto do exame; ter uma referência objetiva para atrofia leve ou limítrofe; conseguir indicar no laudo o que foi avaliado |
| Dores/frustrações | [H] Pedido sem contexto clínico; atrofia limítrofe sem padrão objetivo de comparação (Entrega 1, item 4.2); fila de laudos extensa; nenhum retorno sobre o que o médico fez com o laudo |
| Motivadores | [H] Precisão do laudo; não ser a causa de um diagnóstico atrasado; ter respaldo técnico para o que escreve |
| Restrições/acessibilidade | [F] Horas contínuas em sala de leitura com luz atenuada (Entrega 1, item 5.3); [H] meta de produtividade por laudo |
| Ambiente típico de uso | [F] Sala de leitura de radiologia, workstation com monitor duplo integrada ao PACS (Entrega 1, itens 5.1 e 5.2) |
| Comportamentos relevantes | [H] Usa linguagem cautelosa ("pode ser compatível com a faixa etária") quando falta contexto; recomenda "correlacionar com dados clínicos"; raramente fala com o médico solicitante |

**Decisões de design influenciadas por P03 (hipóteses):**

- [H] A explicação localizada (Grad-CAM) e as medidas associadas (ex.: volume hipocampal) podem servir de referência objetiva nos casos limítrofes — como apoio à leitura, nunca no lugar do laudo.
- [H] A pergunta clínica e os dados preparados por P04 deveriam acompanhar a imagem até quem lauda, e não se perder entre o pedido e o laudo.
- Linguagem técnica de imagem é adequada a este perfil (Entrega 1, item 2.4), diferente do que vale para P01 — reforça a ideia de camadas de detalhe já prevista para P02.

### Persona P04 — Bruno Tavares Lima

- **Autor(a):** Nathan Gabriel da Fonseca Leite - 221230287
- **Tipo:** primária — responsável pela atividade A01 (preparar e enviar os dados do paciente), da qual dependem todas as etapas seguintes
- **Base de evidências:** Entrega 1 (item 2.2 — Técnico de Laboratório / Preparação de Dados; item 2.4 — conhecimento operacional, linguagem de aquisição, sem necessidade de métricas do modelo; item 3.2 — A01 com frequência alta e criticidade média-alta; item 4.1 — aquisição de MRI e armazenamento no PACS; item 4.2 — protocolos variam e não há padrão de qualidade; item 5.3 — LGPD)
- **Hipóteses relacionadas:** **H07** — problemas de qualidade da MRI e de dados clínicos incompletos só são percebidos depois que o paciente saiu do setor, o que gera reconvocação e atraso no diagnóstico.

![Persona P04](https://github.com/rapha661/Alzheimer-XAI-ihc2026/blob/main/assets/03_personas/persona_p04_v2.svg)

**Bruno Tavares Lima, técnico em radiologia — "se o exame sair ruim, ninguém percebe até o paciente já ter ido embora"**

*A frase acima e vários detalhes da narrativa são hipóteses da equipe sobre o perfil (H07) — em especial a frequência de pedidos médicos vagos, o atraso até a descoberta do problema e a reconvocação.*

Bruno tem 32 anos e trabalha há oito como técnico em radiologia no setor de imagem de um hospital geral. Ele opera o aparelho de ressonância magnética, prepara os exames e os envia para laudo. Conhece bem as sequências de aquisição e sabe reconhecer um artefato de movimento, mas não faz interpretação diagnóstica: isso é papel do radiologista. [H] Nos casos de investigação de demência, os pacientes costumam ser idosos, às vezes confusos ou agitados, e têm dificuldade de ficar parados durante o exame. [H] Os pedidos médicos nem sempre dizem o que se quer investigar, e Bruno precisa decidir sozinho qual protocolo usar. Depois do exame, ele ainda junta as informações clínicas do prontuário que precisam acompanhar as imagens. [H] Quando alguma coisa fica faltando, ele só descobre depois, quando o laudo volta com a observação "exame limitado", e o paciente pode precisar ser chamado de novo — **esta é exatamente a hipótese H07, ainda não confirmada**.

| Campo | Descrição |
|---|---|
| Faixa etária / contexto relevante | [H] 28–40 anos; formação técnica em radiologia, com anos de prática em ressonância magnética |
| Ocupação/papel | [F] Técnico em radiologia / preparação de dados: adquire as imagens, confere a qualidade e envia exame e dados clínicos para análise (papel já listado na Entrega 1, item 2.2) |
| Conhecimento do domínio | [F] Alto em aquisição de imagem (sequências, protocolos, artefatos); baixo em interpretação diagnóstica de Alzheimer, que não é sua função (Entrega 1, item 2.4) |
| Experiência tecnológica | [H] Alta — opera o console do scanner, o PACS e o prontuário eletrônico todos os dias |
| Objetivos | [H] Entregar um exame completo e com qualidade na primeira tentativa, com os dados clínicos corretos e do paciente certo, sem precisar reconvocar ninguém |
| Necessidades | [H] Saber quais sequências e dados clínicos o caso exige antes de começar; conferir a qualidade da imagem enquanto o paciente ainda está no setor; levar os dados clínicos do prontuário sem redigitá-los; anonimizar os dados sem trabalho manual extra |
| Dores/frustrações | [H] Pedido médico vago ("RM de crânio"), sem protocolo definido para demência; artefato de movimento em pacientes agitados; erro descoberto só depois, no laudo; dados clínicos (MMSE, idade, histórico) espalhados no prontuário; risco de associar dados ao paciente errado — nenhum destes itens tem frequência medida (H07) |
| Motivadores | [H] Evitar retrabalho e reconvocação de pacientes idosos; entregar um exame que realmente sirva para o diagnóstico; não ser apontado como a causa de um atraso |
| Restrições/acessibilidade | [H] Agenda cheia no scanner, com pouco tempo entre um paciente e outro; pacientes com dificuldade de colaborar; obrigação de proteger dados sensíveis (LGPD — este último ponto é [F], exigência legal geral) |
| Ambiente típico de uso | [F]/[H] Setor de imagem: sala de comando do scanner e estação de trabalho com PACS, em turnos — plausível por analogia ao processo descrito na Entrega 1, item 4.1 |
| Comportamentos relevantes | [H] Confere as imagens logo depois da aquisição; repete uma sequência quando o paciente ainda tolera; copia dados do prontuário para a requisição; liga para o radiologista quando tem dúvida sobre o protocolo |

**Decisões de design influenciadas por P04:**

- Indicadores de qualidade devem usar a linguagem de aquisição de imagem (sequência, artefato, cobertura), nunca métricas do modelo, como já previsto na Entrega 1 (item 2.4).
- [H] A verificação dos requisitos do caso (sequências e dados clínicos obrigatórios) deve acontecer antes do envio, enquanto o paciente ainda está no setor, e não depois do laudo — depende de H07 se confirmar.
- [H] Os dados clínicos devem vir do prontuário, sem redigitação, com uma confirmação explícita da identidade do paciente antes do envio.
- [H] O fluxo de preparo deve ser curto e direto, já que o contato do técnico com a interface é breve e acontece entre um exame e outro.


### Síntese das personas

| | P01 — Dr. Marcos Andrade | P02 — Dr. César Andrade de Melo | P03 — Dra. Helena Siqueira Prado | P04 — Bruno Tavares Lima |
|---|---|---|---|---|
| Tipo | Primária | Primária | Secundária | Primária |
| Usa a interface de diagnóstico? | Sim — é o fluxo principal | Sim — em casos de validação/escalonamento (ver Jornada, etapa 9) | Sim — consulta a imagem + explicação ao laudar, com a profundidade técnica de P02 | Sim — abre e prepara o caso (A01), antes de P01 interpretar a explicação |
| O que só ele(a) traz | A atividade mais crítica (A03, hipótese) e o objetivo priorizado desde a Entrega 1 | Profundidade técnica (SHAP detalhado, opacidade do heatmap) — como hipótese de design, não fato | O laudo que P01 e P02 leem: como um caso limítrofe é descrito antes de chegar ao médico (H08) | A entrada do fluxo (A01): qualidade dos dados antes de qualquer interpretação acontecer | 

**P01 continua sendo a persona prioritária** do projeto — é quem realiza a atividade que a equipe hipotetiza ser a mais frequente e crítica (A03) e cujo objetivo (compreender a sugestão com confiança proporcional e decidir) já havia sido escolhido na Entrega 1, item 7.2. As demais personas entram em pontos diferentes do mesmo fluxo: **P04 prepara e envia o exame → P03 lauda → P01 interpreta a explicação e decide → P02 valida os casos difíceis**. P03 é secundária porque usa a mesma visualização pensada para P01 e P02, sem fluxo próprio, mas traz uma necessidade que nenhuma outra persona cobre: o laudo genérico de um caso limítrofe é justamente o que P01 e P02 recebem hoje (ver Entrega 4, C01 e C04). 

A persona P04, Bruno Tavares Lima (técnico em radiologia, persona primária de A01), está registrada em `RASTREABILIDADE.md`, seção 5.

## 2. Mapa de empatia — equipe

**Persona escolhida:** P01 — Dr. Marcos Andrade
**Justificativa:** é o usuário priorizado desde a Entrega 1 (item 7.2) — a atividade mais crítica do projeto (A03, interpretar explicações XAI) é dele.

![Mapa de empatia](https://github.com/rapha661/Alzheimer-XAI-ihc2026/blob/main/assets/03_personas/mapa_empatia_v2.svg)

| Dimensão | Conteúdo | Evidência/Hipótese |
|---|---|---|
| **O que pensa e sente** | "Será que estou certo? Não quero atrasar nem errar o diagnóstico deste paciente." Sente-se sozinho ao decidir sem apoio técnico imediato. | [H] — inferido a partir do contexto de responsabilidade legal (Entrega 1, item 5.4) |
| **O que ouve** | Colegas comentando casos de discordância entre especialistas; famílias de pacientes pedindo respostas rápidas; a instituição cobrando documentação para auditoria. | [H] — itens 4.5 e 5.5 |
| **O que vê** | Fila de pacientes esperando; relatórios de radiologia em texto livre, sem score objetivo; prontuário eletrônico que não se conecta automaticamente ao resultado de imagem. | [F]/[H] — item 4.1 (relatório em texto livre) e item 4.2 |
| **O que fala e faz** | Explica o diagnóstico ao paciente/família em linguagem simples; documenta a decisão; às vezes liga para um colega pedindo uma opinião informal. | [H] — item 5.4 |
| **Dores** | Decidir sozinho, sem apoio técnico imediato; medo de errar o diagnóstico e responder por isso legalmente; informação insuficiente ou mal documentada no relatório de imagem. | [H] — itens 4.2, 5.6 |
| **Ganhos** | Sair da consulta seguro da decisão que tomou e de como explicá-la; ter a decisão respaldada e documentada sem esforço extra; saber quando e como passar o caso adiante, sem sentir que "falhou"; ser visto pela família como quem explica, não só como quem dá o diagnóstico. | [H] — ligado a H01/H03 |

## 3. Contexto de uso — consolidação

| Dimensão | Descrição | Implicação de design |
|---|---|---|
| Usuários | Foco em P01 (Médico Clínico); P02 (Neurologista) participa em validação/escalonamento de casos complexos; **P04 (Bruno) usa a interface na etapa de entrada (A01), antes de P01 interpretar a explicação**; P03 (radiologista) consulta a imagem + explicação ao laudar | Interface desenhada em camadas: entrada (P04), interpretação/decisão (P01), validação aprofundada (P02 e P03); recursos mais técnicos (opacidade de heatmap, SHAP detalhado, medidas) reservados a uma camada de detalhe |
| Tarefas | A01 (preparar/abrir caso) principalmente de P04, com abertura formal por P01; A03 (interpretar explicação XAI — hipótese de atividade crítica) e A02 (registrar decisão) para P01; validação/ajuste fino e exportação de laudo para P02; leitura da explicação localizada como apoio ao laudo para P03 | A03 deve ser o centro do design da tela principal; A01 deve ser rápida e acontecer enquanto o paciente ainda está no setor (P04); A02 deve aproveitar o que já foi mostrado na explicação; funções avançadas de P02 ficam em uma camada "expandir detalhes" |
| Equipamentos | P01: desktop padrão de consultório; P02: workstation com tela de alta resolução integrada ao PACS; **P04: console do scanner de MRI e estação de trabalho com PACS no setor de imagem**; P03: workstation de leitura com monitor duplo e PACS | A visão padrão (P01) não pode depender de recursos de exibição especializados; a visão expandida (P02) pode aproveitar mais tela/resolução; a visão de P04 precisa funcionar no equipamento do setor de imagem, com fluxo curto entre um exame e outro |
| Ambiente físico | P01: consultório com iluminação variável, uso pontual, possível presença de paciente/família durante parte do atendimento; P02: sala de leitura de radiologia, iluminação atenuada, uso contínuo por horas; **P04: sala de comando do scanner no setor de imagem, em turnos, com o paciente fisicamente presente durante a preparação dos dados**; P03: sala de leitura com luz atenuada, horas contínuas, muitas vezes em outra unidade (telerradiologia) | Bom contraste em diferentes condições de luz; interface não pode assumir sala escura como padrão; a tela de P04 precisa ser utilizável com o paciente ainda no setor e sob pressão de agenda entre exames |
| Ambiente social/organizacional | Responsabilidade legal do diagnóstico é do médico (P01/P02) — a IA é apoio, nunca substituição; hospital exige documentação para auditoria; **P01 pode estar sozinho analisando dados entre consultas, mas também pode ter paciente/família presentes durante parte do atendimento — a visibilidade de informação sensível em tela precisa considerar os dois casos**; **P04 interage com o paciente diretamente durante a preparação do exame, e pode precisar de apoio do acompanhante do paciente**; contato entre P01 e P02 ocorre por encaminhamento/escalonamento (ver Entrega 4, C02); P03 lauda à distância e raramente fala com quem pediu o exame (ver Entrega 4, C01) | Linguagem sempre de "sugestão"; log automático de decisão; interface deve permitir pausar/retomar quando há interrupção por presença de terceiros; nenhuma tela clínica deve expor dados que não sejam necessários à tarefa em curso |
| Papéis/permissões/governança | P01 decide; P02 valida quando acionado; P04 prepara e confere dados antes do envio; P03 lauda e descreve, mas não decide a conduta | Controle de acesso por perfil |
| Volume de dados/histórico | [H] Cada paciente pode ter mais de um exame ao longo do tempo; volume de casos/mês ainda não medido (ver Entrega 1, item 3.2) | Comparação longitudinal (F05) no nível do caso; nada de arquitetura de "big data" é necessário para o escopo priorizado |

## 4. Jornada do usuário — equipe

**Persona:** P01 — Dr. Marcos Andrade
**Objetivo da jornada:** diagnosticar com confiança um paciente com suspeita de Alzheimer e documentar a decisão, do primeiro sinal de alerta até o registro final (ou encaminhamento).
**Início e fim da jornada:** início — paciente relata esquecimentos em consulta de rotina; fim — decisão registrada e comunicada ao paciente/família.

| Etapa | Situação/ação | Objetivo | Pensamento/emoção | Dor | Oportunidade de design | Evidência |
|---|---|---|---|---|---|---|
| 1 (antes) | Percebe sinais de possível comprometimento cognitivo numa consulta de rotina | Decidir se investiga mais a fundo | "Isso pode ser só idade, ou pode ser algo sério" — incerteza inicial | Sem critério objetivo de triagem inicial | Fora do escopo direto da interface (etapa pré-exame) | [H] rotina clínica geral |
| 2 (antes) | Solicita MMSE/MoCA e MRI; aguarda os resultados | Reunir dados suficientes para investigar | Paciência, mas consciente da demora do sistema de saúde | Fila de espera de meses | Fora do escopo da interface, mas o sistema poderia mostrar status do caso enquanto aguarda | [F] Entrega 1, item 4.2 |
| 3 (durante) | Abre o caso na interface com os dados já prontos (MRI + MMSE/MoCA) | Iniciar a análise assistida por IA | Leve ansiedade; quer eficiência | Se o upload for confuso, perde tempo já escasso | Fluxo de abertura de caso simples e rápido (F01) | [F] Entrega 1, item 9.2 (F01) |
| 4 (durante) | Visualiza a explicação (MRI + regiões destacadas + features clínicas) e o score de confiança | Entender o "porquê" da sugestão do modelo | Momento crítico — quer confiar, mas precisa entender, não só aceitar | Se a explicação for só um número, gera confiança falsa ou desconfiança | Explicação combinada, em linguagem clínica, com opção de aprofundar (F03/F08) | [H] H01/H03; Al-bakri et al., 2025 |
| 5 (durante) | Compara com exame anterior do mesmo paciente, se existir | Avaliar se houve progressão | Mais seguro quando há dado longitudinal | Sem isso, decide "no escuro" sobre a evolução do quadro | Comparação de histórico (F05) | [F] Entrega 1, item 5.5 |
| 6 (durante) | Decide: confirma o diagnóstico, ou marca como incerto e encaminha a um especialista (P02) | Tomar a melhor decisão possível dentro do tempo disponível | Alívio se confiante; ainda ansioso se incerto, mas aliviado por ter opção de escalar | Medo de decidir sozinho em caso limítrofe | [H] Necessidade a investigar: que o caminho de encaminhar a um especialista (F07) permaneça acessível ao longo da decisão, sem ficar escondido — a forma exata (sempre visível? sob quantos cliques?) é hipótese de solução a validar, não requisito fechado | [H] Entrega 1, item 5.4 |
| 7 (durante) | Registra a decisão com justificativa documentada | Cumprir a necessidade de rastreabilidade/compliance | Quer que seja rápido, não burocrático | Se for redundante/manual, gera atrito e risco de pular a etapa | [H] Necessidade: reaproveitar o que já foi mostrado na explicação para compor a justificativa, em vez de redigitar do zero (F06) — forma exata é hipótese de solução, a testar | [H] Entrega 1, item 5.5 |
| 8 (depois) | Comunica o resultado ao paciente/família em linguagem acessível | Transmitir a decisão com clareza e empatia | Quer evitar confusão como a do caso Maria Silva (narrativa ilustrativa) | Traduzir termos técnicos para leigos exige esforço extra | Fora do escopo direto de P01; resumo "para o paciente" gerável a partir do relatório é possibilidade hipotética futura (ver Entrega 1, seção 8) | [H] Entrega 1, item 4.5 |
| 9 (depois) | Se encaminhou, aguarda o retorno de P02 (Neurologista) e depois atualiza o caso | Fechar o ciclo com o parecer do especialista | Alívio por ter compartilhado a responsabilidade em um caso difícil | Se não houver forma de preservar e retomar o raciocínio do especialista, a continuidade do caso se perde | [H] Necessidade de continuidade/rastreabilidade do parecer — "reabrir caso" é uma solução candidata, não a única possível | [H] registrada como **H06** |
| 10 (depois) | Estado final: Marcos encerrou o ciclo com uma decisão documentada e, quando necessário, compartilhada com o especialista | Consolidar o ganho obtido com o uso da solução, não apenas concluir uma tarefa | [H] Hipótese de benefício percebido: maior segurança para justificar a decisão, menos retrabalho documental, raciocínio preservado para o futuro | Se a interface só adicionou etapas sem gerar esse ganho, ela não está de fato apoiando o objetivo humano — este é o teste de validade da própria solução | O que muda para Marcos: ele passa a ter uma decisão respaldada por evidência explicada, documentada de forma auditável, e um caminho para retomar o raciocínio com um colega quando o caso é difícil (ver Ganhos no mapa de empatia) | [H] |

## Síntese

Necessidades e objetivos que devem obrigatoriamente aparecer nos cenários e nas tarefas seguintes (Entregas 4 e 5):

1. [H] A explicação (visual + clínica) deveria aparecer junto de alguma síntese/confiança — nunca um número isolado (P01, P02); a forma exata da síntese ainda é hipótese (ver Entrega 2, RC03).
2. [H] O fluxo de abertura de caso e registro de decisão precisa ser investigado quanto à rapidez necessária — poucos cliques, linguagem simples, como hipótese de design (P01, P04).
3. [H] A comparação com histórico do paciente é candidata a estar disponível quando existir exame anterior (P01) — função de apoio, não núcleo (ver Entrega 1, seção 8).
4. [H] Encaminhar a um especialista é uma necessidade identificada para P01 — a necessidade é que esse caminho permaneça acessível durante a decisão; a forma exata (sempre visível? sob quantos cliques? algum bloqueio por score?) ainda não foi investigada e não deve ser tratada como requisito fechado.
5. [H] P02 pode precisar de uma camada de detalhe técnico adicional (opacidade do heatmap, SHAP, exportação de laudo) que não deve poluir a tela padrão de P01 — hipótese herdada em parte da análise de concorrência (OHIF), a validar com P02 diretamente, não assumida como fato.
6. [H] Existe uma necessidade de preservar e retomar o raciocínio de um parecer de especialista obtido informalmente, para não perder contexto quando o caso precisa ser reaberto — registrada como **H06** na rastreabilidade. "Reabrir caso" é uma solução candidata, não a única possível (ver Entrega 4, C02).
7. [H] Problemas de qualidade de dados/imagem podem só ser percebidos depois que o paciente já saiu do setor, gerando reconvocação — registrada como **H07** (persona P04/Bruno; ver Entrega 4, C03).

## Checklist

- [x] Existe pelo menos uma persona por integrante (P01 Paulo, P02 Ana Carolina, P03 Raphael, P04 Nathan).
- [x] As personas não são apenas diferenças demográficas superficiais.
- [x] Está claro o que é dado real e o que é hipótese/proto-persona.
- [x] A persona não "validou por ficção" uma hipótese da Entrega 1; H03/H04 continuam marcadas como hipótese.
- [x] Objetivos e dores têm consequência para o design.
- [x] Contexto de uso está coerente com a Entrega 1.
- [x] Em TCC sem interface original, a persona possui relação explícita com a contribuição técnica.
- [x] Papéis administrativos, técnicos e decisórios só foram criados quando possuem objetivos/tarefas diferentes (P03, P04).
- [x] Jornada possui etapas, dores, oportunidades e etapa final de benefício percebido; não é apenas wireflow.
- [x] IDs das personas foram adicionados à rastreabilidade (`RASTREABILIDADE.md`, seção 3).
- [x] Há predominância de personas primárias (P01, P02, P04); a única secundária (P03) tem justificativa explícita.
- [x] P04 está sincronizada em todo o documento (Bruno Tavares Lima) em Síntese, Contexto de uso, Jornada e Síntese final.
- [x] H06/H07 usam os identificadores estáveis da `RASTREABILIDADE.md` em todo o documento.
