# 📊 Desafio de Modelagem e Transformação de Dados com DAX

## 📌 Descrição

Este projeto foi desenvolvido para o desafio de aplicar as técnicas de transformação de dados com Power BI.  
Modelagem e Transformação de Dados com DAX da DIO.

O objetivo consistiu em transformar a tabela única **Financial Sample** em um modelo dimensional baseado em **Star Schema**, organizando os dados em tabelas fato e dimensão para otimizar análises e futuras visualizações no Power BI.

---

## 🎯 Objetivos do Projeto

- Criar um modelo dimensional utilizando Star Schema.
- Separar os dados em tabelas fato e dimensão.
- Aplicar transformações utilizando Power Query.
- Utilizar funções DAX para construção de tabelas auxiliares.
- Melhorar a organização e performance do modelo de dados.

---

## 🏗️ Estrutura do Modelo

A partir da tabela original **Financials_origem**, foram criadas as seguintes tabelas:

### Tabela Fato

**F_Vendas**

Campos utilizados:

- SK_ID
- ID_Produto
- Produto
- Units Sold
- Sale Price
- Discount Band
- Segment
- Country
- Sales
- Profit
- Date

---

### Tabelas Dimensão

#### D_Produtos

Contendo informações consolidadas sobre os produtos:

- ID_Produto
- Produto
- Média de Unidades Vendidas
- Média de Valor de Vendas
- Mediana de Valor de Vendas
- Valor Máximo de Venda
- Valor Mínimo de Venda

---

#### D_Produtos_Detalhes

Contendo informações detalhadas dos produtos:

- ID_Produto
- Discount Band
- Sale Price
- Units Sold
- Manufacturing Price

---

#### D_Descontos

Contendo informações relacionadas aos descontos:

- ID_Produto
- Discount
- Discount Band

---

#### D_Detalhes

Criada para armazenar informações complementares não contempladas nas demais dimensões.

---

## 📅 Dimensão Calendário

Foi criada uma tabela de calendário utilizando a função DAX:

```DAX
D_Calendario =
CALENDAR(
    MIN(F_Vendas[Date]),
    MAX(F_Vendas[Date])
)
```

A partir da data gerada, foram criados atributos auxiliares para facilitar análises temporais:

- Ano
- Mês
- Nome do Mês
- Trimestre
- Dia
- Semestre

Essa dimensão foi relacionada à tabela fato através do campo **Date**, permitindo análises temporais das vendas.

---

## ⚙️ Funções Utilizadas

Durante o desenvolvimento do projeto foram utilizadas funções DAX e recursos do Power BI como:

### DAX

- CALENDAR()
- YEAR()
- MONTH()
- FORMAT()
- DAY()
- QUARTER()
- MEDIAN()
- MAX()
- MIN()
- AVERAGE()

### Transformações

- Agrupamento de dados
- Criação de colunas calculadas
- Reorganização de colunas
- Relacionamentos entre tabelas
- Modelagem dimensional

---

## ⭐ Modelo Star Schema

O modelo foi estruturado utilizando a abordagem Star Schema, onde:

- A tabela **F_Vendas** atua como tabela fato.
- As tabelas **D_Produtos**, **D_Produtos_Detalhes**, **D_Descontos**, **D_Detalhes** e **D_Calendario** atuam como dimensões.
- Os relacionamentos foram configurados para permitir análises eficientes e organizadas.

---

## 📚 Aprendizados

Este desafio permitiu consolidar conhecimentos sobre:

- Modelagem Dimensional
- Star Schema
- Power Query
- DAX
- Tabelas Fato e Dimensão
- Relacionamentos
- Dimensão Calendário
- Transformação de Dados no Power BI

---

## 👩‍💻 Autora

Projeto desenvolvido por **Nayara** durante a formação em Dados da DIO.
