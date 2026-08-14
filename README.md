<img width="2170" height="379" alt="ChatGPT Image 14 de ago  de 2026, 00_14_19" src="https://github.com/user-attachments/assets/dc876b73-496e-4173-8b7c-004881082eaf" />

<div align="center">

# Relatório de Vendas no Power BI: Financial Sample

![Status Concluído](https://img.shields.io/badge/Status-Conclu%C3%ADdo-brightgreen)
![Bootcamp Santander + DIO](https://img.shields.io/badge/Bootcamp-Santander%20%2B%20DIO-cc0000)
![Tema Vendas](https://img.shields.io/badge/Tema-Vendas-5B2A86)
![Power BI](https://img.shields.io/badge/Power_BI-F2C94C?logo=powerbi&logoColor=black)
![Power Query](https://img.shields.io/badge/Power_Query-107C41?logo=microsoft-excel&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-00758F?logo=sqlite&logoColor=white)

<p align="center">
  Relatório interativo em Power BI que investiga a relação entre vendas e lucratividade, identificando os produtos, segmentos e países que mais contribuem para os resultados.
</p>

<p align="center">
  📁 <b>Arquivos:</b> <a href="./relatorio-de-vendas.pbix">Relatório (.pbix)</a> • <a href="./base-financial-sample.xlsx">Base de dados (.xlsx)</a>
</p>

</div>

## 📑 Índice

- [Contexto](#-contexto)
- [Estrutura do relatório](#-estrutura-do-relatório)
- [Principais insights](#-principais-insights)
- [Decisões de design e visualização de dados](#-decisões-de-design-e-visualização-de-dados)
- [Sobre os dados](#️-sobre-os-dados)
- [Regras de negócio e indicadores](#-regras-de-negócio-e-indicadores)
- [Preparação dos dados](#️-preparação-dos-dados)
- [Medidas DAX](#-medidas-dax)
- [Referência](#-referência)

---

## 🌐 Contexto

Este projeto foi desenvolvido como parte do Bootcamp Santander em parceria com a DIO, utilizando a base Financial Sample, disponibilizada pela Microsoft.

A proposta consistia em construir e publicar um relatório de vendas no Power BI que permitisse investigar a relação entre vendas e lucratividade sob diferentes perspectivas, como produtos, segmentos, países e períodos.

---

## 📊 Estrutura do relatório

### 📄 Página 1 — Visão geral de produtos

Receita, preços antes e após descontos e evolução mensal por segmento.

**Perguntas respondidas:**

- Quais produtos mais contribuem para a receita?
- Como os descontos afetam o preço médio por unidade de cada produto?
- Como a receita evolui ao longo do tempo e quais segmentos sustentam o resultado?

<img width="868" height="488" alt="{C91306FC-2241-45C3-8BA8-0CD0908BB5CB}" src="https://github.com/user-attachments/assets/2db65a47-a020-40d6-a5fa-25290231e913" />

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

| **Decisão** | **Justificativa** |
| --- | --- |
| **Substituição do mapa por gráficos de barras** | Como a base contempla apenas cinco países e o objetivo é comparar seus desempenhos, as barras possibilitam uma leitura mais precisa sem depender da dimensão territorial de cada país. |
| **Substituição do gráfico de pizza por barras em *Lucro por segmento*** | Gráficos de pizza não representam adequadamente valores negativos, como o prejuízo do segmento `ENTERPRISE`. As barras horizontais preservam a escala e evidenciam o sinal do resultado. |
| **Formatação condicional por sinal (DAX)** | Aplicação dinâmica de roxo (`#5B2A86`) para resultados positivos e vermelho (`#C0392B`) para resultados negativos, direcionando a atenção para o segmento com prejuízo. |
| **Barras agrupadas para os preços bruto e líquido por unidade** | O gráfico de área foi substituído porque os produtos representam categorias independentes. As barras agrupadas permitem comparar o valor médio por unidade antes e após os descontos, evidenciando o impacto das concessões comerciais. |
| **Dicas de ferramenta personalizadas** | Os gráficos Participação da receita por produto e Comparação de preços por unidade apresentam informações complementares ao posicionar o cursor sobre cada produto, mantendo a página principal limpa e objetiva. |
| **Organização do cabeçalho e navegação** | O título, o segmentador de período e os botões de navegação foram reunidos no cabeçalho, mantendo os controles consistentes entre as páginas e liberando espaço para os visuais. |

### Identidade visual

O fundo em lilás-claro (#F7F5FA) cria uma separação suave em relação aos cartões brancos (#FFFFFF), favorecendo a hierarquia visual. Cada produto, segmento e país conserva sua identificação cromática ao longo de todo o relatório, garantindo consistência visual entre as páginas e acelerando o reconhecimento das categorias.

#### Produtos

| Produto | Amostra | Hexadecimal |
| :--- | :---: | :--- |
| **Paseo** | ![](https://img.shields.io/badge/-%20-5B2A86) | `#5B2A86` |
| **VTT** | ![](https://img.shields.io/badge/-%20-7656B8) | `#7656B8` |
| **Velo** | ![](https://img.shields.io/badge/-%20-C44E9B) | `#C44E9B` |
| **Amarilla** | ![](https://img.shields.io/badge/-%20-2884C6) | `#2884C6` |
| **Montana** | ![](https://img.shields.io/badge/-%20-36A6A6) | `#36A6A6` |
| **Carretera** | ![](https://img.shields.io/badge/-%20-2446A8) | `#2446A8` |

#### Segmentos

| Segmento | Amostra | Hexadecimal |
| :--- | :---: | :--- |
| **Channel Partners** | ![](https://img.shields.io/badge/-%20-2884C6) | `#2884C6` |
| **Enterprise** | ![](https://img.shields.io/badge/-%20-2446A8) | `#2446A8` |
| **Government** | ![](https://img.shields.io/badge/-%20-EE7133) | `#EE7133` |
| **Midmarket** | ![](https://img.shields.io/badge/-%20-6B197D) | `#6B197D` |
| **Small Business** | ![](https://img.shields.io/badge/-%20-D941A6) | `#D941A6` |

#### Países

| País | Amostra | Hexadecimal |
| :--- | :---: | :--- |
| **Canadá** | ![](https://img.shields.io/badge/-%20-2884C6) | `#2884C6` |
| **França** | ![](https://img.shields.io/badge/-%20-2446A8) | `#2446A8` |
| **Alemanha** | ![](https://img.shields.io/badge/-%20-EE7133) | `#EE7133` |
| **México** | ![](https://img.shields.io/badge/-%20-36A66A) | `#36A66A` |
| **Estados Unidos** | ![](https://img.shields.io/badge/-%20-C44E9B) | `#C44E9B` |

---

## 🗂️ Sobre os dados

- **Fonte:** Microsoft Financial Sample;
- **Período:** setembro de 2013 a dezembro de 2014;
- **Volume:** 700 registros;
- **Estrutura:** tabela única denominada `financials`;
- **Granularidade:** cada linha representa o desempenho de um produto em determinado país, segmento, faixa de desconto e período;
- **Principais campos:** produto, segmento, país, data, unidades vendidas, preço de venda, receita, descontos, custo dos produtos vendidos e lucro;
- **Moeda:** os campos monetários foram formatados com o símbolo `$`, aplicado pelo Power BI. Como a documentação da amostra não especifica a moeda utilizada, o símbolo foi mantido sem atribuição a uma moeda ou país específico.

---

## 🧠 Regras de negócio e indicadores

Para orientar a leitura do relatório, foram consideradas as seguintes definições e relações presentes na base:

- **Receita bruta (`Gross Sales`):** valor das vendas antes da aplicação dos descontos;
- **Descontos (`Discounts`):** valor deduzido da receita bruta;
- **Receita após descontos (`Sales`):** receita bruta menos os descontos concedidos;
- **Custo dos produtos vendidos (`COGS`):** custo associado aos produtos comercializados;
- **Lucro (`Profit`):** receita após descontos menos o custo dos produtos vendidos;
- **Margem de lucro:** percentual da receita após descontos que permanece como lucro depois da dedução do custo dos produtos vendidos.

### Relações de cálculo

$$ \text{Receita Bruta} - \text{Descontos} = \text{Receita após Descontos} $$

$$ \text{Receita após Descontos} - \text{COGS} = \text{Lucro} $$

$$ \left( \frac{\text{Lucro}}{\text{Receita após Descontos}} \right) \times 100 = \text{Margem de Lucro \%} $$

> 💡 *Nota: a base Financial Sample utiliza o campo Sales para representar a receita após descontos, sem considerar outras deduções, como impostos ou devoluções.*

---

## ⚙️ Preparação dos dados

Os dados foram carregados e analisados no Power Query antes da criação dos visuais.

Foram realizadas as seguintes etapas:

- Verificação dos tipos de dados das colunas;
- Verificação da existência de valores nulos;
- Manutenção dos valores decimais da coluna `Units Sold`.

Os valores decimais de `Units Sold` foram preservados para manter a precisão da base original, pois não foi identificada uma regra de negócio que justificasse seu arredondamento.

Como a base já apresentava uma estrutura adequada ao escopo do projeto, não foram necessárias alterações estruturais nem remoções de registros.

Após o carregamento, as colunas `Sale Price`, `Sales` e `Profit` foram configuradas na exibição de tabela do Power BI com formato monetário e duas casas decimais.

---

## 📐 Medidas DAX

| Medida | Aplicação |
| :--- | :--- |
| **Margem de Lucro** | Cartão da página *Rentabilidade e eficiência* |
| **Preço Médio Bruto por Unidade** | Comparativo de preços e tooltip de preços e descontos |
| **Preço Médio Líquido por Unidade** | Comparativo de preços e tooltip de preços e descontos |
| **Taxa de Desconto** | Tooltip de preços e descontos |
| **Desconto Total** | Tooltip de preços e descontos |
| **Cor do Resultado** | Formatação condicional do gráfico *Lucro por segmento* |

---

### 1. Margem de lucro
Calcula a proporção da receita após descontos que permanece como lucro. A função `DIVIDE` previne erros de divisão por zero.

```dax
Margem de Lucro = 
DIVIDE(
    SUM(financials[Profit]),
    SUM(financials[Sales]),
    0
)
```

### 2. Preço médio bruto por unidade
Calcula quanto cada unidade vendida representou, em média, antes da aplicação dos descontos.

```dax
Preço Médio Bruto por Unidade =
DIVIDE(
    SUM(financials[Gross Sales]),
    SUM(financials[Units Sold]),
    0
)
```
### 3. Preço médio líquido por unidade
Calcula quanto cada unidade vendida gerou, em média, após a aplicação dos descontos.

```dax
Preço Médio Líquido por Unidade =
DIVIDE(
    SUM(financials[Sales]),
    SUM(financials[Units Sold]),
    0
)
```

A comparação entre os preços bruto e líquido por unidade permite observar o efeito dos descontos sobre o valor médio gerado. Diferentemente da média simples da coluna Sale Price (que atribui o mesmo peso a cada linha), essas medidas calculam a média ponderada pelo volume total de unidades vendidas.

### 4. Taxa de desconto
Calcula a participação dos descontos sobre a receita bruta. A medida permite comparar proporcionalmente o efeito das concessões comerciais, independentemente do volume de vendas.

```dax
Taxa de Desconto =
DIVIDE(
    SUM(financials[Discounts]),
    SUM(financials[Gross Sales]),
    0
)
```

### 5. Desconto total
Soma o valor dos descontos concedidos no contexto analisado.

```dax
Desconto Total =
SUM(financials[Discounts])
```

### 6. Cor do resultado
Retorna uma cor de acordo com o sinal do lucro no contexto de filtro: vermelho para resultados negativos e roxo para resultados positivos ou iguais a zero.

```dax
Cor do Resultado =
IF(
    SUM(financials[Profit]) < 0,
    "#C0392B",
    "#5B2A86"
)
```

## 🔗 Referência

- [Repositório power_bi_analyst — Juliana Zanelatto](https://github.com/julianazanelatto/power_bi_analyst)

*A partir da proposta original, foram realizadas melhorias na construção dos indicadores, na escolha dos visuais, nas dicas de ferramenta, na navegação e na identidade visual do relatório.*

[⬆️ Voltar ao início](#inicio)

---

> **Nota:** este README foi escrito originalmente em português. A tradução automática do navegador pode alterar termos técnicos ou elementos de formatação. Para uma melhor experiência, consulte a versão original da página.
