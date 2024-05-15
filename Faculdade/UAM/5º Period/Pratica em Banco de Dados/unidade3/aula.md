# Mineração de dados INSPIRE_SE.

Dados tem grandes valores nas organizações...

- extrai dados , manipula e carrega em outro destino...

- python... pandas... powerBI...\

# Tendencias...

- big data...

# Videoaula...

## Cursores em SQL

dados de registro, manipular dados...

- delete e update trata tabela completa

- cursores registro de linha a linha....
  - select que retorna subconjunto e ent trabalha linha a linha

TABELA x de pedidos tem qtd vendida de x item, vc quer inserir x qtd de linhas na tabela com base em y coisa... que gera inserção na tabela filha...

### Cursores podem gerar problemas de perfromance !!!

- Uso de rede -> muitas chamadas
- Uso de memória do cliente
  ![problemas uso de cursores](image.png)

Alternativas ao uso dos cursores : inner join , left join , right join...

## Big Data e Data Lakes

BIGDATA > geramos muitossss dadosssssssss > mercados, lojas , rede social... GERA MUUITOOSS DADOSSS

dados tem q gerar insights... ordem que as coisas funcinonam...

-DATA LAKE E DATA WAREHOUSE

alguns tipos de dados nao sao compativeis com relacional
data lake -> base para criacao de paineis , bi , machine learning.... permitem procurar padroes nos dados...
![alt text](image-1.png)

NOSQL - criacao devido a diversidade de dados... MONGODB pares de valores
key value.

## banco de dados baseados em documentos - noSQL mongo db...

- banco de dados e uma gigantesca PUTARIA
- armazenar video-audio
- json.... xml....
- associa a um ID
  ![alt text](image-2.png)
  acessa o dado de maneira mais rapida

![alt text](image-3.png)

Conceito de datalake , bigdata e data warehouse de acordo com o GPT

Vamos explorar esses conceitos que são fundamentais no mundo da análise de dados e do gerenciamento de informações:

### Big Data

Big Data refere-se a conjuntos de dados extremamente grandes que são complexos e crescem exponencialmente com o tempo. Esses dados são tão volumosos e complexos que os métodos tradicionais de processamento de dados são inadequados para lidar com eles. Big Data é caracterizado por três principais atributos, conhecidos como os "3 Vs":

- **Volume**: A quantidade de dados gerados é maciça, frequentemente medindo em terabytes ou petabytes.
- **Velocidade**: A velocidade com a qual os dados são gerados e processados é crucial; muitas vezes, eles precisam ser analisados em tempo real.
- **Variedade**: Os dados vêm em todos os tipos de formatos, desde estruturados, como bancos de dados, até não estruturados, como textos, imagens e vídeos.

### Data Lake

Um Data Lake é um sistema ou repositório que armazena uma grande quantidade de dados brutos em seu formato nativo. A ideia é que os dados possam ser armazenados sem uma estrutura definida, permitindo mais flexibilidade na hora de processar e analisar diferentes tipos de dados. Data Lakes são geralmente usados para armazenar Big Data e são eficazes para executar análises de dados de alta complexidade e machine learning, pois permitem o armazenamento de dados não só estruturados, mas também semiestruturados e não estruturados.

### Data Warehouse

Diferentemente de um Data Lake, um Data Warehouse é um sistema usado para o armazenamento e análise de dados que são estruturados e filtrados para um propósito específico. Os dados aqui são limpos e transformados (processo conhecido como ETL - Extração, Transformação e Carga) antes de serem armazenados. Isso torna um Data Warehouse ideal para realizar análises complexas e consultas de dados eficientes em um ambiente estável e controlado. Os Data Warehouses são projetados para facilitar a análise de negócios e relatórios, suportando funções como OLAP (Processamento Analítico Online).

Em resumo, enquanto o Big Data descreve informações em grande escala que crescem rapidamente, um Data Lake é um depósito para armazenar uma vasta quantidade de dados brutos, e um Data Warehouse é uma solução mais refinada que ajuda as organizações a realizar análises detalhadas a partir de dados estruturados e limpos.
