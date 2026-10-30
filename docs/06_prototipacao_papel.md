# Entrega 6 — Prototipação em papel

**Data:** 30/10/2026  
**Status:** 🟩 Concluída
**Responsabilidade:** 1 solução integrada por equipe

## Objetivo da atividade

Externalizar rapidamente ideias de interação em baixa fidelidade para explorar alternativas antes de investir em detalhes visuais. O valor da atividade está no **ciclo construir → simular → observar → revisar**, não na beleza do desenho.

## Forma do protótipo nesta entrega

A equipe já tinha uma interface navegável, construída a partir das Entregas 1 a 5, e por isso documentou o protótipo com **prints da plataforma** em vez de desenhos em papel:


## 1. Escopo do protótipo

**Personas:** P01 — Dr. Marcos Andrade (médico clínico, persona prioritária); P02 — Dr. César Andrade de Melo (neurologista); P04 — Bruno Tavares Lima (técnico em radiologia, na entrada do caso). P03 — Dra. Helena Siqueira Prado (radiologista) é atendida só na consulta do mapa de atenção e da volumetria.  
**Cenários/tarefas cobertos:** C02/T01, C04/T04, C03/T03 e, de forma parcial, C01/T02 (ver tabela abaixo).  
**Objetivos principais:** compreender a sugestão do modelo e calibrar a confiança pela evidência; registrar uma decisão justificada e rastreável; enviar um exame com os dados que o modelo usa; perceber quando a análise está em andamento ou falhou.

### Cobertura das tarefas da Entrega 5

| Tarefa | O que o protótipo cobre | O que não cobre |
|---|---|---|
| T01 — Retomar a conduta de um paciente já avaliado por especialista (P01/C02) | Localizar o caso (HTA 2.1); registrar a decisão com justificativa, nome e horário, sem possibilidade de edição (HTA 4), para que a próxima retomada encontre o raciocínio | Não há onde registrar nem consultar o **parecer do especialista**, nem histórico de exames anteriores (HTA 2.2 e 2.3). É a principal lacuna do protótipo frente à T01 (H06) |
| T04 — Decidir a conduta diante de evidências conflitantes (P02/C04) | Ver a sugestão com a faixa de confiança e os dados que entraram no modelo; registrar "concordo parcialmente" ou "discordo" com justificativa (HTA 3 e 4.2) | O relato da família só existe como observação em texto livre, sem data por episódio; os testes cognitivos não aparecem; não há comparação lado a lado (HTA 1 e 2) |
| T03 — Realizar a aquisição com qualidade diagnóstica e dados completos (P04/C03) | Envio do exame com campos obrigatórios validados antes do envio; estado de falha quando a série não é a esperada (GOMS T03, GOAL 3 e 4) | A falha da série só aparece **depois** do envio (P09), o que reproduz o problema da H07; não há conferência de qualidade antes de liberar o paciente |
| T02 — Laudar uma RM com atrofia limítrofe (P03/C01) | Consulta do mapa de atenção com opacidade ajustável e da volumetria do hipocampo em relação ao volume intracraniano | Não há redação de laudo nem pergunta clínica junto do exame (H08) |

## 1.1 Possíveis famílias de interface

Das famílias sugeridas, o protótipo usa só as que as tarefas pedem:

| Família | Onde aparece | Tarefa que justifica |
|---|---|---|
| Entrada/seleção de dados com validação | P07 Novo caso | T03 — enviar o exame com os dados que o modelo usa |
| Acompanhamento de execução | P08 Processando, P09 Falha | T03 — saber se a análise terminou ou falhou |
| Relatório/resultados com explicação | P03, P04, P06 | T01 e T04 — interpretar a sugestão antes de decidir |
| Histórico com busca e filtros | P02 Casos | T01 — localizar o caso do paciente que voltou |
| Auditoria | P05e e P10 (decisão com nome e horário, sem edição) | T01 e T04 — registrar a decisão e a justificativa |

Não foram criados dashboard, administração de usuários nem comparação. Os indicadores de P02 funcionam como **filtro** da lista, e não como painel de monitoramento. A comparação seria necessária para T01 e T04 e está registrada como lacuna.

## 2. Fluxos escolhidos

| Fluxo | Tarefa/objetivo | Por que foi priorizado |
|---|---|---|
| PF01 | Interpretar a sugestão de um caso e registrar a decisão (P02 → P03 → P05 → P05d → P05e → P06) | É o objetivo principal do usuário prioritário (Entrega 1, item 7.3) e cobre o registro da decisão de T01 (HTA 4) e T04 (HTA 4.2) |
| PF02 | Decidir em um caso de confiança baixa e registrar a divergência (P02 → P04 → P05 com aviso → P05e) | É onde a confiança calibrada é testada (H03): a interface precisa frear um "concordo" automático; é o caso de evidências que não fecham, como em T04 |
| PF03 | Enviar um novo caso e acompanhar a análise (P02 → P07 → P07b → P08 → P03) | É a entrada do fluxo (T03, GOMS GOAL 3 e 4) e mostra o estado de processamento |
| PF04 | Lidar com uma análise que falhou (P02 → P09 → P07) | Reproduz a ruptura do C03: o problema da série só aparece depois do envio (H07) |
| PF05 | Localizar um caso já decidido e consultar a decisão (P02 → P10 → P06) | É o primeiro passo da retomada de T01 (HTA 2.1) |

## 3. Telas e estados

### Mapa de navegação

![Mapa de navegação](../assets/06_prototipos/mapa_navegacao.svg)

### Índice das telas e estados

| ID | Tela/estado | Controles que mudam o estado | Tarefa, decisão ou informação que justifica |
|---|---|---|---|
| P01 | Entrar | "Entrar"; "Preencher" (conta de demonstração) | A decisão é gravada com o nome de quem decidiu (auditoria); estação de trabalho compartilhada (Entrega 3, P01) |
| P01b | Senha incorreta | Corrigir e tentar de novo | Estado de erro do acesso |
| P02 | Casos | Indicadores (filtram a lista), busca por nome ou prontuário, filtro de status, "Novo caso", clicar no caso | T01 HTA 2.1 / GOMS GOAL 2.1 — abrir o caso do paciente |
| P02b | Lista filtrada (aguardando revisão) | "Limpar" | Fila do que falta revisar |
| P02c | Nenhum caso encontrado | "Limpar filtros" | Estado vazio da busca |
| P03 | Caso com sugestão | Mostrar/ocultar mapa (tecla O), opacidade do mapa, termos do glossário, "Relatório", "Registrar decisão" | T01 e T04 — interpretar a sugestão: número com faixa de confiança, de onde veio a sugestão, limites do modelo e dados que entraram |
| P03b | Mapa de atenção oculto | Mostrar mapa | Ver a imagem sem a sobreposição (Entrega 2, RC01) |
| P03c | Termo do glossário aberto | Passar o mouse no termo | Entender um termo técnico sem sair da tela (F08) |
| P04 | Caso com confiança baixa | Os mesmos de P03 | T04 — sugestão que não fecha: aviso de confiança baixa e volumetria "imputada" |
| P05 | Sua decisão | Concordo / Concordo parcialmente / Discordo; conclusão; justificativa; "Revisar e registrar" | T01 HTA 4 e T04 HTA 4.2 — registrar a decisão com o raciocínio |
| P05b | Campos pendentes na decisão | Preencher os campos | Não registrar uma decisão sem conclusão ou justificativa |
| P05c | "Concordo" em caso de confiança baixa | Rever a escolha | H03 — evitar concordância automática com uma sugestão fraca |
| P05d | Confirmar registro | "Voltar e revisar"; "Registrar decisão" | A decisão não pode ser desfeita: o médico confere antes |
| P05e | Decisão registrada | "Relatório" | Verificação do resultado: o médico vê que a decisão foi gravada, com nome e horário (GOMS T01, OP. 4.4) |
| P06 | Relatório | Imprimir / salvar PDF | Levar a sugestão e a decisão para o prontuário |
| P07 | Novo caso | Campos do paciente, RM (arrastar ou selecionar), dados clínicos, "Enviar para análise" | T03 GOMS GOAL 3 e 4 — completar os dados e entregar o exame |
| P07b | Novo caso com campos pendentes | Corrigir os campos indicados | Impedir o envio de um caso incompleto |
| P08 | Analisando o exame | Nenhum (o sistema avisa quando termina) | Acompanhar a análise; o usuário pode sair da tela |
| P09 | Falha na análise | Nenhum na própria tela: para reenviar, o usuário volta a "Casos" e cria um novo caso | T03 — a série enviada não serve; mostra o motivo |
| P10 | Caso concluído | "Relatório" | T01 — consultar uma decisão já registrada |

### P01 — Entrar

![P01 Entrar](../assets/06_prototipos/p01a_login.png)

**P01b — senha incorreta**

![P01b Senha incorreta](../assets/06_prototipos/p01b_login_erro.png)

### P02 — Casos

![P02 Casos](../assets/06_prototipos/p02a_lista_casos.png)

**P02b — lista filtrada por "Aguardando revisão"** (clique no indicador)

![P02b Lista filtrada](../assets/06_prototipos/p02b_lista_filtrada.png)

**P02c — busca sem resultado**

![P02c Nenhum caso encontrado](../assets/06_prototipos/p02c_busca_vazia.png)

### P03 — Caso com sugestão

Primeira tela do caso: à esquerda, o corte da RM com o mapa de atenção; à direita, a sugestão com a faixa de confiança, de onde veio a sugestão (imagem × dados clínicos) e os limites do modelo.

![P03 Caso com sugestão](../assets/06_prototipos/p03a_caso_sugestao.png)

Página inteira do caso, com os dados enviados ao modelo e a seção de decisão:

![P03 Página inteira](../assets/06_prototipos/p03_caso_pagina_inteira.png)

**P03b — mapa de atenção oculto**

![P03b Mapa oculto](../assets/06_prototipos/p03b_mapa_oculto.png)

**P03c — termo do glossário**

![P03c Glossário](../assets/06_prototipos/p03c_glossario.png)

### P04 — Caso com confiança baixa

![P04 Confiança baixa](../assets/06_prototipos/p04a_confianca_baixa.png)

### P05 — Sua decisão

![P05 Sua decisão](../assets/06_prototipos/p05a_decisao_vazia.png)

**P05b — campos pendentes**

![P05b Campos pendentes](../assets/06_prototipos/p05b_decisao_erros.png)

**P05c — "Concordo" num caso de confiança baixa**

![P05c Aviso de confiança baixa](../assets/06_prototipos/p05c_alerta_confianca_baixa.png)

**P05d — confirmar registro**

![P05d Confirmar registro](../assets/06_prototipos/p05d_confirmacao.png)

**P05e — decisão registrada**

![P05e Decisão registrada](../assets/06_prototipos/p05e_decisao_registrada_pagina.png)

### P06 — Relatório

![P06 Relatório](../assets/06_prototipos/p06_relatorio.png)

### P07 — Novo caso

![P07 Novo caso](../assets/06_prototipos/p07a_novo_caso.png)

**P07b — campos pendentes**

![P07b Campos pendentes](../assets/06_prototipos/p07b_novo_caso_erros.png)

**P07 preenchido, com o exame de exemplo anexado**

![P07 Preenchido](../assets/06_prototipos/p07c_novo_caso_preenchido.png)

### P08 — Analisando o exame

![P08 Analisando o exame](../assets/06_prototipos/p08_processando.png)

### P09 — Falha na análise

![P09 Falha na análise](../assets/06_prototipos/p09_falha.png)

### P10 — Caso concluído

![P10 Caso concluído](../assets/06_prototipos/p10_concluido_pagina.png)

### Revisão da equipe sobre as telas

Antes da simulação, a equipe comparou as telas com as Entregas 4 e 5. Os pontos abaixo são da própria equipe e não substituem a observação da seção 4.

| Tela/ação | Problema observado | Origem na documentação | Consequência para o design |
|---|---|---|---|
| P03, P10 | Não há onde registrar nem consultar o parecer do especialista, nem exames anteriores do mesmo paciente | T01, HTA 2.2 e 2.3; H06 | Incluir o parecer do especialista no caso, com os exames que o sustentaram, sem reduzir a solução a "reabrir caso" (feedback da Entrega 5) |
| P03, P04 | O relato da família aparece só como "Observações (fora do modelo)", em texto livre e sem data | T04, HTA 1.1 e 2.1 | Registrar os episódios relatados com data e mostrá-los ao lado dos dados objetivos |
| P07 → P09 | A série errada só é apontada depois do envio e do processamento | T03, H07 | Verificar o tipo de série no momento do envio, antes do processamento |
| P09 | A tela explica a falha, mas não oferece nenhuma ação: para reenviar, o usuário volta à lista e cria o caso de novo, redigitando os dados | T03, GOMS GOAL 3 (transcrição sujeita a erro) | Oferecer "Reenviar exame" no próprio caso, mantendo os dados já preenchidos |
| P02, menu do usuário | A conta de demonstração se chama "Dra. Helena Prado", mesmo nome da persona radiologista (P03), mas age como médica que decide | Entrega 3, P03 | Renomear a conta de demonstração para a persona P01 (Dr. Marcos Andrade) |
| P03 (caso Ivo) | A observação diz que o esquecimento foi relatado "pela esposa"; no C02 quem relata é o filho | Entrega 4, C02 | Alinhar o texto do caso de demonstração ao cenário |
| P07 | Os testes cognitivos (MMSE, MoCA) não aparecem em lugar nenhum, porque não entram no modelo; T01 e T04 dependem da comparação desses escores | T01 HTA 1.2; T04 HTA 1.2.1 | Mostrar os escores como contexto clínico, separados do que entra no modelo |

## 4. Simulação / walkthrough

Realize uma simulação com uma pessoa que não participou da elaboração dessas telas. Um colega pode ser usado **para essa iteração formativa**, mas isso não substitui os participantes finais da Entrega 14.

### Participante e condução

- **Participante:** Nathan Gabriel da Fonseca Leite, integrante da equipe. Não participou da construção das telas do front-end e teve o primeiro contato com a interface nesta sessão.
- **Papel assumido:** médico clínico (P01 — Dr. Marcos Andrade), com pouco tempo de consulta, que precisa interpretar a sugestão sem tratá-la como diagnóstico.
- **Limitação:** Nathan conhece o domínio e as personas do projeto e não é profissional de saúde. A sessão vale como iteração formativa: não valida as hipóteses com usuários reais (Entrega 7) nem substitui os participantes da Entrega 14.


### Roteiro da sessão

- **Duração:** cerca de 20 minutos.
- **Abertura:** "Imagine que você é um médico clínico e tem pouco tempo de consulta. A ferramenta apresenta uma sugestão e explica as evidências, mas a decisão final é sua. Use a interface como achar mais natural e diga em voz alta o que estiver pensando."
- **Condução:** a equipe apresentou as tarefas e registrou ações, dúvidas e comentários. Durante a execução, ninguém explicou onde clicar nem antecipou o resultado esperado.

| # | Tarefa apresentada a Nathan | Fluxo | O que observar |
|---|---|---|---|
| 1 | "O Sr. Ivo voltou à consulta. Encontre o caso dele e explique o que o modelo sugere e qual é o nível de confiança." | PF05 → PF01 | Se localiza o caso; se diferencia a probabilidade da faixa de confiança; se consulta os limites |
| 2 | "Analise o caso da Maria Silva e registre a conduta que você considera adequada." | PF02 | Se percebe a baixa confiança e a volumetria imputada; se o aviso influencia a decisão; se entende o registro irreversível |
| 3 | "Cadastre um novo caso usando o exame de exemplo e acompanhe o processamento." | PF03 | Se entende os campos obrigatórios, o que entra no modelo e o que fazer durante a espera |
| 4 | "O caso do José Carlos aparece sem sugestão. Descubra o que aconteceu e como você resolveria." | PF04 | Se compreende a falha e identifica o próximo passo sem ajuda |

### Registro da sessão

As falas entre aspas são de Nathan, registradas durante a sessão.

| Etapa | Ação e fala de Nathan | Observação do moderador | Resultado |
|---|---|---|---|
| **Tarefa 1 — localizar o caso** | Nathan olha a lista e comenta: "O Ivo está aqui em cima. Acho que nem preciso pesquisar." Abre o registro e diz: "Encontrei o exame. Vou olhar o resultado antes de decidir." | O caso está na primeira linha da lista; a busca por nome ou prontuário também está disponível. | **Concluída sem ajuda.** A localização do caso é direta e atende ao HTA T01 2.1. |
| **Tarefa 1 — interpretar a sugestão** | Ao abrir o caso, Nathan comenta: "Noventa e quatro por cento… parece bem alto. Mas onde vejo se o modelo está seguro disso?" Depois de procurar no card, encontra a faixa de confiança: "Ah, está aqui no canto. Eu olharia isso junto com os 94%, não separado." | O percentual é o elemento de maior destaque; a faixa de confiança aparece menor e afastada, no canto do card. | **Concluída com hesitação.** Há risco de o usuário se prender ao percentual e não perceber a confiança calibrada. |
| **Tarefa 1 — conferir os limites** | Nathan rola um pouco a tela e diz: "Certo, aqui explica o que o modelo não consegue avaliar. Isso muda como eu interpreto o resultado." | Os limites aparecem abaixo de "De onde veio a sugestão" e permanecem visíveis na captura de tela utilizada. | **Concluída.** Manter os limites próximos da sugestão. |
| **Tarefa 2 — avaliar baixa confiança** | Ao abrir Maria Silva, Nathan comenta: "Aqui está diferente. As probabilidades estão próximas e ainda tem um dado imputado. Eu não trataria isso como uma resposta fechada." | A tela sinaliza baixa confiança pela faixa vermelha, pela mensagem textual e pelo aviso sobre volumetria incompleta. | **Concluída.** Os sinais de alerta são percebidos; manter a sinalização redundante. |
| **Tarefa 2 — registrar a decisão** | Nathan seleciona "Concordo parcialmente" e comenta: "Quero deixar claro que estou considerando a queixa e os outros dados, não só o resultado." Ao visualizar a confirmação, pergunta: "Depois que eu registrar, não consigo corrigir?" | A interface exige conclusão e justificativa, e informa que o registro não pode ser desfeito. | **Concluída com confirmação de entendimento.** A irreversibilidade está indicada, mas deve continuar explícita antes da gravação. |
| **Tarefa 3 — cadastrar novo caso** | Nathan abre "Novo caso" e diz: "Vou preencher os dados do paciente e anexar a ressonância." Ao encontrar os campos obrigatórios, comenta: "Se eu esquecer alguma coisa, o sistema aponta onde está faltando?" | O formulário valida os campos e leva o foco ao primeiro erro. O link "Usar exame de exemplo" é pequeno dentro da área de envio. | **Concluída.** A validação é compreensível; o acesso ao exame de exemplo poderia ter mais destaque na demonstração. |
| **Tarefa 3 — entender os dados do modelo** | Nathan lê o aviso sobre MMSE e MoCA: "Então esses testes não são usados pelo modelo? Seria bom eu conseguir registrar o resultado deles em outro lugar para considerar na avaliação clínica." | O formulário explica que os testes cognitivos não entram no modelo, mas não oferece campo para registrá-los como contexto. | **Concluída com ressalva.** Confirmada a necessidade de separar contexto clínico dos dados de entrada do modelo. |
| **Tarefa 3 — acompanhar o processamento** | Durante a espera, Nathan comenta: "Está processando. Posso adiantar outra coisa e voltar quando terminar?" | P08 informa que a análise está em andamento, permite sair da tela e apresenta aviso quando termina. | **Concluída sem ajuda.** O estado de processamento comunica o que está acontecendo. |
| **Tarefa 4 — entender a falha** | Nathan abre o caso de José Carlos e diz: "A análise falhou. Mas o que significa essa parte de T1 volumétrica e skull strip? Eu teria que perguntar para o pessoal da ressonância." | A mensagem apresenta termos técnicos que podem não fazer parte do vocabulário de um médico clínico. | **Concluída parcialmente.** Nathan identifica que houve um problema no exame, mas não entende com clareza a causa nem a orientação. |
| **Tarefa 4 — decidir o próximo passo** | Nathan procura uma ação e comenta: "Não tem um botão para corrigir ou mandar o exame de novo? Vou voltar para a lista… mas vou ter que cadastrar tudo outra vez?" | P09 não oferece ação de reenvio; é necessário voltar à lista e iniciar um novo cadastro. | **Não concluída de forma direta.** O fluxo exige redigitação e deve oferecer reenvio no próprio caso. |

### Síntese do teste

A sessão indica que Nathan consegue localizar casos, interpretar os principais elementos da sugestão, registrar uma decisão e cadastrar um exame. As maiores dificuldades aparecem quando a interface precisa comunicar **o grau de confiança** e, principalmente, orientar o usuário diante de uma **falha técnica**.

Os pontos que merecem revisão são:

1. **Confiança:** aproximar visualmente a faixa de confiança do percentual da sugestão, para que os dois sejam interpretados em conjunto.
2. **Limite do modelo:** quando a classificação for binária, deixar claro junto da sugestão que o modelo não avalia comprometimento leve.
3. **Justificativa da decisão:** em casos de baixa confiança, solicitar que a justificativa indique qual evidência clínica sustenta a concordância.
4. **Falha na análise:** substituir termos técnicos isolados por uma explicação em linguagem clínica e indicar o próximo passo.
5. **Reenvio:** disponibilizar a ação "Reenviar exame" no próprio caso, mantendo os dados já preenchidos.
6. **Contexto clínico:** oferecer espaço para registrar MMSE e MoCA sem misturá-los às entradas do modelo.

Os achados vêm de um único participante da própria equipe, sem formação em saúde. Eles orientam a próxima iteração e precisam ser confrontados com médicos na coleta da Entrega 7 e na observação da Entrega 14.

### Revisão da primeira versão (23/10)

Antes da versão publicada, a equipe revisou a primeira versão (commit `f25089a`) em duas frentes:
- comparar cada tela com o que o modelo do TCC realmente devolve (repositório `tcc-alzheimer-diagnosis-multimodal-xai`, branch `codigo-treinamento`);
- comparar cada tela com as tarefas da Entrega 5.

**Primeira versão (23/10), antes da revisão:**

| Painel | Caso | Novo caso |
|---|---|---|
| ![v1 Painel](../assets/06_prototipos/v1_painel.png) | ![v1 Caso](../assets/06_prototipos/v1_caso.png) | ![v1 Novo caso](../assets/06_prototipos/v1_novo_caso.png) |

Página inteira do caso na primeira versão:

![v1 Página do caso](../assets/06_prototipos/v1_caso_pagina.png)

| Observação | Tela/ação | Evidência | Consequência para o design |
|---|---|---|---|
| O visualizador oferecia três planos (coronal, axial, sagital) e listava regiões nomeadas ("hipocampo esquerdo — influência alta") | Caso → visualizador e "Regiões destacadas pelo mapa de atenção" | O Grad-CAM do modelo é de **um corte axial 2D**, em grade 7×7, sem rótulo anatômico (`gradcam.py`) | A explicação não pode afirmar mais do que o modelo calcula: mostrar só o corte axial com o mapa, sem nomear regiões (confiança calibrada, H03) |
| A aba "Fatores" mostrava a contribuição de cada variável (volume do hipocampo, MoCA, MMSE…) | Caso → aba Fatores | O SHAP do modelo só separa **imagem × dados clínicos**; o ramo tabular é uma Random Forest (§5.2 do README do modelo) | Trocar a lista de fatores pelo peso de cada modalidade ("De onde veio a sugestão") |
| A aba "Biomarcadores" mostrava percentis normativos ("percentil 2 para a idade") | Caso → aba Biomarcadores | O pipeline não tem referência normativa | Mostrar o volume e a proporção em relação ao volume intracraniano, sem percentil |
| MMSE e MoCA eram pedidos no envio e apareciam entre os fatores da sugestão | Novo caso → etapa "Dados clínicos"; Caso → Fatores | O rótulo da ADNI é derivado desses testes; usá-los como entrada faria o modelo "ver a resposta" | Retirar os testes cognitivos do que entra no modelo e avisar no formulário. Como T01 e T04 dependem desses escores, eles devem voltar como **contexto clínico** separado (seção 3) |
| Perfis (técnico, radiologista, neurologista), encaminhamento, parecer estruturado, trilha de auditoria e painel com gráficos dependiam de dados que nenhum serviço fornece | Painel; Caso → "Encaminhar" e "Parecer de Neurologia" | O repositório do modelo tem só o código de treino; essas funções exigiriam um backend de aplicação inteiro além da inferência | Reduzir o escopo ao que o backend sustenta. Com isso, o **parecer do especialista (T01)** e a **conferência antes da liberação (T03)** voltam a ser lacunas, registradas na seção 3 |
| O painel inicial reunia indicadores, gráficos e listas que não respondiam a uma tarefa da Entrega 5 | Painel | Checklist desta entrega: "não criar dashboard apenas para parecer completo" | Manter só a lista de casos, com indicadores que funcionam como filtro |

## 5. Alterações após a simulação

A revisão abaixo separa as mudanças já implementadas na passagem da primeira versão (23/10) para a versão publicada (28/10) das alterações propostas a partir da sessão com Nathan. Os prints de "Depois" são as telas atuais da seção 3; os itens marcados como **próxima versão** ainda não devem ser entendidos como implementados.

| Antes | Problema identificado | Depois / alteração | Origem e justificativa |
|---|---|---|---|
| Visualizador com três planos e regiões anatômicas nomeadas, com nível de influência | A interface mostrava uma explicação mais precisa do que a que o modelo produz | **Implementado:** corte axial com mapa de atenção, opacidade ajustável e tecla O (P03, P03b) | Revisão técnica da primeira versão: a explicação precisa corresponder ao que o modelo calcula; uma explicação inventada leva a confiança indevida (H03) |
| Aba "Fatores" com SHAP por variável clínica | O modelo não separa a contribuição de cada variável | **Implementado:** card "De onde veio a sugestão", com o peso da imagem e dos dados clínicos (P03) | Revisão técnica: o SHAP disponível só separa as duas modalidades |
| Aba "Biomarcadores" com percentil normativo | Não há referência normativa para calcular o percentil | **Implementado:** "Dados enviados ao modelo", com volume e proporção do volume intracraniano, e aviso "Imputado" quando o dado falta (P03, P04) | Revisão técnica: mostrar o que o modelo de fato recebeu, inclusive o que foi estimado |
| MMSE e MoCA como entrada do modelo | Os testes que geram o rótulo entravam como dado de entrada | **Implementado:** formulário avisa que os testes cognitivos não entram no modelo (P07) | Revisão técnica: evitar que o modelo "veja a resposta". Os escores ainda precisam voltar como contexto clínico |
| Envio em 4 etapas com checklist do técnico (identidade, T1 volumétrica, cobertura, artefato) | O fluxo dependia do perfil do técnico, que saiu do escopo | **Implementado:** formulário único, com validação antes do envio (P07, P07b) | Revisão técnica: o formulário pede só o que o modelo usa. A conferência antes da liberação (T03, H07) fica como lacuna |
| Painel com indicadores, gráficos e pareceres registrados | Informações sem tarefa correspondente | **Implementado:** lista de casos com indicadores que filtram, busca e filtro de status (P02) | Revisão técnica: cada tela precisa responder a uma tarefa; o painel não respondia a nenhuma |
| Perfis, encaminhamento, parecer estruturado e trilha de auditoria | Dependiam de um backend de aplicação inexistente | **Implementado parcialmente:** uma única conta; decisão registrada com nome e horário, sem edição (P05e, P10) | Revisão técnica: o registro da decisão sustenta T01 (HTA 4) e T04 (HTA 4.2). O parecer do especialista volta como prioridade quando houver backend de aplicação (H06) |
| Glossário em página própria | Exigia sair do caso para entender um termo | **Implementado:** glossário como dica no próprio termo (P03c) | Revisão técnica: entender o termo sem perder o contexto do caso (F08) |
| Faixa de confiança pequena, no canto do card (P03) | Nathan primeiro leu o percentual e só depois procurou a faixa de confiança | **Próxima versão:** faixa de confiança ao lado do número, com o mesmo destaque | Sessão com Nathan, tarefa 1; confiança calibrada (H03; Entrega 2, RC03 e RC10) |
| "Concordo" em confiança baixa só mostra um aviso de uma linha (P05c) | Nathan percebeu o aviso, mas a interface ainda permite registrar sem relacionar a justificativa à evidência clínica | **Próxima versão:** em confiança baixa, a justificativa precisa citar a evidência clínica que sustenta a concordância | Sessão com Nathan, tarefa 2; evitar concordância automática com uma sugestão fraca (H03) |
| Limite "não avalia comprometimento leve" só no card de limites (P04) | A informação pode passar despercebida quando o usuário concentra a atenção na sugestão | **Próxima versão:** quando o modelo for binário, avisar junto da sugestão | Sessão com Nathan, tarefa 2; Entrega 2, RC11 |
| Mensagem de falha técnica e sem ação (P09) | Nathan não compreendeu os termos técnicos e não encontrou como corrigir o envio | **Próxima versão:** mensagem em linguagem clínica e botão "Reenviar exame", mantendo os dados | Sessão com Nathan, tarefa 4; T03 e H07, evitar redigitação e reconvocação |
| Testes cognitivos sem lugar na interface (P07) | Nathan entendeu que MMSE e MoCA não entram no modelo, mas sentiu falta de um local para registrá-los como contexto | **Próxima versão:** campo de contexto clínico, separado do que entra no modelo | Sessão com Nathan, tarefa 3; T01 HTA 1.2 e T04 HTA 1.2.1 |

## Checklist

- [x] O protótipo cobre tarefas relevantes da Entrega 5.
- [x] Cada tela/estado pode ser justificado por uma tarefa, decisão ou informação necessária.
- [x] O projeto não criou dashboard/CRUD/login apenas para parecer “completo”.
- [x] Telas/estados estão numerados e navegáveis na documentação.
- [x] Há pelo menos uma simulação/walkthrough documentado.
- [x] Críticas não foram apenas listadas: geraram decisão de revisão.
