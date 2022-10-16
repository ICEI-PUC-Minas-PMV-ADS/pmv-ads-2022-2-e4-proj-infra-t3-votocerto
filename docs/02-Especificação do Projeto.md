# Especificações do Projeto
### Personas

| `Persona` | `Idade` | `Descrição` | `Fontes de informação utilizados` | `Motivações` | `Frustrações`  |  `Hobbies` |
|:-----------:|:---------:|:-------------:|:---------------------------------:|:--------------:|:----------------:|:------------:|
|Raimundo Mota|18|Estudante do ensino médio. Acabou de tirar o título de eleitor.|Instagram, Facebook, Twitter, Youtube|Verificcar como cada candidato se posiciona em relação às políticas de quotas raciais para ingresso na universidade.| Dificuldade de realmente conhecer os candidatos em ano eleitoral, já que tanto candidatos se maqueiam, quanto oposição dissemina fake news.|Filmes e séries, academia|
|Daniela Ferreira|34| Professora da rede pública estadual de Minas Gerais|Instagram, Portal de notícias, TV|Saber como os candidatos que ela pretende votar, se posicionam em relação ao piso salarial|Excesso de desinformação e notícias falsas, brigas em grupos de família.|Ler e mexer na Internet|
|Benício Almada |61|Policial Civil aposentado, se auto-intitulo como cidadão conservador de direita.|WhatsApp, rádio, TV, facebook e portais de notícias|Encontrar candidatos do legislativo que compartilhem da mesma pauta política e apoiem seus candidatos do executivo.|	Acredita que muitos (deputados e senadores) eleitos na última eleição por supostamente apoiarem o presidente da república, mudaram de posicionamento após estarem no poder.|Pescar, sair pra comer|
|Jaqueline de Jesus|27|Desempregada. Perdeu o emprego durante a pandemia e agora precisa de auxílio do governo para manter a família.|TV e WhatsApp| Ter acesso a informação confiável sobre os candidatos, e como eles pretendem reduzir a taxa de desemprego.|Recebe muita notícia no Whatsapp mas não sabe o que é verdade ou mentira|Assistir TV e passear com os filhos|

<span style="color:red">Pré-requisitos: <a href="1-Documentação de Contexto.md"> Documentação de Contexto</a></span>

> **Links Úteis**:
> - [Rock Content](https://rockcontent.com/blog/personas/)
> - [Hotmart](https://blog.hotmart.com/pt-br/como-criar-persona-negocio/)
> - [O que é persona?](https://resultadosdigitais.com.br/blog/persona-o-que-e/)
> - [Persona x Público-alvo](https://flammo.com.br/blog/persona-e-publico-alvo-qual-a-diferenca/)
> - [Mapa de Empatia](https://resultadosdigitais.com.br/blog/mapa-da-empatia/)
> - [Mapa de Stalkeholders](https://www.racecomunicacao.com.br/blog/como-fazer-o-mapeamento-de-stakeholders/)
>
Lembre-se que você deve ser enumerar e descrever precisamente e personalizada todos os clientes ideais que sua solução almeja.

## Histórias de Usuários

Com base na análise das personas forma identificadas as seguintes histórias de usuários:

|EU COMO... `PERSONA`| QUERO/PRECISO ... `FUNCIONALIDADE` |PARA ... `MOTIVO/VALOR`                 |
|--------------------|------------------------------------|----------------------------------------|
|Usuário do sistema  | Registrar minhas tarefas           | Não esquecer de fazê-las               |
|Administrador       | Alterar permissões                 | Permitir que possam administrar contas |

Apresente aqui as histórias de usuário que são relevantes para o projeto de sua solução. As Histórias de Usuário consistem em uma ferramenta poderosa para a compreensão e elicitação dos requisitos funcionais e não funcionais da sua aplicação. Se possível, agrupe as histórias de usuário por contexto, para facilitar consultas recorrentes à essa parte do documento.

> **Links Úteis**:
> - [Histórias de usuários com exemplos e template](https://www.atlassian.com/br/agile/project-management/user-stories)
> - [Como escrever boas histórias de usuário (User Stories)](https://medium.com/vertice/como-escrever-boas-users-stories-hist%C3%B3rias-de-usu%C3%A1rios-b29c75043fac)
> - [User Stories: requisitos que humanos entendem](https://www.luiztools.com.br/post/user-stories-descricao-de-requisitos-que-humanos-entendem/)
> - [Histórias de Usuários: mais exemplos](https://www.reqview.com/doc/user-stories-example.html)
> - [9 Common User Story Mistakes](https://airfocus.com/blog/user-story-mistakes/)

## Modelagem do Processo de Negócio 

### Análise da Situação Atual

Em época de eleições, é comum que os meios de comunicação dediquem-se a publicar matérias sobre as mais variadas fórmulas que o eleitor deve usar na hora de decidir em quem votar. Para obter informações sobre os candidatos, uma saída é ficar atento a notícias, jornais, revistas, propagandas eleitorais veiculadas no rádio e na televisão, pesquisas e debates entre os concorrentes. Dessa forma, é possível saber se o candidato já esteve envolvido em algum escândalo, o que ele realizou em mandatos anteriores e avaliar suas propostas.   

### Descrição Geral da Proposta

A proposta do Vote Certo é centralizar em uma única plataforma, candidatos e políticos eleitos, para os candidatos, se são novos no cenário político ou se já foram eleitos alguma vez, o que estes tem feito no governo, projetos que tem sido favoráveis e/ou contra, gastos divulgados no portal da transparência. Além disso o sistema também contribuirá para evitar a disseminação de mentiras e a desinformação, voltado para checagens, fontes ouvidas e veículo de origem.

### Processo 1 – Cenário atual

O fluxograma abaixo ilustra o cenário atual deste processo:

![Processo 1](img/02-bpmn-proc1.png)

### Processo 2 – Cenário Vote Certo

O fluxograma abaixo ilustra o cenário utilizando a aplicação Vote Certo como ferramenta:

![Processo 2](img/02-bpmn-proc2.png)

## Indicadores de Desempenho

Apresente aqui os principais indicadores de desempenho e algumas metas para o processo. Atenção: as informações necessárias para gerar os indicadores devem estar contempladas no diagrama de classe. Colocar no mínimo 5 indicadores. 

Usar o seguinte modelo: 

![Indicadores de Desempenho](img/02-indic-desemp.png)
Obs.: todas as informações para gerar os indicadores devem estar no diagrama de classe a ser apresentado a posteriori. 

## Requisitos

As tabelas que se seguem apresentam os requisitos funcionais e não funcionais que detalham o escopo do projeto. Para determinar a prioridade de requisitos, aplicar uma técnica de priorização de requisitos e detalhar como a técnica foi aplicada.

### Requisitos Funcionais

|ID    | Descrição do Requisito  | Prioridade |
|------|-----------------------------------------|----|
|RF-001| Permitir a criação de contas, dentro do site e do App. | ALTA | 
|RF-002| Ter uma página para a listagem dos candidatos.   | ALTA |
|RF-003| Ter uma página para a listagem dos eleitos e membros ativos dos 3 poderes .  | ALTA |
|RF-004| Ter um link para o plano de governo de cada candidatos a partir do seu regisstro.   | ALTA |
|RF-005| Informar se o candidato já ocupou algum cargo no governo.   | ALTA |
|RF-006| Listar, dentro de cada candidato e membro ativo do governo, projetos de lei propostos por eles, caso eles já tenham proposto algum. | ALTA |
|RF-007| Ter uma página com todas as leis, decretos, resoluções ... já aprovadas (Resumo e link para o arquivo oficial no portal oficial do governo). | ALTA|
|RF-008| Na página de legislações. listar todos que votaram a favor e contra   | MEDIA |
|RF-009| Na página principal, permitir que o usuário pesquise dinamicamente, termos que deseja buscar |MEDIA|
|RF-010| Permitir que o usuário crie alertas por localidade, candidatos ou membros ativos, assunto que deseja receber notificação | BAIXA |
|RF-011| Cada candidato ou membro ativo do governo, precisa ter sua própria página, com informações do mesmo.   | ALTA |
|RF-012| Ter uma página de fake check. com notícias atuais.   | MÉDIA |


### Requisitos não Funcionais

|ID     | Descrição do Requisito  |Prioridade |
|-------|-------------------------|----|
|RNF-001| Deve existir uma padronização na navegação tanto no Mobile quando no Web. | ALTA | 
|RNF-002| O Site deve atender aos requisitos de SEO, aplicados pelo Google. |  MÉDIA |
|RNF-003| O App e a aplicação Web, devem compartilhar as mesmas informações de login e cadastro de usuários. |  ALTA | 



## Restrições

O projeto está restrito pelos itens apresentados na tabela a seguir.

|ID| Restrição                                             |
|--|-------------------------------------------------------|
|01| O projeto deverá ser entregue até o final do semestre |
       |
## Diagrama de Casos de Uso

O diagrama de casos de uso é o próximo passo após a elicitação de requisitos, que utiliza um modelo gráfico e uma tabela com as descrições sucintas dos casos de uso e dos atores. Ele contempla a fronteira do sistema e o detalhamento dos requisitos funcionais com a indicação dos atores, casos de uso e seus relacionamentos. 

As referências abaixo irão auxiliá-lo na geração do artefato “Diagrama de Casos de Uso”.

> **Links Úteis**:
> - [Criando Casos de Uso](https://www.ibm.com/docs/pt-br/elm/6.0?topic=requirements-creating-use-cases)
> - [Como Criar Diagrama de Caso de Uso: Tutorial Passo a Passo](https://gitmind.com/pt/fazer-diagrama-de-caso-uso.html/)
> - [Lucidchart](https://www.lucidchart.com/)
> - [Astah](https://astah.net/)
> - [Diagrams](https://app.diagrams.net/)

# Matriz de Rastreabilidade

A matriz de rastreabilidade é uma ferramenta usada para facilitar a visualização dos relacionamento entre requisitos e outros artefatos ou objetos, permitindo a rastreabilidade entre os requisitos e os objetivos de negócio. A matriz contempla todos os elementos relevantes que fazem parte do sistema, bem como os *stakeholders* envolvidos no projeto. 

A matriz deve contemplar todos os elementos relevantes que fazem parte do sistema, conforme a figura meramente ilustrativa apresentada a seguir.

![Exemplo de matriz de rastreabilidade](Matriz de Rastreabilidade.PNG)

> **Links Úteis**:
> - [Artigo Engenharia de Software 13 - Rastreabilidade](https://www.devmedia.com.br/artigo-engenharia-de-software-13-rastreabilidade/12822/)
> - [Verificação da rastreabilidade de requisitos usando a integração do IBM Rational RequisitePro e do IBM ClearQuest Test Manager](https://developer.ibm.com/br/tutorials/requirementstraceabilityverificationusingrrpandcctm/)
> - [IBM Engineering Lifecycle Optimization – Publishing](https://www.ibm.com/br-pt/products/engineering-lifecycle-optimization/publishing/)


# Gerenciamento de Projeto

De acordo com o PMBoK v6 as dez áreas que constituem os pilares para gerenciar projetos, e que caracterizam a multidisciplinaridade envolvida, são: Integração, Escopo, Cronograma (Tempo), Custos, Qualidade, Recursos, Comunicações, Riscos, Aquisições, Partes Interessadas. Para desenvolver projetos um profissional deve se preocupar em gerenciar todas essas dez áreas. Elas se complementam e se relacionam, de tal forma que não se deve apenas examinar uma área de forma estanque. É preciso considerar, por exemplo, que as áreas de Escopo, Cronograma e Custos estão muito relacionadas. Assim, se eu amplio o escopo de um projeto eu posso afetar seu cronograma e seus custos.

## Gerenciamento de Tempo

Com diagramas bem organizados que permitem gerenciar o tempo nos projetos, o gerente de projetos agenda e coordena tarefas dentro de um projeto para estimar o tempo necessário de conclusão.

![Diagrama de rede simplificado notação francesa (método francês)](img/02-diagrama-rede-simplificado.png)

O gráfico de Gantt ou diagrama de Gantt também é uma ferramenta visual utilizada para controlar e gerenciar o cronograma de atividades de um projeto. Com ele, é possível listar tudo que precisa ser feito para colocar o projeto em prática, dividir em atividades e estimar o tempo necessário para executá-las.

![Gráfico de Gantt](img/02-grafico-gantt.png)

## Gerenciamento de Equipe

O gerenciamento adequado de tarefas contribuirá para que o projeto alcance altos níveis de produtividade. Por isso, é fundamental que ocorra a gestão de tarefas e de pessoas, de modo que os times envolvidos no projeto possam ser facilmente gerenciados. 

![Simple Project Timeline](img/02-project-timeline.png)

## Gestão de Orçamento

O processo de determinar o orçamento do projeto é uma tarefa que depende, além dos produtos (saídas) dos processos anteriores do gerenciamento de custos, também de produtos oferecidos por outros processos de gerenciamento, como o escopo e o tempo.
Dentro deste contexto, foi elaborado um orçamento estimado para o desenvolimento do projeto Vote Certo, podendo sofrer alterações.

![Orçamento](img/02-orcamento.png)



















