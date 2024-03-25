# Vídeo: Inspire-se

### Otimização de banco de dados

Modelos de banco de dados relacionais em produção devem ser otimizados com boas rotinas...

Mais volume e mais usuários causam atraso nas respostas.

Com o tempo, os usuários ficam mais seletivos e com necessidades individuais, entre elas o feedback e o tempo de resposta de algo...

Tempo é dinheiro.

A otimização traz muitos benefícios para a empresa:

- Melhora a eficiência do processo.
- Diminui reclamações.
- O tempo de consultas e retorno precisa ser ajustado.
- Quanto mais rápido, mais usuários são atendidos e suas necessidades cumpridas.
- Aprimoramento das lógicas implementadas originalmente...

Regras de negócio são atualizadas com o passar do tempo, adaptando-se aos novos interesses do mercado. Com isso, rotinas relacionadas às regras de negócio devem ser analisadas novamente.

A otimização no banco de dados torna aplicativos e sites mais eficientes...

- Confidencialidade.
- Integridade.
- Disponibilidade das informações.

É necessário ter segurança na base de dados... Algoritmos de criptografia são utilizados, como hash function... SHA.

Strings não podem ser decifradas facilmente.

Boas implementações de roles são necessárias.

É muito difícil controlar a informação na era digital...

Com relação à segurança, não há muita garantia, mas é necessário ter um bom plano e controle de risco... Isso minimiza danos na empresa de maneira física e mercadológica.

É muito importante compreender como utilizar os bancos de dados.

# Videoaula (Aula)

### Cap I - O Sistema de gerenciamento de banco de dados como um ambiente de desenvolvimento

armazenar e recuperar info ->>> ambiente de rotinas para acesso ao info

3 grupos de rotinas para coisa q cria q nao e so dados fornecidos

- tabelas virtuais / views
- procedures e functions
- trilhas / gatilhos

prgoramas criados pelo dba principalmente para a seguranca

- um site que o proprio user pode criar uma consulta sql e rodar em um db.
  - seria uma brecha de seguranca...

alem disso, como o site acessa ao db, o mesmo se torna a porta de entrada de infos, mas tambem porta de entrada para problemas...

tem q limitar o maximo doq o site pode com o db

rotinas sao criadas no db e o site somente executa as rotinas...

vantagens da utilizacao de rotinas...

AUTOMATISMO -> Acoes q ocorrem sempre que algo for inserido ou precisa-se de uma atualizacao em lote.

- ex: programa de fidelidade de cliente, onde ao atingir x nivel de vendas eles sejam enquadrados de forma diferente.... pode ser feito no db

a cada venda feita no db a categoria do cliente e atualizada, verificando o quanto foi consumido e mudando a classificacao do cliente.

as _(Rotinas)_ sao feitas usando SQL, ate mesmo bancos q nao sao sql podem criar rotinas internas.

alem de rotinas, tambem e imporatnte as VIEWS, consultas feitas regularmente no DB

essas consultas sao parecidas,muitas vezes a mudanca e em um parametro ou outro e por isso vamos criar consultas pardonizadas denominadas views onde daremos apenas o parametro e ela ira repetir o processo de criacao da consulta...

### Cap 2 - Views em história dos procedures

Duas coiass importanets dentor dos banco de dados sao os programas deles...

varios selects ficam bem grandes.... ai comeca a fazer relacionamento entre as tabelas

- cliente
- pedido
- item pedido

ex: codigo do cliente aparece na tabela do pedido e um codigo de pedidos que aparece na tabela de itens de pedidos.

as tabelas estao relacionadas...

existe tbm uma tabela de frete... pois devido a locacalizacao geografica do cliente nos temos diferentes custos
uma tabela de impostos.... depende do produto
tabelas de produtos....

Cliente fez um pedido pelo site e queremos colocar para ele uma tela com todas as informacoes que resuam o pedido feito.... Para que consiga tal info, precisa-se fazer uma consulta no db que esta relacionando inumeras tabelas ao mesmo tempo, tornando a consulta grande e complexa.

View -> Pegar uma consulta que relaciona varias tabelas e criar apenas uma view...

```sql
CREATE VIEW "NOME DA VIEW" AS "SELECT * FROM pedidos.."
```

A partir desse ponto, todas as vezes que quisermos refazer essa consulta devemos chamar essa view.Isso também tem um impacto grande em desempenho....

Os sistemas de banco de dados fazem uma serie de operacoes na hora de buscar dados e montar o resultado da consulta. Quando relaciona duas ou tres tabelas, eles buscam informacoes em cada tabela individualmente depois filtram para dar o resultado.

Essa busca inicial das tabelas, pode ser armazenada quando trabalhamos com uma view.

Ou seja, se tiver que fazer a mesma consulta varias vezes, onde o que vai mudar serao apenas os filtros aplicados ao fim da consulta.

A view e executada, cria tabelas temporarias na memoria do sistema de gerenciamento de banco de dados, e ficam armazenadas para quando forem executadas novamente as tabelas ja estarem la e sera necessario refazer apenas o filtro.

Isso ganha em performance alem de seguranca. podemos criar uma conta de usuario que nao de acesso a qualquer select, mas so consutla dado pelas views.

Ou seja, so consulta testada e padronizada...

#### Procedures

- views pegam dados, procedures modificam dados dos banco de dados...

Elas podem realizar um aumento de preços no sistema de vendas pela internet, podemos criar um procedure que dado algumas aliquotas de aumento ela aplique nos produtos cadastrados.

Vantagem de usar uma história de procedures... 1. Trabalho fica reduzido 2. Seguranca 3. Garantir logs de ocorridos..

As functions são muito parecidas com as procedures, mas retornam um unico valor
busca e retorna um unico valor...

### Cap 3 - Gatilhos / Triggers

Tipo de procedure especial..

Normalmente os gatilhos sao procedures, e se diferenciam pela maneira como sao executados.

A procedure e invocada pelo usuario do sistema de banco de dados, ja o gatilho acontece quando determinadas condicoes acontecem no DB....

pode-se criar u gatilho que sera executado imediatamente, antes da adicao de um registro...

por exemplo, podem ser usados para fazer uma verificacao de dados e se os dados que estao sendo colocados naquele registros sao validos...

chamado de right before, imediatamente antes da insercao dos dados no banco de dados.

tambem tem o gatilho right after, que e um gatilho executado depois da insercao do registro no db.

registrar hora q registro x foi criado....

Ele é muito importante quando quer dar rastreabilidade para as coisas, pode-se criar um gatilho que ira colocar no registro a hora q ele foi criado.

o gatilho nao e disparado pelo usuario, e disparado automaticamente pelo banco de dados quando alguma condicao dessa acontece.

Um uso comum de gatilhos e a criacao de um sistema de auditorias, podemos ter um banco de dados que armazena informacao importantes, com severidade, informacoes criticas de uma empresa...

e toda vez q essas informacoes sao atualizadas, o proprio db faz um registro a parte do que aconteceu...

por ex: cliente novo -> registro foi criado -> trigger e criao na tabela auditoria -> e registra quem, hora o ip da maquina que criou... e no momento de rastrear e melhor...

tem q ser usado com cuidado -> se uma tabela gera gatilho pra outra, que gera para a mesma, gera um loop infinito de triggers... crasha o db....

GATILHO E unico de uma tabela para a outra..

quando trabalha com muitas tabelas tem q prestar atencao para nao cair em um loop desses... crasha o sistema LEGAL...

sao muito uteis.... lidar com horas, dados de criacao...
