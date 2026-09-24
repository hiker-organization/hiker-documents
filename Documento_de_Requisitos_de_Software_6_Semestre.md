# CENTRO PAULA SOUZA

## FACULDADE DE TECNOLOGIA DE JAHU

## CURSO DE TECNOLOGIA EM DESENVOLVIMENTO DE SOFTWARE MULTIPLATAFORMA

# DOCUMENTAÇÃO DO PROJETO INTERDISCIPLINAR (PI)

# HIKER

## Aplicação mobile de avaliação de locais turísticos

**Jahu, SP**

**6º semestre/2026**

**Autores:** Jhonatan Marcelino de Jesus, Kieran Santos Corrêa, Leonardo Roque Delandrea, Pablo Valentin, Victor Hugo dos Santos

---

## RESUMO

O crescimento do turismo no Brasil e a expansão do uso de tecnologias digitais têm transformado a maneira como os viajantes buscam e compartilham informações sobre destinos. No entanto, essas informações encontram-se dispersas entre múltiplas plataformas, como Google Maps, TripAdvisor, Instagram e redes sociais diversas, dificultando o planejamento de viagens de forma centralizada e confiável.

Neste contexto, o presente trabalho apresenta o **Hiker**, um aplicativo mobile desenvolvido como Projeto Interdisciplinar (PI) do curso de Tecnologia em Desenvolvimento de Software Multiplataforma da FATEC Jahu. O aplicativo tem como objetivo centralizar avaliações geolocalizadas de destinos turísticos em uma única plataforma, baseada em conhecimento coletivo e em um sistema de reputação de usuários.

A metodologia de desenvolvimento adotada foi o **SCRUM**, com seis sprints planejadas e suporte da ferramenta Jira para gestão das tarefas. A solução tecnológica utiliza **.NET MAUI** para o aplicativo mobile, **NestJS** no backend, **PostgreSQL** como banco de dados relacional e hospedagem na plataforma **Azure**.

O sistema contempla funcionalidades como autenticação de usuários, gestão de publicações, feed personalizado, pesquisa de locais, sistema de reputação e conformidade com a Lei Geral de Proteção de Dados (LGPD). Os resultados parciais demonstram a viabilidade técnica e de negócio da solução, com potencial para se consolidar como uma referência nacional em avaliações turísticas colaborativas.

**Palavras-chave:** turismo; aplicativo mobile; publicações; desenvolvimento de software.

---

## SUMÁRIO

1. [Resumo da Aplicação Web](#resumo-da-aplicação-web)
   - 1.1 [Objetivos](#objetivos)
   - 1.2 [Métodos da Pesquisa](#métodos-da-pesquisa)

2. [Documento de Requisitos](#documento-de-requisitos)
   - 2.1 [Requisitos Funcionais](#requisitos-funcionais)
   - 2.2 [Requisitos Não Funcionais](#requisitos-não-funcionais)
   - 2.3 [Diagrama de Casos de Uso](#diagrama-de-casos-de-uso)
   - 2.4 [Diagrama de Classes](#diagrama-de-classes)

3. [Regras de Negócio](#regras-de-negócio)

4. [Estudo de Viabilidade](#estudo-de-viabilidade)

5. [Modelo de Dados](#modelo-de-dados)

6. [Design](#design)

7. [Protótipo](#protótipo)

8. [Aplicação](#aplicação)

9. [Banco de Dados](#banco-de-dados)

10. [Considerações Finais](#considerações-finais)

---

## RESUMO DA APLICAÇÃO WEB

O turismo no Brasil é uma atividade em constante ascensão, sendo uma valiosa parte da estratégia para o crescimento econômico do país. Nas últimas décadas, este setor vem adaptando-se às novas mudanças sociais e tecnologias, impulsionando a economia com as crescentes oportunidades para os viajantes.

O aumento no uso de tecnologia é um dos vários fatores que ocasionam mudanças no turismo, uma vez que "a internet revolucionou a maneira como os turistas planejam e reservam viagens" (SILVA, 2025, p. 17).

Sendo assim, a internet e suas tecnologias apresentam-se como uma parte importante para o setor turístico no século XXI:

> "As tecnologias digitais têm desempenhado um papel fundamental na transformação da indústria do turismo, permitindo que os viajantes acessem informações detalhadas sobre destinos, alojamentos, atividades e itinerários com facilidade. Ao mesmo tempo, as próprias tecnologias estão moldando o processo de produção de roteiros de viagens, com um impacto significativo na maneira como os profissionais do setor e os viajantes independentes abordam a criação de experiências de viagem memoráveis" (LEITE JÚNIOR, 2023, p. 6).

A partir da década de 1930, o governo brasileiro passa a normatizar o turismo, estabelecendo regras para agências de viagens. Já em 1966, é criada a Empresa Brasileira de Turismo (EMBRATUR) e o investimento em infraestrutura para este setor cresce nas próximas décadas. Em 1994, é criado o Plano Nacional de Municipalização do Turismo (PNMT), caracterizado por protagonizar os municípios na gestão e planejamento de atividades, conscientizando os habitantes sobre a importância do turismo. Em 2003, é criado o Ministério do Turismo, garantindo um orçamento federal para essa área.

Deste modo, é possível observar a crescente preocupação do governo brasileiro em institucionalizar, desenvolver e expandir o turismo no país (SILVA, 2025, p. 17). Segundo dados da EMBRATUR[^1], em 2025 a receita turística nominal anual no Brasil atingiu índices maiores do que os pré-pandemia – cerca de US$7,8 bilhões. Isso demonstra uma alta capacidade de recuperação do setor após momentos de crise mundial, alcançando receitas recorde desde 2023.

A partir desta análise, pode-se inferir que o turismo apresenta diversas oportunidades de investimento e inovação, principalmente na área da tecnologia. Por este motivo, a equipe deste projeto decidiu desenvolver um aplicativo móvel de avaliação de cidades brasileiras, no âmbito turístico.

Foram entrevistadas pessoas que viajam com frequência para entender as dificuldades no planejamento dessa atividade. O principal problema relatado foi a **descentralização das informações**, as quais encontram-se espalhadas por diversas plataformas e websites na internet, como Google, Instagram, Youtube e Facebook.

A partir do aplicativo, os usuários podem visualizar a opinião de outras pessoas, criar suas próprias publicações e acessar informações compartilhadas sobre cidades que desejam visitar. O principal objetivo do aplicativo é ajudar na etapa inicial do planejamento de viagens: encontrar informações sobre possíveis destinos, através do conhecimento coletivo, centralizado e social sobre o local.

### OBJETIVOS

#### Objetivo Geral

- Produzir um aplicativo mobile com o intuito de ajudar pessoas a encontrarem informações específicas e confiáveis sobre locais para viagem.

#### Objetivos Específicos

- Entrevistar stakeholders para levantamento das necessidades e definição dos requisitos do sistema.
- Investigar possíveis concorrentes e soluções existentes no mercado.
- Definir a arquitetura do sistema e planejar as etapas de desenvolvimento.
- Planejar as milestones do projeto, organizando as entregas e etapas de implementação.
- Desenvolver um protótipo de alta fidelidade para validação da interface.
- Construir o aplicativo utilizando Flutter, Node.js, banco de dados PostgreSQL e o sensor de acelerômetro e localização do aparelho móvel.
- Utilizar técnicas de Processamento de Linguagem Natural para reconhecer discursos ofensivos.
- Utilizar técnicas de Mineração de Dados para fazer análise em massa de métricas da plataforma e para desenvolver um algoritmo de preferências para os usuários.
- Construir o painel de administração utilizando Vue.js, Node.js e PostgreSQL.
- Fazer o deploy para produção.

### MÉTODOS DA PESQUISA

O projeto foi realizado por cinco integrantes, os quais optaram pela metodologia **SCRUM** para a organização e administração do desenvolvimento. Para apoiar a gestão do processo, foi utilizada a ferramenta **Jira**, que permitiu o acompanhamento das tarefas, o controle do backlog e a visualização do progresso de cada etapa.

O desenvolvimento foi estruturado em **seis sprints**, cada uma com duração de duas semanas e objetivos específicos:

- **Sprint 1:** Atividades de planejamento, como entrevista com stakeholders; pesquisa de mercado; definição dos requisitos do software; definição do modelo de negócio; divisão das equipes de desenvolvimento; configuração das etapas de desenvolvimento; e definição das sprints.

- **Sprint 2:** Configurações iniciais de ambientes de desenvolvimento, modelagem do banco de dados e estruturação das telas de cadastro, login e recuperação de senha.

- **Sprint 3:** Desenvolvimento da gestão de publicações, incluindo a criação, edição, exclusão e visualização de publicações.

- **Sprint 4:** Desenvolvimento das funcionalidades necessárias para a gestão de usuários, como a visualização de perfis e alteração de dados pessoais.

- **Sprint 5:** Feed, busca por locais e suas respectivas páginas.

- **Sprint 6:** Funcionalidades de locais favoritos, concordar e discordar de publicações, reputação dos usuários, linhas do tempo e algoritmo de preferências. *Nota: Será desenvolvida durante o segundo semestre de 2026.*

#### Ferramentas Utilizadas

- Computadores pessoais e computadores disponibilizados pela Fatec
- Microsoft Word: escrita do projeto
- Ferramenta Canva: criação dos slides de apresentação, modelo de negócio e modelo de navegação
- Ferramenta Figma: criação do wireframe e protótipo
- Adobe Color: criação da paleta de cores
- Trello: gestão do projeto
- Visual Code Studio: escrita do código backend em JavaScript/NestJS e frontend em Flutter
- Github e Git: controle de versão e repositório
- PostgreSQL: armazenamento de dados
- Azure: hospedagem da API
- Google Cloud Platform: hospedagem de APIs de machine learning
- Databricks/Apache Airflow: construção do pipeline de ETL

#### Cronograma

Durante os meses de janeiro e fevereiro, a equipe realizou pesquisa de mercado para idealizar um novo produto. Através de entrevistas com amigos e familiares, surgiu a ideia de criar um aplicativo mobile para ajudar os usuários a encontrar novos destinos de viagem.

Durante os meses de fevereiro e março, o escopo do projeto foi transformado em requisitos de software documentados sistematicamente. No mês de março, foi pensado o modelo de negócio do produto e modelado o banco de dados, iniciando-se a construção do mockup do aplicativo.

A partir do final do mês de março, iniciou-se o desenvolvimento da gestão de publicações. A partir do mês de abril, teve início o desenvolvimento da gestão de usuários. Por fim, foi planejada para o desenvolvimento da gestão de locais e do feed de publicações, com alocação na Azure para futura disponibilização.

---

## DOCUMENTO DE REQUISITOS

Os requisitos de software constituem a base fundamental para o desenvolvimento de sistemas computacionais, sendo classificados em duas categorias principais:

- **Requisitos Funcionais:** Descrevem as funcionalidades específicas que o sistema deve executar, definindo o comportamento esperado do software em resposta a determinadas entradas e condições.

- **Requisitos Não Funcionais:** Estabelecem os critérios de qualidade que o sistema deve atender, abrangendo atributos como desempenho, segurança, usabilidade, confiabilidade, escalabilidade e manutenibilidade.

A correta elicitação, análise e documentação de ambas as categorias de requisitos é essencial para garantir que o sistema desenvolvido atenda plenamente às necessidades dos stakeholders e esteja em conformidade com os padrões técnicos e normativos aplicáveis.

### REQUISITOS FUNCIONAIS

#### Grupo de RF 1 – Aplicativo Mobile

##### RF1: Fazer Cadastro

**Descrição:** O usuário deve acessar a tela de cadastro para criar uma conta.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN1.1 Campos** | O usuário deve fornecer: E-mail*, Nome de usuário*, Nome de exibição*, Data de aniversário*, Número de celular*, Senha*, Confirmação de senha* | ✓ | |
| **RN1.2 Segurança de Senha** | A senha deve conter no mínimo 8 dígitos, uma letra maiúscula, uma minúscula e um caractere especial | ✓ | |
| **RN1.3 Restrições de nome de usuário** | Não pode conter espaços, máximo 20 caracteres, podendo conter números e caracteres especiais "." e "@" | ✓ | |
| **RN1.4 E-mail válido** | O usuário deve informar um formato de e-mail válido | ✓ | |
| **RN1.5 Tempo de cadastro** | Tempo de execução inferior a cinco segundos | | ✓ |
| **RN1.6 Restrições de nome de exibição** | Máximo 30 caracteres | ✓ | |

##### RF2: Recuperar Senha

**Descrição:** Caso o usuário esqueça sua senha, poderá alterá-la através da tela de login.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN2.1 Exigir o e-mail** | O usuário deve fornecer o e-mail da conta | ✓ | |
| **RN2.2 Mensagem genérica** | "Caso exista uma conta associada a este e-mail, o link de recuperação de senha foi enviado" | ✓ | |
| **RN2.3 Link de recuperação de senha** | Sistema envia link ao e-mail informado | ✓ | |

##### RF3: Fazer Login

**Descrição:** O usuário deve fazer login para acessar a plataforma.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN3.1 Confirmação de e-mail** | O usuário deve confirmar o e-mail para fazer login | ✓ | |
| **RN3.2 Campos** | E-mail e Senha | ✓ | |
| **RN3.3 Lembrar login** | Sistema mantém usuário logado até logout solicitado | ✓ | |
| **RN3.4 Múltiplos dispositivos** | Usuário pode logar em diversos dispositivos simultaneamente | | ✓ |
| **RN3.5 Token de validação** | Sistema gera token para validar login | ✓ | |
| **RN3.6 Mensagem genérica** | "E-mail ou senha incorretos" | ✓ | |

##### RF4: Fazer Logout

**Descrição:** O usuário pode se deslogar do aplicativo quando quiser.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN4.1 Botão visível e intuitivo** | Usuário deve identificar facilmente o botão logout | ✓ | |
| **RN4.2 Revogar token de login** | Sistema revoga token em dispositivos deslogados | ✓ | |

##### RF5: Visualizar Feed de Publicações

**Descrição:** Na página principal, o usuário visualiza o feed de locais e publicações.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN5.1 Filtros** | País e Estado | | ✓ |
| **RN5.2 Ordem das publicações** | Apresentadas de forma cronológica | ✓ | |

##### RF6: Pesquisar Local

**Descrição:** O usuário pode procurar um local na barra de pesquisa.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN6.1 Digitar** | Usuário digita para encontrar local | ✓ | |
| **RN6.2 Locais disponíveis** | Sistema apresenta locais da API externa conforme digitado | ✓ | |

##### RF7: Visualizar um Local

**Descrição:** O usuário acessa a página de um local e visualiza nota, publicações de outros usuários e rótulos.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN7.1 Ordem das avaliações** | Publicações em ordem cronológica | ✓ | |
| **RN7.2 Locais disponíveis** | Associado a locais da API externa | ✓ | |
| **RN7.3 Avaliações anônimas** | Sem informações pessoais, apenas reputação | ✓ | |

##### RF8: Concordar ou Discordar de Publicação

**Descrição:** O usuário pode concordar ou discordar de uma publicação.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN8.1 Locais possíveis** | Página principal, páginas de locais e perfis | | ✓ |
| **RN8.2 Opção única** | Não pode concordar e discordar simultaneamente | ✓ | |

##### RF9: Favoritar uma Publicação

**Descrição:** O usuário pode adicionar publicações como favoritas.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN9.1 Sem limite máximo** | Quantidade ilimitada de favoritos | ✓ | |
| **RN9.2 Remover favorito** | Usuário remove publicação de favoritos | ✓ | |
| **RN9.3 Favorito duplicado** | Uma publicação não é adicionada mais de uma vez | ✓ | |
| **RN9.4 Clareza nos locais favoritos** | Sistema indica visualmente favoritos | ✓ | |

##### RF10: Visualizar Publicações Favoritos

**Descrição:** O usuário visualiza suas publicações marcadas como favoritas.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN10.1 Página dedicada** | Sistema apresenta favoritos em página dedicada | ✓ | |
| **RN10.2 Redirecionamento do local** | Acesso à página de detalhes do local | ✓ | |
| **RN10.3 Lista de favoritos vazia** | "Nenhuma publicação favorita" | ✓ | |
| **RN10.4 Informações da página** | Agrupadas por local com nome, estado e média de notas | ✓ | |

##### RF11: Publicar sobre Local

**Descrição:** O usuário pode publicar uma avaliação sobre um local.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN11.1 Restrição de publicação** | Uma publicação por local por dia | ✓ | |
| **RN11.2 Vínculo ao local** | Publicação vinculada a local de API externa | ✓ | |
| **RN11.3 Limites de tamanho** | Foto/vídeo máximo 2MB, descrição máximo 150 caracteres | | ✓ |
| **RN11.4 Imagens** | Máximo cinco fotos ou vídeos, opcionais | ✓ | |
| **RN11.5 Publicação anônima** | Usuário pode optar por anonimato | ✓ | |
| **RN11.6 Campos obrigatórios** | Local, Nota, Descrição | ✓ | |
| **RN11.7 Campos não obrigatórios** | Rótulos, Imagens | ✓ | |

##### RF12: Excluir Publicação

**Descrição:** O usuário pode deletar suas próprias publicações.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN12.1 Exclusão lógica** | Ocultar dados ao invés de apagá-los | ✓ | |

##### RF13: Visualizar Publicação

**Descrição:** O usuário visualiza sua própria publicação ou de outro usuário.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN13.1 Anonimidade** | Sem informações pessoais de usuários anônimos | ✓ | |
| **RN13.2 Interação** | Publicação expandida na mesma tela | ✓ | |

##### RF14: Visualizar Perfil de Outro Usuário

**Descrição:** O usuário visualiza o perfil de outro usuário.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN14.1 Informações do perfil** | Nome, nome de usuário, foto, publicações, número de publicações, reputação | ✓ | |

##### RF15: Exibir Linha do Tempo de Viagens

**Descrição:** Sistema apresenta linha do tempo com locais visitados e datas.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN15.1 Tempo de carregamento** | Até 3 segundos após abertura do perfil | | ✓ |
| **RN15.2 Consistência de dados** | Refletem corretamente os registros | ✓ | |
| **RN15.3 Atualização de dados** | Aparecem em até 5 segundos | | ✓ |
| **RN15.4 Informações** | Nome do local, estado, nota e data | ✓ | |

##### RF16: Visualizar Próprio Perfil

**Descrição:** O usuário visualiza seu próprio perfil para solicitar alterações.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN16.1 Informações do perfil** | Nome, nome de usuário, foto, publicações, número de publicações, reputação | ✓ | |

##### RF17: Alterar Informações Pessoais

**Descrição:** Sistema permite que usuário altere suas informações pessoais.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN17.1 Segurança de edição** | Apenas o próprio usuário autenticado altera informações | ✓ | |
| **RN17.2 Tempo de atualização** | Até 5 segundos | | ✓ |
| **RN17.3 Validação de dados** | Valida dados antes de salvar | ✓ | |
| **RN17.4 Integridade dos dados** | Nenhuma informação é perdida | ✓ | |
| **RN17.5 Alteração de senha** | Solicita senha atual para nova senha | ✓ | |
| **RN17.6 Alteração de e-mail** | Envia e-mail de verificação | ✓ | |
| **RN17.7 Informações** | Nome, nome de exibição, foto, data de aniversário, e-mail, senha | ✓ | |

##### RF18: Alterar Visibilidade do Perfil

**Descrição:** O usuário altera seu perfil para público ou privado.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN18.1 Sem tempo mínimo** | Pode alterar a qualquer momento | ✓ | |
| **RN18.2 Modo público** | Mostra todas as publicações | ✓ | |
| **RN18.3 Modo privado** | Mostra apenas reputação e número de publicações | ✓ | |
| **RN18.4 Clareza no modo de perfil** | Indica visualmente se público ou privado | ✓ | |

##### RF19: Calcular Reputação do Usuário

**Descrição:** Sistema calcula reputação com base nas notas e interações.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN19.1 Atualização** | Recalculada em até 5 segundos | | ✓ |
| **RN19.2 Integridade dos dados** | Utiliza apenas avaliações válidas | ✓ | |
| **RN19.3 Consistência** | Consistente em todas as telas | ✓ | |

##### RF20: Algoritmo de Preferências

**Descrição:** Sistema calcula preferências do usuário para retornar feed personalizado.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN20.1 Número mínimo de interações** | Mínimo dez interações na plataforma | ✓ | |

##### RF21: Algoritmo de Detecção de Discurso Ofensivo

**Descrição:** Sistema avalia publicações para detectar discurso ofensivo.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN21.1 Frequência** | A cada nova publicação | | ✓ |
| **RN21.2 Resolução** | Publicação ofensiva sinalizada para avaliação humana | ✓ | |

##### RF22: Excluir Conta

**Descrição:** O usuário pode excluir sua conta a qualquer momento.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN22.1 Exclusão imediata** | Permitida quando conta é criada | ✓ | |
| **RN22.2 LGPD** | Dados guardados por no máximo cinco anos | ✓ | |

##### RF23: Notificações do Usuário

**Descrição:** Sistema notifica sobre interações relevantes.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN23.1 Eventos notificáveis** | Publicação bloqueada, denunciada, bloqueio/banimento de conta | ✓ | |

##### RF24: Iniciar uma Trilha

**Descrição:** O usuário pode iniciar o registro de uma trilha.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN24.1 Rastreio da trilha** | Sistema rastreia passos e quilometragem | ✓ | |

##### RF25: Pausar uma Trilha

**Descrição:** O usuário pausa trilha em andamento.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN25.1 Manutenção dos dados** | Sistema mantém registrados passos e quilometragem | ✓ | |

##### RF26: Encerrar uma Trilha

**Descrição:** O usuário encerra trilha registrando informações finais.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN26.1 Campos a informar** | Nota*, Descrição*, Imagens, Rótulos | ✓ | |

##### RF27: Visualizar Trilhas

**Descrição:** O usuário visualiza lista de todas as trilhas realizadas.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN27.1 Informações** | Local, Estado, Data, Nota | ✓ | |

##### RF28: Visualizar uma Trilha

**Descrição:** O usuário visualiza detalhes de uma trilha realizada.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN28.1 Informações** | Local, estado, total de quilômetros, total de passos, trajeto no mapa, nota, descrição, imagens, labels, data | ✓ | |

##### RF29: Compartilhar uma Trilha

**Descrição:** O usuário compartilha uma trilha realizada.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN29.1 Visibilidade** | Trilha fica visível no feed de postagens | ✓ | |

##### RF30: Excluir uma Trilha

**Descrição:** O usuário exclui uma trilha realizada.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN30.1 Confirmação** | Sistema pede confirmação antes de excluir | ✓ | |
| **RN30.2 Exclusão lógica** | A exclusão deve ser lógica | ✓ | |

#### Grupo de RF 2 – Aplicação Web

##### RF31: Realizar Login Administrativo

**Descrição:** O administrador faz login em tela exclusiva.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN31.1 Credenciais exclusivas** | Diferentes das dos usuários comuns | ✓ | |

##### RF32: Visualizar Métricas da Plataforma

**Descrição:** Administrador visualiza métricas gerais do dashboard.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN32.1 Filtro por período** | Pode filtrar dados por período | | ✓ |
| **RN32.2 Atualização dos dados** | Atualizados em até 24 horas | | ✓ |

##### RF33: Visualizar Lista de Usuários

**Descrição:** Administrador visualiza lista de usuários cadastrados.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN33.1 Busca e filtro** | Pode buscar e filtrar usuários bloqueados e banidos | ✓ | |
| **RN33.2 Campos da tabela** | Nome, email, total de postagens, postagens bloqueadas, denúncias | ✓ | |

##### RF34: Visualizar um Usuário

**Descrição:** Administrador seleciona usuário para visualizar detalhes.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN34.1 Detalhes do usuário** | Informações cadastrais e status (ativo, bloqueado, banido) | ✓ | |

##### RF35: Excluir um Usuário

**Descrição:** Administrador exclui a conta de um usuário.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN35.1 Confirmação** | Sistema solicita confirmação | ✓ | |
| **RN35.2 Notificação** | Sistema avisa usuário por e-mail | | ✓ |

##### RF36: Bloquear um Usuário

**Descrição:** Administrador bloqueia temporariamente a conta.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN36.1 Justificativa** | Administrador informa justificativa e dias de bloqueio | ✓ | |
| **RN36.2 Notificação** | Sistema avisa usuário ao tentar acessar | ✓ | |

##### RF37: Banir um Usuário

**Descrição:** Administrador bane definitivamente a conta.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN37.1 Justificativa** | Administrador informa justificativa | ✓ | |
| **RN37.2 Notificação** | Sistema avisa usuário ao tentar acessar | ✓ | |
| **RN37.3 Tempo de banimento** | 30 anos de bloqueio | | ✓ |

##### RF38: Visualizar Lista de Publicações

**Descrição:** Administrador visualiza lista de publicações.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN38.1 Filtro de listagem** | Por usuário, bloqueadas, detectadas, denunciadas | ✓ | |
| **RN38.2 Campos da tabela** | ID do usuário, nome do usuário, data, status, denúncias | ✓ | |

##### RF39: Visualizar uma Publicação

**Descrição:** Administrador seleciona publicação para visualizar conteúdo.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN39.1 Motivo da denúncia** | Sistema exibe motivo se denunciada | ✓ | |

##### RF40: Bloquear uma Publicação

**Descrição:** Administrador bloqueia (remove) uma publicação.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN40.1 Remoção** | Remove da visualização dos demais usuários | ✓ | |
| **RN40.2 Notificação** | Avisa o autor | | ✓ |
| **RN40.3 Exclusão lógica** | Não exclui do banco de dados | ✓ | |

##### RF41: Aceitar Detecção de Publicação

**Descrição:** Administrador aceita detecção de publicação ofensiva.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN41.1 Remoção** | Implica na exclusão da detecção | ✓ | |
| **RN41.2 Notificação** | Sistema pede confirmação | ✓ | |

##### RF42: Rejeitar Detecção de Publicação

**Descrição:** Administrador rejeita detecção de publicação.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RN42.1 Remoção** | Publicação fica visível para usuários | ✓ | |
| **RN42.2 Notificação** | Sistema pede confirmação | ✓ | |

### REQUISITOS NÃO FUNCIONAIS

| Requisito | Descrição | Categoria | Obrigatório | Desejável |
|---|---|---|---|---|
| **RNF1** | Suporte para novas features | Escalabilidade | ✓ | |
| **RNF2** | Suporte para aumento de usuários | Escalabilidade | | ✓ |
| **RNF3** | Tempo de carregamento inferior a um segundo | Performance | ✓ | |
| **RNF4** | Backups frequentes de informações | Confiabilidade | ✓ | |
| **RNF5** | Compatibilidade com dispositivos Android | Compatibilidade | ✓ | |
| **RNF6** | Avisos de manutenção prevista | Disponibilidade | | ✓ |
| **RNF7** | Conformidade com LGPD | Legalidade | ✓ | |

#### Requisitos Não-Funcionais de Segurança

##### RNFS1: Verificar E-mail no Cadastro

**Descrição:** Após cadastro, sistema envia e-mail de verificação para ativar conta.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RNFS1.1 Envio automático** | Enviado automaticamente após cadastro | ✓ | |
| **RNFS1.2 Acesso restrito** | Conta permanece inativa até verificação | ✓ | |
| **RNFS1.3 Reenvio** | Usuário pode solicitar reenvio | | ✓ |
| **RNFS1.4 Expiração do link** | Expira em 24 horas | | ✓ |

##### RNFS2: Limitar Tentativas de Login

**Descrição:** Sistema bloqueia acesso após múltiplas tentativas malsucedidas.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RNFS2.1 Limite de tentativas** | Bloqueio por 15 minutos após 5 tentativas | ✓ | |
| **RNFS2.2 Mensagem de bloqueio** | Informa bloqueio e tempo restante | ✓ | |
| **RNFS2.3 Reset do contador** | Zerado após login bem-sucedido | ✓ | |
| **RNFS2.4 CAPTCHA** | Após 3 tentativas | | ✓ |

##### RNFS3: Expirar Token de Sessão

**Descrição:** Sistema gerencia ciclo de vida dos tokens de autenticação.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RNFS3.1 Expiração do token** | Token expira em 24 horas | ✓ | |
| **RNFS3.2 Refresh token** | Refresh token com validade de 90 dias | ✓ | |
| **RNFS3.3 Revogação de refresh token** | Revogado no logout ou troca de senha | ✓ | |
| **RNFS3.4 Reautenticação** | Novo login após expiração do refresh token | ✓ | |

##### RNFS4: Expirar Link de Recuperação de Senha

**Descrição:** Link de recuperação deve ter validade limitada.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RNFS4.1 Validade do link** | Expira em 1 hora após envio | | ✓ |
| **RNFS4.2 Uso único** | Expira em 1 hora após envio | | ✓ |
| **RNFS4.3 Invalidação ao solicitar novo link** | Anterior é invalidado imediatamente | ✓ | |

##### RNFS5: Validação de Entradas do Usuário

**Descrição:** Sistema valida todos os dados antes de processar ou armazenar.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RNFS5.1 Prevenção de XSS** | Escapa caracteres especiais | ✓ | |
| **RNFS5.2 Prevenção de injeção** | Consultas parametrizadas | ✓ | |
| **RNFS5.3 Validação no servidor** | Independentemente de validação no cliente | ✓ | |
| **RNFS5.4 Tamanho máximo de campos** | Rejeita entradas que excedem limite | ✓ | |

##### RNFS6: Validar Arquivos de Upload

**Descrição:** Sistema verifica arquivos antes de armazenar.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RNFS6.1 Validação de tipo MIME** | JPEG, PNG, GIF e MP4 | ✓ | |
| **RNFS6.2 Verificação real do conteúdo** | Baseada no conteúdo, não apenas extensão | ✓ | |
| **RNFS6.3 Armazenamento isolado** | Não em diretórios públicos ou executáveis | ✓ | |
| **RNFS6.4 URLs temporárias** | Com prazo de expiração | | ✓ |

##### RNFS7: Garantir Anonimato Real nas Publicações

**Descrição:** Sistema assegura que publicações anônimas não exponham dados pessoais.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RNFS7.1 Omissão na API** | Sem identificador, nome ou dados pessoais | ✓ | |
| **RNFS7.2 Omissão em metadados** | Removidos antes do armazenamento | ✓ | |
| **RNFS7.3 Consistência entre camadas** | Interface e API | ✓ | |

##### RNFS8: Respeitar Visibilidade de Perfil Privado na API

**Descrição:** Sistema garante que perfis privados não exponham dados.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RNFS8.1 Restrição na API** | Não retorna publicações para terceiros | ✓ | |
| **RNFS8.2 Dados permitidos** | Apenas reputação e número de publicações | ✓ | |

##### RNFS9: Solicitar Exclusão de Conta

**Descrição:** Usuário pode solicitar exclusão permanente em conformidade com LGPD.

| Regra de Negócio | Descrição | Obrigatório | Desejável |
|---|---|---|---|
| **RNFS9.1 Solicitação pelo usuário** | Opção nas configurações de perfil | ✓ | |
| **RNFS9.2 Confirmação antes da exclusão** | Exige confirmação explícita | ✓ | |
| **RNFS9.3 Exclusão de dados pessoais** | Removidos ou anonimizados em 30 dias | ✓ | |
| **RNFS9.4 Publicações após exclusão** | Anonimizadas | | ✓ |

### DIAGRAMA DE CASOS DE USO

Um diagrama de casos de uso é um tipo de diagrama da UML (Unified Modeling Language) que representa, de forma visual e simplificada, as interações entre os usuários e um sistema, descrevendo o que o sistema deve fazer do ponto de vista do usuário final.

Ele é composto por:
- **Atores:** Representados por bonecos
- **Casos de Uso:** Representados por elipses com o nome da funcionalidade
- **Relações:** Associações, inclusões (*include*) e extensões (*extend*)

Seu principal objetivo é capturar os requisitos funcionais do sistema de maneira acessível, facilitando a comunicação entre desenvolvedores, analistas e stakeholders que não possuem conhecimento técnico aprofundado.

### DIAGRAMA DE CLASSES

O diagrama de classes, que representará a estrutura estática do sistema (classes, atributos e relacionamentos), encontra-se em desenvolvimento pela equipe do projeto e será incorporado a esta documentação em versão futura.

---

## REGRAS DE NEGÓCIO

### O QUE É?

O **Hiker** é um aplicativo de avaliações geolocalizadas de destinos de viagem, que centraliza experiências reais de viajantes em uma única plataforma com sistema de reputação. O projeto resolve um problema concreto: as informações sobre destinos hoje estão fragmentadas entre TripAdvisor, Google Maps, Instagram, e outras plataformas sem foco em viagem e na credibilidade de quem avalia.

O Hiker propõe um feed de avaliações com nota e rótulos, histórico de viagens do usuário e um algoritmo de preferências que evolui com o uso.

### PARA QUEM É FEITO?

O público-alvo do aplicativo são **pessoas interessadas em viajar**, seja em viagens longas e distantes ou curtas e próximas. Inicialmente, o projeto irá abordar apenas o público brasileiro em busca de destinos de viagens e avaliações confiáveis de pessoas reais com uma reputação verificada.

### COMO SERÁ FEITO?

O Hiker será desenvolvido utilizando:
- **MAUI** para o aplicativo mobile
- **NestJS** para backend
- **PostgreSQL** como banco de dados
- **APIs externas de localização**

A distribuição acontecerá pelas lojas de aplicativos, com presença obrigatória no Android, além de indicação entre viajantes, parcerias com agências de turismo e divulgação em redes sociais como Instagram e TikTok.

A operação envolve hospedagem, backup, monitoramento e conformidade com a LGPD.

### QUANTO IRÁ CUSTAR?

A estrutura de custos contempla o time de desenvolvimento, infraestrutura de backend, banco de dados e APIs externas, além dos custos operacionais contínuos de hospedagem, segurança e suporte.

A receita virá inicialmente de:
- Anúncios ou patrocínios no feed
- Prioridade em buscas e recomendações
- Possível modelo de mensalidade ou custo por mil visualizações (CPM)

No futuro, o modelo se expande com:
- Plano premium para viajantes
- Comissões por parcerias com empresas de turismo

---

## ESTUDO DE VIABILIDADE

## MODELO DE DADOS

Um modelo de banco de dados é uma representação abstrata que define a estrutura, organização e as regras de como os dados são armazenados, relacionados e manipulados em um sistema de banco de dados.

Ele serve como um esquema conceitual que determina de que forma as informações são organizadas, seja em tabelas com linhas e colunas, em documentos JSON aninhados, em pares de chave-valor, entre outros.

A escolha do modelo influencia diretamente a eficiência das consultas, a escalabilidade do sistema e a facilidade de manutenção, sendo uma das decisões mais fundamentais no projeto de qualquer aplicação que lida com dados persistentes.

---

## DESIGN

Com base nos princípios apresentados por Steve Krug em "Don't Make Me Think" (2014), o design de aplicativos é o processo de planejar e construir a interface e a experiência de uso de um software mobile, com foco em tornar a interação mais simples e intuitiva.

Krug defende que um bom design não deve exigir que o usuário precise parar para pensar sobre como usar o sistema; cada tela, botão e fluxo de navegação deve comunicar sua função de forma imediata e óbvia. Isso envolve decisões sobre hierarquia visual, organização do conteúdo, escolha de componentes de interface e consistência entre as telas, sempre orientadas pelo comportamento real do usuário.

No contexto de aplicativos mobile, esse processo ganha ainda mais importância dado o espaço reduzido de tela e a natureza dinâmica do uso em movimento, o que exige que cada elemento presente na interface justifique sua existência e contribua diretamente para que o usuário atinja seus objetivos com o mínimo de esforço cognitivo possível.

Deste modo, o design se torna indispensável para a criação de um aplicativo, sendo o protótipo uma estrutura base para o desenvolvimento do software.

### PALETA DE CORES

A paleta de cores deste projeto é composta pelo **amarelo** como cor principal e o **laranja** como cor secundária.

De acordo com Eva Heller em "A Psicologia das Cores" (2013), o amarelo é a cor mais associada à alegria, otimismo e aventura, os quais são sentimentos diretamente conectados à experiência de viajar e explorar novos lugares. Por ser a cor de maior luminosidade visível ao olho humano, o amarelo naturalmente atrai atenção e transmite energia, o que favorece o engajamento do usuário em uma plataforma cujo objetivo é despertar o desejo de conhecer novos destinos.

Aliado aos tons de laranja como cor secundária, os quais Heller associa à sociabilidade, entusiasmo e movimento, a paleta reforça a proposta central do aplicativo: uma comunidade ativa de viajantes compartilhando experiências reais. A combinação também garante boa legibilidade e contraste quando aplicada sobre fundos claros, atendendo aos requisitos de usabilidade e mantendo uma identidade visual marcante e coerente com o universo do turismo.

### TIPOGRAFIA

A fonte **Amiko**, do autor Impallary Type, foi escolhida para a implementação deste projeto. Segundo os princípios de tipografia aplicada ao design digital (BRINGHURST, 2004), uma boa tipografia para interfaces deve equilibrar legibilidade, neutralidade e personalidade, características que a Amiko reúne com consistência.

Desenvolvida pelos designers Pablo Impallari, Rodrigo Fuenzalida e Andres Torres e disponibilizada pelo Google Fonts, a Amiko é uma fonte sans-serif humanista projetada especificamente para funcionar bem em telas de baixa resolução, o que a torna especialmente adequada para aplicativos mobile direcionados ao público brasileiro, onde a diversidade de dispositivos Android é uma realidade.

Seus traços arredondados conferem um caráter amigável e acessível à interface, sem perder a clareza necessária para a leitura de avaliações, descrições de locais e informações de perfil. A Amiko contribui para uma identidade visual que equilibra dinamismo e confiabilidade, reforçando a proposta do aplicativo de ser uma plataforma ao mesmo tempo vibrante e digna de confiança.

### LOGO

O logotipo é a representação visual da identidade de uma marca, sendo o principal elemento pelo qual um produto ou empresa é reconhecido pelo público. Segundo Robin Landa (2010), um bom logo deve ser singular, memorável e capaz de funcionar bem em diferentes contextos e tamanhos; desde um ícone minúsculo na tela de um celular até uma peça de divulgação em grande formato.

No caso do aplicativo Hiker, a decisão de utilizar o nome completo "Hiker" como logotipo principal e a abreviação "Hi" como ícone do aplicativo na loja é uma escolha estrategicamente sólida por diversas razões:

- O nome completo garante clareza e reconhecimento imediato da marca dentro do aplicativo
- A abreviação "Hi" para o ícone é uma solução mais funcional em espaços reduzidos
- "Hi" carrega um duplo significado: é ao mesmo tempo a contração natural de "Hiker" e uma saudação universal em inglês, reforçando o caráter social e acolhedor da plataforma

Foram projetados dois logos para este projeto:
1. **Logotipo:** Utilizado dentro da plataforma
2. **Isotipo:** Utilizado nos dispositivos móveis para representar o aplicativo

### WIREFRAME

O wireframe é uma representação visual esquemática e de baixa fidelidade de uma interface, utilizado nas etapas iniciais do processo de design para definir a estrutura, hierarquia e disposição dos elementos de uma tela antes que qualquer decisão estética seja tomada.

Segundo Jesse James Garrett em "The Elements of User Experience" (2011), o wireframe opera na camada estrutural do design, sendo responsável por traduzir os requisitos funcionais do sistema em arranjos visuais concretos, definindo onde cada componente — botões, campos de texto, imagens, menus e listas — estará posicionado e como o usuário irá interagir com eles.

Por ser propositalmente desprovido de cores, tipografias definitivas e imagens reais, o wireframe permite que a equipe de desenvolvimento e os stakeholders avaliem o fluxo e a usabilidade da interface sem se distrair com elementos visuais, facilitando revisões rápidas e baratas antes que o projeto avance para etapas mais custosas como o mockup e o protótipo.

No contexto do Hiker, os wireframes são especialmente importantes para validar decisões como a disposição do feed na tela inicial, a organização das informações na página de um local e a estrutura do perfil do usuário, garantindo que a experiência de navegação seja intuitiva antes mesmo de uma linha de código ser escrita.

---

## PROTÓTIPO

O protótipo é uma versão interativa e navegável da interface de um aplicativo, desenvolvida com o objetivo de simular a experiência real de uso antes que o produto seja efetivamente construído.

De acordo com Bill Buxton (2010), o protótipo vai além do wireframe ao adicionar interatividade, transições e, muitas vezes, elementos visuais próximos do design final, permitindo que usuários reais testem os fluxos de navegação e forneçam feedback concreto sobre a experiência.

Diferente do wireframe, que responde à pergunta "onde cada coisa estará?", o protótipo responde à pergunta "como o usuário vai se mover entre as telas e interagir com o sistema?". Essa distinção é fundamental no processo de design centrado no usuário, pois permite identificar problemas de usabilidade, inconsistências nos fluxos e pontos de fricção na jornada antes que o desenvolvimento seja iniciado, reduzindo significativamente o custo de correções tardias.

No caso do Hiker, um protótipo bem construído permitiria, por exemplo, validar se o fluxo de criação de uma publicação é fluido e compreensível para o usuário, ou se etapas precisam ser reorganizadas ou simplificadas para garantir uma experiência mais satisfatória.

*Os protótipos foram criados pela equipe do projeto utilizando a ferramenta Figma.*

---

## APLICAÇÃO

O Hiker é um **aplicativo mobile de avaliação colaborativa de destinos turísticos**, desenvolvido para dispositivos Android utilizando o framework **.NET MAUI**. Sua proposta central é resolver a descentralização das informações turísticas, problema identificado a partir de entrevistas realizadas com viajantes frequentes, que relataram a dificuldade de reunir opiniões confiáveis sobre um destino em um único lugar.

O aplicativo permite que usuários cadastrados:
- Publiquem avaliações sobre localidades
- Atribuam notas
- Adicionem rótulos descritivos
- Incluam fotos e vídeos
- Interajam com publicações de outros usuários por meio de concordâncias e discordâncias

### Arquitetura do Sistema

O sistema é composto por **três camadas principais**:

1. **Frontend Mobile:** Desenvolvido em MAUI
2. **Backend:** Construído com NestJS (framework Node.js orientado a módulos)
3. **Banco de Dados:** PostgreSQL relacional hospedado em Supabase
4. **API:** Hospedada na plataforma Microsoft Azure para escalabilidade e disponibilidade
5. **Geolocalização:** Integração com Google Places API

### Funcionalidades Implementadas

Até o momento, destacam-se as seguintes funcionalidades:
- Autenticação segura com tokens JWT
- Recuperação de senha por e-mail
- Feed cronológico de publicações
- Gestão completa de publicações (criação, edição, exclusão lógica)
- Publicações anônimas (com dados pessoais não expostos em nenhuma camada)

### Design e Identidade Visual

O aplicativo adota:
- **Fonte:** Amiko
- **Paleta de Cores:** Amarelo e laranja
- **Logotipo:** "Hiker" para uso interno
- **Isotipo:** "Hi" para lojas de aplicativos

O processo de design seguiu as etapas de wireframe e mockup, todas realizadas na ferramenta Figma, garantindo que as decisões de interface fossem validadas antes do início do desenvolvimento.

### Modelo de Negócio

A monetização será inicialmente por:
- Anúncios e patrocínios no feed
- Expansão futura: plano premium para viajantes frequentes
- Comissionamento por parcerias com agências de turismo

### Conformidade Legal

O projeto está em conformidade com a Lei Geral de Proteção de Dados (LGPD), adotando:
- Exclusão lógica de dados
- Anonimização de dados
- Gerenciamento seguro de sessões

---

## BANCO DE DADOS

O modelo de banco de dados foi desenvolvido durante o mês de março. Para este projeto, optou-se pela utilização de um **banco de dados relacional**.

O banco consiste em três tabelas principais:

1. **Usuário:** Dados e informações de contas
2. **Review:** Publicações e avaliações
3. **Denúncia:** Sistema de flagging (ainda não desenvolvido)

A funcionalidade de denúncia não foi desenvolvida nesta etapa do projeto, sendo assim a tabela ainda não foi criada no banco.

### Relacionamentos

- Um usuário pode ter **nenhuma ou várias** publicações
- Uma publicação deve ter **apenas um** usuário
- Os usuários podem criar, excluir e visualizar publicações

---

## CONSIDERAÇÕES FINAIS

O desenvolvimento do **Hiker** teve como objetivo central produzir um aplicativo mobile capaz de auxiliar viajantes a encontrarem informações específicas e confiáveis sobre destinos turísticos brasileiros, centralizando em uma única plataforma o conhecimento coletivo que hoje se encontra disperso entre redes sociais e outros serviços.

O desenvolvimento do Hiker permitiu à equipe vivenciar, na prática, as etapas fundamentais da engenharia de software, desde a elicitação de requisitos e modelagem do sistema até a implementação e o deploy em ambiente de produção.

Ao longo das sprints realizadas, foi possível validar a viabilidade técnica da solução proposta, consolidando uma aplicação mobile funcional capaz de centralizar avaliações turísticas de forma colaborativa, segura e em conformidade com a LGPD.

Ainda que funcionalidades previstas para a **Sprint 6**, como o algoritmo de preferências e o sistema completo de reputação, permaneçam em desenvolvimento, os resultados obtidos até o momento demonstram que o Hiker responde de maneira concreta ao problema identificado nas entrevistas iniciais com os stakeholders: a descentralização das informações sobre destinos de viagem.

Sendo assim, o desenvolvimento continuará no segundo semestre de 2026. Dessa forma, o projeto se consolida não apenas como um exercício acadêmico interdisciplinar, mas como uma proposta com potencial real de inserção no mercado de tecnologia voltado ao turismo brasileiro.

---

## REFERÊNCIAS BIBLIOGRÁFICAS

BUXTON, Bill. **Sketching user experiences: getting the design right and the right design**. Morgan kaufmann, 2010.

HELLER, Eva. **A psicologia das cores: como as cores afetam a emoção e a razão**. Editora Gustavo Gili, São Paulo. 2013, 541 p.

KRUG, Steve. **Don't make me think, Revisited: A Common Sense Approach to Web Usability**. New Riders, 2014.

LANDA, Robin. **Graphic Design Solutions**. Thomson Learning, 2nd ed, 2001.

LEITE JÚNIOR, Geraldo Soares. **As influências das novas tecnologias nas atividades turísticas e nos processos de roteiros de viagem**. Dissertação de Mestrado, 2023.

SILVA, João Vitor Rodrigues. **Turismo como estratégia de desenvolvimento econômico no Brasil: uma análise das políticas governamentais, de 1990 a 2022**. 2025.

---

[^1]: Dados sobre as receitas turísticas no Brasil: https://embratur.com.br/para-o-trader/inteligencia-de-dados/paineis-de-dados/receitas-turisticas/
