# 📈 Análise de Vendas e Marketing - E-commerce KurtTech

![Status](https://img.shields.io/badge/Status-Concluído-green)
![Python](https://img.shields.io/badge/Python-3.11-blue)
![SQL Server](https://img.shields.io/badge/SQL%20Server-2019-red)
![Power BI](https://img.shields.io/badge/Power%20BI-Desktop-yellow)

## 🔖 Sobre o Projeto

Este projeto consiste em uma solução completa de **Business Intelligence** para a empresa fictícia *KurtTech*. O objetivo foi simular um ambiente corporativo real, onde os dados chegam em arquivos brutos (CSV), precisam ser carregados em um Banco de Dados Relacional (Data Warehouse) e, posteriormente, analisados para tomada de decisão estratégica.

O diferencial técnico deste projeto é a construção do **Pipeline de ETL** utilizando Python para orquestrar a carga de dados no SQL Server e o uso de **SQL Avançado** para criação de tabelas dimensionais.

---

## 🏗️ Arquitetura e Tecnologias

O fluxo de dados segue as etapas de **Extração, Carregamento e Transformação (ELT)**:

1.  **Python (Engenharia de Dados):**
    * Uso da biblioteca `Pandas` para leitura e tratamento inicial dos arquivos CSV.
    * Utilização do `SQLAlchemy` e `pyodbc` para criar a conexão (Engine) com o SQL Server.
    * Automação da inserção de dados (`to_sql`) garantindo a integridade dos tipos de dados.

2.  **SQL Server (Data Warehousing):**
    * **Modelagem Dimensional:** Criação de um *Star Schema* (Esquema Estrela) com tabela Fato (`FactVendas`) e Dimensões (`DimCliente`, `DimProduto`, etc.).
    * **CTEs Recursivas:** Script avançado para gerar a `DimData` automaticamente, criando uma série temporal de 2020 a 2025 sem necessidade de input manual.
    * Definição de *Primary Keys* e *Foreign Keys* para garantir a integridade referencial.

3.  **Power BI (Analytics):**
    * Modelagem de relacionamentos.
    * Cálculos DAX para medidas de inteligência de tempo.
    * Design de interface focado em UX (Modo Escuro).

---

## 📊 Visualizações e Insights

### 1. Visão Geral de Vendas
Monitoramento dos principais KPIs financeiros ao longo do tempo.
<img width="1536" height="862" alt="Dashboard 1 Faturamento" src="https://github.com/user-attachments/assets/bec92a2e-a2c7-414a-a19f-9003036ce5a6" />
* **Insight:** O faturamento apresenta sazonalidade clara, com picos nos meses de Março e Maio.
* **Meios de Pagamento:** O Cartão de Crédito representa a maior fatia da receita (42,3%).

### 2. Análise de Lucratividade
Foco na saúde financeira da operação.
<img width="1533" height="860" alt="Dashboard 2 Lucro" src="https://github.com/user-attachments/assets/49eeb663-4e0d-4cc6-bc6e-d5c14ef43b2f" />
* **Margem de Lucro:** A operação mantém uma margem saudável de aproximadamente **49,78%**.
* **Ticket Médio:** R$ 336,28.

### 3. Performance de Produtos e Fornecedores
<img width="1534" height="859" alt="Dashboard 3 Produto" src="https://github.com/user-attachments/assets/c3bd3078-c3df-4dfd-a91c-76b529ef7903" />
* Uso de **Árvore Hierárquica** para identificar quais fornecedores trazem os produtos mais vendidos.
* O *Notebook Ultra Slim 14"* é o campeão de faturamento (R$ 536 Mil), enquanto o *Sistema Operacional Pro* lidera em volume de vendas.

### 4. Ranking de Vendedores
<img width="1533" height="860" alt="Dashboard 4 Vendedores" src="https://github.com/user-attachments/assets/75ee5665-41ea-407e-8e14-87c3b85d568d" />
* Análise individual de performance para bonificação e metas.

---

## 🗂️ Estrutura do Repositório

* `ImportTabelasCSV.ipynb`: Script Python responsável pelo ETL (Carga dos CSVs para o SQL Server).
* `CREATE TABLES.sql`: Script DDL para criação da estrutura do banco de dados.
* `DimData.sql`: Script SQL com CTE Recursiva para geração da dimensão de tempo.
* `Tabelas csv/`: Arquivos fontes utilizados no projeto.
* `Dashboards/`: Imagens das visualizações finais.

---

## 🚀 Como Executar

1.  Tenha o **SQL Server** instalado localmente.
2.  Execute o script `CREATE TABLES.sql` para criar o banco `AnaliseVendasEcommerce`.
3.  Configure a string de conexão no arquivo `ImportTabelasCSV.ipynb` para apontar para o seu servidor local.
4.  Execute o Jupyter Notebook para popular o banco.
5.  Conecte o Power BI ao banco de dados SQL Server local.

---

**Desenvolvido por [Jessica Freitas](https://www.linkedin.com/in/jessica-freitas-49b68632s13)**
