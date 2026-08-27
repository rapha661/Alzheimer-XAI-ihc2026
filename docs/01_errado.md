# Entrega 1 — Conhecendo o problema

- **Data:** 13/08/2026  
- **Status:** 🟩 Concluída
- **Responsabilidade:** Desenvolver uma interface para intermediar o uso do modelo de inteligência artificial explicável que visa auxiliar no diagnóstico da doença de alzheimer por profissionais da área da saúde.

## Objetivo da atividade

Delimitar o produto, os usuários, os benefícios, as funcionalidades e o **contexto de uso** antes de iniciar decisões de interface. Esta entrega funciona como contrato de escopo para as demais.

## 1.1 Membros da equipe

| Nome completo | Matrícula | GitHub |
|---|---:|---|
| Paulo Hudson | 22.222.013-9 | @Paulo Hudson
| Ana Carolina | 22.123.001-4 | @lazzuriana08
| Raphael | 22.123.014-7 | @rapha661
| Nathan | 22.123.028-7 | @NathanGbl

## 1.2 Título original do TCC/projeto

M-XAI: Um framework multimodal de inteligência artificial explicável para diagnóstico da doença de alzheimer

## 1.3 Orientador(a)

Murillo Freitas Bouzon

## 1.4 Está previsto desenvolver interface?

- [X] Sim
- [ ] Não

**Justificativa:**

O projeto tem como intuíto desenvolver uma aplicação web para intermediar a utilização do modelo de inteligência artificial. Por meio da aplicação, o profissional de saúde poderá fornecer dados do paciente, como imagens de exames e informações clínicas, e consultar o resultado produzido pelo modelo juntamente com sua respectiva explicação.

A interface será responsável por apresentar as etapas de envio dos dados, processamento e consulta do resultado de forma adequada ao contexto de utilização por profissionais da área da saúde.

## 1.5 Objetivo do trabalho

Descreva o **resultado que o projeto pretende alcançar**, não apenas a tecnologia a utilizar.

O projeto tem como objetivo desenvolver uma aplicação web que permita a profissionais da área da saúde utilizar um modelo multimodal de inteligência artificial explicável para auxiliar na análise de casos relacionados à doença de Alzheimer.

O sistema deverá permitir que o médico:

forneça dados clínicos do paciente;
envie imagens médicas, como imagens de ressonância magnética ou tomografia, quando aplicável ao modelo;
acompanhe o processamento da solicitação;
consulte a classificação produzida pelo modelo;
visualize os principais fatores considerados pelo modelo para produzir a classificação.

A interface será desenvolvida considerando que o usuário possui conhecimento médico, mas não necessariamente conhecimento em inteligência artificial ou programação. Dessa forma, os elementos necessários para executar cada tarefa deverão ser apresentados utilizando termos compreensíveis dentro do contexto médico e seguindo uma sequência compatível com o fluxo de análise do caso.

O resultado apresentado pelo sistema terá caráter de apoio à decisão, não substituindo a avaliação e a decisão final do profissional de saúde.

## 1.6 Produto final

O que será efetivamente entregue? Ex.: aplicação Web, aplicativo móvel, dashboard, dispositivo interativo, serviço com interface, ferramenta de apoio etc.

Uma aplicação web.

## 1.7 Usuário final

Quem interage diretamente com o produto? Diferencie usuário final, cliente, administrador, especialista e demais stakeholders quando necessário.

<p>Usuário final: Médico</p>
<p>Cliente: Hospital</p>
<p>Administrador: Equipe de TI do hospital</p>
<p>Especialista: Pesquisadores da área médica</p>
<p>Demais stakeholders: Redes de hospitais e convênios</p>

## 1.8 Benefícios para o usuário

| Benefício esperado | Problema/necessidade associada | Para qual usuário |
|---|---|---|
| Facilitar o uso do modelo por trás da interface | A impossibilidade de profissionais da área da saúde de utilizar tecnologias que não são de seu campo de conhecimento | Profissionais da área da saúde |

## 1.9 Funcionalidades — visão do usuário

Escreva funcionalidades como capacidades observáveis pelo usuário, não como detalhes de backend.

| ID | Funcionalidade | Objetivo do usuário atendido | Prioridade inicial |
|---|---|---|---|
| F01 | Cadastro/login | Poder acessar o sistema | alta |
| F02 | Upload de arquivos | Poder enviar dados do paciente (imagens/planilhas) | alta |
| F03 | Visualização de diagnóstico | Obter resultado do diagnóstico com sua justificativa | alta |
| F04 | Acompanhamento das solicitações | Acompanhar as solicitações de classificações feitas | Média |

## 1.10 Tecnologias e ferramentas previstas

| Camada/uso | Tecnologia/ferramenta | Por que foi escolhida | Impacto potencial na interação |
|---|---|---|---|
| Interface | **React** | Reutilização e manutenção da interface web. | Responsividade e atualização dos elementos durante as tarefas. |
| Backend | **Node.js** | Desenvolvimento do servidor e criação de APIs utilizando JavaScript. | Processamento das solicitações e comunicação entre as camadas. |
| Banco de dados | **Banco de dados relacional** | Escolhido devido a sua estruturação de armazenamento dos dados da aplicação. | Impacta no tempo de acesso aos dados (pode variar conforme a conexão do usuário) e a disponibilidade do serviço utilizado. |

### Interface — React

O **React** será utilizado para o desenvolvimento da interface da aplicação web. A tecnologia permite estruturar a aplicação por meio de componentes reutilizáveis, facilitando a organização, manutenção e evolução das telas.

Na interação com o usuário, o React será responsável pela apresentação dos elementos utilizados nas principais tarefas, como:

- Autenticação;
- Inserção de dados;
- Seleção e envio de arquivos;
- Acompanhamento das solicitações;
- Visualização da classificação;
- Visualização da explicação do modelo.

A utilização do React permitirá atualizar determinados elementos da interface conforme o usuário realiza essas ações, sem a necessidade de recarregar toda a página.

### Backend — Node.js

O **Node.js** será utilizado no desenvolvimento do backend da aplicação. Ele será responsável por processar as requisições realizadas pela interface e estabelecer a comunicação entre o frontend, o banco de dados e os demais componentes necessários ao funcionamento do sistema.

Entre suas responsabilidades estarão:

- Receber as solicitações realizadas pela interface;
- Disponibilizar APIs para comunicação entre as camadas;
- Processar os dados enviados pelo usuário;
- Realizar operações relacionadas ao banco de dados;
- Encaminhar e receber informações necessárias para a análise.

Para o usuário, o desempenho do backend poderá influenciar diretamente o tempo necessário para concluir tarefas como envio de arquivos e consulta dos resultados. Esse tempo poderá variar conforme a conexão de rede e o processamento da solicitação.

### Banco de dados relacional

Será utilizado um **banco de dados relacional** para o armazenamento estruturado das informações necessárias ao funcionamento da aplicação.

A escolha por um banco de dados relacional considera a necessidade de:

- armazenar informações estruturadas;
- estabelecer relações entre diferentes conjuntos de dados;
- realizar consultas e operações sobre os dados da aplicação;
- garantir organização e consistência das informações.

## 1.11 Contexto de uso

### Usuários

O principal usuário da aplicação será o **médico**, que utilizará o sistema para fornecer dados de um paciente e consultar os resultados produzidos pelo modelo de inteligência artificial.

Características relevantes para a interação:

- O usuário possui conhecimento da área médica.
- O usuário pode não possuir conhecimento específico sobre inteligência artificial, aprendizado de máquina ou programação.
- O usuário utilizará termos e conceitos relacionados à sua área profissional.
- A frequência de utilização poderá variar de acordo com a rotina do profissional e a quantidade de casos analisados.
- O usuário poderá utilizar a aplicação durante atividades profissionais que exigem atenção simultânea a outras informações clínicas.
- O sistema deverá apresentar as informações necessárias para cada tarefa sem exigir que o usuário conheça o funcionamento interno do modelo.

A interface deverá considerar principalmente o conhecimento de domínio médico do usuário, evitando exigir conhecimento técnico sobre os métodos utilizados pelo modelo para executar as tarefas previstas.

### Tarefas e objetivos

As principais tarefas realizadas pelo médico serão:

1. Realizar o login na aplicação.
2. Iniciar uma nova análise.
3. Informar os dados necessários para o caso.
4. Selecionar e enviar os arquivos necessários para a análise.
5. Aguardar o processamento da solicitação.
6. Consultar a classificação produzida pelo modelo.
7. Consultar os fatores utilizados pelo modelo para justificar a classificação.
8. Utilizar as informações apresentadas como apoio à análise do caso.

A tarefa de consulta do resultado possui **alta criticidade**, pois está relacionada a um contexto de saúde. Por esse motivo, a aplicação deverá apresentar de forma diferenciada o resultado produzido pelo modelo e sua explicação, evitando que informações de processamento sejam confundidas com uma decisão clínica.

O sistema não deverá apresentar o resultado como substituto da avaliação médica. A decisão clínica permanecerá sob responsabilidade do profissional de saúde.

### Equipamentos e plataforma

A aplicação será desenvolvida para utilização em **navegadores web**, tendo como plataforma principal computadores e notebooks utilizados em ambientes profissionais.

As condições previstas são:

- utilização de teclado e mouse como principais dispositivos de entrada;
- utilização de monitores com diferentes tamanhos e resoluções;
- necessidade de apresentação de textos, resultados e imagens médicas;
- necessidade de conexão com a internet para comunicação com o backend e o banco de dados;
- dependência da disponibilidade dos serviços utilizados pela aplicação;
- possibilidade de variação no tempo de resposta conforme a qualidade da conexão e o processamento das solicitações.

A interface deverá ser responsiva para diferentes tamanhos de tela, mas o cenário prioritário será a utilização em computadores e notebooks, considerando o contexto profissional e a necessidade de visualização de informações médicas.

### Ambiente físico

A aplicação será utilizada principalmente em ambientes profissionais, como:

- hospitais;
- clínicas;
- consultórios;
- centros de pesquisa.

### Ambiente social e organizacional

A utilização da aplicação será predominantemente individual, com o médico realizando as tarefas diretamente no sistema.

Entretanto, a aplicação estará inserida em um ambiente organizacional que poderá envolver diferentes papéis:

- **Médico:** realiza a análise utilizando os dados e os resultados fornecidos pela aplicação.
- **Equipe de TI:** administra aspectos técnicos e de acesso ao sistema.
- **Pesquisadores da área médica:** podem utilizar os resultados para avaliação e pesquisa.
- **Hospital ou instituição:** define as condições organizacionais para utilização da solução.

A consequência de um erro de interpretação é relevante devido ao contexto de saúde. Portanto:

- o resultado do modelo deverá ser apresentado de forma claramente identificável;
- a explicação deverá estar associada ao resultado correspondente;
- informações técnicas do sistema não deverão ser apresentadas de maneira que possam ser confundidas com uma conclusão médica;
- a aplicação deverá deixar explícito que o resultado é uma ferramenta de apoio à análise profissional;
- a decisão clínica final permanecerá sob responsabilidade do médico.

## Delimitação inicial

### Dentro do escopo

- Desenvolvimento de uma aplicação web para intermediar a utilização do modelo de inteligência artificial.
- Desenvolvimento das telas necessárias para autenticação do usuário.
- Desenvolvimento do fluxo de inserção e envio dos dados para análise.
- Envio de imagens médicas e dados clínicos compatíveis com as entradas previstas pelo modelo.
- Apresentação da classificação produzida pelo modelo.
- Apresentação dos principais fatores considerados pelo modelo na classificação.
- Armazenamento dos dados necessários para o funcionamento da aplicação.
- Organização das informações considerando o fluxo de trabalho do médico.
- Desenvolvimento da interface para utilização prioritária em computadores e notebooks.

### Fora do escopo

- Substituição do médico ou de outro profissional de saúde na tomada de decisão.
- Realização autônoma de diagnóstico médico definitivo.
- Desenvolvimento de um novo modelo de inteligência artificial como parte da interface.
- Realização ou processamento físico de exames médicos.
- Integração inicial com equipamentos hospitalares.
- Integração inicial com sistemas externos de prontuário eletrônico.
- Desenvolvimento de uma versão específica para dispositivos móveis.
- Utilização da aplicação por pacientes como público principal.
- Definição de condutas ou tratamentos médicos a partir do resultado produzido pelo modelo.

## Síntese da entrega

O projeto terá como foco uma aplicação web destinada principalmente a médicos, utilizada para intermediar o acesso a um modelo de inteligência artificial explicável voltado ao apoio na análise da doença de Alzheimer. O usuário poderá inserir dados clínicos e imagens médicas, consultar a classificação produzida pelo modelo e visualizar uma justificativa para o resultado. A interface deverá considerar que os usuários possuem conhecimento médico, mas não necessariamente conhecimento técnico em inteligência artificial. O sistema será utilizado principalmente em computadores e em ambientes profissionais, como hospitais e clínicas. Devido à criticidade do contexto de saúde, a apresentação dos resultados deverá ser clara e objetiva, deixando evidente que o sistema atua como ferramenta de apoio à decisão e não substitui a avaliação médica. Essas definições orientarão as decisões de arquitetura da informação, navegação, acessibilidade e design da interface nas próximas etapas.

## Checklist

- [x] O problema está descrito sem confundir problema com solução.
- [x] Usuário final está identificado de forma específica.
- [x] Funcionalidades estão na visão do usuário.
- [x] Benefícios estão ligados a necessidades reais/hipóteses explícitas.
- [x] Contexto inclui usuários, tarefas, plataforma e ambientes físico/social.
- [x] Escopo e limites estão claros.
- [ ] A matriz de rastreabilidade foi iniciada.
