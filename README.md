<img width="4400" height="777" alt="banner-relatorio-vendas-power-bi-final" src="https://github.com/user-attachments/assets/e4f89878-f24f-4c13-b75f-23f935028649" />

<div align="center">

# Relatório de Vendas no Power BI: Financials Sample

![Status Concluído](https://img.shields.io/badge/Status-Conclu%C3%ADdo-brightgreen)
![Bootcamp Santander + DIO](https://img.shields.io/badge/Bootcamp-Santander%20%2B%20DIO-cc0000)
![Tema Vendas](https://img.shields.io/badge/Tema-Vendas-5B2A86)
![Power BI](https://img.shields.io/badge/Power_BI-F2C94C?logo=powerbi&logoColor=black)
![Power Query](https://img.shields.io/badge/Power_Query-107C41?logo=microsoft-excel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-00758F?logo=sqlite&logoColor=white)

<p align="center">
  Relatório interativo em Power BI que investiga a relação entre vendas e lucratividade, identificando os produtos, segmentos e países que mais contribuem para os resultados.
</p>

</div>

## 📑 Índice

- [Contexto](#-contexto)
- [Estrutura do relatório](#-estrutura-do-relatório)
- [Principais insights](#-principais-insights)
- [Decisões de design e visualização de dados](#-decisões-de-design-e-visualização-de-dados)
- [Modelagem \& Engenharia de Dados](#️-modelagem--engenharia-de-dados)
- [Paleta de Cores \& Identidade Visual](#-paleta-de-cores--identidade-visual)
- [Ferramentas Utilizadas](#️-ferramentas-utilizadas)
- [Estrutura do Repositório](#-estrutura-do-repositório)
- [Próximos Passos (Evoluções Futuras)](#-próximos-passos-evoluções-futuras)

---

## 🌐 Contexto

Este projeto foi desenvolvido como parte do Bootcamp Santander em parceria com a DIO, utilizando a base Financials Sample, disponibilizada pela Microsoft.

A proposta consistia em construir e publicar um relatório de vendas no Power BI que permitisse investigar a relação entre vendas e lucratividade sob diferentes perspectivas, como produtos, segmentos, países e períodos.

---

## 📊 Estrutura do relatório

### 📄 Página 1 — Visão geral de produtos

Receita, preços médios e evolução mensal por segmento.

**Perguntas respondidas:**

- Quais produtos mais contribuem para a receita?
- Como os produtos se posicionam em relação ao preço médio?
- Como a receita evolui ao longo do tempo e quais segmentos sustentam o resultado?

<img width="872" height="489" alt="{0475591D-BD28-48FC-A5E2-A455767399E3}" src="https://github.com/user-attachments/assets/54815da6-53a7-420b-89cb-3ae63477fb9c" />

---

### 📄 Página 2 — Desempenho geográfico

Receita, lucro e unidades vendidas por país.

**Perguntas respondidas:**

- Quais países geram mais receita?
- Quais países apresentam os maiores resultados de lucro?
- Como o lucro de cada país evolui ao longo do tempo?
  
<img width="871" height="488" alt="{668BB0D0-5D47-418A-9312-211EF5EFD988}" src="https://github.com/user-attachments/assets/cadd6163-deed-4b8f-b1ce-10b195971ca3" />

---

### 📄 Página 3 — Rentabilidade e eficiência

Lucro, custos e descontos por produto e segmento.

**Perguntas respondidas:**

- Quais segmentos mais contribuem para o lucro e quais apresentam prejuízo?
- Como o lucro de cada produto é composto pelos diferentes segmentos?
- Quais produtos concentram os maiores valores de desconto?
  
<img width="869" height="487" alt="{0DC6CD61-DC07-4FA6-A12F-1B1CB47F08A1}" src="https://github.com/user-attachments/assets/95495321-661b-4e90-83d3-b07d8097cb7a" />

---

## 💡 Principais insights

Analisando os resultados consolidados do período de 2013 a 2014:

* 🏛️ **Dependência do segmento governamental:** o segmento GOVERNMENT responde por aproximadamente 67% do lucro total, com $11,39 milhões dos $16,89 milhões registrados. O resultado indica uma concentração relevante da lucratividade nesse segmento.
* ⚠️ **Resultado negativo no segmento empresarial:** embora gere receita, o segmento ENTERPRISE apresenta margem negativa de 3,13% e prejuízo de aproximadamente $614,5 mil. Esse resultado sugere a necessidade de investigar sua estrutura de custos, política de descontos e condições comerciais.
* 🌍 **Equilíbrio de receita entre os países:** a receita apresenta distribuição relativamente equilibrada entre os cinco países, variando de aproximadamente $20 milhões a $25 milhões. Os Estados Unidos lideram em receita, com $25,03 milhões, enquanto França e Alemanha registram os maiores lucros, com $3,78 milhões e $3,68 milhões, respectivamente.
* 🏆 **Liderança e descontos do produto Paseo:** o produto PASEO lidera a geração de receita, com $33,01 milhões, mas também concentra o maior valor de descontos, totalizando $2,60 milhões. Essa combinação merece acompanhamento para avaliar o impacto das concessões comerciais sobre sua rentabilidade.
* 💰 **Resultado consolidado:** o período registra $118,73 milhões em receita, $16,89 milhões em lucro e margem de 14,23%, considerando aproximadamente 1,13 milhão de unidades vendidas.

---

## 🎨 Decisões de design e visualização de dados

O projeto priorizou boas práticas de visualização de dados em relação ao relatório de referência:

| Decisão tomada | Justificativa |
| --- | --- |
| **Substituição do mapa por gráficos de barras** | Como a base contempla apenas cinco países e o objetivo é comparar seus desempenhos, as barras possibilitam uma leitura mais precisa sem depender da dimensão territorial de cada país. |
| **Substituição do gráfico de pizza por barras no lucro por segmento** | Gráficos de pizza não representam adequadamente valores negativos, como o prejuízo do segmento `ENTERPRISE`. As barras horizontais preservam a escala e evidenciam o sinal do resultado. |
| **Formatação condicional por sinal** | Aplicação dinâmica de roxo (`#5B2A86`) para resultados positivos e vermelho (`#C0392B`) para resultados negativos, direcionando a atenção para segmentos com prejuízo. |
| **Gráfico de barras para o preço médio** | Substituição do gráfico de área para evitar a percepção de continuidade entre produtos, que representam categorias independentes. |
| **Dicas de ferramenta personalizadas** | Páginas específicas exibem informações complementares ao posicionar o cursor sobre os visuais, preservando a objetividade das páginas principais. |

---

## ⚙️ Modelagem & Engenharia de Dados

### 🗂️ Estrutura da Base
- **Fonte:** Microsoft Financials Sample (700 linhas, período 2013-2014).
- **Tabela Única:** `financials` (Visão flat, ideal para análise exploratória e descritiva).
- **Moeda:** Mantida em **USD ($)** para preservar a integridade da amostra original sem introduzir ruído cambial.

### 📐 Medidas DAX Principais

**1. Margem de Lucro Consolidada**
Calculada via DAX garantindo segurança contra divisões por zero e dinamicidade ao contexto de filtro:

```dax
Margem de Lucro = 
DIVIDE(
    SUM(financials[Profit]),
    SUM(financials[Sales]),
    0
)
