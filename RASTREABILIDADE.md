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
| Possíveis beneficiários/stakeholders | Médico clínico, neurologista, radiologista, paciente, familiares, gestor hospitalar, auditor/compliance | Entrega 1, item 2.2 e 2.3 | F / H |
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
| H01 | Explicação Feature-Augmented aumenta a confiança do médico clínico em relação a um score isolado | H | É a premissa central de valor do TCC e da interface | Entrega 7 | PENDENTE | aberta | Define se a explicação combinada é priorizada no design |
| H02 | Explicação combinada (imagem + biomarcadores) reduz o tempo de decisão do médico | H | Sustenta o benefício de rapidez (Entrega 1, item 9.1) | Entrega 7 | PENDENTE | aberta | Impacta metas de usabilidade (Entrega 8) |
| H03 | Médico clínico consegue interpretar corretamente o score de confiança sem treinamento extenso | H | Risco de má interpretação já identificado (Entrega 1, item 2.4) | Entrega 6/7 | PENDENTE | aberta | Pode exigir glossário/ajuda contextual (F08) |
| H04 | Gestores hospitalares aprovariam a adoção da ferramenta caso haja ganho comprovado | H | Impacta viabilidade real de adoção, ainda que fora do escopo direto de IHC | Não priorizado nesta disciplina | PENDENTE | aberta | Não altera o recorte atual; registrado como lacuna |
| H05 | Pacientes/familiares não serão usuários diretos da interface nesta fase | H | Delimita o escopo do projeto, evitando expansão excessiva | Reavaliar em versões futuras do TCC | PENDENTE | aberta | Confirma exclusão de perfis de paciente do recorte atual |

## 3. Rastreabilidade entre contribuição técnica, necessidades e artefatos

| ID | Capacidade do TCC utilizada | Necessidade/problema | Persona | Cenário problema | Objetivo/tarefa | HTA/GOMS/CTT | Cenário de interação / signos | MoLIC | Tela(s) Figma | Heurística / problema | Tarefa no teste | Decisão/melhoria |
|---|---|---|---|---|---|---|---|---|---|---|---|---|
| R01 | {{ex.: recomendação de otimização}} | {{...}} | {{P01}} | {{C01}} | {{T01}} | {{links}} | {{...}} | {{M01}} | {{F01...}} | {{V01 ou —}} | {{UT01}} | {{...}} |
| R02 |  |  |  |  |  |  |  |  |  |  |  |  |

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
| {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |

## Como usar

- Use identificadores estáveis (`H01`, `P01`, `C01`, `T01`, `M01`, `F01`, `UT01`).
- Quando uma necessidade/problema tiver origem em hipótese da Entrega 1, cite o ID correspondente.
- Em TCC sem interface original, pelo menos uma linha deve mostrar claramente **como uma capacidade técnica chega até uma tarefa de usuário e uma tela/fluxo**.
- Uma linha pode se desdobrar quando um objetivo possui múltiplos caminhos.
- Não force relação inexistente: se algo ainda não foi modelado, marque `PENDENTE`.
- Ao remover uma funcionalidade, registre a decisão em vez de apagar silenciosamente o histórico.
- Dashboard, CRUD, filtros e relatórios só devem aparecer quando houver objetivo/tarefa que os justifique.
