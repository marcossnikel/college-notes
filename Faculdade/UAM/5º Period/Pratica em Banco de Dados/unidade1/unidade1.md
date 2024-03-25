Aqui estão suas anotações corrigidas e formatadas em Markdown:

# Inspire-se

## Banco de Dados

### Hierárquico (1960 - IBM)

- Registro pai/único: Possui uma hierarquia semelhante a uma estrutura de árvore.
- Registros irmãos: Possuem uma ordem específica para armazenamento.

### Redes (Anteriormente Popular)

- Conjunto da matemática...
- Vários registros pais...
- Em 1970, Edgar Frank publicou "A Relational Model of Data for Large Shared Data Banks", abordando a extração e inserção de grandes quantidades de dados.

### Relacionais

- Bancos relacionais são formados por entidades, tabelas que referenciam objetos físicos do mundo real (pessoas, produtos, processos de venda e troca).
- Em 1985, Edgar Codd lançou 13 regras para bancos de dados relacionais.
- Na década de 1980, empresas começaram a criar seus próprios modelos de bancos de dados, como Oracle2 da Oracle, IBM SQL/DS, DB2 e o SQL Server da Microsoft.
- Contribuíram para o surgimento de novas linguagens de desenvolvimento mais adequadas à realidade do mundo e princípios de orientação a objetos.
- Surgimento de bancos de dados orientados a objetos e serviços em nuvem.

## NoSQL

- Ênfase em velocidade, volume de informações, big data e análise preventiva.
- Auxilia organizações na tomada de decisões mais eficientes.
- Fundamentais no processo de gestão corporativa.

### Videoaula (Aula)

Manter banco de dados é de extrema importância para qualquer sistema de informática.

Devido à sua importância, é realizada por softwares específicos que armazenam banco de dados.

Esses softwares são chamados de gerenciadores de banco de dados ou engines.

### Os mais comuns

- SQL Server
- Oracle
- MySQL

Além dos 3 maiores, também há o PostgreSQL e o MongoDB, mas basicamente o mercado se divide entre esses 3 gerenciadores.

### Funções básicas

- Armazenar dados
- Garantir integridade dos dados (informação correta)
- Parece simples, mas por exemplo, em um banco, uma transação de dinheiro ocorre problemas...
- Integridade dos dados... Dinheiro pode sair da minha conta e não entrar na da outra pessoa, ou ele pode entrar na conta de outra pessoa e não ter saído da minha conta.
- Se o dado perde a integridade ele já não é válido.
- SGBD se preocupa muito com a garantia da integridade da informação armazenada.
- SGBD deve possuir uma boa segurança, somente pessoas que têm acessos às informações podem acessá-las ou modificá-las.
- Outra característica é a velocidade com que a informação é disponibilizada.
- Dentro do SGBD, as informações são estruturadas seguindo o modelo relacional, ou seja, o modelo onde as tabelas são criadas com campos e chaves que se relacionam entre si.
- É comum ter um código de um cliente em uma tabela onde os clientes estão armazenados, e em outra termos os pedidos com algo como clientId.
- Esse código do cliente está presente nas duas tabelas para que possa buscar os pedidos de x cliente.
- Essa relação implica na criação de índices, que garantem a velocidade na retirada das informações.
- A maneira com que o DB organiza o índice impacta no desempenho...

### Problemas:

- Tem que ser rápido... (a quantidade de dados armazenada por segundo é enorme e tem que ser rápido...)
  Não adianta ser só rápido, tem que ter rotinas e índices corretos nas tabelas para que a informação seja disponibilizada de forma rápida e efetiva.

### Capítulo 2 - Transações e integridade

A integridade é muito importante, uma das formas de garantir a integridade é com o uso das transações, que são componentes monolíticos formados por conjuntos de operações que vão acontecer no banco de dados, e tendo que acontecer TODAS ou nenhuma.

#### Transações

Normalmente define-se com um programa em MySQL todos os bancos de dados hoje em dia falam essa linguagem...

Começa uma transação com o comando BEGIN TRANSACTION. O que acontecer a partir desse ponto deve ser executado como um bloco único.

Retornando ao exemplo do banco, teremos a retirada do saldo de uma conta e incremento de outra... (transação)

São duas operações diferentes que vão acontecer no DB, em momentos diferentes, registros diferentes.... E podem envolver DIVERSAS TABELAS e atualizar todas delas na mesma transação.

De qualquer maneira, todas transações vão dentro de uma estrutura única começando com BEGIN TRANSACTION e no final vai-se ter o comando de COMMIT.

O comando **COMMIT** faz que a transação seja gravada no DB.

O SGBD tem uma forma de garantir que todas sejam executadas ou nenhuma... Isso é feito através de **logs**, de registros do que estava sendo executado e ao executar o COMMIT, tudo que havia sido executado é gravado no banco de dados.

Existe também o comando **ROLLBACK**, que é para cancelar uma transação....

Em determinado momento, percebemos que uma transação não pode prosseguir e nesse caso o próprio sistema pode emitir um comando de ROLLBACK para abortar todas as transações que estavam sendo realizadas.

Um exemplo de ROLLBACK é quando vamos fazer um saque bancário em uma máquina automática, e após colocar a senha o mesmo começa a ser executado, nesse momento o banco começa atualizar as tabelas no DB... Mas caso tenha algo que impeça a saída do dinheiro, nesse momento a máquina vai emitir um ROLLBACK e a transação terá que ser cancelada...

O conceito de COMMIT e ROLLBACK é muito importante.

As transações afetam várias tabelas, e com isso afetam os ÍNDICES delas...

A fonte mais comum de problemas em DB, é a corrupção não de tabela, mas de índices da tabelas...

Falaremos mais de índices em otimizações de consultas e velocidade de execução de consultas, mas a garantia da integridade dos índices das tabelas é extremamente importante.

Outra coisa também muito importante é a criação dos logs que permitem a replicação dos bancos de dados.

Uma empresa que tenha 2 DB em locais diferentes, para garantir a integridade nos 2 locais, tem que se garantir que as transações que ocorram

em um lugar também sejam replicadas em outro lugar.

Para isso, os SGBD têm logs que são replicados em lugares diferentes... Então o conceito de TRANSACTION vai além de criar pequenos códigos que garantem todas as transações ocorram ao mesmo tempo...

Logs permitem a integridade nos DBs diferentes, garantindo equidade em DBs localizados em locais diferentes.

#### Capítulo 3 - Otimização e índices em tabelas

Como fazer para garantir que as informações sejam disponibilizadas na velocidade necessária?

Nesse momento vem o conceito de **engines**, e o conceito de **índice** também se relacionando com a integridade.

Por exemplo, um arquivo de documentos em papel, com milhares de pastas... Precisa localizar a pasta do cliente Armando... Se o arquivo não tiver organização localizá-lo vai demorar muito para encontrá-lo.

Se o arquivo tiver índice/organizado em ordem alfabética que seja... Será mais fácil... É comum também criar índices no DB... Caminhos que o sistema encontra para otimizar consultas.

- Podemos definir no banco de dados o nome como uma palavra importante e criar um índice para buscar pelo nome.

Voltando ao exemplo das pastas... Você não tem o nome da pessoa mas sim o CPF... Toda a organização que foi feita não vai servir de nada. Terá que ver pasta por pasta até encontrar o determinado CPF...

Em um banco de dados eletrônicos é mais fácil pois pode-se ter vários índices para a mesma tabela... Pode ter para o nome, para o CPF... Ambas buscas ficam rápidas.

Pode-se criar também índices únicos, que possam garantir a integridade... O CPF, por exemplo, é comum indexar as tabelas de contatos e as tabelas de clientes pelo CPF e colocar a obrigação de que ele seja único.

Isso significa que naquela tabela cada registro tem seu único CPF, se tenta duplicar dá erro...

Porque teria 2 registros com mesmo CPF? Problema de integridade...

Outra coisa, é que toda tabela tem uma chave primária. Essa chave primária é um campo ou um conjunto de campos que identifica unicamente aquele registro.

Normalmente é um campo de código ou um conjunto de campos que faz com que o registro seja realmente único dentro da tabela.

É essencial para a organização do DB e também a velocidade da informação.

Ajuda com integridade e velocidade > ÍNDICES...

Tem que colocar muito cuidado também com eles e não colocar em todos campos pois cada índice ocupa espaço e precisa ser criado quando criamos a tabela no banco de dados e armazena mais informação por conta do índice.

Cada índice também pode ser corrompido e quando ocorre uma corrupção de índice é um problema TENSO... O SGBD precisa do índice para funcionar adequadamente... Corrupção gera perda de dados.

Índices são utilizados para o que realmente deve ser utilizado para as buscas...

Espero que isso ajude! Se precisar de mais alguma coisa, estou à disposição.

### GPT OVERVIEW

Claro, aqui está a explicação dos comandos SQL em um único bloco Markdown:

````markdown
### Comandos SQL

#### SELECT

O comando `SELECT` é utilizado para recuperar dados de um banco de dados. Com ele, você pode especificar quais colunas deseja selecionar e de quais tabelas.

Exemplo:

```sql
SELECT nome, sobrenome FROM clientes;
```
````

Isso selecionará as colunas "nome" e "sobrenome" da tabela "clientes".

#### INSERT

O comando `INSERT` é utilizado para adicionar novos registros a uma tabela.

Exemplo:

```sql
INSERT INTO clientes (nome, sobrenome) VALUES ('João', 'Silva');
```

Isso adicionará um novo cliente com nome "João" e sobrenome "Silva" à tabela "clientes".

#### UPDATE

O comando `UPDATE` é utilizado para modificar dados existentes em uma tabela.

Exemplo:

```sql
UPDATE clientes SET sobrenome = 'Santos' WHERE id = 1;
```

Isso atualizará o sobrenome do cliente com ID igual a 1 para "Santos" na tabela "clientes".

#### DELETE

O comando `DELETE` é utilizado para excluir registros de uma tabela.

Exemplo:

```sql
DELETE FROM clientes WHERE id = 1;
```

Isso excluirá o cliente com ID igual a 1 da tabela "clientes".

#### BEGIN TRANSACTION, COMMIT e ROLLBACK

Esses comandos são usados para controlar transações em bancos de dados relacionais.

- `BEGIN TRANSACTION`: Inicia uma transação, indicando o início de um conjunto de operações que devem ser tratadas como uma unidade.
- `COMMIT`: Confirma as operações realizadas durante uma transação, fazendo com que as alterações sejam permanentemente aplicadas ao banco de dados.
- `ROLLBACK`: Cancela uma transação, revertendo todas as alterações feitas desde o início da transação.

Esses comandos são cruciais para garantir a consistência e integridade dos dados em um banco de dados, especialmente em cenários onde várias operações precisam ser tratadas de forma atômica, ou seja, todas ocorrem ou nenhuma ocorre.

```

Essa é a explicação dos comandos SQL em um único bloco Markdown. Se precisar de mais alguma coisa, estou à disposição para ajudar!
```
