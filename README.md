Análise de Clientes Inativos com AWS
Sobre o Projeto
Este projeto foi desenvolvido para resolver o desafio de identificar e compreender clientes que se tornaram inativos. Utilizando um pipeline de dados na Amazon Web Services (AWS), a solução transforma dados brutos em insights estratégicos, permitindo que a equipe de marketing entenda o perfil desses clientes e planeje ações de reengajamento mais inteligentes e eficazes.


Arquitetura da Solução
O fluxo de trabalho foi construído utilizando uma arquitetura serverless na AWS, seguindo as melhores práticas de processamento e análise de dados.

1. Coleta e Armazenamento de Dados

Tecnologia: Amazon S3.


Descrição: Os dados brutos de compras são centralizados em um bucket do Amazon S3, que atua como um data lake. Esta abordagem garante um armazenamento seguro, escalável e organizado para os dados, preparando-os para as próximas etapas.


2. Preparação dos Dados e Catálogo

Tecnologias: AWS Glue Crawler, AWS Glue Data Catalog.


Descrição: O AWS Glue Crawler é utilizado para escanear os dados no S3, inferir o esquema (colunas, tipos de dados) e criar uma "ficha" técnica no AWS Glue Data Catalog. Isso torna os dados facilmente detectáveis e acessíveis para outros serviços da AWS.


3. Processamento e Análise de Negócio

Tecnologia: AWS Glue (ETL Job).


Descrição: Um Job de ETL no AWS Glue executa a principal lógica de negócio. Ele limpa e organiza os dados e, em seguida, aplica regras para classificar os clientes inativos em segmentos específicos, como "Viajantes de Alto Valor" ou "Viajantes Sazonais".

4. Análise e Visualização Estratégica

Tecnologias: Amazon Athena, SQL Views, Power BI.


Descrição: O Amazon Athena é usado para executar consultas SQL diretamente nos dados armazenados no S3. Foram criadas 

Views SQL para simplificar o acesso aos dados já classificados. Finalmente, o Power BI se conecta ao Athena para transformar esses dados em painéis interativos e visuais para a equipe de marketing.


5. Segurança e Governança

Tecnologia: AWS IAM (Identity and Access Management).


Descrição: O AWS IAM é utilizado para controlar o acesso aos dados e serviços. Com ele, garantimos que apenas usuários e serviços autorizados possam visualizar e manipular os recursos no S3 e no Glue, seguindo os princípios de segurança do projeto.

Inteligência de Negócio e KPIs
O dashboard final fornece insights estratégicos através dos seguintes KPIs e visualizações:

Indicadores-Chave de Desempenho (KPIs)

Soma de gmv_success: Valor total de vendas da empresa, oferecendo uma visão geral da receita.


Soma de total_tickets_quantity_success: Volume total de passagens vendidas, complementando a receita com a quantidade de transações.


Valor do Segmento "Inativo de Alto Valor": Destaca o potencial de receita que pode ser recuperado ao reengajar o segmento de clientes mais importante.

Análise e Classificação de Clientes

Gráfico de Pizza: É o coração da solução, mostrando a proporção entre clientes ativos e inativos e evidenciando o problema que o projeto resolve.


Gráfico de Linha (Vendas ao Longo do Tempo): Exibe as vendas por data, permitindo identificar picos e sazonalidades, como feriados e períodos de férias.


Gráfico de Barras (Vendas por Ano): Mostra a tendência de vendas anuais, ajudando a identificar crescimento ou queda na receita ao longo do tempo.

Campos para Análise

valor_total_gasto: Valor financeiro total que um cliente gastou, indicando sua importância para a empresa.


Ano, Trimestre, Mês, Dia: Campos que permitem à equipe de marketing analisar o comportamento de compra sazonal dos clientes.


potencial_cliente: Classificação do cliente com base no potencial de reengajamento (ex: "Bronze").


perfil_cliente: Classificação do cliente (ex: "Inativo de Baixo Valor").
