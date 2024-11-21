# Projeto de Engenharia de Dados no Airbnb - Rio de Janeiro

## Descrição do Projeto

Este projeto utiliza dados do Airbnb no Rio de Janeiro para construir um pipeline de dados completo usando **Databricks**. O pipeline realiza a ingestão, transformação e testes de qualidade dos dados, organizando-os nas camadas **Bronze**, **Silver** e **Gold** de um Data Lake. Cada camada adiciona qualidade e estrutura aos dados brutos para facilitar análises e relatórios.

### Objetivos

1. **Ingestão de Dados**: Carregar e descompactar os dados brutos para a camada Bronze.
2. **Limpeza e Transformação**: Realizar a limpeza de dados na camada Silver, incluindo remoção de valores inválidos e conversões de tipos.
3. **Testes de Qualidade**: Garantir a consistência e qualidade dos dados na camada Silver.
4. **Agregações e Transformações Avançadas**: Criar agregações especializadas e salvar os dados transformados na camada Gold no formato **Parquet**.

## Estrutura do Projeto

O projeto segue a arquitetura **Medallion** (Bronze, Silver, Gold) para a organização dos dados:

- **Bronze**: Contém os dados brutos, descompactados e carregados no Delta Lake.
- **Silver**: Contém dados limpos e padronizados, com tipos de dados corretos e validações de qualidade.
- **Gold**: Contém dados agregados e transformados, salvos no formato **Parquet**, prontos para análise.

## Dataset

O projeto utiliza três conjuntos de dados comprimidos `.csv.gz` do Airbnb:
- `reviews.csv.gz`: Avaliações dos usuários.
- `calendar.csv.gz`: Disponibilidade e preços das propriedades.
- `listings.csv.gz`: Listagem de propriedades.

## Tecnologias Utilizadas

- **Databricks** para orquestração do pipeline.
- **Delta Lake** para armazenamento intermediário.
- **Parquet** para armazenamento final na camada Gold.
- **PySpark** para manipulação e transformação dos dados.
- **Spark SQL** para consultas e agregações.

## Estrutura do Repositório

```plaintext
├── notebooks/
│   ├── ingestao_bronze.ipynb          # Código para ingestão inicial na camada Bronze
│   ├── limpeza_transformacao_silver.ipynb # Código de limpeza e transformação na camada Silver
│   └── agregacoes_gold.ipynb          # Agregações e transformações na camada Gold
├── data/
│   ├── bronze/
│   ├── silver/
│   └── gold/
└── README.md
