# Unidade 2

### Javascript ::: Inpire-se

    : Qual a importância do Javascript para o Desenvolvimento WEB??
    :: Projetos Interativos
    :: Essencial para o Mercado de Trabalho

## Desenvolvimento de Software para a WEB.

### O que é PMI - Project Management Institute

- Solução para gerenciar riscos, problemas e incertezas no Desenvolvimento de Software

- É a assoçiação líder mundial para todos aqueles que consideram a gestão de projetos, programas e portfólios a sua profissão
- Métrica utilizada para garantir que os projetos são organizados/manuseados de maneira assertiva
- Pode ser utilizado em qualquer tipo de projeto...
  As boas práticas de Gerenciamento de Projetos, descritas no PMBOK, podem ser aplicadas em todos os tipos de projetos, independentemente de segmento, área, dimensões, pessoas envolvidas, prazos e orçamentos.
- Utilizado para mitigar Riscos.

**Oque é um projeto:**
É um esforço temporário para criar um produto, serviço, ou resultado exclusivo. No caso de software é um projeto temporário.

Por melhor que ele seja, ele vai se transformando... Ele muda de versão, cada versão é algo temporário desenvolvido.

**Para que serve o PMI:**

- Desenvolver um novo produto ou serviço
- Efetuar mudança na estrutura, no pessoal ou no estilo de uma organização.
- Conceber um novo veículo de transporte
- Desenvolver ou adquirir um sistema de informações novo ou modificado
- Construir um edifício ou uma instalação
- Conduzir uma campanha política
- Implantar um novo procedimento ou processo de negócio.

**Recomendações para projetos de Software:**

Projetos de software são atividades de alto riscos...

![alt text](image-1.png)

- Dentro riscos inerentes no desenvolvimento de Software... A gestão de projetos e onde ocorre mais riscos...

- A gerencia de risco esta muito presente nessa parte de gestão

### PMI E o Desenvolvimento de Software

- Riscos em projetos de softwares são uma série de fatores ou condições que podem representar uma séria ameaça para o êxito da realização do projeto.

- Ameaças geralmente que trazem insatisfações honerosas... (Gasto de mais horas, mais dinheiro...)

##### Estudo conduzido pelo The Standarship Group (2000) mostra, por meio de Chaos Report, o resultado final sobre projetos de software

O que mais acontece quando chega no apice da entrega de um projeto de software.

1. 28% dos projetos do referido ano foram projetos de sucesso, entregues no tempo e com o custo previstos com todas as funcionalidades especificadas.
2. 49% foram entregues com atraso, fora do custo ou não atendendendo as funcionalidades previstas.
3. 23% foram cancelados antes de sua finalização. Segundo Emmam & Koru 2008.

Faltou uma boa definicão de escopo...

##### E qual o problema que mais ocorre?

Apesar das melhorias ja alcançadas, muitos projetos de desenvolvimento de software ainda usam mais recursos do que o planejado, levam mais tempo para ser concluídos e fornecem menos qualidade e funcionalidade do que o esperado

Justamente para mitigar os problemas que existe a métodologia do PMI

![alt text](image-2.png)

Muito importante esses requerimentos...

## Falhas no desenvolvimento de Software

**Planejamento!** Muito importante na hora de o desenvolvimento de um Software.

Falhas em projetos são resultado de uma multiplicidade de riscos inerentes em ambiente de projetos de software.

1. Metas irrealistas (Ideias inalcançaveis), expectativa não sanada
2. Tempo > Estimativas imprecisa de recursos..

Apesar de alguns gestores afirmarem que gerenciam os riscos em seus projetos, há evidencias de que **não o gerenciam sistemicamente**. Da mesma forma, avaliam riscos técnicos, em detrimento dos riscos de mercado e financeiros, vitais para o suceso de desenvolvimento de software.

As mudanças de **requisito e escopo** são as principais razões para cancelamento de projetos.

##### A adoção de padrões de projeto auxilia com:

1. Criação de dinamicidade
2. Redução de custos do sistema

### MVC

Dentre as vantagens, destacamos:

- Reutilização de código, diminuindo o tempo e o esforço para o desenvolvimento de componentes de software

- Melhor estruturação do sistema, tornando-o mais legível, facilitando a abstração e manutenção.

- Facilitar a portabilidade para outros ambientes computacionais pois, com a adoção de padrões, pode-se projetar o sistema em camadas funcionais, separando aquelas que são dependentes daquelas independentes do ambiente no qual o sistema será implantado.

Na prática, existem duas grandes famílias de padrões de projeto: GRASP (General Responsibility Assignment Software Patterns – Padrões de Software de Atribuição Geral de Responsabilidade) e GOF (Gang of Four – Bando dos quatro).

De acordo com Palmeira (2013), a característica básica do GRASP é a sua centralização em critérios de responsabilidade, ou seja, com o GRASP, facilita-se a atribuição de responsabilidade a classes e objetos que comporão o sistema computacional. Por sua vez, os padrões baseados em GOF, possuem outros níveis de abstrações para que seja possível atuar no projeto dos sistemas computacionais.

###### Padrões de criação

Esses padrões são responsáveis pela definição pelo processo de criação. Constituem os padrões de criação: **_Factory Method, Abstract Factory, Singleton, Builder, Prototype._**

###### Padrões estruturais

Definem a forma de associação e organização entre os objetos e classes de forma a possibilitar a criação de estruturais complexas por meio da composição, herança e associação entre as classes. Fazem parte dos padrões estruturais: **_Adapter, Bridge, Composite, Decorator, Facade, Flyweight, Proxy._**

###### Padrões comportamentais

Voltados para a definição de como os objetos/classes de comunicam e se interagem, buscando um baixo acoplamento para permitir, assim, uma flexibilidade e reuso mais fácil dos componentes vinculados. Esse grupo de padrões é formado pelos seguintes padrões: **_Chain of Responsability, Command, Interpreter, Iterator, Mediator, Memento, Observer, State, Strategy, Template, Method, Visitor._**

[Introducão Padrão MVC Dev Media](https://www.devmedia.com.br/introducao-ao-padrao-mvc/29308)

##### Camada de Model

Representa o próprio processamento, ou seja, codifica as regras de negócio e gerencia o processo de armazenamento e recuperação de objetos persistentes, por intermédio da manipulação de sistemas de gerenciadores de bancos de dados (SGBD). A camada de modelo manipula os dados sem ter o conhecimento de quais, especificamente, serão utilizados. Essa tarefa é atribuída à camada controladora.

##### Camada de View

A camada de visão objetiva o interfaceamento com o usuário. A interface pode apresentar mudanças em função das alterações do estado da aplicação.

##### Camada de Controller

Tem a função de controlar e intermediar as ações entre as outras duas camadas, ou seja, define o comportamento do sistema em função da demanda do usuário.

---

Cabe salientar que a utilização de padrões, tal como o MVC, acarreta em muitos benefícios à produção das páginas, como a possibilidade de reutilização de código (diminuindo-se, assim, o tempo de codificação), melhor abstração do sistema de modo a permitir uma criação e uma manutenção mais eficientes e divisão das responsabilidades entre os colaboradores do desenvolvimento, de forma mais clara.

### Resumo Capítulo

Chegamos ao fim deste capítulo. Tivemos a oportunidade de entender como deixar as páginas dinâmicas. Para isso, passamos por alguns conceitos relativos aos padrões de projeto, utilização de linguagens (como JavaScript e PHP), para validar formulários, atuar na apresentação visual de sua página, assim como realizar o interfaceamento com o servidor.

Como foi abordado neste capítulo, construção de páginas não é um trabalho trivial, deve-se analisar muito bem o ambiente onde o sistema irá interagir, assim como as suas regras de negócio. Para facilitar, aplica-se padrões de projeto, para que o seu trabalho fique menos oneroso e com mais qualidade.

Com os pontos pelos quais caminhamos neste capítulo, esperamos que você continue incrementando as funcionalidades de suas páginas, para torná-las mais acessíveis, dinâmicas e independentes de tecnologias representadas pelos dispositivos que servirão para acessá-las.

Neste capítulo, você teve a oportunidade de:

- ter contato com padrões de projeto de modo que você possa aplicá-los no desenvolvimento de suas páginas;
- analisar e empregar JavaScript para a validação de formulários;
- esboçar e desenvolver soluções baseadas na utilização da linguagem PHP;
- compor um sistema/páginas pela aplicação de MVC;
- aplicar os conceitos para o desenvolvimento de páginas responsivas e acessíveis.
