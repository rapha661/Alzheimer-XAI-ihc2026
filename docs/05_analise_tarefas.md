# Entrega 5 — Análise de tarefas: HTA, GOMS e CTT

- **Data:** {{22/10/2026}}  
- **Status:** 🟩 concluída
- **Responsabilidade:** cada integrante modela pelo menos 1 HTA, 1 GOMS e 1 CTT. As três técnicas podem abordar a mesma funcionalidade ou funcionalidades distintas, conforme a orientação da disciplina.

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
| T02 | Laudar uma RM de investigação cognitiva com atrofia hipocampal limítrofe, dentro do prazo da fila | P03/C01 | [H] frequência alta (toda RM de investigação de demência passa pelo laudo; fila de 41 exames no C01); criticidade alta (o laudo é o que P01 e P02 leem — uma frase genérica num caso limítrofe pode atrasar o diagnóstico, H08) | Raphael Garavati Erbert |
| T03 | Realizar a aquisição de imagem de ressonância com qualidade diagnóstica e dados clínicos completos, dentro da agenda | P04/C03 | [H] frequência alta (a cada exame de investigação de demência); criticidade média-alta (a qualidade dos dados de entrada condiciona todo o restante do fluxo — Entrega 1, item 3.2) | Nathan Gabriel da Fonseca Leite |
| T04 | Decidir a conduta sobre a autonomia do paciente diante de evidências conflitantes | P02/C04 | [H] frequência média (casos limítrofes em que a família relata episódios que os testes não mostram); criticidade alta (o erro nos dois sentidos afeta a segurança e a liberdade do paciente — Entrega 1, item 5.6) | Ana Carolina Lazzuri |

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

## HTA — T02 Laudar uma RM de investigação cognitiva com atrofia limítrofe dentro do prazo da fila
 
**Autor(a):** Raphael Garavati Erbert — 22.123.014-7
 
### Descrição da tarefa
 
**Objetivo:** emitir um laudo útil e seguro para a RM de crânio de um paciente idoso em investigação de déficit cognitivo, com atrofia hipocampal limítrofe, dentro do prazo da fila (objetivo extraído do cenário C01, seção 4). **Ponto de início:** a Dra. Helena abre o próximo exame da fila de laudos; o pedido diz só "RM de crânio — investigação de déficit cognitivo" e o campo clínico traz apenas a idade. **Conclusão esperada:** laudo liberado ao hospital de origem, com uma conclusão sobre o hipocampo que ajude quem vai decidir a conduta. **Contexto:** serviço de telerradiologia, fila de 41 exames de hospitais diferentes, meta de prazo por exame [H, Q1], urgências que passam na frente [H, Q5], PACS só com medidas lineares [H, Q2] e nenhum exame anterior para comparar (P03, cenário C01).
 
O objetivo tem dois critérios que competem entre si: **utilidade/segurança** do laudo e **prazo**. Num caso limítrofe, cada passo que aumenta a segurança (buscar contexto, graduar, medir) custa tempo da fila. É essa tensão que torna a tarefa relevante para IHC, e é ela que empurra o laudo para a frase cautelosa do C01.
 
A modelagem descreve como a tarefa é feita hoje, no PACS do serviço de telerradiologia, e não com a interface que o projeto ainda vai propor.
 
### Diagrama
 
![HTA T02](../assets/05_tarefas/hta_t02.svg)
 
### Decomposição e planos
 
Planos escritos dentro da caixa de cada objetivo (`1>2` sequencial, `1/2` seleção, `1+2` paralelo, `1+2>3` paralelo e depois sequência). Operações têm a linha dupla sob a caixa.
 
| ID | Objetivo/operação | Plano/ordem | Problema ou decisão de design observada |
|---|---|---|---|
| 0 | Laudar a RM de investigação cognitiva com um laudo útil e seguro, dentro do prazo da fila | 1 > 2 > 3 > 4 | **Input:** exame na fila com o pedido “RM de crânio — investigação de déficit cognitivo” e prazo por exame [H, Q1]. **Feedback:** o laudo sai da fila — mas ninguém informa se ele serviu a quem pediu [?, Q6]. **Problema:** “útil” faz parte do objetivo e nunca é verificado; a tarefa termina na liberação, não na resposta à pergunta clínica. |
| 1 | Contextualizar o exame | 1 > 2 > 3 | **Problema:** o contexto que decide a leitura de um caso limítrofe (queixa, MMSE/MoCA, exame anterior) não chega a quem lauda (H08). |
| 1.1 | Abrir o exame na fila de laudos | operação | **Problema:** exames de urgência (ex.: suspeita de AVC) passam na frente e encurtam o tempo dos casos de demência [H, Q5]; a fila não distingue casos que pedem investigação mais longa. |
| 1.2 | Ler o pedido e os dados clínicos | operação | **Input:** pedido em texto livre e só a idade no campo clínico, resumidos pelo técnico do hospital de origem [F, Q3]. **Recomendação:** a pergunta clínica e os dados mínimos (queixa, MMSE/MoCA, histórico) acompanham a imagem até quem lauda. |
| 1.3 | Obter o contexto que falta | 1 / 2 (conforme haja canal com o solicitante e folga no prazo) | **Problema:** a seleção quase sempre cai em 1.3.2 — a alternativa 1.3.1 existe no papel, não na rotina. |
| 1.3.1 | Contatar o médico solicitante | operação | **Problema:** não há canal ágil; o solicitante está em outro hospital e raramente fala com a radiologista [?, Q6]. **Recomendação:** um canal de dúvida ligado ao próprio exame, assíncrono, que não trave a fila. |
| 1.3.2 | Prosseguir só com os dados recebidos | operação | **Problema:** é o caminho do C01; a incerteza não desaparece, só passa para as etapas 2 e 3. |
| 2 | Avaliar as imagens | 1 + 2 > 3 (1 e 2 em qualquer ordem; depois 3) | **Ação:** a busca pelo exame anterior pode correr enquanto os cortes são percorridos; a avaliação do hipocampo depende das duas. |
| 2.1 | Percorrer os cortes e descrever os achados gerais | operação | **Input:** RM no PACS, com zoom e janelamento (P03). **Feedback:** impressão de hipocampos “um pouco reduzidos”, insuficiente para afirmar atrofia na idade do paciente. |
| 2.2 | Buscar exame anterior para comparar | operação | **Problema:** exames feitos em outro hospital não estão no PACS do serviço; no C01 não há anterior. **Recomendação:** comparação longitudinal quando houver exame anterior (F05). |
| 2.3 | Avaliar o volume hipocampal | 1 / 2 / 3 (conforme o grau de dúvida e o tempo restante) | **Problema:** quanto mais objetivo o método, mais tempo ele custa; no caso limítrofe, quem escolhe é a fila, não a dúvida. Os critérios estão no GOMS (GOAL 2.6). |
| 2.3.1 | Estimar visualmente | operação | **Problema:** julgamento subjetivo, que varia entre leitores [F, Entrega 1, item 4.2]. |
| 2.3.2 | Graduar por escala visual (ex.: MTA) | operação | **Problema:** o limiar de normalidade da escala muda com a idade; num caso limítrofe a nota fica justamente na fronteira [H, Q4]. |
| 2.3.3 | Medir com a régua linear do PACS | operação | **Problema:** o PACS só tem medidas lineares, sem volumetria nem referência normativa [H, Q2]; medir à mão consome um tempo que a fila não tem [H, Q1]. **Recomendação:** referência objetiva (volume hipocampal e região destacada) como apoio à leitura, nunca no lugar dela. |
| 3 | Redigir a conclusão do laudo | 1 / 2 / 3 (conforme a segurança obtida em 2.3) | **Problema:** a conclusão herda a incerteza de 1.3 e 2.3; sem contexto e sem medida, 3.3 vira o padrão. |
| 3.1 | Afirmar atrofia hipocampal | operação | **Problema:** sem referência objetiva, risco de falso positivo — e de responder por ele (P03 quer respaldo técnico para o que escreve). |
| 3.2 | Declarar compatível com a faixa etária | operação | **Problema:** risco de falso negativo — é o laudo “normal para a idade” que aparece no C04. |
| 3.3 | Usar frase cautelosa e pedir correlação clínica | operação | **Problema:** é a escolha do C01; devolve a dúvida a P01, que não interpreta RM. **Recomendação:** registrar o que foi avaliado, por qual método e que dúvida ficou, em vez de uma frase genérica. |
| 4 | Liberar o laudo e abrir o próximo exame | operação | **Feedback:** inexistente — sem retorno do solicitante nem auditoria de laudos inconclusivos [?, Q6]. **Recomendação:** fechar o ciclo: saber o que foi feito com o laudo dos casos limítrofes. |
 
**Verificação do HTA:**
 
- O objetivo 0 representa uma meta do usuário? Sim — é o estado que Helena quer alcançar (um laudo que sirva a quem decide, sem atrasar a fila), não uma função do sistema.
- As subtarefas são necessárias e suficientes? Sim — cobrem o C01 da abertura do exame à liberação; sem 1, 2 ou 3 o objetivo não é atingido.
- Os planos indicam ordem, alternativa, repetição ou condição? Sim — sequencial (0 e 1), paralelo seguido de sequência (2: 1+2>3) e seleção (1.3, 2.3 e 3).
- A decomposição parou em nível útil? Sim — as folhas são ações que a radiologista reconhece (ler, percorrer, graduar, medir, redigir, liberar); cliques ficam para o GOMS.
---
 
## GOMS — T02 Laudar uma RM de investigação cognitiva com atrofia limítrofe dentro do prazo da fila
 
**Autor(a):** Raphael Garavati Erbert — 22.123.014-7
 
O GOMS abre os três pontos que o HTA marca como seleção (1.3, 2.3 e 3) e mostra **o que decide cada escolha**. A leitura mais importante está na regra de GOAL 3: ela depende do que GOAL 1.5 e GOAL 2.6 produziram.
 
### Goal
 
`G0: laudar a RM de investigação cognitiva com um laudo útil e seguro, dentro do prazo da fila`
 
### Métodos, operadores e regras de seleção
 
- **Method M1:** contatar o médico solicitante (para G1.5 — obter o contexto que falta)
  - Operators: procurar o contato no pedido; ligar ou escrever para o hospital de origem; aguardar a resposta; guardar a pergunta clínica na memória
- **Method M2:** prosseguir com os dados recebidos (para G1.5)
  - Operators: decidir laudar sem a pergunta clínica
- **Selection Rule SR1:** usar M1 quando o pedido traz contato direto do solicitante e o prazo permite esperar; usar M2 quando não há canal ágil ou o prazo não permite esperar (caso do C01).
- **Method M3:** estimar visualmente (para G2.6 — avaliar o volume hipocampal)
  - Operators: comparar os hipocampos com a referência mental da idade; decidir se há atrofia
- **Method M4:** graduar por escala visual (MTA) (para G2.6)
  - Operators: selecionar o corte coronal; comparar fissura coroidea e corno temporal com a escala; atribuir a nota; comparar a nota com o limiar da idade
- **Method M5:** medir com a régua linear do PACS (para G2.6)
  - Operators: clicar na ferramenta de régua; arrastar a régua sobre cada hipocampo; comparar as medidas com a referência que lembrar
- **Selection Rule SR2:** usar M3 quando a redução é evidente ou claramente ausente para a idade, ou quando o prazo já estourou; usar M4 quando a redução é discreta e há tempo para graduar [H, Q4]; usar M5 quando a dúvida persiste depois da escala e o prazo ainda permite medir [H, Q1, Q2].
- **Method M6:** afirmar atrofia hipocampal (para G3 — redigir a conclusão)
- **Method M7:** declarar compatível com a faixa etária (para G3)
- **Method M8:** frase cautelosa e correlação clínica (para G3)
  - Operators (M6–M8): digitar a conclusão correspondente
- **Selection Rule SR3:** usar M6 quando G2.6 deu segurança de que a redução excede a esperada para a idade; usar M7 quando deu segurança de que está dentro do esperado; usar M8 quando a dúvida persiste, sem pergunta clínica (M2) e sem medida conclusiva (G2.6) — caso do C01.
Modelo completo, no formato da aula (Barbosa e Silva, 2010). Os operadores sobre o PACS assumem um PACS genérico, com fila de laudos, aba de histórico e régua linear [H, Q2]. GOAL 2 lista os passos em sequência, mas percorrer os cortes e buscar o exame anterior podem ocorrer em qualquer ordem (plano 1+2 do HTA).
 
```text
GOAL 0: laudar a RM de investigação cognitiva com um laudo útil e seguro, dentro do prazo da fila
  GOAL 1: contextualizar o exame
    OP. 1.1: deslocar o cursor para a fila de laudos
    OP. 1.2: clicar duas vezes no próximo exame
    OP. 1.3: ler o pedido “RM de crânio — investigação de déficit cognitivo”
    OP. 1.4: ler o campo de dados clínicos (só a idade)
    GOAL 1.5: obter o contexto que falta
      METHOD 1.5.A: contatar o médico solicitante
      (SEL. RULE: o pedido traz um contato direto do solicitante e o prazo permite esperar a resposta)
        OP. 1.5.A.1: procurar o contato do solicitante no pedido
        OP. 1.5.A.2: ligar ou escrever para o hospital de origem
        OP. 1.5.A.3: aguardar a resposta
        OP. 1.5.A.4: guardar a pergunta clínica na memória
      METHOD 1.5.B: prosseguir com os dados recebidos
      (SEL. RULE: não há canal ágil com o solicitante ou o prazo não permite esperar — caso do C01)
        OP. 1.5.B.1: decidir laudar sem a pergunta clínica
  GOAL 2: avaliar as imagens
    OP. 2.1: girar a roda do mouse para percorrer os cortes
    OP. 2.2: ajustar janela e zoom sobre os lobos temporais
    OP. 2.3: perceber ventrículos, sulcos e substância branca
    OP. 2.4: digitar a descrição dos achados gerais
    GOAL 2.5: buscar exame anterior
      OP. 2.5.1: clicar na aba de histórico do paciente no PACS
      OP. 2.5.2: verificar se há exame anterior (no C01, não há)
    GOAL 2.6: avaliar o volume hipocampal
      METHOD 2.6.A: estimar visualmente
      (SEL. RULE: a redução é evidente, ou claramente ausente, para a idade — ou o prazo já estourou)
        OP. 2.6.A.1: comparar os hipocampos com a referência mental da idade
        OP. 2.6.A.2: decidir se há atrofia
      METHOD 2.6.B: graduar por escala visual (MTA)
      (SEL. RULE: a redução é discreta e há tempo para graduar no corte coronal [H, Q4])
        OP. 2.6.B.1: selecionar o corte coronal na altura dos hipocampos
        OP. 2.6.B.2: comparar fissura coroidea e corno temporal com a escala
        OP. 2.6.B.3: atribuir a nota da escala
        OP. 2.6.B.4: comparar a nota com o limiar esperado para a idade
      METHOD 2.6.C: medir com a régua linear do PACS
      (SEL. RULE: a dúvida persiste depois da escala e o prazo ainda permite medir [H, Q1, Q2])
        OP. 2.6.C.1: clicar na ferramenta de régua
        OP. 2.6.C.2: arrastar a régua sobre o hipocampo direito
        OP. 2.6.C.3: arrastar a régua sobre o hipocampo esquerdo
        OP. 2.6.C.4: comparar as medidas com a referência que lembrar
  GOAL 3: redigir a conclusão do laudo
    METHOD 3.A: afirmar atrofia hipocampal
    (SEL. RULE: GOAL 2.6 deu segurança de que a redução excede a esperada para a idade)
      OP. 3.A.1: digitar “atrofia hipocampal” com o grau observado
    METHOD 3.B: declarar compatível com a faixa etária
    (SEL. RULE: GOAL 2.6 deu segurança de que a redução está dentro do esperado)
      OP. 3.B.1: digitar “volume hipocampal compatível com a faixa etária”
    METHOD 3.C: frase cautelosa e correlação clínica
    (SEL. RULE: a dúvida persiste, sem pergunta clínica (1.5.B) e sem medida conclusiva (2.6) — caso do C01)
      OP. 3.C.1: digitar “redução volumétrica hipocampal discreta, que pode ser compatível com a faixa etária”
      OP. 3.C.2: digitar “correlacionar com dados clínicos”
  GOAL 4: liberar o laudo
    OP. 4.1: reler o texto do laudo
    OP. 4.2: clicar em “assinar e liberar”
    OP. 4.3: verificar que o exame saiu da fila
    OP. 4.4: clicar duas vezes no próximo exame
```
 
### Comparação entre os métodos de GOAL 2.6
 
| Método (GOAL 2.6) | Custo no prazo da fila | Objetividade | Resultado num caso limítrofe | Uso hoje |
|---|---|---|---|---|
| 2.6.A Estimar visualmente | Quase nenhum | Baixa — referência mental de cada leitor | Mantém a dúvida | Padrão quando a fila aperta |
| 2.6.B Escala visual (MTA) | Baixo — um corte coronal | Média — escala padronizada, julgamento ainda visual | Nota na fronteira do limiar da idade | Quando sobra algum tempo [H, Q4] |
| 2.6.C Régua linear do PACS | Alto — medir os dois lados à mão | Média — dá um número, mas sem norma para comparar | Medida sem referência no próprio PACS | Raro [H, Q1, Q2] |
 
**O que o modelo mostra:** a regra de seleção de GOAL 3 usa como entrada o resultado de GOAL 1.5 e de GOAL 2.6. Quando 1.5 cai em B (sem pergunta clínica) e 2.6 termina em A ou B (sem medida conclusiva), a única regra satisfeita é a de 3.C. A frase cautelosa do C01 não é descuido da radiologista: é a saída que o próprio modelo prevê para essas condições.
 
**Implicação de design:** para mudar o laudo é preciso mudar as condições das regras, não o texto. Trazer a pergunta clínica junto do exame torna 1.5 desnecessário; uma referência objetiva barata (volume hipocampal calculado, com a região destacada) faz 2.6.C caber no prazo e permite chegar a 3.A ou 3.B com respaldo.
 
O GOMS-KLM não foi aplicado: a etapa crítica (GOAL 2.6) é sobretudo cognitiva, e a interface que mudaria esse custo ainda vai ser projetada — o cálculo fica para a avaliação da Entrega 11.
 
---
 
## CTT — T02 Laudar uma RM de investigação cognitiva com atrofia limítrofe dentro do prazo da fila
 
**Autor(a):** Raphael Garavati Erbert — 22.123.014-7
 
### Descrição
 
O CTT modela a mesma tarefa pela ordem temporal e por quem executa cada parte. Ele mostra dois pontos que o HTA e o GOMS não representam: a **suspensão** do laudo por um exame de urgência, que depois é retomado (`|>`), e o fato de que a avaliação do hipocampo e a decisão da conclusão acontecem **fora do sistema**.
 
### Diagrama
 
![CTT T02](../assets/05_tarefas/ctt_t02.svg)
 
### Legenda e relações temporais usadas
 
| Operador/relação | Significado no diagrama | Exemplo no modelo |
|---|---|---|
| `>>` ativação | A segunda tarefa só começa quando a primeira termina | Abrir exame da fila `>>` Ler pedido e dados clínicos; Redigir o laudo `>>` Liberar o laudo |
| `[]>>` ativação com passagem de informação | A segunda começa depois e usa a informação da primeira | Contextualizar `[]>>` Avaliar as imagens `[]>>` Redigir; Buscar exame anterior `[]>>` Avaliar o hipocampo; Decidir a conclusão `[]>>` Digitar o laudo; Liberar `[]>>` Enviar ao hospital |
| `[]` escolha | Ao iniciar uma, as outras são descartadas | Estimar visualmente `[]` Graduar por escala visual `[]` Medir com régua linear — o mesmo ponto de HTA 2.3 e GOMS 2.6 |
| `\|\|\|` concorrência | Em qualquer ordem ou ao mesmo tempo | Percorrer os cortes `\|\|\|` Buscar exame anterior — o plano 1+2 do HTA 2 |
| `\|>` suspensão/retomada | A segunda interrompe a primeira, que continua de onde parou | Elaborar o laudo `\|>` Atender exame de urgência [H, Q5] |
 
As demais relações da notação (`|[]|` concorrência com comunicação, `|=|` independência e `[>` desativação) não aparecem porque nenhuma situação da tarefa as exige.
 
**Tipos de tarefa no modelo** (os quatro tipos da notação, com os ícones da aula):
 
- **Tarefas do usuário** (realizadas fora do sistema): estimar visualmente; graduar por escala visual; decidir a conclusão.
- **Tarefas do sistema** (processamento sem interação): enviar laudo ao hospital de origem.
- **Tarefas interativas** (diálogo usuário–sistema): abrir exame da fila; ler pedido e dados clínicos; percorrer os cortes; buscar exame anterior; medir com régua linear; digitar o laudo; liberar o laudo; atender exame de urgência.
- **Tarefas abstratas** (composição que auxilia a decomposição): laudar a RM; elaborar o laudo; contextualizar o exame; avaliar as imagens; avaliar o hipocampo; redigir o laudo.
**O que o modelo revela:** duas das três formas de avaliar o hipocampo e a decisão da conclusão são tarefas do usuário — acontecem na cabeça da radiologista, sem apoio do sistema, e é ali que o caso limítrofe se resolve. A única tarefa do sistema é transportar o laudo pronto. A suspensão (|>) mostra outro ponto: quando a urgência acaba, Helena retoma um caso cuja dúvida não ficou registrada em lugar nenhum. Oportunidades: tornar “Avaliar o hipocampo” interativa, com referência objetiva calculada, e preservar o estado da avaliação na retomada.
---

## HTA — T03 Realizar a aquisição de imagem de ressonância dentro da agenda

**Autor(a):** Nathan Gabriel da Fonseca Leite — 221230287

### Descrição da tarefa

**Objetivo:** realizar a aquisição de imagem de ressonância com qualidade diagnóstica e dados clínicos completos, dentro da agenda (objetivo extraído do cenário C03, seção 4). **Ponto de início:** o paciente entra no setor de imagem com o pedido médico de investigação de déficit cognitivo. **Conclusão esperada:** o paciente é liberado com as imagens em qualidade diagnóstica adquiridas, os dados clínicos completos e a janela da agenda respeitada — sem necessidade de reconvocação. **Contexto:** setor de imagem hospitalar, escala com intervalos curtos entre pacientes [H, C03 Q1] e paciente idosa com dificuldade de cooperação (P04, cenário C03).

O objetivo tem três critérios de sucesso que valem ao mesmo tempo, e é a tensão entre eles que torna a tarefa relevante para IHC:

| Critério | Evidência no C03 |
|---|---|
| Qualidade diagnóstica | "exame limitado por artefato de movimento; ausência de sequência volumétrica" |
| Dados clínicos completos | "dados clínicos incompletos"; transcrição manual sujeita a lapsos [H, Q4] |
| Dentro da agenda | escala com intervalos curtos entre pacientes [H, Q1] |

Os dois primeiros **competem** com o terceiro: repetir uma sequência melhora a imagem e consome a janela. Por isso a restrição de tempo entra no objetivo, e não apenas no contexto.

A modelagem descreve como a tarefa é feita hoje, com o console do scanner, o PACS e o prontuário, e não com a interface que o projeto ainda vai propor. O envio do exame para análise fica fora do recorte: ele começa depois que a aquisição é encerrada, e é na liberação do paciente que a janela de correção se fecha.

### Diagrama

![HTA T03](../assets/05_tarefas/hta_t03.svg)

### Decomposição e planos

Cada plano é escrito dentro da caixa do objetivo e numera apenas os seus próprios subobjetivos (`1 > 2` sequencial, `1 / 2` seleção, `1 + 2` paralelo). No diagrama, as **operações** — as folhas da árvore — são marcadas com a linha dupla sob a caixa; as caixas sem essa linha são objetivos.

| ID | Objetivo/operação | Plano/ordem | Problema ou decisão de design observada |
|---|---|---|---|
| 0 | Realizar a aquisição com qualidade diagnóstica e dados clínicos completos, dentro da agenda | 1 > 2 > 3 | **Input:** pedido médico e janela da agenda. **Feedback:** confirmação de que o exame está completo antes de liberar o paciente. **Problema:** esse retorno não existe — a falha só aparece dias depois, no laudo, porque o fluxo não tem validador precoce de qualidade no PACS [H, Q5]. **Recomendação:** antecipar a conferência para antes da liberação do paciente (H07). |
| 1 | Preparar a aquisição | 1 > 2 > 3 | **Problema:** o pedido vem como "RM de crânio", sem indicar a suspeita, e a escolha do protocolo recai sobre o técnico — cuja autonomia formal para alterá-lo é uma questão em aberto [?, Q2]. |
| 1.1 | Ler o pedido e identificar a suspeita | operação | **Input:** texto livre do pedido médico. **Problema:** informação incompleta na origem. |
| 1.2 | Definir protocolo e dados obrigatórios | operação | **Feedback:** hoje inexistente — não há lista do que o caso exige. **Recomendação:** apresentar sequências e dados clínicos obrigatórios **antes** da aquisição (F03, `RASTREABILIDADE.md`). |
| 1.3 | Estimar o tempo do protocolo na janela | operação | **Problema:** o técnico não sabe de antemão se o protocolo completo cabe na janela; descobre durante a aquisição [H, Q1]. **Recomendação:** exibir a duração estimada contra o tempo restante. |
| 2 | Executar a aquisição | 1 + 2 (em qualquer ordem) | **Ação:** nada obriga os dados clínicos a esperarem as imagens; reuni-los enquanto o paciente é posicionado economiza janela. É por fazê-los **depois** que, no C03, a transcrição ocorre sob ritmo acelerado [H, Q4]. |
| 2.1 | Adquirir as imagens | 1 > 2 > 3 | — |
| 2.1.1 | Posicionar e orientar o paciente | operação | **Problema:** pacientes com declínio cognitivo têm dificuldade de permanecer imóveis. |
| 2.1.2 | Executar as sequências do protocolo | operação | **Input:** protocolo definido em 1.2. **Feedback:** imagens no console. |
| 2.1.3 | Garantir a qualidade diagnóstica | 1 / 2 / 3 | **Problema:** a escolha é feita sem critério escrito de quanto movimento é tolerável e sem saber quanto tempo resta. O conjunto de ações de contenção disponíveis na rotina é ele próprio uma lacuna [H, Q3]. Qual caminho se aplica é detalhado no GOMS (GOAL 2). **Recomendação:** indicar a qualidade em linguagem de aquisição (sequência, artefato, cobertura), nunca em métricas do modelo (Entrega 1, item 2.4). |
| 2.1.3.1 | Conter o movimento e repetir a sequência | operação | **Ação:** orientar novamente a paciente ou aplicar contenções leves antes de repetir [H, Q3]; só é possível com o paciente ainda no aparelho e com folga na janela. |
| 2.1.3.2 | Encurtar o protocolo preservando a sequência crítica | operação | **Problema:** depende de o serviço autorizar o técnico a ajustar o protocolo [?, Q2]. **Recomendação:** o sistema deve indicar qual sequência é indispensável para a suspeita, para que o corte não atinja justamente ela. |
| 2.1.3.3 | Registrar a limitação do exame | operação | **Recomendação:** a limitação deve acompanhar o caso até quem lauda, e não ficar só no laudo final. |
| 2.2 | Completar os dados clínicos | 1 > 2 > 3 | **Problema:** transcrição manual do prontuário para a requisição, sujeita a lapsos de digitação [H, Q4]. |
| 2.2.1 | Importar dados do prontuário | operação | **Recomendação:** trazer idade, queixa, MMSE/MoCA e histórico sem redigitação. |
| 2.2.2 | Confirmar a identidade do paciente | operação | **Problema:** risco de associar imagens e dados a pacientes diferentes (Entrega 1, item 5.3). **Recomendação:** confirmação explícita, feita por pessoa. |
| 2.2.3 | Completar os dados que faltarem | operação | **Feedback:** indicar o que ainda falta, em vez de aceitar o caso incompleto em silêncio. |
| 3 | Encerrar a aquisição | 1 > 2 | **Ação:** é o último momento em que a correção ainda é barata. |
| 3.1 | Conferir qualidade e completude antes de liberar o paciente | operação | **Problema:** essa conferência não existe no fluxo atual — é o ponto exato da ruptura do C03 [H, Q5]. **Recomendação:** bloquear o encerramento enquanto houver item obrigatório pendente (F03). |
| 3.2 | Liberar o paciente e registrar o tempo usado | operação | **Feedback:** registrar o tempo efetivo contra a janela alimenta o indicador de agenda do setor. |

**Verificação do HTA:**

- O objetivo 0 representa uma meta do usuário? Sim — é o estado que Bruno quer alcançar (exame adquirido, completo e dentro da janela), não uma função do sistema.
- As subtarefas são necessárias e suficientes? Sim — retirar qualquer um dos três objetivos de primeiro nível impede alcançar o objetivo, e nenhuma outra etapa aparece no C03 dentro deste recorte.
- Os **planos** indicam ordem, alternativa, repetição ou condição? Sim — há plano sequencial (0, 1, 2.1, 2.2 e 3), paralelo (2) e de seleção entre três caminhos (2.1.3).
- A decomposição parou em nível útil para projeto de interação? Sim — as folhas são operações observáveis (ler, definir, estimar, posicionar, conter, importar, conferir, liberar). Descer até cliques pressuporia uma interface que só será projetada na Entrega 6.

---

## GOMS — T03 Realizar a aquisição de imagem de ressonância dentro da agenda

**Autor(a):** Nathan Gabriel da Fonseca Leite — 221230287

O GOMS reabre o ponto que o HTA marca apenas como seleção: **quando há mais de uma forma de atingir um subobjetivo, o que decide qual usar**. Dois subobjetivos têm métodos alternativos — obter imagens com qualidade diagnóstica (GOAL 2) e completar os dados clínicos (GOAL 3) —, e são exatamente os dois pontos do HTA com mais de um caminho possível. Nas regras de seleção de GOAL 2, o tempo restante na janela aparece como condição explícita: é ele que arbitra o conflito entre qualidade e agenda.

### Modelo GOMS

Notação da aula: `GOAL`, `METHOD`, `(SEL. RULE: ...)` logo abaixo de cada método, e `OP.` para os operadores, com a numeração herdada do nível acima.

```
GOAL 0: realizar a aquisição de imagem de ressonância com qualidade
        diagnóstica e dados clínicos completos, dentro da agenda

  GOAL 1: definir o que o caso exige e o tempo disponível
      OP. 1.1: ler o pedido e identificar a suspeita clínica
      OP. 1.2: perceber o protocolo e os dados clínicos obrigatórios
      OP. 1.3: estimar o tempo do protocolo na janela da agenda

  GOAL 2: obter imagens com qualidade diagnóstica

      METHOD 2.A: conter o movimento e repetir a sequência
      (SEL. RULE: paciente ainda no aparelho, tolera a repetição
       e ainda há folga na janela da agenda)
          OP. 2.A.1: perceber o artefato nas imagens
          OP. 2.A.2: decidir que o problema é recuperável
          OP. 2.A.3: orientar a paciente novamente
          OP. 2.A.4: aplicar contenções leves, se necessário   [H, C03 Q3]
          OP. 2.A.5: acionar o console e repetir a sequência
          OP. 2.A.6: perceber o novo resultado

      METHOD 2.B: encurtar o protocolo preservando a sequência crítica
      (SEL. RULE: a janela da agenda está acabando, a sequência crítica
       ainda não foi adquirida e o serviço autoriza o técnico a ajustar
       o protocolo — condição em aberto, C03 Q2)
          OP. 2.B.1: perceber o tempo restante
          OP. 2.B.2: decidir qual sequência é crítica para a suspeita
          OP. 2.B.3: suprimir as sequências acessórias
          OP. 2.B.4: adquirir a sequência crítica

      METHOD 2.C: registrar a limitação do exame
      (SEL. RULE: a limitação é parcial e não atinge a região de interesse)
          OP. 2.C.1: perceber a limitação
          OP. 2.C.2: decidir que ela não impede a análise
          OP. 2.C.3: clicar em "registrar limitação"
          OP. 2.C.4: digitar o motivo

      METHOD 2.D: reconvocar o paciente
      (SEL. RULE: a janela acabou ou o paciente não tolera,
       e o item faltante é obrigatório)
          OP. 2.D.1: perceber que o item faltante é obrigatório
          OP. 2.D.2: decidir que não há como corrigir agora
          OP. 2.D.3: marcar novo exame na agenda
          OP. 2.D.4: notificar o médico solicitante

  GOAL 3: completar os dados clínicos do caso

      METHOD 3.A: importar do prontuário
      (SEL. RULE: os dados estão estruturados e disponíveis no prontuário)
          OP. 3.A.1: selecionar o paciente
          OP. 3.A.2: importar idade, queixa e MMSE
          OP. 3.A.3: confirmar a identidade
          OP. 3.A.4: perceber o que ficou faltando

      METHOD 3.B: completar manualmente
      (SEL. RULE: o dado só existe em evolução antiga ou em laudo
       não estruturado)
          OP. 3.B.1: procurar o dado no prontuário
          OP. 3.B.2: digitar o valor no caso          [H, C03 Q4]
          OP. 3.B.3: confirmar a identidade
          OP. 3.B.4: perceber o que ficou faltando

  GOAL 4: encerrar a aquisição dentro da janela
      OP. 4.1: conferir qualidade e completude antes de liberar
      OP. 4.2: liberar o paciente
      OP. 4.3: registrar o tempo usado na janela da agenda
```

Os operadores estão em nível de tarefa (*perceber*, *decidir*, *orientar*, *acionar*, *clicar*, *digitar*, *confirmar*). A variante **GOMS-KLM** (K, P, H, B, M, R, com tempos somados) não foi aplicada porque pressupõe uma interface concreta cujas teclas e cliques possam ser cronometrados; ela fica registrada para a Entrega 11, onde será especialmente pertinente por o objetivo ter restrição de tempo.

> **Sobre a forma do artefato:** o GOMS é um **modelo textual**. Diferente do HTA e do CTT, ele não se representa como diagrama de caixas e setas — a hierarquia é expressa pela indentação, como nos exemplos da aula. O mesmo modelo está tipografado em [`../assets/05_tarefas/goms_t03.svg`](../assets/05_tarefas/goms_t03.svg), para uso em slides e impressão.

### Comparação entre os métodos de GOAL 2

| Método | Custo na janela da agenda | Custo para o paciente | Qualidade diagnóstica resultante | Risco |
|---|---|---|---|---|
| 2.A Conter e repetir | Alto — consome o tempo restante | Permanecer mais tempo no aparelho | Preservada | Baixo — corrige o problema na origem |
| 2.B Encurtar o protocolo | Baixo — cabe na janela | Nenhum | Preservada na região de interesse; perde achados acessórios | Médio — depende de acertar a sequência crítica e de haver autonomia para alterar o protocolo [?, Q2] |
| 2.C Registrar limitação | Nenhum | Nenhum imediato | Comprometida, mas declarada | Alto — a limitação pode não chegar a quem decide |
| 2.D Reconvocar | Nenhum agora; consome vaga futura | Nova viagem, acompanhante, semanas de atraso | Adiada | Alto — é o desfecho do cenário C03 |

**O que o modelo mostra:** 2.A e 2.B são os únicos métodos que ainda entregam qualidade diagnóstica, e ambos só existem **enquanto o paciente está no aparelho**. Eles se distinguem pelo tempo: 2.A exige folga na janela, 2.B é a saída quando a folga acabou. Hoje, como a falta só é percebida dias depois (H07), o processo não escolhe entre eles — cai direto em 2.D, o método que mais custa ao paciente. A implicação de design é que a verificação precisa acontecer cedo o bastante para que 2.A e 2.B ainda sejam aplicáveis, e que a interface deve informar o tempo restante, já que é ele que distingue os dois. Em GOAL 3, 3.B existe apenas porque o prontuário não entrega o MMSE de forma estruturada — eliminar essa causa elimina o método mais lento e mais sujeito a erro [H, Q4].

---

## CTT — T03 Realizar a aquisição de imagem de ressonância dentro da agenda

**Autor(a):** Nathan Gabriel da Fonseca Leite — 221230287

### Descrição

O CTT modela o mesmo objetivo sob a perspectiva temporal, distinguindo o que é feito pelo técnico, o que é feito pelo sistema e o que exige interação entre os dois. Ele mostra dois pontos que o HTA não representa: a **concorrência** entre adquirir as imagens e completar os dados clínicos, e a **desativação** da aquisição quando o paciente não tolera o exame.

### Diagrama

![CTT T03](../assets/05_tarefas/ctt_t03(1).svg)

### Legenda e relações temporais usadas

| Operador/relação | Significado no diagrama | Exemplo no modelo |
|---|---|---|
| `>>` ativação | A segunda tarefa só pode iniciar após a primeira terminar | "Completar dados clínicos" `>>` "Encerrar a aquisição" |
| `[ ]>>` ativação com passagem de informação | Além de só iniciar depois, a segunda tarefa recebe a informação produzida pela primeira | "Preparar a aquisição" `[ ]>>` "Adquirir as imagens": o protocolo definido determina as sequências |
| `[ ]` escolha | Ambas estão habilitadas, mas iniciar uma desabilita a outra | "Conter o movimento e repetir a sequência" `[ ]` "Encurtar o protocolo" `[ ]` "Registrar limitação do exame" — corresponde à seleção `1 / 2 / 3` do objetivo 2.1.3 do HTA e aos métodos 2.A, 2.B e 2.C do GOMS |
| `\|\|\|` concorrência | As tarefas podem ser realizadas em qualquer ordem ou ao mesmo tempo | "Adquirir as imagens" `\|\|\|` "Completar dados clínicos" — corresponde ao plano `1 + 2` do objetivo 2 do HTA |
| `[>` desativação | A primeira tarefa é completamente interrompida pela segunda | "Executar as sequências do protocolo" `[>` "Interromper por intolerância do paciente" — é o que acontece no C03, quando Dona Aparecida pede para sair |

As demais relações da notação (`\| [ ] \|` concorrência com comunicação, `\|=\|` independência e `\|>` suspensão/retomada) não aparecem neste modelo porque nenhuma situação da tarefa as exige.

**Tipos de tarefa no modelo** (os quatro tipos da notação, com os ícones da aula):

- **Tarefas do usuário** (realizadas fora do sistema): ler o pedido médico; definir protocolo e dados obrigatórios; estimar o tempo na janela da agenda; posicionar e orientar o paciente.
- **Tarefas do sistema** (processamento sem interação): validar qualidade diagnóstica; importar dados do prontuário; conferir qualidade e completude; registrar o tempo usado na janela.
- **Tarefas interativas** (diálogo usuário–sistema): executar as sequências do protocolo; interromper por intolerância do paciente; conter o movimento e repetir a sequência; encurtar o protocolo; registrar limitação do exame; confirmar identidade do paciente; completar dados que faltarem; liberar o paciente.
- **Tarefas abstratas** (composição que auxilia a decomposição): realizar a aquisição; preparar a aquisição; adquirir as imagens; completar dados clínicos; encerrar a aquisição.

**O que o modelo revela:** validar a qualidade diagnóstica, importar os dados clínicos e conferir a completude estão tipadas como **tarefas do sistema**, mas hoje todas são feitas por pessoas — o técnico avalia a imagem no olho, transcreve manualmente os dados [H, Q4] e não faz conferência nenhuma antes de liberar o paciente [H, Q5]. "Estimar o tempo na janela da agenda" aparece como tarefa do **usuário** justamente porque nenhum sistema oferece esse dado hoje; convertê-la em tarefa do sistema é uma das oportunidades de design mais diretas deste modelo. A confirmação de identidade permanece como tarefa interativa porque a responsabilidade é humana e não deve ser automatizada em silêncio.

---
## HTA — T04 Decidir a conduta sobre a autonomia do paciente diante de evidências conflitantes

**Autor(a):** Ana Carolina Lazzuri — 22.123.001-4

### Descrição da tarefa

**Objetivo:** decidir se o Sr. Roberto pode continuar dirigindo e morando com a autonomia atual, ou se é preciso emitir um laudo restritivo (suspensão da CNH e maior supervisão em casa). **Ponto de início:** o paciente volta à consulta com a filha, que relata episódios recentes (se perdeu voltando da padaria, lapsos nas contas domésticas), enquanto o prontuário mostra MMSE estável e um laudo de MRI limítrofe. **Conclusão esperada:** uma conduta definida (laudo restritivo, avaliação neuropsicológica complementar ou manutenção da autonomia com reavaliação), explicada ao paciente e à filha e registrada no prontuário com a justificativa. **Contexto:** consultório neurológico especializado, decisão de alto impacto ético e pessoal, sem um protocolo no sistema para ponderar o relato da família frente aos escores e ao laudo (P02, cenário C04).

A modelagem descreve como a tarefa é feita hoje, com o prontuário eletrônico e a conversa com a família.

### Diagrama

![HTA T04](https://github.com/rapha661/Alzheimer-XAI-ihc2026/blob/main/assets/05_tarefas/hta-t04.jpeg)

### Decomposição e planos

| ID | Objetivo/operação | Plano/ordem | Problema ou decisão de design observada |
|---|---|---|---|
| 0 | Decidir a conduta sobre a autonomia do paciente | 1 > 2 > 3 > 4 | **Input:** relato da filha, escores de MMSE e laudo de MRI apontando em direções diferentes. **Feedback:** a conduta fica explicada à família e registrada com justificativa. **Problema:** os dados objetivos e o relato não aparecem juntos em lugar nenhum; o confronto acontece só na cabeça do médico. |
| 1 | Reunir as evidências do caso | 1 + 2 (em qualquer ordem) | — |
| 1.1 | Ouvir o relato da filha | operação | **Input:** episódios do dia a dia (se perder na rua, errar contas, insistir em dirigir). **Problema:** o relato é oral e não fica registrado de forma estruturada; nas consultas seguintes ele depende do que o médico anotou em texto livre [H]. |
| 1.2 | Revisar os dados do prontuário | 1 + 2 (em qualquer ordem) | — |
| 1.2.1 | Consultar os escores de MMSE | operação | **Feedback:** pontuação estável em relação à consulta anterior. **Problema:** o escore total não mostra quais domínios cognitivos variaram, e é justamente aí que os episódios relatados poderiam aparecer [H]. |
| 1.2.2 | Ler o laudo de MRI | operação | **Feedback:** achados limítrofes de declínio leve. |
| 2 | Confrontar as evidências | 1 > 2 | — |
| 2.1 | Comparar escores com os episódios relatados | operação | **Problema:** não há protocolo no sistema para ponderar o relato frente às métricas (C04, Q2); o peso de cada fonte fica a critério da experiência pessoal do médico. **Recomendação:** apresentar a evolução dos escores e dos achados de imagem lado a lado com o relato registrado, com a data de cada episódio. |
| 2.2 | Ponderar risco de acidente e dano da restrição | operação | **Problema:** um erro nos dois sentidos tem consequência relevante: liberar um condutor inapto ou restringir sem necessidade a liberdade do paciente [F] (Entrega 1, item 5.6). |
| 3 | Definir a conduta | 1 / 2 / 3 (conforme o resultado do confronto em 2) | **Problema:** a escolha é feita sob incerteza, sem apoio para justificar o peso dado a cada evidência. |
| 3.1 | Emitir laudo restritivo | operação | **Problema:** exige respaldo legal e normativo (CFM, legislação de trânsito) que o médico precisa conhecer de antemão (C04, Q1) [H]. |
| 3.2 | Solicitar avaliação neuropsicológica | operação | **Decisão observada:** é a alternativa que adia a restrição até haver evidência mais forte (C04, Q3). **Problema:** o paciente continua dirigindo enquanto a avaliação não sai. |
| 3.3 | Manter a autonomia e reavaliar no retorno | operação | **Problema:** a efetividade e a aceitação da conduta só aparecem nos retornos dos meses seguintes (C04, Q5). |
| 4 | Comunicar e registrar a decisão | 1 + 2 (em qualquer ordem) | — |
| 4.1 | Explicar a conduta ao paciente e à filha | operação | **Problema:** a família não usa o sistema (H05); tudo o que ela entende da decisão depende da explicação oral do médico. |
| 4.2 | Registrar decisão e justificativa no prontuário | operação | **Problema:** o conflito entre a avaliação objetiva e a narrativa familiar é registrado em texto livre, sem campo próprio (C04, Q4). **Recomendação:** registrar quais evidências sustentaram a decisão e qual era a divergência, para que o próximo retorno parta desse ponto. |

**Verificação do HTA:**

- O objetivo 0 representa uma meta do usuário? Sim — decidir a conduta sobre a autonomia é o que o Dr. César precisa alcançar na consulta, não uma função do sistema.
- As subtarefas são necessárias e suficientes? Sim — cobrem o que o cenário C04 mostra, da chegada do paciente com a filha ao registro da conduta.
- Os **planos** indicam ordem, alternativa, repetição ou condição? Sim — há planos sequenciais (0 e 2), de seleção (3) e paralelos (1, 1.2 e 4).
- A decomposição parou em nível útil para projeto de interação? Sim — as operações são ações que o médico reconhece; o nível de cliques e teclas fica para o GOMS.

---

## GOMS — T04 Decidir a conduta sobre a autonomia do paciente diante de evidências conflitantes

**Autor(a):** Ana Carolina Lazzuri — 22.123.001-4

Notação da aula: `GOAL`, `METHOD`, `(SEL. RULE: ...)` logo abaixo de cada método, e `OP.` para os operadores, com a numeração herdada do nível acima.

```text
GOAL 0: decidir a conduta sobre a autonomia do paciente
  GOAL 1: reunir as evidências do caso
    OP. 1.1: ouvir o relato da filha sobre os episódios recentes
    GOAL 1.2: revisar os dados do prontuário
      GOAL 1.2.1: consultar os escores de MMSE
        OP. 1.2.1.1: deslocar o cursor para a aba de testes cognitivos
        OP. 1.2.1.2: clicar na aba de testes cognitivos
        OP. 1.2.1.3: ler o escore atual e o da consulta anterior
      GOAL 1.2.2: ler o laudo de MRI
        METHOD 1.2.2.A: ler só a conclusão do laudo no prontuário
        (SEL. RULE: o laudo é conclusivo)
          OP. 1.2.2.A.1: deslocar o cursor para a aba de exames
          OP. 1.2.2.A.2: clicar no laudo de MRI
          OP. 1.2.2.A.3: ler a conclusão do laudo
        METHOD 1.2.2.B: conferir as imagens no visualizador
        (SEL. RULE: o laudo é limítrofe e o médico quer conferir os achados)
          OP. 1.2.2.B.1: deslocar o cursor para "abrir imagens"
          OP. 1.2.2.B.2: clicar em "abrir imagens"
          OP. 1.2.2.B.3: aguardar o carregamento no visualizador DICOM
          OP. 1.2.2.B.4: percorrer os cortes de interesse
          OP. 1.2.2.B.5: comparar o que viu com a conclusão do laudo
  GOAL 2: confrontar as evidências
    OP. 2.1: comparar o escore estável com os episódios relatados
    OP. 2.2: ponderar o risco de acidente e o dano de uma restrição precipitada
  GOAL 3: definir a conduta
    METHOD 3.A: emitir laudo restritivo
    (SEL. RULE: o relato e os dados objetivos indicam risco claro ao dirigir)
      OP. 3.A.1: deslocar o cursor para "documentos"
      OP. 3.A.2: clicar em "novo laudo"
      OP. 3.A.3: digitar a recomendação de suspensão da direção e de supervisão domiciliar
      OP. 3.A.4: digitar a fundamentação clínica
      OP. 3.A.5: clicar em "assinar e imprimir"
    METHOD 3.B: solicitar avaliação neuropsicológica
    (SEL. RULE: o relato e os dados objetivos divergem e não há segurança para restringir)
      OP. 3.B.1: deslocar o cursor para "solicitar exame"
      OP. 3.B.2: clicar em "solicitar exame"
      OP. 3.B.3: selecionar "avaliação neuropsicológica"
      OP. 3.B.4: digitar a justificativa clínica
      OP. 3.B.5: clicar em "enviar pedido"
    METHOD 3.C: manter a autonomia e reavaliar no retorno
    (SEL. RULE: os episódios relatados são isolados e os dados objetivos seguem estáveis)
      OP. 3.C.1: definir o intervalo do retorno
      OP. 3.C.2: orientar a filha sobre os sinais que devem ser observados
  GOAL 4: comunicar e registrar a decisão
    OP. 4.1: explicar a conduta ao paciente e à filha
    GOAL 4.2: registrar a decisão no prontuário
      OP. 4.2.1: deslocar o cursor para o campo de evolução
      OP. 4.2.2: digitar a decisão, as evidências consideradas e a divergência encontrada
      OP. 4.2.3: clicar em "salvar"
      OP. 4.2.4: verificar se a evolução aparece na lista
```

---

## CTT — T04 Decidir a conduta sobre a autonomia do paciente diante de evidências conflitantes

**Autor(a):** Ana Carolina Lazzuri — 22.123.001-4

### Descrição

A árvore mostra a mesma tarefa do ponto de vista da ordem temporal e de quem executa cada parte. **Tarefas abstratas** (nuvem): Decidir a conduta sobre a autonomia, Reunir as evidências, Revisar os dados do prontuário, Definir a conduta, Comunicar e registrar e Registrar no prontuário. **Tarefas do usuário** (pessoa): Ouvir o relato da filha, Confrontar as evidências, Manter a autonomia e reavaliar e Explicar a conduta à família. **Tarefas interativas** (monitor + pessoa): Consultar os escores de MMSE, Ler o laudo de MRI, Emitir laudo restritivo, Solicitar avaliação neuropsicológica e Digitar decisão e justificativa. **Tarefa do sistema** (monitor): Gravar evolução.

Confrontar as evidências é tarefa do usuário: o prontuário mostra os escores e o laudo, mas o relato da filha não está no sistema e nada ajuda a colocar as três fontes lado a lado. A parte mais difícil da tarefa acontece fora do sistema, e só a conclusão volta para ele no registro.

### Diagrama

![CTT T04](https://github.com/rapha661/Alzheimer-XAI-ihc2026/blob/main/assets/05_tarefas/CTT-T04.jpeg)

### Legenda e relações temporais usadas

| Operador/relação | Significado no diagrama | Exemplo no modelo |
|---|---|---|
| `[]>>` ativação com passagem de informação | A segunda tarefa começa depois da primeira e usa a informação produzida por ela | Reunir as evidências `[]>>` Confrontar as evidências; Confrontar as evidências `[]>>` Definir a conduta; Definir a conduta `[]>>` Comunicar e registrar; Digitar decisão `[]>>` Gravar evolução |
| `[]` escolha | As alternativas estão disponíveis, mas quando uma começa as outras são descartadas | Emitir laudo restritivo `[]` Solicitar avaliação neuropsicológica `[]` Manter a autonomia e reavaliar |
| `\|\|\|` concorrência | Podem ser feitas em qualquer ordem ou ao mesmo tempo | Ouvir o relato da filha `\|\|\|` Revisar os dados do prontuário; Explicar a conduta à família `\|\|\|` Registrar no prontuário |
| `\|=\|` independência de ordem | Podem ser feitas em qualquer ordem, mas uma de cada vez | Consultar os escores de MMSE `\|=\|` Ler o laudo de MRI |

---

## Síntese da equipe

Quais problemas de interação, oportunidades e requisitos apareceram a partir das modelagens? Quais tarefas irão para o protótipo e para o teste de usabilidade?

**T01 (Paulo):** as três técnicas apontam o mesmo ponto de ruptura — o parecer do especialista não fica registrado de forma recuperável (HTA 2.2 e 2.3), o que força o médico a um método que exige uma inferência que ele não domina (GOMS, M2) e deixa as etapas críticas fora do sistema (CTT). Requisitos candidatos, ainda hipóteses: [H] o parecer do especialista fica registrado no próprio caso, com os exames e achados que o sustentaram, e aparece quando o caso é retomado (H06); [H] o teste de memória anterior e o atual aparecem lado a lado; [H] a nova conduta fica ligada ao parecer anterior. Tarefa candidata para o protótipo e o teste de usabilidade: retomar um caso e localizar o parecer anterior.

**T02 (Raphael):** as três técnicas chegam ao mesmo ponto — num caso limítrofe, a conclusão do laudo é decidida sem contexto clínico e sem referência objetiva. O HTA mostra três seleções em cadeia (1.3, 2.3 e 3); o GOMS mostra que a regra que leva à frase cautelosa (3.C) é a única satisfeita quando falta a pergunta clínica (1.5.B) e a medida (2.6); o CTT mostra que a avaliação do hipocampo e a decisão da conclusão são tarefas do usuário, sem apoio do sistema, e que a urgência suspende o laudo sem guardar a dúvida. Requisitos candidatos, ainda hipóteses: [H] a pergunta clínica e os dados mínimos acompanham o exame até quem lauda; [H] uma referência objetiva (volume hipocampal com a região destacada) apoia a leitura, sem substituí-la; [H] o laudo permite registrar o que foi avaliado, por qual método e qual dúvida ficou; [H] o estado da avaliação é preservado quando o laudo é suspenso. Tarefa candidata para o protótipo e o teste de usabilidade: avaliar o hipocampo de um caso limítrofe com a referência objetiva e redigir a conclusão.

**T03 (Nathan):** as três técnicas convergem no mesmo ponto de ruptura — não existe conferência de qualidade e completude enquanto o paciente ainda está no setor (HTA 3.1), e é isso que elimina os dois únicos métodos que ainda preservam a qualidade diagnóstica (GOMS, 2.A e 2.B, ambos válidos só com o paciente no aparelho), empurrando o processo para a reconvocação (2.D); o CTT mostra por que a conferência não acontece — validar a qualidade, importar os dados do prontuário e conferir a completude estão tipadas como tarefas do sistema, mas hoje são todas executadas por pessoas, e estimar o tempo restante da janela é tarefa do usuário porque nenhum sistema oferece esse dado. Requisitos candidatos, ainda hipóteses: [H] a conferência de qualidade e completude acontece antes da liberação do paciente, bloqueando o encerramento enquanto houver item obrigatório pendente (H07, F03); [H] as sequências e os dados clínicos obrigatórios do caso são apresentados antes da aquisição; [H] a duração estimada do protocolo aparece contra o tempo restante da janela, já que é esse dado que distingue repetir de encurtar o protocolo (GOMS, 2.A e 2.B); [H] os dados clínicos vêm do prontuário sem redigitação, com confirmação explícita da identidade do paciente; [?] o sistema indica qual sequência é crítica para a suspeita, o que depende de o serviço autorizar o técnico a ajustar o protocolo (C03, Q2). Tarefa candidata para o protótipo e o teste de usabilidade: encerrar a aquisição conferindo qualidade e completude antes de liberar o paciente.

**T04 (Ana Carolina):** as três técnicas mostram o mesmo problema: o confronto entre as evidências (relato da família, escores e laudo de MRI) acontece só na cabeça do médico, sem apoio do sistema. O HTA mostra que o relato é oral e que o MMSE total não indica quais domínios variaram (1.1 e 1.2.1), e que a decisão é tomada sem protocolo para ponderar cada fonte (2.1 e 3). No GOMS, as regras de seleção de GOAL 3 dependem do resultado de GOAL 2, que só tem operadores mentais (comparar e ponderar). No CTT, "Confrontar as evidências" é tarefa do usuário: só a conclusão volta ao sistema, no registro da evolução. O foco é o confronto das evidências, não a avaliação de aptidão para dirigir. Requisitos candidatos, ainda hipóteses: [H] o relato da família fica registrado de forma estruturada, com a data de cada episódio; [H] escores (por domínio) e achados de imagem aparecem lado a lado com o relato; [H] a explicação localizada indica em que regiões da imagem o achado se apoia, ligando o laudo às queixas (H01); [H] a decisão é registrada com as evidências consideradas e a divergência encontrada. Tarefa candidata para o protótipo e o teste de usabilidade: confrontar evidências divergentes de um caso e registrar a conduta com a justificativa.

## Checklist

- [x] Cada integrante produziu ao menos 1 HTA, 1 GOMS e 1 CTT.
- [x] Cada artefato identifica autor e tarefa.
- [x] Diagramas são legíveis e possuem fonte editável quando possível.
- [x] HTA contém planos, não apenas árvore de tópicos.
- [x] GOMS distingue Goals, Operators, Methods e Selection Rules.
- [x] CTT usa operadores temporais e tipos de tarefa coerentes.
- [x] Há texto explicando cada diagrama.
- [ ] Tarefas estão ligadas a cenários/personas na rastreabilidade.
- [x] Em TCC técnico, as tarefas descrevem o que a pessoa faz com a contribuição/resultados, não passos internos do código.
- [x] CRUDs, relatórios, filtros e atividades administrativas foram escolhidos por relevância ao objetivo do usuário.
