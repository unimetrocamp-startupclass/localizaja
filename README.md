![](Aspose.Words.e450ccd8-4595-4e03-969a-3d962591a4b3.001.png)![](Aspose.Words.e450ccd8-4595-4e03-969a-3d962591a4b3.002.png)

**Documentação do Sistema**



SUMÁRIO

[Dados do Cliente	2](#_heading=h.gjdgxs)

[Equipe de Desenvolvimento	3](#_heading=h.30j0zll)

[1. Introdução	4](#_heading=h.1fob9te)

[2. Objetivo	5](#_heading=h.3znysh7)

[3. Escopo	6](#_heading=h.2et92p0)

[4. Backlogs do Produto	7](#_heading=h.tyjcwt)

[5. Cronograma	8](#_heading=h.3dy6vkm)

[6. Materiais e Métodos	9](#_heading=h.1t3h5sf)

[7. Resultados	10](#_heading=h.4d34og8)

[8. Conclusão	11](#_heading=h.2s8eyo1)

[9. Homologação do MVP junto ao cliente	12](#_heading=h.17dp8vu)

[10. Divulgação	13](#_heading=h.3rdcrjn)

[11. Carta de Apresentação	15](#_heading=h.26in1rg)

[12. Carta de Autorização	16](#_heading=h.lnxbz9)

[13. Relato individual do processo	18](#_heading=h.35nkun2)





|<h1><a name="_heading=h.gjdgxs"></a>**Dados do Cliente**</h1>|
| - |
Título do Projeto: **LocalizaJa: um sistema de rastreamento de entregas de telhas.**

Cliente: **NACIONAL TELHA INDUSTRIA E COMERCIO LTDA**

CNPJ/CPF: **05.898.538/0001-89**

Contato: **Carlos Felix de Alencar**

Telefone de contato: **+55 19 98393-0454**



|<h1><a name="_heading=h.30j0zll"></a>**Equipe de Desenvolvimento** </h1>|
| - |
|**Nome completo**|**Curso**|**Disciplina**|
| :-: | :-: | :-: |
|Daniel Vitor Fonseca de Oliveira|ADS|Programação orientada a objetos em Java|
|Richard Castro Gois|ADS|Programação orientada a objetos em Java|
|Pedro Henrique De Souza Pereira|ADS|Programação orientada a objetos em Java|
|Gabriel Flausino Rodrigues|ADS|Programação orientada a objetos em Java|
||||

|**Professor Orientador**|
| :-: |
|Kesede Rodrigues Julio|

|<h1>1. <a name="_heading=h.1fob9te"></a>**Introdução**</h1>|
| - |

O cliente identificou a necessidade de um sistema eficiente para rastreamento de entregas de telhas, garantindo maior transparência e controle sobre o processo logístico. Atualmente, o acompanhamento das entregas é feito de forma manual, o que pode gerar atrasos, falta de comunicação e dificuldades na gestão das rotas. Para solucionar esse problema, será desenvolvido o **LocalizaJá**, um aplicativo de rastreamento de entregas que permitirá a visualização da localização dos pedidos, envio de notificações e relatórios de status. O sistema contará com um painel administrativo para gestão das entregas e para motoristas registrarem o progresso da rota. 

**Tecnologias Utilizadas:** O projeto tem como base a linguagem **JavaScript/TypeScript**, já que o **React Native**, framework utilizado no desenvolvimento, é fundamentado nessas tecnologias. O **React Native** é o principal *framework* do projeto, permitindo o desenvolvimento de aplicativos móveis para Android e iOS com uma base de código única.

**Bibliotecas Principais**

Para facilitar a navegação e a criação da interface, são utilizadas bibliotecas como o **React Navigation**, que cuida das rotas e da navegação entre telas (Stack e Bottom Tabs), e o **React Native Paper**, que oferece componentes prontos no estilo Material Design (botões, formulários, cartões, etc). Também é utilizado o **React Native Vector Icons**, que permite o uso de ícones customizáveis no aplicativo, como engrenagens e mapas.

Na parte de geolocalização, o projeto faz uso do **React Native Maps** para integrar o Google Maps (ou Apple Maps) diretamente nas telas. Para cálculo de trajetos e rotas em tempo real, a integração com a **Google Directions API** é essencial.

Para comunicação em tempo real, especialmente no rastreamento de entregas, o aplicativo utiliza o **Socket.IO Client**, garantindo uma conexão bidirecional constante com o backend, permitindo atualizações de localização em tempo real.

O gerenciamento de estado global é feito através do **Redux** ou da **Context API**, permitindo o controle do status das entregas e outros dados compartilhados entre componentes.

Animações e interações fluídas são possíveis com o **React Native Reanimated**, responsável por transições e efeitos visuais, e com o **React Native Gesture Handler**, que reconhece gestos como toques e arrastes.

As requisições HTTP, como autenticação de usuários e recuperação de dados de entregas, são feitas com a biblioteca **Axios**. Já para funcionalidades específicas como calendário e popups, são utilizadas as bibliotecas **React Native Calendars** e **React Native Paper Modal**, respectivamente.
### **Dependências Opcionais**
Além das bibliotecas principais, o projeto pode utilizar dependências opcionais como o **Lottie**, que permite a inclusão de animações em JSON (ideal para microinterações), e o **React Native SVG**, útil para renderizar ícones ou imagens vetoriais customizadas.

## **🔄 Fluxo do Aplicativo**
O aplicativo é composto por diversas telas e componentes que interagem com as bibliotecas mencionadas:

- **Tela de Login**: Utiliza componentes do React Native Paper como TextInput e Button para autenticar motoristas.
- **Menu Inferior**: Implementado com React Navigation (Bottom Tabs), permitindo acesso rápido às principais áreas do app: Home, Mapa e Calendário.
- **Lista de Entregas**: Mostra uma lista de entregas utilizando FlatList com suporte a animações (via Reanimated), permitindo a expansão para mais detalhes.
- **Tela de Mapa**: Exibe a rota e localização atual da entrega com o React Native Maps e linhas de rota (Polyline).
- **Popup de Confirmação**: Utiliza o React Native Paper Modal para exibir mensagens como "Mensagem enviada ao cliente".
- **Tela de Calendário**: Oferece um componente interativo para seleção de datas, utilizando React Native Calendars, o que permite filtrar entregas por período.
## **📌 Observações**
- Todas as bibliotecas mencionadas são efetivamente **dependências**, pois estão registradas no arquivo package.json.
- A palavra "biblioteca" é usada para descrever conjuntos de funcionalidades específicas (como mapas ou animações).
- O **React Native** é considerado um *framework* pois fornece toda a estrutura necessária para desenvolvimento de apps móveis.
- A **Google Directions API** é um serviço externo e, portanto, é classificada como uma *API externa*, não como uma biblioteca.
## **🔧 Framework Principal**
O backend do sistema é construído com **FastAPI**, um framework moderno, leve e extremamente rápido para a criação de APIs em Python. Ele oferece tipagem estática, validação automática com Pydantic e documentação interativa integrada, sendo ideal para sistemas que exigem desempenho e escalabilidade.
## **📦 Bibliotecas Essenciais**
Abaixo estão listadas as bibliotecas fundamentais utilizadas no projeto:

- **requests**: utilizada para o consumo de APIs externas de forma simples e síncrona.
- **httpx**: alternativa assíncrona ao requests, com maior desempenho em aplicações que utilizam async/await.
- **pydantic**: responsável pela validação de dados, garantindo integridade e consistência das informações trafegadas.
- **sqlalchemy** ou **tortoise-orm**: ferramentas ORM para mapeamento de dados relacionais no PostgreSQL. A escolha entre elas depende da preferência entre código síncrono ou assíncrono.
- **motor**: cliente assíncrono utilizado para conectar e interagir com bancos de dados MongoDB.
- **aioredis**: biblioteca para conexão assíncrona com Redis, ideal para cache, filas e dados temporários.
- **python-dotenv**: permite o carregamento de variáveis de ambiente a partir de arquivos .env, facilitando a configuração segura do ambiente de execução.
- **celery**: utilizado para o processamento de tarefas assíncronas, como envio de mensagens ou geração de relatórios.
- **pandas**: oferece ferramentas poderosas para manipulação de dados e geração de relatórios analíticos.
- **matplotlib** ou **plotly**: bibliotecas para visualização de dados e geração de gráficos, úteis para análise de métricas e desempenho das entregas.
- **pytest**: framework de testes automatizados para garantir a confiabilidade e a qualidade do código.
## **🗃️ Banco de Dados**
O sistema utiliza o **PostgreSQL**, um banco de dados relacional robusto e confiável. Ele é ideal para armazenar dados estruturados como informações de usuários, empresas, entregas e configurações do sistema.
## **🌐 APIs Externas Gratuitas**
O projeto faz uso de diversas APIs públicas e gratuitas para ampliar suas funcionalidades sem depender de serviços pagos:

- **OSRM (Open Source Routing Machine)**: serviço gratuito para cálculo de rotas e distâncias. Pode ser executado localmente ou via endpoints públicos.
- **OpenStreetMap (OSM)**: plataforma de mapas livres, utilizada para exibição de mapas no frontend.
- **Nominatim**: API gratuita para geocodificação, ou seja, conversão de endereços em coordenadas geográficas e vice-versa.
- **LibreTranslate**: alternativa open-source ao Google Translate, útil para tradução de mensagens e notificações.
- **Rocket.Chat** ou **CallMeBot**: utilizados para envio gratuito de mensagens via WhatsApp, com algumas limitações de volume e funcionalidade.
## **🔐 Autenticação**
O sistema implementa autenticação via **JWT (JSON Web Tokens)**, garantindo sessões seguras e sem a necessidade de armazenar estado no servidor.
` `Como alternativa opcional, é possível implementar autenticação com **OAuth2**, permitindo login com provedores como Google ou GitHub, respeitando os limites gratuitos de uso dessas plataformas.

|<h1>2. <a name="_heading=h.3znysh7"></a>**Objetivo**</h1>|
| - |

Nosso cliente enfrenta um grande desafio no dia a dia, o rastreamento das entregas de telhas ainda é feito de forma manual, o que gera atrasos, falhas na comunicação e dificuldades para organizar as rotas. Sem um sistema eficiente, gestores têm pouca visibilidade sobre o status dos pedidos, e isso pode afetar tanto a logística quanto a satisfação dos clientes, e nossa solução seria o **LocalizaJá** um aplicativo que permitirá o rastreamento em tempo real das entregas, automatizando a atualização de status e otimizando a gestão logística. O aplicativo oferecerá um painel administrativo para acompanhamento das entregas e um app para motoristas registrarem seu percurso, garantindo mais controle e transparência no processo.



|<h1>3. <a name="_heading=h.2et92p0"></a>**Escopo**</h1>|
| - |

O **LocalizaJá** será um **aplicativo** simples e eficiente para ajudar no rastreamento de entregas de telhas, trazendo mais transparência e controle para o cliente. Nosso foco é facilitar o acompanhamento das entregas e melhorar a comunicação entre gestores e motoristas.

📌 **O que será implementado?**

✅ **Painel Administrativo:** Um espaço dentro do aplicativo onde os gestores poderão acompanhar, em tempo real, o status das entregas, visualizar rotas e gerenciar pedidos de forma prática.

✅ **Rastreamento de Entregas:** Integração com APIs de geolocalização para monitoramento da localização dos veículos e atualização dinâmica do percurso.

✅ **Atualização de Status e Notificações:** O sistema permitirá que os responsáveis atualizem o status das entregas (em trânsito, entregue etc.), garantindo mais clareza e melhor comunicação com a equipe e os clientes.

📌 **O que não será implementado?**

❌ **Versão Web Completa:** O **LocalizaJá** será desenvolvido como um aplicativo móvel, sem um painel administrativo acessível via navegador.

❌ **Gestão Financeira e Emissão de Notas:** O foco do sistema será apenas o rastreamento de entregas, sem funcionalidades para controle financeiro ou emissão de documentos fiscais.

|<h1>4. <a name="_heading=h.tyjcwt"></a>**Backlogs do Produto**</h1>|
| - |
## **📱 Fluxo de Telas e Funcionalidades – LocalizaJá**
### **🔐 Tela de Login**
- **Objetivo:** Permitir que motoristas acessem o sistema com seu CPF e senha.
- **Ação principal:**
  - Campo de entrada de CPF e senha.
  - Botão para **"Entrar"**, que valida as credenciais e redireciona para a **Tela Home**.

### **🏠 Tela Home**
- **Para usuários sem entregas atribuídas:**
  - Exibe mensagem informativa de que não há entregas disponíveis no momento.
  - Instruções para aguardar atribuição de entregas.
#### **🛠️ Tela Home com Entregas Atribuídas:**
- Lista de entregas pendentes e em andamento.
- Cada entrega apresenta informações como:
  - Endereço de retirada e entrega.
  - Nome do cliente e telefone para contato.
  - Status da entrega.
- Ícone de localização leva à **Tela de Mapa** com a rota traçada.

### **📍 Tela de Mapa**
- Mapa com a rota traçada da entrega.
- Mostra:
  - Posição atual do motorista.
  - Ponto de retirada e ponto de entrega.
- Botão para iniciar a entrega.
- Após o início, o usuário é levado à **Tela de Entregas (Principal)**.
### **📦 Tela de Entregas (Principal)**
- Exibe a rota da entrega em tempo real.
- Ações disponíveis:
  - Botão para sinalizar **"Entrega Realizada"**.
  - Botão para **ligar para o cliente**.
- Informações da entrega em destaque:
  - Produto, endereço, horário estimado.
  - Observações adicionais do cliente.
#### **✅ Tela de Entregas com Scroll (Principal)**
- Ao confirmar a entrega:
  - Exibe **mensagem de sucesso**.
  - Campo para **inserção de observações** sobre a entrega.
  - Botão para retornar à tela principal (Home).
### **📆 Tela de Entregas Concluídas (Calendário)**
- Exibe um calendário com o histórico de entregas realizadas.
- O usuário pode selecionar datas específicas para visualizar entregas concluídas.
- Cada entrega exibe:
  - Nome do cliente, endereço, horário e status.
## **🔁 Fluxo Geral de Navegação**
1. **Login → Home**
1. **Home → Mapa (ao clicar em uma entrega)**
1. **Mapa → Entrega (Início da entrega)**
1. **Entrega → Confirmação de entrega → Home**
1. **Home → Calendário (Histórico de entregas)**



|<h1>5. <a name="_heading=h.3dy6vkm"></a>**Cronograma**</h1>|
| - |

Aqui está uma tabela com o cronograma do projeto **LocalizaJá**, seguindo uma periodicidade de 2 semanas para cada etapa:

|**Fase**|**Atividade**|**Duração**|**Data de Início**|**Data de Término**|
| :-: | :-: | :-: | :-: | :-: |
|**Planejamento**|Definição de requisitos e escopo|1 semana|08/04/2025|14/04/2025|
|**Design**|Protótipo da interface e experiência do usuário|1 semana|15/04/2025|21/04/2025|
|**Desenvolvimento - Frontend**|Implementação do painel administrativo |2 semanas|22/04/2025|05/05/2025|
|**Desenvolvimento - Backend**|Criação da API, banco de dados e integração|2 semanas|06/05/2025|19/05/2025|
|**Integração e Testes**|Conectar frontend ao backend, testar e corrigir erros|1 semana|20/05/2025|26/05/2025|
|**Implantação**|Publicação do sistema e ajustes finais|1 semana|27/05/2025|02/06/2025|
|**Entrega Final**|Apresentação ao cliente e treinamento|1 dia|03/06/2025|03/06/2025|


|<h1>6. <a name="_heading=h.1t3h5sf"></a>**Materiais e Métodos**</h1>|
| - |


1. **Modelagem do sistema**: <Dica: a modelagem do seu sistema são diagramas (desenhos) da sua estrutura ou comportamento. A UML (Unified Modelling Language) oferece diversos diagramas para que você possa modelar seu sistema. Escolha, pelo menos, dois modelos e insira aqui. Por exemplo, Modelo de Dados (Diagrama de Classe ou MER), Casos de Uso, Diagrama de Sequência, Diagrama de Atividades etc. Estes modelos são próprios para construção da comunicação, entendimento e implantação dos requisitos do sistema. Você pode usar ferramentas, como: LucidChart, Draw.io etc. Veja exemplos em [Diagramas UML: exemplo e modelos | Lucidchart Blog](https://www.lucidchart.com/blog/pt/modelos-e-exemplos-de-diagramas-uml)>. Recomendo os diagramas: Caso de Uso: mostra as relações entre Atores e Processos, Diagrama de Classes: mostra as relações entre as classes (quando houver) do sistema e o MER (Modelo Entidade-Relacionamento): mostra as relações entre os dados das tabelas de BD. Mas cada sistema pede diagramas diferentes. Portanto, aplique conforme necessidade;
1. **Tecnologias utilizadas**: <Dica: escreva quais linguagens foram utilizadas, quais  frameworks, bibliotecas e API’s consumidas/criadas. Quais ferramentas foram usadas para desenho dos modelos. Para cada um deles, faça uma pequena descrição de uso.>

1. **Arquitetura do sistema**: <Dica: insira aqui uma imagem contendo a arquitetura do sistema e o fluxo das informações. Se a arquitetura for muito simples, detalhe o fluxo dos processos. (veja um exemplo na figura 1 (pag. 79) deste artigo: [Monitor de WhatsApp: Um Sistema para Checagem de Fatos no Combate à Desinformação](https://www.researchgate.net/publication/355943388_Monitor_de_WhatsApp_Um_Sistema_para_Checagem_de_Fatos_no_Combate_a_Desinformacao)>. Este diagrama será muito bom para usar no banner da FENETEC.


|<h1>7. <a name="_heading=h.4d34og8"></a>**Resultados**</h1>|
| - |

1. **Protótipo**: <Dica: são as telas do software e suas descrições. Em cada uma delas, descreva as ações possíveis do usuário e reações do sistema. Isto pode ser feito através do print das telas do seu sistema. As telas não podem ocupar muito espaço da página, porém também não podem ficar ilegíveis>
1. **Códigos das principais funcionalidades**: <Dica: copy-cole aqui as seções mais relevantes do seu código. Insira comentários sobre cada seção.>

|<h1>8. <a name="_heading=h.2s8eyo1"></a>**Conclusão**</h1>|
| - |

1. **Impacto do sistema:** <Dica: como o sistema impactou (alterou positivamente) o processo do cliente>
1. **Melhorias Futuras**: <Dica: elencar, pelo menos, uma melhoria que poderá ser realizada futuramente no sistema.>


|<h1>9. <a name="_heading=h.17dp8vu"></a>**Homologação do MVP junto ao cliente**</h1>|
| - |

Após as entregas parciais, realizadas de acordo com os requisitos do sistema  e cronograma, o MVP foi apresentado em uma reunião, realizada entre o time de desenvolvedores e o cliente.

<Dica: inserir uma foto da homologação em cada linha do quadro abaixo. Serão 4 fotos (tiradas no momento da homologação) e, na linha debaixo, uma legenda para cada uma delas. A homologação, preferencialmente, deve ser presencial. Se não for viável, pode ser feita por videoconferência com prints da tela.>

|<foto 1: foto do time e cliente com o primeiro slide de fundo>|<foto 2: foto de um integrante apresentando o MVP.>|
| :-: | :-: |
|Da esquerda para direita: <legenda 1: descreva quem está na foto>|<legenda 2: coloque o nome de quem está apresentando>|
|<foto 3: foto dos participantes assistindo a homologação>|<foto 4: foto do plano geral do local>|
|Participantes da homologação assistindo a apresentação|Participantes da homologação|

Segue abaixo a lista de presentes na homologação do MVP.

|**Lista de presentes na Homologação**|
| :-: |
|<Cole aqui a foto da lista de presentes na homologação.>|

Ao final da apresentação, o sistema  foi homologado pelo cliente.

|<h1>10. <a name="_heading=h.3rdcrjn"></a>**Divulgação**</h1>|
| - |

1. **Linkedin do Projeto**

   https://www.linkedin.com/company/106975638/admin/dashboard/
  
   ![](Aspose.Words.e450ccd8-4595-4e03-969a-3d962591a4b3.003.png)

1. **Seminário de Projetos de Software**

   **Vídeo da apresentação:** <Grave sua apresentação, poste no Linkedin do projeto e insira aqui o link público (acesso sem login) do vídeo da apresentação>

   <Na tabela abaixo, inserir uma foto da apresentação em cada linha. Serão 4 fotos (tiradas no momento da apresentação). Para cada foto, descreva uma legenda na linha de baixo.>

|<foto 1: foto do time com o primeiro slide de fundo>|<foto 2: foto de um integrante apresentando o sistema.>|
| :-: | :-: |
|Da esquerda para direita: <legenda 1: descreva quem está na foto>|<legenda 2: coloque o nome de quem está apresentando>|
|<foto 3: foto plano geral da apresentação de frente para o fundo da sala>|<foto 4:  foto plano geral da apresentação do fundo para a frente da sala>|
|Participantes do evento assistindo a apresentação|Participantes do evento assistindo a apresentação|

Segue abaixo a lista de presentes na apresentação.

|**Lista de presentes na Apresentação**|
| :-: |
|<Faça uma lista de presença numa folha A4, contendo no alto da folha “Seminários de Projetos de Software”. A lista deve conter ra, nome e assinatura dos presentes. Cole aqui a foto desta lista.>|

1. **FENETEC: Feira de Negócios em Tecnologia**

   **Apresentação do projeto:** <Um vídeo deve ser produzido mostrando o time apresentando seu projeto para algum visitante. Importante que neste video tenha uma tomada do banner e dos integrantes. Insira aqui o link público deste vídeo.>

   <Na tabela abaixo, inserir uma foto da apresentação em cada linha. Serão 4 fotos (tiradas do evento). Para cada foto, descreva uma legenda na linha de baixo.>

|<foto 1: foto do time ao lado do poster>|<foto 2: foto de um integrante apresentando o sistema.>|
| :-: | :-: |
|Da esquerda para direita: <legenda 1: descreva quem está na foto>|<legenda 2: coloque o nome de quem está apresentando>|
|<foto 3: foto do público assistindo sua apresentação>|<foto 4:  foto plano geral da FENETEC>|
|Participantes do evento assistindo a apresentação|Estandes da FENETEC|

Segue abaixo a lista de presentes na FENETEC.

|**Lista de presentes na Apresentação**|
| :-: |
|<cole aqui a lista de presença dos visitantes da FENETEC com nome e email do visitante . Os próprios times farão um form contendo no cabeçalho: Lista de Visitantes FENETEC. Compartilhe a planilha gerada pelo form com todos os times.>|














|<h1>11. <a name="_heading=h.26in1rg"></a>**Carta de Apresentação**</h1>|
| - |
Vimos por desta apresentar o grupo de acadêmicos do Centro Universitário Unimetrocamp, localizada à Rua Sales de Oliveira, 1661 - Campinas - SP, a fim de convidá-lo a participar de uma atividade extensionista associada ao componente curricular <inserir o nome da disciplina>, sob responsabilidade do orientador Prof. Kesede Rodrigues Julio (profkesede64@gmail.com).

Em consonância ao Plano Nacional de Educação vigente, o Centro Universitário Unimetrocamp promove o Desenvolvimento de Software que, norteados pela metodologia de Gerenciamento Ágil Scrum, tem por princípios fundantes o diagnóstico dos problemas/demandas/necessidades, a participação ativa dos interessados/públicos participantes, a construção dialógica, coletiva e experiencial de conhecimentos, o planejamento de ações, o desenvolvimento e avaliação das ações, a sistematização dos conhecimentos, a avaliação das ações desenvolvidas.

Nesse contexto, a disciplina acima mencionada tem como principal escopo os temas relacionados à Programação Orientada à Objeto / Padrões de Projetos de Software, no que diz respeito ao desenvolvimento de um software utilizando Programação Orientada à Objeto.

Sendo assim, pedimos o apoio de <nome do cliente> para a realização das seguintes atividades: levantamento de requisitos, validação das entregas parciais, revalidação dos requisitos, homologação do MVP, ou qualquer outra intervenção que auxilie no desenvolvimento das competências de nossos acadêmicos e ao mesmo tempo possa contribuir para a comunidade em que estamos inseridos.

Aproveitamos a oportunidade para solicitarmos, em caso de aceite, que a parceria seja formalizada, mediante assinatura da Carta de Autorização, as atividades e informações que o(s) aluno(s) poderá(ão) ter acesso.

Em tempo, registramos ainda, o convite para a participação de todos os interessados no fórum semestral de acompanhamento e avaliação das atividades realizadas, que está previsto para o final deste semestre, e será comunicado previamente em convite específico.

Desde já nos colocamos à sua disposição para quaisquer esclarecimentos.

Atenciosamente,

Campinas, \_\_\_\_ de \_\_\_\_\_\_\_\_\_ de 202\_\_\_.![](Aspose.Words.e450ccd8-4595-4e03-969a-3d962591a4b3.004.jpeg)

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Assinatura Direção Acadêmica da IES**

` `![](Aspose.Words.e450ccd8-4595-4e03-969a-3d962591a4b3.005.jpeg)

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

**Assinatura Docente**


|<h1>12. <a name="_heading=h.lnxbz9"></a>**Carta de Autorização**</h1>|
| - |
Eu, (preencher com nome do responsável), (preencher com cargo ocupado), da (nome da empresa, organização, associação, escola, secretaria, etc., situada no endereço – inserir o endereço), autorizo a realização das seguintes atividades acadêmicas do componente extensionista <código e nome da disciplina>, do Centro Universitário Unimetrocamp, sob orientação do Prof. Kesede Rodrigues Julio.



|**Atividades:**|
| - |
|** |
|** |
|** |
|** |

Conforme combinado em contato prévio, as atividades acima descritas são autorizadas para os seguintes alunos:



|**Nome dos/das alunos/as**|**Curso**|**Matrícula**|
| :-: | :-: | :-: |
| | | |
| | | |
| | | |
| | | |
||||


Declaro que fui informado por meio da **Carta de Apresentação** sobre as características e objetivos das atividades que serão realizadas na organização/instituição/empresa a qual represento e afirmo estar ciente de tratar-se de uma atividade realizada com intuito **exclusivo de ensino de alunos de graduação**, sem a finalidade de exercício profissional.



Desta forma, autorizo, em caráter de confidencialidade:



- ` `o acesso a informações e dados que forem necessários à execução da atividade;
- ` `o registro de imagem por meio de fotografias;
- ` `outro: (especificar)





Campinas, \_\_\_ de \_\_\_\_\_\_\_\_\_\_\_de 202\_.



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

(Assinatura, nome completo do responsável, email de contato e com carimbo da empresa)



|<h1>13. <a name="_heading=h.35nkun2"></a>**Relato individual do processo**</h1>|
| - |

|<nome do aluno>|
| :- |
|<um breve relato pessoal sobre o trabalho extensionista desenvolvido>|

|<nome do aluno>|
| :- |
|<um breve relato pessoal sobre o trabalho extensionista desenvolvido>|

|<nome do aluno>|
| :- |
|<um breve relato pessoal sobre o trabalho extensionista desenvolvido>|

|<nome do aluno>|
| :- |
|<um breve relato pessoal sobre o trabalho extensionista desenvolvido>|

|<nome do aluno>|
| :- |
|<um breve relato pessoal sobre o trabalho extensionista desenvolvido>|





|/18|
| -: |

