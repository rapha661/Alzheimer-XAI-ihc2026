# Entrega 5 — Análise de tarefas: HTA, GOMS e CTT

**Data:** {{dd/mm/aaaa}}  
**Status:** 🟨 em andamento  
**Responsabilidade:** cada integrante modela pelo menos 1 HTA, 1 GOMS e 1 CTT. As três técnicas podem abordar a mesma funcionalidade ou funcionalidades distintas, conforme a orientação da disciplina.

## Objetivo da atividade

Modelar tarefas importantes sob perspectivas complementares: decomposição hierárquica (HTA), estrutura de metas/métodos/operações (GOMS) e relações temporais entre tarefas (CTT). O diagrama deve ser acompanhado de interpretação textual.

## Para projetos cujo TCC não previa interface

Modele **tarefas humanas relacionadas ao uso da contribuição técnica**, e não a implementação interna do algoritmo. Exemplos de boas tarefas para análise:

- investigar uma consulta de baixo desempenho;
- configurar uma análise e selecionar parâmetros;
- submeter um dataset e verificar sua validade;
- acompanhar uma execução demorada;
- comparar dois resultados/modelos;
- interpretar uma recomendação e decidir se a aceita;
- localizar uma execução anterior usando busca/filtros;
- gerar e compartilhar um relatório;
- administrar papéis/permissões quando isso for parte do trabalho real;
- revisar um alerta e registrar uma decisão.

Um CRUD pode gerar tarefas relevantes, mas “cadastrar usuário” só merece modelagem se tiver significado no domínio (papéis, validações, riscos, permissões, dependências).

## Seleção das tarefas

| ID | Tarefa | Persona/cenário de origem | Frequência/criticidade | Autor responsável |
|---|---|---|---|---|
| T01 | Retomar a conduta de um paciente já avaliado por especialista | P01/C02 | [H] frequência média (sempre que um caso encaminhado volta ao clínico); criticidade alta (a conduta é decidida sem o raciocínio já obtido) | Paulo Hudson Josué da Silva |
| T02 | {{...}} | P03/C01 | {{...}} | Raphael Garavati Erbert |
| T03 | {{...}} | P04/C03 | {{...}} | Nathan Gabriel da Fonseca Leite |
| T04 | {{...}} | P02/C04 | {{...}} | Ana Carolina Lazzuri |

---

## HTA — T01 Retomar a conduta de um paciente já avaliado por especialista

**Autor(a):** Paulo Hudson Josué da Silva — 22.222.013-9

### Descrição da tarefa

**Objetivo:** retomar com segurança a conduta do Sr. Ivo, aproveitando o raciocínio do parecer que o neurologista deu por telefone dois meses antes. **Ponto de início:** o paciente volta à consulta e o filho relata piora da memória. **Conclusão esperada:** uma conduta decidida (novo exame, reencaminhamento ou acompanhamento) e registrada no prontuário com justificativa. **Contexto:** consultório de atenção primária, agenda cheia, especialista indisponível no momento da consulta e, no prontuário, só a nota "neuro: sem AD por ora, reavaliar" (P01, cenário C02).

A modelagem descreve como a tarefa é feita hoje, com o prontuário eletrônico e o telefone, e não com a interface que o projeto ainda vai propor.

### Diagrama

![HTA T01](../assets/05_tarefas/hta_t01.svg)

### Decomposição e planos

| ID | Objetivo/operação | Plano/ordem | Problema ou decisão de design observada |
|---|---|---|---|
| 0 | Retomar a conduta do paciente já avaliado por especialista | 1 > 2 > 3 > 4 | **Input:** o paciente volta com o filho relatando piora; no prontuário há só uma anotação breve do parecer. **Feedback:** a conduta fica registrada com justificativa. **Problema:** o parecer foi obtido por canal informal e o raciocínio do especialista não foi registrado. |
| 1 | Avaliar a situação atual do paciente | 1 + 2 (em qualquer ordem) | — |
| 1.1 | Ouvir o relato do filho sobre a piora | operação | **Input:** relato da família sobre as últimas semanas. |
| 1.2 | Reaplicar o teste de memória (MMSE/MoCA) | operação | **Feedback:** novo escore, que só tem valor se puder ser comparado ao anterior. |
| 2 | Recuperar o contexto do parecer anterior | 1 > 2 > 3 | — |
| 2.1 | Abrir o prontuário do paciente | operação | — |
| 2.2 | Localizar a anotação do parecer | operação | **Problema:** a anotação é uma nota de rodapé, misturada às anotações de rotina; o prontuário não distingue um parecer de especialista de uma anotação comum [H]. **Recomendação:** registrar o parecer em um lugar próprio do caso, visível quando o caso é retomado. |
| 2.3 | Obter os critérios do neurologista | 1 / 2 | **Problema:** os critérios existiram só na ligação; nenhuma das duas opções garante recuperá-los. |
| 2.3.1 | Ligar para o neurologista | operação | **Problema:** depende da disponibilidade do especialista — no cenário, ele está em cirurgia. |
| 2.3.2 | Reconstruir pelos exames anteriores | operação | **Problema:** o médico clínico não interpreta MRI tecnicamente (P01); o que ele reconstrói é a própria leitura, não o raciocínio do especialista. **Recomendação:** guardar junto do parecer os exames e achados que sustentaram a conclusão (H06). |
| 3 | Decidir a conduta | 1 / 2 / 3 (conforme o contexto recuperado em 2) | **Problema:** sem o contexto, a escolha é feita sob incerteza. |
| 3.1 | Solicitar novo exame | operação | **Problema:** risco de repetir um exame já feito e revisado. |
| 3.2 | Reencaminhar ao neurologista | operação | **Problema:** ocupa de novo uma vaga de uma fila que já é longa (Entrega 1, item 4.2). |
| 3.3 | Conduzir sem o especialista | operação | **Problema:** a decisão ignora um raciocínio clínico que já tinha sido obtido. |
| 4 | Registrar a decisão no prontuário | operação | **Recomendação:** registrar a conduta ligada ao parecer anterior, para que a próxima retomada do caso não repita o problema (Entrega 1, item 5.4). |

**Verificação do HTA:**

- O objetivo 0 representa uma meta do usuário? Sim — retomar a conduta é o que o Dr. Marcos quer alcançar, não uma função do sistema.
- As subtarefas são necessárias e suficientes? Sim — cobrem o que o cenário C02 mostra, da chegada do paciente ao registro da decisão.
- Os **planos** indicam ordem, alternativa, repetição ou condição? Sim — há planos sequenciais (0 e 2), de seleção (2.3 e 3) e paralelo (1).
- A decomposição parou em nível útil para projeto de interação? Sim — as operações são ações que o médico reconhece; o nível de cliques e teclas fica para o GOMS.

---

## GOMS — T01 Retomar a conduta de um paciente já avaliado por especialista

**Autor(a):** Paulo Hudson Josué da Silva — 22.222.013-9

### Goal

`G0: retomar a conduta do paciente já avaliado por especialista`

### Métodos, operadores e regras de seleção

- **Method M1:** perguntar diretamente ao neurologista (para G2.3 — obter os critérios do neurologista)
  - Operators: discar o número do neurologista; aguardar o atendimento; perguntar quais exames revisou e por que descartou Alzheimer; guardar a resposta na memória
- **Method M2:** reconstruir o raciocínio pelos exames anteriores (para G2.3)
  - Operators: deslocar o cursor para a aba de exames; clicar no laudo de MRI anterior; ler a conclusão do laudo; clicar no resultado do MMSE anterior; comparar o MMSE anterior com o atual; inferir o critério usado pelo neurologista
- **Selection Rule SR1:** usar M1 quando o neurologista está disponível e a consulta permite esperar; usar M2 quando o neurologista não atende ou a consulta não permite esperar.
- **Method M3:** solicitar novo exame (para G3 — decidir a conduta)
  - Operators: deslocar o cursor para "solicitar exame"; clicar em "solicitar exame"; selecionar o tipo de exame; digitar a justificativa clínica; clicar em "enviar pedido"
- **Method M4:** reencaminhar ao neurologista (para G3)
  - Operators: deslocar o cursor para "encaminhamento"; clicar em "encaminhamento"; selecionar a especialidade "neurologia"; digitar o motivo; clicar em "enviar"
- **Method M5:** conduzir sem o especialista (para G3)
  - Operators: definir a conduta (por exemplo, reavaliar em um intervalo menor); explicar a conduta ao paciente e ao filho
- **Selection Rule SR2:** usar M3 quando os exames anteriores não explicam a piora relatada; usar M4 quando o raciocínio anterior não foi recuperado e a piora é significativa; usar M5 quando o raciocínio foi recuperado e a piora é compatível com o quadro já avaliado.

Modelo completo, no formato da aula (Barbosa e Silva, 2010). Os subobjetivos sem alternativa (G1, G2.1, G2.2 e G4) têm só operadores; os métodos acima aparecem dentro de G2.3 e G3. Os operadores sobre o prontuário assumem um prontuário eletrônico genérico, com busca, abas e botão de salvar [H].

```text
GOAL 0: retomar a conduta do paciente já avaliado por especialista
  GOAL 1: avaliar a situação atual do paciente
    OP. 1.1: ouvir o relato do filho sobre a piora da memória
    OP. 1.2: aplicar o MMSE/MoCA
  GOAL 2: recuperar o contexto do parecer anterior
    GOAL 2.1: abrir o prontuário do paciente
      OP. 2.1.1: deslocar o cursor para o campo de busca de pacientes
      OP. 2.1.2: digitar o nome do paciente
      OP. 2.1.3: clicar no registro do paciente
    GOAL 2.2: localizar a anotação do parecer
      OP. 2.2.1: deslocar o cursor para a aba de evoluções
      OP. 2.2.2: clicar na aba de evoluções
      OP. 2.2.3: rolar a lista até a data do encaminhamento
      OP. 2.2.4: ler a nota "neuro: sem AD por ora, reavaliar"
    GOAL 2.3: obter os critérios do neurologista
      METHOD 2.3.A: perguntar diretamente ao neurologista
      (SEL. RULE: o neurologista está disponível e a consulta permite esperar)
        OP. 2.3.A.1: discar o número do neurologista
        OP. 2.3.A.2: aguardar o atendimento
        OP. 2.3.A.3: perguntar quais exames revisou e por que descartou Alzheimer
        OP. 2.3.A.4: guardar a resposta na memória
      METHOD 2.3.B: reconstruir o raciocínio pelos exames anteriores
      (SEL. RULE: o neurologista não atende ou a consulta não permite esperar)
        OP. 2.3.B.1: deslocar o cursor para a aba de exames
        OP. 2.3.B.2: clicar no laudo de MRI anterior
        OP. 2.3.B.3: ler a conclusão do laudo
        OP. 2.3.B.4: clicar no resultado do MMSE anterior
        OP. 2.3.B.5: comparar o MMSE anterior com o atual
        OP. 2.3.B.6: inferir o critério usado pelo neurologista
  GOAL 3: decidir a conduta
    METHOD 3.A: solicitar novo exame
    (SEL. RULE: os exames anteriores não explicam a piora relatada)
      OP. 3.A.1: deslocar o cursor para "solicitar exame"
      OP. 3.A.2: clicar em "solicitar exame"
      OP. 3.A.3: selecionar o tipo de exame
      OP. 3.A.4: digitar a justificativa clínica
      OP. 3.A.5: clicar em "enviar pedido"
    METHOD 3.B: reencaminhar ao neurologista
    (SEL. RULE: o raciocínio anterior não foi recuperado e a piora é significativa)
      OP. 3.B.1: deslocar o cursor para "encaminhamento"
      OP. 3.B.2: clicar em "encaminhamento"
      OP. 3.B.3: selecionar a especialidade "neurologia"
      OP. 3.B.4: digitar o motivo do encaminhamento
      OP. 3.B.5: clicar em "enviar"
    METHOD 3.C: conduzir sem o especialista
    (SEL. RULE: o raciocínio foi recuperado e a piora é compatível com o quadro já avaliado)
      OP. 3.C.1: definir a conduta (por exemplo, reavaliar em um intervalo menor)
      OP. 3.C.2: explicar a conduta ao paciente e ao filho
  GOAL 4: registrar a decisão no prontuário
    OP. 4.1: deslocar o cursor para o campo de evolução
    OP. 4.2: digitar a conduta e a justificativa
    OP. 4.3: clicar em "salvar"
    OP. 4.4: verificar se a evolução aparece na lista
```


---

## CTT — T01 Retomar a conduta de um paciente já avaliado por especialista

**Autor(a):** Paulo Hudson Josué da Silva — 22.222.013-9

### Descrição

A árvore mostra a mesma tarefa do ponto de vista da ordem temporal e de quem executa cada parte. **Tarefas abstratas** (nuvem): Retomar a conduta do paciente, Avaliar a situação atual, Recuperar o contexto do parecer, Obter os critérios do neurologista e Registrar a decisão. **Tarefas do usuário** (pessoa): Ouvir o relato do filho, Reaplicar o teste de memória, Decidir a conduta e Ligar para o neurologista. **Tarefas interativas** (monitor + pessoa): Abrir o prontuário, Ler a anotação do parecer, Consultar exames anteriores e Digitar conduta e justificativa. **Tarefa do sistema** (monitor): Gravar evolução no prontuário.

Decidir a conduta e Ligar para o neurologista ficam fora do sistema — é por isso que o raciocínio do especialista nunca entra no prontuário. A única tarefa do sistema em toda a árvore é gravar a evolução: hoje o prontuário só recebe a decisão pronta.

### Diagrama

![CTT T01](../assets/05_tarefas/ctt_t01.svg)

### Legenda e relações temporais usadas

| Operador/relação | Significado no diagrama | Exemplo no modelo |
|---|---|---|
| `>>` ativação | A segunda tarefa só começa quando a primeira termina | Avaliar a situação atual `>>` Recuperar o contexto do parecer; Abrir o prontuário `>>` Ler a anotação do parecer |
| `[]>>` ativação com passagem de informação | A segunda tarefa começa depois da primeira e usa a informação produzida por ela | Ler a anotação `[]>>` Obter os critérios; Recuperar o contexto `[]>>` Decidir a conduta; Decidir a conduta `[]>>` Registrar a decisão; Digitar conduta `[]>>` Gravar evolução |
| `[]` escolha | As duas estão disponíveis, mas quando uma começa a outra é descartada | Ligar para o neurologista `[]` Consultar exames anteriores |
| `\|\|\|` concorrência | Podem ser feitas em qualquer ordem ou ao mesmo tempo | Ouvir o relato do filho `\|\|\|` Reaplicar o teste de memória |



---

## HTA — T02 {{nome da tarefa}}

**Autor(a):** {{nome — matrícula}}

### Descrição da tarefa

{{objetivo, ponto de início, conclusão esperada, contexto}}

### Diagrama

![HTA T02](../assets/05_tarefas/hta_t02.svg)

### Decomposição e planos

| ID | Objetivo/operação | Plano/ordem | Problema ou decisão de design observada |
|---|---|---|---|
| 0 | {{objetivo principal}} | {{1 }} 2 > 3 / 1 ou 2 etc.> | {{...}} |

**Verificação do HTA:**

- O objetivo 0 representa uma meta do usuário?
- As subtarefas são necessárias e suficientes?
- Os **planos** indicam ordem, alternativa, repetição ou condição?
- A decomposição parou em nível útil para projeto de interação?

---

## GOMS — T02 {{nome da tarefa}}

**Autor(a):** {{nome — matrícula}}

### Goal

`G0: {{meta do usuário}}`

### Métodos, operadores e regras de seleção

- **Method M1:** {{...}}
  - Operators: {{perceber, apontar, clicar, digitar, decidir... conforme o nível adotado}}
- **Method M2:** {{...}}
  - Operators: {{...}}
- **Selection Rule SR1:** usar M1 quando {{condição}}; usar M2 quando {{condição}}.

> Não chame qualquer passo de “método”. Em GOMS, métodos são sequências alternativas capazes de atingir uma meta; regras de seleção explicam quando escolher entre eles.

---

## CTT — T02 {{nome da tarefa}}

**Autor(a):** {{nome — matrícula}}

### Descrição

{{...}}

### Diagrama

![CTT T02](../assets/05_tarefas/ctt_t02.svg)

### Legenda e relações temporais usadas

| Operador/relação | Significado no diagrama | Exemplo no modelo |
|---|---|---|
| {{...}} | {{...}} | {{...}} |

Identifique, quando aplicável, tarefas de usuário, sistema, interação e tarefas abstratas. Verifique se concorrência, escolha, habilitação, desabilitação e repetição estão representadas corretamente segundo a notação adotada em aula.

---

## Síntese da equipe

Quais problemas de interação, oportunidades e requisitos apareceram a partir das modelagens? Quais tarefas irão para o protótipo e para o teste de usabilidade?

**T01 (Paulo):** as três técnicas apontam o mesmo ponto de ruptura — o parecer do especialista não fica registrado de forma recuperável (HTA 2.2 e 2.3), o que força o médico a um método que exige uma inferência que ele não domina (GOMS, M2) e deixa as etapas críticas fora do sistema (CTT). Requisitos candidatos, ainda hipóteses: [H] o parecer do especialista fica registrado no próprio caso, com os exames e achados que o sustentaram, e aparece quando o caso é retomado (H06); [H] o teste de memória anterior e o atual aparecem lado a lado; [H] a nova conduta fica ligada ao parecer anterior. Tarefa candidata para o protótipo e o teste de usabilidade: retomar um caso e localizar o parecer anterior.

## Checklist

- [ ] Cada integrante produziu ao menos 1 HTA, 1 GOMS e 1 CTT.
- [ ] Cada artefato identifica autor e tarefa.
- [ ] Diagramas são legíveis e possuem fonte editável quando possível.
- [ ] HTA contém planos, não apenas árvore de tópicos.
- [ ] GOMS distingue Goals, Operators, Methods e Selection Rules.
- [ ] CTT usa operadores temporais e tipos de tarefa coerentes.
- [ ] Há texto explicando cada diagrama.
- [ ] Tarefas estão ligadas a cenários/personas na rastreabilidade.
- [ ] Em TCC técnico, as tarefas descrevem o que a pessoa faz com a contribuição/resultados, não passos internos do código.
- [ ] CRUDs, relatórios, filtros e atividades administrativas foram escolhidos por relevância ao objetivo do usuário.
