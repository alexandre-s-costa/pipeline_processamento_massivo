# Projeto de Pipeline de Dados com HDFS/Hive - Processos Jurídicos

![Linguagem](https://img.shields.io/badge/Linguagem-Python%20%7C%20HQL-blue)
![Tecnologia](https://img.shields.io/badge/Tecnologias-HDFS%20%7C%20Hive%20%7C%20Jupyter-yellow)
![Arquitetura](https://img.shields.io/badge/Arquitetura-Medallion%20(B%7CS%7CG)-brightgreen)
![Licença](https://img.shields.io/badge/Licen%C3%A7a-MIT-lightgrey)

## 📜 Visão Geral

Este projeto demonstra um pipeline completo de processamento de dados em batch, simulando o tratamento de um grande volume de dados processuais. O fluxo de trabalho engloba desde a ingestão de dados brutos até a criação de tabelas analíticas agregadas, prontas para consumo por ferramentas de Business Intelligence ou análise de dados.

A arquitetura utilizada é a **Medallion Architecture**, que organiza os dados em três camadas lógicas: **Bronze** (bruto), **Silver** (limpo e transformado) e **Gold** (agregado e pronto para negócio).

---

## 🏗️ Arquitetura do Pipeline

O fluxo de dados foi desenhado para garantir rastreabilidade, qualidade e performance, seguindo as etapas abaixo:

![Pipeline](pipeline.png)


1.  **Ingestão (Python/Jupyter)**: O notebook `Ingestao.ipynb` realiza o pré-processamento inicial, tratando inconsistências e gerando um arquivo CSV limpo.
2.  **Carregamento no HDFS**: O CSV é transferido para o HDFS, servindo como fonte para a primeira camada do Data Lake.
3.  **Camada Bronze**: Os dados são armazenados em seu formato bruto, como uma cópia fiel da origem, garantindo um ponto de recuperação.
4.  **Camada Silver**: Os dados são limpos, transformados, enriquecidos e particionados para otimizar consultas futuras.
5.  **Camada Gold**: Os dados da camada Silver são agregados para criar modelos de dados específicos para as necessidades de negócio, como KPIs e métricas de performance.

---

## 🛠️ Tecnologias Utilizadas

*   **Ingestão e Pré-processamento**: Python 3.12, Pandas, Jupyter Notebook
*   **Armazenamento Distribuído**: HDFS (Hadoop Distributed File System)
*   **Data Warehousing e ETL**: Apache Hive (HiveQL)
*   **Formato de Armazenamento**: Parquet (para camadas Silver e Gold)

---