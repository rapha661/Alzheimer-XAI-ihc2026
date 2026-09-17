# Matriz de rastreabilidade de IHC

A matriz deve ser atualizada ao longo do semestre. Ela ajuda a demonstrar que a interface não surgiu arbitrariamente e registra **como o conhecimento da equipe evoluiu**.

Para projetos cujo TCC não previa interface, esta matriz é especialmente importante: deve ficar visível a passagem da **contribuição técnica do TCC** para um **cenário de uso plausível**, e desse cenário para as decisões de interação.

## 1. Derivação do escopo de IHC a partir do TCC

| Elemento | Registro da equipe | Evidência/justificativa | Estado |
|---|---|---|---|
| Tema do TCC | M-XAI: framework multimodal de IA explicável para diagnóstico da doença de Alzheimer | Entrega 1, item 0.2 | definido |
| Resultado técnico esperado | Modelo de IA/ML (multimodal: MRI + dados tabulares) | Entrega 1, item 0.4 | definido |
| O TCC previa interface? | sim | Entrega 1, item 0.5 — app web para envio de dados e consulta de resultado | definido |
| Capacidade/contribuição central | Diagnóstico explicável de Alzheimer via abordagem Feature-Augmented (combina features do modelo com biomarcadores clinicamente significativos) | Entrega 1, item 1.3 e 1.5 | definido |
| Possíveis beneficiários/stakeholders | Médico clínico, neurologista, radiologista, técnico de radiologia, paciente, familiares, gestor hospitalar, auditor/compliance | Entrega 1, item 2.2 e 2.3 | F / H |
| Usuário escolhido para IHC | Médico clínico sem expertise em neuroimagem, sem acesso imediato a especialista | Entrega 1, item 7.2 | F |
| Objetivo principal do usuário | Diagnosticar Alzheimer com confiança e rapidez, compreendendo claramente a explicação do sistema | Entrega 1, item 7.3 | F |
| Contexto de uso adotado | Sala de consulta/hospital, tempo limitado, sem especialista disponível, requisitos de privacidade (LGPD/HIPAA) | Entrega 1, seção 5 | F |
| Interface/recorte de IHC | Visualizar MRI + explicação sobreposta, ver features/confiança em linguagem clínica, comparar histórico, registrar decisão justificada, encaminhar a especialista | Entrega 1, item 7.4 | proposta |
| Relação com o TCC | extensão conceitual | Entrega 1, item 7.5 — aprofunda o app já previsto, com foco no médico clínico | definido |

> Se o escopo de IHC mudar ao longo do semestre, preserve a decisão anterior no histórico e registre **qual evidência motivou a mudança**.

## 2. Registro de hipóteses e lacunas da Entrega 1

Use esta tabela para itens importantes marcados como `[H]` ou `[?]`. Preserve o histórico: não apague uma hipótese refutada.

| ID | Afirmação / dúvida inicial | Tipo | Por que importa | Como/onde investigar | Evidência obtida | Estado atual | Impacto no projeto |
|---|---|---|---|---|---|---|---|
| H01 | Explicação Feature-Augmented aumenta a confiança do médico clínico em relação a um score isolado | H | É a premissa central de valor do TCC e da interface | Entrega 7 | Indício parcial: Al-bakri et al. (2025, Diagnostics) testaram formatos de explicação combinada com 5 médicos e obtiveram 100% de trust score (20% confiança total, 80% condicional) — ver Entrega 2, C02. Amostra pequena; não é confirmação definitiva | parcialmente sustentada (evidência externa fraca, n=5) | Reforça a explicação combinada (F03) como prioridade de design |
| H02 | Explicação combinada (imagem + biomarcadores) reduz o tempo de decisão do médico | H | Sustenta o benefício de rapidez (Entrega 1, item 9.1) | Entrega 7 | PENDENTE | aberta | Impacta metas de usabilidade (Entrega 8) |
| H03 | Médico clínico consegue interpretar corretamente o score de confiança sem treinamento extenso | H | Risco de má interpretação já identificado (Entrega 1, item 2.4) | Entrega 6/7 | Indício indireto contrário: no mesmo estudo (Al-bakri et al., 2025), 80% dos médicos relataram confiança apenas "condicional" mesmo com explicação combinada, sugerindo necessidade de esclarecimento adicional | aberta, com indício de risco | Reforça a necessidade de glossário/ajuda contextual (F08) |
| H04 | Gestores hospitalares aprovariam a adoção da ferramenta caso haja ganho comprovado | H | Impacta viabilidade real de adoção, ainda que fora do escopo direto de IHC | Não priorizado nesta disciplina | PENDENTE | aberta | Sustenta a persona P03 (Entrega 3) e o cenário C01 (Entrega 4) |
| H05 | Pacientes/familiares não serão usuários diretos da interface nesta fase | H | Delimita o escopo do projeto, evitando expansão excessiva | Reavaliar em versões futuras do TCC | PENDENTE | aberta | Confirma exclusão de perfis de paciente do recorte atual |
| H06 | Permitir reabrir/atualizar um caso encaminhado depois que o especialista responde, evitando perda do parecer e do raciocínio clínico | H | Gap identificado na jornada de P01 (Entrega 3, etapa 9); aprofundado no cenário C02 (Entrega 4) | Entrega 7 | PENDENTE | aberta | Sustenta P01/P02 e o cenário C02; pode gerar nova funcionalidade (reabrir caso) além de F01–F08 |
| H07 | Problemas de qualidade da MRI e dados clínicos incompletos só são percebidos depois que o paciente sai do setor, gerando reconvocação e atraso no diagnóstico | H | Se confirmada, justifica verificar qualidade e dados antes do envio | Entrega 7 (entrevista com técnicos e radiologistas) | PENDENTE | aberta | Sustenta a persona P04 (Bruno) e o cenário C03 |

> **Histórico de hipóteses removidas**: uma hipótese sobre "pressão institucional para usar a ferramenta como substituta do especialista" havia sido proposta na Entrega 3, ligada à persona P04 original (Otávio Rezende Prado, diretor financeiro). Essa persona foi removida por decisão da equipe (ver seção 5) e a hipótese foi retirada junto, por não ter mais evidência/persona que a sustente. H06 e H07 acima foram renumeradas para evitar colisão com essa hipótese removida e com a hipótese de Bruno, que também havia sido registrada como H06 por engano.

## 3. Rastreabilidade entre contribuição técnica, necessidades e artefatos

| ID | Capacidade do TCC utilizada | Necessidade/problema | Persona | Cenário problema | Objetivo/tarefa | HTA/GOMS/CTT | Cenário de interação / signos | MoLIC | Tela(s) Figma | Heurística / problema | Tarefa no teste | Decisão/melhoria |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| R01 | Explicação Feature-Augmented combinada com histórico de casos do paciente | Reconstituir o raciocínio de um parecer especializado obtido informalmente, para retomar um caso com segurança (H06) | P01 | C02 — "O parecer que se perdeu" | A02 (registrar decisão) + necessidade nova de reabrir/atualizar caso encaminhado | a definir | a definir | a definir | a definir | — | a definir | — |
| R02 | Indicadores objetivos de uso da ferramenta (tempo de diagnóstico, concordância entre médicos) | Decidir, com evidência agregada, se a ferramenta deve ser adotada, expandida ou descontinuada (H04) | P03 | C01 — "A decisão sem números" | fora do escopo de IHC desta disciplina — relatório institucional, registrado para trabalho futuro | — | — | — | — | — | — | — |
| R03 | Preparação e envio de MRI + dados clínicos com verificação de qualidade | Evitar exame incompleto e reconvocação do paciente (H07) | P04 | C03 — "O exame que precisou ser refeito" | A01 — preparar e enviar dados; F01 — abrir caso | a definir | a definir | a definir | a definir | — | a definir | — |

## 4. Rastreabilidade de padrões de interface

Use esta tabela quando o projeto incorporar padrões como dashboard, relatório, histórico, filtros ou administração. O objetivo é **justificar o padrão**, não apenas listar telas.

| ID da tela/fluxo | Padrão de interface | Objetivo/tarefa que justifica | Informação/ação principal | Evidência de necessidade | Artefatos relacionados |
|---|---|---|---|---|---|
| F01 | dashboard | {{T01}} | {{...}} | {{H01/evidência...}} | {{C01/M01}} |
| F02 | histórico com filtros | {{T02}} | {{...}} | {{...}} | {{...}} |
| F03 | administração/CRUD | {{T03}} | {{...}} | {{...}} | {{...}} |

## 5. Registro de mudanças de escopo

| Data | O que mudou | Evidência/feedback que motivou | Artefatos afetados | Responsável |
|---|---|---|---|---|
| 17/09/2026 | Persona P04 alterada de Otávio Rezende Prado (diretor financeiro, persona negativa) para Bruno Tavares Lima (técnico em radiologia, persona primária da atividade A01) | Decisão da equipe: a persona negativa não tinha uma atividade própria a modelar, enquanto A01 (preparo e envio de dados) estava sem persona dedicada | Persona P04 (Entrega 3); regras de design "nunca bloquear encaminhamento por score" e "nenhuma informação de custo/faturamento na tela clínica", que só o Otávio sustentava, foram removidas; hipótese de pressão institucional (antiga H07) foi retirada da seção 2 | Nathan Gabriel da Fonseca Leite |
| 17/09/2026 | Cenário do Bruno (P04) renumerado de C02 para C03 | O cenário C02 já havia sido ocupado por outro cenário da equipe ("O parecer que se perdeu", P01) | Entrega 4 — cabeçalho e todas as referências internas do cenário (Q11, implicações, hipótese) | Paulo Hudson / Nathan Gabriel |

## Como usar

- Use identificadores estáveis (`H01`, `P01`, `C01`, `T01`, `M01`, `F01`, `UT01`).
- Quando uma necessidade/problema tiver origem em hipótese da Entrega 1, cite o ID correspondente.
- Em TCC sem interface original, pelo menos uma linha deve mostrar claramente **como uma capacidade técnica chega até uma tarefa de usuário e uma tela/fluxo**.
- Uma linha pode se desdobrar quando um objetivo possui múltiplos caminhos.
- Não force relação inexistente: se algo ainda não foi modelado, marque `PENDENTE`.
- Ao remover uma funcionalidade, registre a decisão em vez de apagar silenciosamente o histórico.
- Dashboard, CRUD, filtros e relatórios só devem aparecer quando houver objetivo/tarefa que os justifique.
