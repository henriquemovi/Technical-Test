#Technical-Test
##Technical Test - DataSprints


Foi criada uma instância de banco SQL Server no Amazon RDS no Free Tier para esse desafio.

A conexão ao banco foi feita através do Python, onde estão separados em 3 arquivos as cargas das stagings, as cargas frias de dimensões e as cargas incrementais de dimensões em T-SQL.

Para acessar o dashboard criado para esse desafio, basta acessar o através do link [Power BI]()

Foi utilizado o software DBFVIEWER para abrir as coordenadas geográficas das cidades brasileiras em formato .dbf e exportar para o formato .xls, e em seguida utilizado o SSIS(SQL Server Integration Services) para inserir os dados no banco.![SSIS](https://github.com/henriquemovi/Technical-Test/blob/master/SSIS%20Teste%20T%C3%A9cnico%20-%20DataSprints.png)

Para dar a carga inicial dos dados utilizei o SSIS para importar o arquivo MICRODADOS_ENEM.csv para dentro do banco com o nome de tabela raw_data, em seguida passei os dados ainda via SSIS para a tabela MICRODADOS_ENEM dentro do banco de dados e a partir daí utilizei apenas o T-SQL para fazer os ETLs e carregar o DataWarehouse.

Em relação à modelagem escolhida, utilizei a modelagem Snowflake com a intenção de obter uma modelagem sem redundâncias e também uma boa governança dos dados, separando as dimensões selecionadas através dos assuntos que seriam de relevância para filtrar os dados fatos na construção do Dashboard. Nesse caso não houve a necessidade de se estruturar uma modelagem híbrida com a modelagem Star Schema devido ao fato de não existir nenhuma análise no Dashboard com base apenas em dimensões filtrando outras dimensões. ![Modelagem](https://github.com/henriquemovi/Technical-Test/blob/master/Modelagem%20Teste%20T%C3%A9cnico%20-%20DataSprints.png)


