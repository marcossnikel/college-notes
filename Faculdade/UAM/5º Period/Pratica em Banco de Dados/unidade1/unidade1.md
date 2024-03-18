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

#### Videoaula (Aula)

Manter banco de dados e de extrema importancia para qualquer sistema de informatica

Devido a sua impotancia e realizada por softwares especificos que armazenam banco de dados.

Esses softwares sao chamados de gerenciadores de banco de dados ou engines

### os mais comum

-sql server

- oracle
- mySQL

alem dos 3 maiores tem tambem o postgres, o mongoDB mas basicamente o mercado se divide entre esses 3 gerenciadores

### funcoes basicas

- armazenar dados
- garantir integridade dos dados.. (info correta)
- parece simples.. mas por ex um banco, uma transacao de dinheiro ocorre problemas...
- integridade dos dados...Dinheiro pode sair da minha conta e nao entrar na da outra pessoa, ou ele pode entrar na conta de outra pessoa e nao ter saido da minha conta.

- se o dado perde a integridade ele ja nao e valido

- sgdb se preocupa muito com a garantia da integridade da info armazenada

- sgbd deve possuir uma boa seguranca, somente pessoas que tem acessos as informações possam acessa-las ou modifica-las

- outra caracteristica e a velocidade o qual a info e disponibilizada
- dentro do sgbd as informacoes sao estruturadas seguindo o modelo relacional. ou seja, o modelo onde as tabelas sao criadas com campos e chaves que se relacionam entre si.

- e comom ter um codigo de um cliente em uma tabela onde os clientes estao armazenados, e em outra termos os pedidos com algo como clientId

- esse codigo do cliente esta presente nas duas tabelas para q possa buscar os pedidos de x cliente
- essa relacao implica na criacao de indices, que garante a velocidade na retirada das informacoes..
- a maneira com que o db organiza o indice impacta no desempenho ...

### problemas:

- tem q ser rapido... (a quantidade de dados armazenada por segundo e enorme e tem q se rapido..)

nao adianta ser so rapido, tem q ter rotinas e indices corretos nas tabelas para que a informacao seja disponibilizada de forma rapida e efetiva.

### cap 2 - Transacoes e integridade

A integridade e muito imporatnte, uma das formas de garantir a integridade e com o uso dos transactions(transcoes), que sao componentes monoliticos formados por conjuntos de operacoes que vao acontecer no banco de dados, e tendo que acontecer TODAS ou nenhuma.

#### Trasncoes

Normalmente define-se com um programa em mysql todos os bancos de dados hoje em dia falam essa linguagem...

Comeca uma transaco com o comando BEGIN TRANSACTINO. o que acontecer a partir desse ponto deve ser executado como um bloco unico

rETORNANDO ao exemplo do banco, teremos a retirada do saldo de uma conta e incremento de outra... (transacao)

sao duas operacao diferente que vao acontecer no db, em momentos diferentes, registros diferentes.... e podem envolver DIVERSAS TABELAS e atualizar todas delas na mesma tarnsaction

de qualque maneira, todas transactions vao dentro de uma estrutura unica comecando com begin transaction e no final vai-se ter o comando de commit.

o comando **commit** faz que a transaction seja gravada no db

o sgdb tem uma forma de garantir que todas sejam executadas ou nenhuma... Isso e feito atraves de **logs**, de registros do que estava sendo executado e ao executar o commit, tudo que havia sido executado e gravado no banco de dados.

Existe tambem o comando **rollback**, que e para cancelar uma transacao....

Em determinado momento, percebsmo que uma transacao nao pode prossegrir e nesse caso o proprio sistema pode emitir um comando de rollback para abortar todas as transacoes que estavam sendo realizadas.

um exemplo de rollback e quando vamos fazer um saque bancario em uma maquina automatica, e apos colocar a senha o mesmo comeca a ser executado, nesse momento o banco comeca atualizar as tabelas no db... Mas caso tenha algo que impeca a saida do money, nesse momento a maquina vai emitir um rollback e a transacao tera q ser cancelada...

o conceito de commit e rollback e muito importante

as transacoes afetam varias tabelas,e com isso afetas os INDICES delas...

a fonte mais comum de problmeas em db, e a corrupcao nao de tabela, mas de indices da tabelas...

FALAREMOS mais de indices em otimizacoes de consultas e velocidade de execucao de consultas, mas a garantira da integridade dos indices das tabelas e extremamente importante.

outra coisa tambem muito importante e criacao dos logs que permitem a replicacao dos bancos de dados.

uma empresa que tenhs 2 DB em locais diferentes , para garantir a integridade nos 2l ocais, tem que - se garantir que as transacoes que ocorram em um lugar tambem sejam replicadas em outro lugar.

para isso, os sgdb tem logs q sao replicados em lugares diferentes... entao o conceito de TRANSACTION vai alem de criar pequenos codigos que garantem todas a s tnrascoes ocorram ao mesmo tempo...

logs permitem a integridade nos dbs diferentes, garantindo equidade em dbs localizados em locais diferentes.

#### cap 3- otimizacao e indices em tabelas

cOMO FAZ para garantir que as informacoes sejam disponibilizadas na velocidade necessaria?

Nesse momento vem o conceito de **engines**, e o conceito de **indice** tambem se relacionando com a integridade.

Por exemplo, um arquivo de documentos em papel, com milhares de pastas..... pRECISA Localizar a pasta do cliente Armando...se o arquivo nao tiver organizacao localiza-lo vai demorar muito para encontra-lo

Se o arquivo tiver indice/organizado em ordem alfabetica que seja... sera mais facil.. E comum tambem criar indices no dB... cAMINHOS q o sistema encontra para otimizar consultas

- Podemos definir no banco de dados o nome como uma palavra importante e criar um indice para buscar pelo nome.

voltando ao exemplo das pastas... vc n tem o nome da pessoa mas sim o cpf.. toda a organizacao que foi feita nao vai servir de nada. Tera q ver pasta por pasta ate encontrar o determinado cpf...

em um banco de dados eletronicos e mais facil pois pode-se ter varios indices para a mesma tabela... pode ter pro nome, pro cpf... ambas buscas ficam rapidas

pode-se criar tambem indices unicos, que possam garantir a integridade.. o cpf por exemplo, e comum indexar as tebals de contatos e as tabelas de clietnes pelo cpf e colocar a obrigacao de que ele seja unico

isso significa q naquela tabela cada registro tem seu unico cpf, se tenta duplicar da erroo

pq teria 2 registro com msm cpf? problema de integridade...

Outra coisa, e que toda tabela tem uma chave primaria.Essa chave primaria e um campo ou um conjunto de campos que identifica unicamente aquele registro.

normalmente e um campo de codigo ou um conujunto de cmapos que faz com que o registro seja realmente unico dentro da tabela.

e essencial para a organizacao do DB e tambem a velocidade da info

ajuda com integridade e velocidade > INDICES...

Tem que colocar muito cuidado tambem com eles e nao colocar em todos campos pois cada indice ocupa esapco e precisa ser criado quando criamos a tabela no banco de dados e armazena mais informacao por conta do indice

Cada indice tambem pode ser corrompido e quando ocorre uma corrupcao de indice e um problema TENSO... o sgdb precisa do indice para funcionar adequadramente... corrupcao gera perda de dados

indices sao utilizados para o que realmente deve ser utilizado para as buscas......
