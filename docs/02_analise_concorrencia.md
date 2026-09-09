# Entrega 2 — Público-alvo e análise de concorrência

- **Data:** 03/09/2026
- **Status:** 🟨 em andamento  
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
| {{...}} | {{...}} | `../assets/02_concorrencia/...` | {{...}} |

#### Experiência do usuário e opiniões

Use avaliações públicas, relatos, estudos, testes próprios ou outra fonte identificável. Não trate opinião isolada como verdade universal.

#### Preço/modelo de negócio

O Glass Health opera sob um modelo freemium baseado em assinaturas SaaS abordando individualmente o profissional ou institucionalmente o hospital.

| Plano | Preço Mensal | Principais Recursos Incluídos |
|---|---:|---|
| Glass Lite | Gratuito ($0) | Uso limitado de gravação de consultas (scribe) e suporte a decisões clínicas. Inclui anúncios. |
| Glass Starter | $20 / mês | Capacidade expandida de gravação de consultas e suporte clínico aprimorado. |
| Glass Pro | $90 / mês | Transcrição de consultas ilimitada, suporte clínico completo e acesso ao modo de Deep Reasoning (Raciocínio Clínico Profundo). |
| Glass Max | $200 / mês | Tudo do plano Pro + Integração com prontuários eletrônicos (EHR) como Epic, athenahealth, eClinicalWorks e Elation. |

#### Padrões e tendências percebidos

{{...}}

#### Pontos positivos, limitações e lições

| Ponto | Evidência | Implicação para nosso projeto |
|---|---|---|
| {{...}} | {{...}} | {{...}} |

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
| Upload de dados do paciente | Médico faz upload do arquivo de MRI e insere manualmente os scores de MMSE e CDR-SB no portal web | `../assets/02_concorrencia/brainsee_portal.png` |Fluxo de entrada muito próximo ao nosso F01 (abrir caso com MRI + dados clínicos) |
| Geração de score de risco (0–100) | Processamento automático no servidor; resultado no mesmo dia | pendente |  |
| Relatório de saída visualizável/baixável/imprimível | Relatório com o score e guia de interpretação | pendente |  |
| Tutorial e guia de interpretação | Material de apoio fornecido junto ao software, tanto para médicos quanto para pacientes/cuidadores | pendente |  |

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


## 3. Softwares que o público-alvo usa no cotidiano

Analise interfaces que moldam a expectativa do público, mesmo que não sejam concorrentes.

| Software | Por que o público usa | Padrões relevantes | Prints | O que aprender |
|---|---|---|---|---|
| {{...}} | {{...}} | {{...}} | {{link local}} | {{...}} |

## 3.1 Padrões de interface relevantes ao escopo de IHC

Registre somente padrões encontrados nas soluções analisadas e que possam ter relação com objetivos reais da equipe.

| Padrão observado | Produto(s) | Para qual tarefa serve | Vantagem percebida | Risco/limitação | Aplicável ao nosso escopo? |
|---|---|---|---|---|---|
| dashboard | {{...}} | {{...}} | {{...}} | {{...}} | sim/não/talvez |
| relatório | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |
| histórico + filtros | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |
| administração/CRUD | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |
| comparação de resultados | {{...}} | {{...}} | {{...}} | {{...}} | {{...}} |

> O objetivo não é concluir “todo concorrente tem dashboard, então teremos um”. O padrão só será adotado se apoiar uma tarefa rastreável.

## 4. Síntese comparativa da equipe

| Critério | C01 | C02 | C03 | Oportunidade para o projeto |
|---|---|---|---|---|
| Navegação |  |  |  |  |
| Feedback/estado |  |  |  |  |
| Prevenção/recuperação de erro |  |  |  |  |
| Terminologia |  |  |  |  |
| Acessibilidade |  |  |  |  |
| Eficiência |  |  |  |  |

## 5. Recomendações derivadas

Liste recomendações com origem explícita.

- **RC01:** {{recomendação}} — derivada de {{C01/C02/evidência}}.
- **RC02:** {{...}}

## Referências

{{fontes dos produtos, avaliações e literatura}}

## Checklist

- [ ] O mapa inicial de alternativas da Entrega 1 foi revisitado e aprofundado.
- [ ] Hipóteses relevantes sobre mercado/padrões foram atualizadas na rastreabilidade quando surgiram evidências.
- [ ] Há pelo menos uma análise completa por integrante.
- [ ] Cada análise contém prints legíveis da interface.
- [ ] Prints mostram telas/estados relevantes, não apenas logos/homepage.
- [ ] Foram analisados concorrentes e/ou interfaces representativas ao público.
- [ ] Em TCC sem interface original, foram investigadas ferramentas profissionais análogas às atividades do usuário escolhido.
- [ ] Padrões como dashboard, relatório, filtros e CRUD foram analisados como soluções para tarefas, não como requisitos automáticos.
- [ ] Opiniões de UX têm fonte.
- [ ] A síntese compara critérios comuns e produz recomendações.
- [ ] Não há “copiar porque o concorrente faz”; há justificativa de adequação ao público/contexto.
