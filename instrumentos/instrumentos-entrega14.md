# Entrega 14 — Instrumentos do teste de usabilidade

Material usado pelo moderador em cada sessão. Cada integrante conduz um participante, e cada participante faz uma tarefa:

| Participante | Tarefa | Papel no cenário | Moderador |
|---|---|---|---|
| U01 | UT01 | Médico clínico | Paulo |
| U02 | UT02 | Neurologista | Ana Carolina |
| U03 | UT03 | Radiologista | Raphael |
| U04 | UT04 | Técnico em radiologia | Nathan |

Os participantes não são da área da saúde e nunca usaram o protótipo.

## 1. Termo de consentimento

> Você está sendo convidado(a) a participar da avaliação de um protótipo de interface desenvolvido na disciplina de Interação Humano-Computador (CC8122) do Centro Universitário FEI. O protótipo apoia profissionais de saúde na investigação de Alzheimer e usa **apenas dados fictícios**. Ele não é uma ferramenta clínica, e você não precisa saber nada de medicina.
>
> **O que será feito:** você vai fazer uma tarefa no protótipo, falando em voz alta o que pensa, e responder a perguntas curtas antes e depois. A sessão dura cerca de 15 minutos, por sala virtual.
>
> **O que é avaliado:** o protótipo, não você. Não existem respostas certas ou erradas.
>
> **Gravação:** a tela e o áudio serão gravados para a equipe conferir tempos, erros e falas. O vídeo será publicado no YouTube {{como não listado}}, e o link vai aparecer no relatório da disciplina.
>
> **Privacidade:** no relatório, você será identificado(a) só por um código (U01, U02...).
>
> **Participação voluntária:** você pode desistir a qualquer momento, sem precisar justificar, e pedir que seus dados sejam descartados.
>
> Declaro que li as informações acima e concordo em participar. ( ) Sim ( ) Não  
> Autorizo a gravação de tela e áudio e a publicação do vídeo. ( ) Sim ( ) Não
>
> Código do participante: ____ Data: ___/___/2026


## 2. Instruções padronizadas (lidas pelo moderador)

> "Obrigado por participar. Vamos avaliar um protótipo; se algo der errado, a culpa é do protótipo, não sua. Ele foi feito no Figma, então nem tudo é clicável. Vou te ler uma situação, e você vai fazer de conta que é a pessoa dela. Enquanto faz, fale em voz alta o que está pensando, o que procura e o que espera que aconteça. Eu não vou poder te ajudar durante a tarefa, porque queremos ver onde o protótipo atrapalha. Se quiser desistir, é só dizer. No fim, vou te fazer algumas perguntas rápidas."

O moderador abre o protótipo já na tela inicial do perfil da tarefa e compartilha o link com controle de tela.

## 3. Cenários das tarefas

Cada cenário traz a situação, o papel do participante e o objetivo, mas não diz por onde ir na interface.

- **UT01 (U01)** — Você é o Dr. Marcos Andrade, 38 anos, clínico geral. O Sr. Ivo Bittencourt, 71 anos, volta à consulta com o filho, que anda preocupado com a memória do pai. Há algum tempo um neurologista avaliou o caso. O filho quer saber o que o especialista concluiu e quando o pai deve ser avaliado de novo. Veja no sistema e responda a ele.
- **UT02 (U02)** — Você é o Dr. César Andrade de Melo, 52 anos, neurologista. Na consulta do Sr. Roberto Mendes, 76 anos, a filha pergunta: "Doutor, esse programa disse que é Alzheimer?". Veja o que o sistema mostra sobre ele e diga em voz alta o que responderia a ela e por quê.
- **UT03 (U03)** — Você é a Dra. Helena Siqueira Prado, 44 anos, radiologista. Você está laudando a RM do Sr. José Ferraz e ficou com uma dúvida que só o médico que pediu o exame pode responder. Mande a pergunta sem perder o que já escreveu do laudo.
- **UT04 (U04)** — Você é o Bruno Tavares Lima, 32 anos, técnico em radiologia. A Dona Aparecida Souza, 74 anos, acabou de fazer a RM de crânio e o próximo paciente já está esperando. Antes de ela ir embora, confira se está tudo certo com o exame e envie para análise.

**Critérios de sucesso (só para o moderador):**

- **UT01:** informa a conclusão do especialista (comprometimento cognitivo leve, sem elementos fortes para Alzheimer) e a reavaliação em fevereiro de 2027.
- **UT02:** diz que é uma sugestão de apoio, não um diagnóstico, e que a confiabilidade é baixa, citando um motivo da tela (probabilidades próximas, 58% × 42%, ou hipocampo estimado).
- **UT03:** chega a "Pergunta enviada" com o laudo ainda preenchido.
- **UT04:** confirma a identidade, troca o arquivo para a série T1, completa o teste cognitivo e envia.

Tempo-limite de 5 minutos.

## 4. Planilha de observação

O moderador usa o modelo da disciplina (`planilha_observacao_modelo.md`), uma por participante, preenchida a partir da gravação. As definições abaixo foram combinadas antes da coleta:

- **Sucesso total:** chega ao critério de sucesso do cenário sem ajuda do moderador e dentro de 5 minutos.
- **Sucesso parcial:** chega ao resultado, mas falta um item do critério, ou só conclui depois de uma ajuda.
- **Falha:** desiste, passa de 5 minutos ou termina num resultado errado (ex.: no UT03, libera o laudo sem enviar a pergunta; no UT04, descarta o envio).
- **Erro:** cada clique ou caminho que não leva ao objetivo e precisa ser desfeito.
- **Ajuda:** qualquer intervenção do moderador além de repetir o cenário ou dizer "continue falando".
- **Pensar em voz alta:** o participante fala o tempo todo e o moderador só lembra com "continue falando". Tudo que ele disser sobre dúvida, expectativa ou surpresa vai para a planilha, com o minuto da gravação.
- **Registro fiel:** tempo, erros e ajudas são conferidos na gravação depois da sessão, e não são estimados nem ajustados.

## 5. Perguntas de compreensão (UT02 — MU05 e MU06)

Feitas depois da avaliação pós-tarefa. Só vale como acerto a resposta com justificativa coerente, não a repetição do rótulo.

| Pergunta | Resposta esperada |
|---|---|
| O que esse resultado permite concluir? Quem decide o diagnóstico? (MU05) | É uma sugestão de apoio, não um diagnóstico; quem decide é o médico |
| O que significam os 58% e a confiabilidade "Baixa"? (MU06-1) | Probabilidade da classe; a confiabilidade é baixa porque as probabilidades estão próximas e o hipocampo foi estimado |
| O que mostra a área colorida na imagem? (MU06-2) | Onde o modelo se apoiou para a sugestão, não uma lesão |
| O que mostram "Peso de cada modalidade" e "O que mais pesou"? (MU06-3) | Quanto a imagem e os dados clínicos (não os relatos da família) contribuíram para a sugestão |

## 6. Entrevista pós-teste

1. O que foi mais fácil de fazer no protótipo? E o mais difícil?
2. Teve algum momento em que você não sabia o que fazer ou onde clicar? Qual?
3. Algum termo da tela ficou sem sentido para você?
4. O que você mudaria nessa tela?
