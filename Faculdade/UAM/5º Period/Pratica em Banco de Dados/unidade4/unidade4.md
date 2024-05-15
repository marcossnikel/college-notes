# business inteligence (bi)

Data warehouse e datamart
-> orienta na tomada de decisoes

-> flexibilidade de informacoes

datamart sistema de gerenciamento-> mais especifico em informacoes....

dashboard -> gerenciar informacoes estrategicas de formas graficas...

faceis de se parâmetrizar.

banco de dados distribuidos -> compartilha infomracoes em varios servidores...

- performance
  info replica em varios equips
  diminui risco de perca de informacoes
  processar muita informacao.

equipamentos conectados em locais diferentes.

aplicar BI para informacao -> ter bons processos definidos sobre informacoes.

## Videoaula.

### Banco de dados e BI (Business Inteligence)

- possui aspectos relacionados a banco de dados
  guardos sao guardados para gerarem informacoes depois

uso de dados permite achismos e senso comum....

Cria-se um BI atraves de um Dasboard

representacoes graficas
tem q ter KPIs -> indicadores de performance....

dados sao gerados para calcular os KPIS
views e funcoes de agregacao que consulta os dados e retorna para montarmos o bang

sum - average.... consulta.... SQL

### Data Minning

informacao util e gerada atraves do dataminning

mineracao de dados

minera informacao atraves de registros (compras de clientes etc etc)

sistema de ERP -> gerencia transacoes financeiras

toda empresa tem planilha que gerencia transicao financeira...

transformar em informação UTIL.

busca padroes tradicional

- associacoes
- sequencias, verificacao de sazonalidades
- algoritmos que classificam os dados em grupos.
- uso de ferramentas estatisticas de egressao linear que permitem a realizacao de prognosticos

machine learning

- rede neural que encontra sozinho os padroes...

muitos padroes sao aprendidos automaticamente.....

### processamentos de dados distribuidos

- crescimento de dados assustador
- disco rigido -> velocidade rapida de procesasmento -> armazenamento muito grande e pouca velocidade.
- nao adianta gravar todas info em um unico dispositivo -> alternativa -> GOOGLE -> GOOGLE ClOUD
- google distribuiu as info -> precisa de mecanismos que controlem como foi distribuida -> tem q acessar varios lugares -> precisa processar os dados de maneira dsitribuida -> alguem q controle a sequencia do processamenti -> Map Reduce

![alt text](image.png)

pares chave valores dos documentos...
pega isso e condensa em outra chave valor que agruopa num reduce
![alt text](image-1.png)

Hadoop -\_> cria sistema de arquivos distribuidos e processa map reduce de forma dsitribuida, assim torna possivel
enfrentamento de grande quantidades de dados de maneira rapida.

Existe conjunto de serviodres espalhados, cada um com uma determinada capacidade de armazenamento.

servidores esstao na nuvem.
