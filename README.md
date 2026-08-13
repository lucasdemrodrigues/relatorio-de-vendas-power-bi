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
- [Demonstração Visual (Galeria)](#-demonstração-visual-galeria)
- [Principais Business Insights](#-principais-business-insights)
- [Decisões de Design \& UX (DataViz)](#-decisões-de-design--ux-dataviz)
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

## 📊 Demonstração visual

### 📄 Página 1 — Visão Geral de Produtos
> **Foco:** Receita, preços médios e evolução mensal por segmento.
<img width="872" height="489" alt="{0475591D-BD28-48FC-A5E2-A455767399E3}" src="https://github.com/user-attachments/assets/54815da6-53a7-420b-89cb-3ae63477fb9c" />

---

### 📄 Página 2 — Desempenho Geográfico
> **Foco:** Comparativo regional entre Receita vs. Lucro, unidades vendidas e tendência temporal.
<img width="871" height="488" alt="{668BB0D0-5D47-418A-9312-211EF5EFD988}" src="https://github.com/user-attachments/assets/cadd6163-deed-4b8f-b1ce-10b195971ca3" />

---

### 📄 Página 3 — Rentabilidade & Eficiência
> **Foco:** Margem de lucro, impacto de custos/descontos e identificação de prejuízos por segmento.
<img width="869" height="487" alt="{0DC6CD61-DC07-4FA6-A12F-1B1CB47F08A1}" src="https://github.com/user-attachments/assets/95495321-661b-4e90-83d3-b07d8097cb7a" />

---

## 💡 Principais Business Insights

Analisando o consolidado do período (2013–2014):

* 🏛️ **Dependência do Segmento Governamental:** O segmento **Government** representa mais de 67% de todo o lucro da empresa (gerando **$11,39M** dos $16,89M totais). Há uma dependência alta desse canal para a sustentabilidade do negócio.
* ⚠️ **Ineficiência no Segmento Enterprise:** Apesar de gerar receita, o segmento **Enterprise** opera com margem negativa (**-3,13%**), acumulando um prejuízo de **-$614,5K**. Recomenda-se revisar custos operacionais ou a política de descontos praticada para esse perfil de cliente.
* 🌍 **Consistência Geográfica vs. Eficiência:** A distribuição de vendas entre os 5 países (França, Alemanha, Canadá, EUA e México) é equilibrada, variando entre **$20M e $25M** por país. No entanto, os **EUA** lideram em receita (**$25,03M**), enquanto a **França** e a **Alemanha** entregam as melhores margens e o maior lucro líquido acumulado (**$3,78M** e **$3,68M**, respectivamente).
* 🏆 **Liderança e Concessões por Produto:** O produto **Paseo** lidera a receita comercial (**$33,01M**), mas também é o canal que mais concentra concessões comerciais, acumulando **$2,60M** em descontos.
* 💰 **Volume & Retenção Geral:** A receita líquida totaliza **$118,73M** para **$16,89M** de lucro, resultando em uma margem consolidada de **14,23%** sobre **1,13M** de unidades vendidas.

---

## 🎨 Decisões de Design & UX (DataViz)

O projeto priorizou boas práticas de visualização em relação ao template básico original:

| Decisão Tomada | Motivo / Benefício de UX |
|---|---|
| **Substituição de Mapas por Barras** | Como a base tem apenas 5 países e o objetivo é ranquear desempenho, gráficos de barras entregam comparação visual precisa sem depender da área geográfica. |
| **Substituição da Pizza por Barras (Lucro por Segmento)** | Gráficos de pizza falham ao representar partes negativas (ex: prejuízo de *Enterprise*). As barras horizontais preservam a escala e o sinal negativo do resultado. |
| **Formatação Condicional Dinâmica por Sinal (DAX)** | Aplicação de cor analítica: roxo (`#5B2A86`) para lucro e vermelho (`#C0392B`) dinâmico para prejuízo. Isso direciona o foco imediato do usuário para o segmento *Enterprise*. |
| **Gráfico de Barras para Preço Médio** | Substituiu o gráfico de área, evitando sugerir uma falsa continuidade temporal entre produtos que são categorias independentes. |
| **Tooltips Personalizadas (Page-by-Page)** | Páginas ocultas fornecem contexto sob demanda ao passar o mouse, mantendo a tela principal limpa e objetiva. |
| **Layout Mobile Dedicado** | Reorganização do fluxo visual em coluna única para navegação perfeita em telas de smartphones. |

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
