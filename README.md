# Credit Risk Analysis with Power BI (Análise de Risco de Crédito)

## 📌 Descrição

Este projeto foi desenvolvido com o objetivo de analisar o perfil de clientes e entender melhor os padrões de inadimplência. A ideia principal é explorar os dados e gerar insights que possam ajudar na tomada de decisão dentro de um contexto de concessão de crédito.

---

## 🎯 Problema de Negócio

Quais características estão mais relacionadas à inadimplência dos clientes? E como essas informações podem ajudar na hora de conceder crédito?

---

## 🎯 Objetivos

* Identificar perfis com maior risco de inadimplência
* Analisar a relação entre renda, valor de crédito e risco
* Explorar possíveis padrões de comportamento dos clientes

---

## 🛠️ Tratamento de Dados

O tratamento foi feito no Power Query, com foco em deixar os dados mais organizados e utilizáveis para análise.

Alguns pontos importantes:

* Foram removidas colunas que não agregavam tanto valor para o objetivo da análise, ajudando a deixar o modelo mais leve e direto
* A coluna **own_car_age** apresentou valores inconsistentes, que não faziam muito sentido dentro do contexto, então optei por não considerar ela nas análises
* A variável **AMT_ANNUITY** (valor das parcelas) tinha alguns valores em branco. Como isso pode impactar a análise, preferi não alterar nem excluir esses dados

Para lidar com isso, criei uma flag chamada **annuity_missing**, com a lógica:
`if [AMT_ANNUITY] = null then "Yes" else "No"`

Assim, consigo identificar esses casos sem mexer na estrutura original da base.

---

## 📊 Modelagem dos Dados

Depois do tratamento, os dados foram carregados e organizados pensando em facilitar as análises.

Foram criadas algumas medidas em DAX para acompanhar os principais indicadores, como:

* Taxa de inadimplência
* Renda média
* Total de clientes inadimplentes
* Volume de propostas

A ideia foi permitir cruzamentos entre diferentes variáveis, como estado civil, renda e posse de imóvel.

---

## 📈 Dashboard

![Dashboard](Imagens/Dashboard.png)

---

## 📊 Análise e Visualizações

O dashboard foi construído com foco em clareza, tentando destacar os principais números logo de cara e deixar o restante das análises mais explorável.

**Observação:** A base utilizada é fictícia e possui uma concentração elevada de clientes de alta renda (incluindo muitos perfis com características de alto patrimônio). Por isso, alguns indicadores — como renda média e valores de crédito — aparecem acima do que seria esperado em um cenário real, o que pode influenciar a distribuição de risco observada.

### Principais KPIs:

* Total de clientes: 308 mil
* Renda média: $1.48 Mi
* Taxa de inadimplência: 8,07%
* Total de inadimplentes: 25 mil

---

## 💡 Principais Insights

* **Estado civil:**
  Clientes solteiros apresentaram uma taxa de inadimplência maior (~9,9%), enquanto viúvos tiveram uma taxa menor (~5,8%). Isso pode indicar diferenças de comportamento ou estabilidade financeira entre os grupos

* **Comportamento semanal:**
  A maior parte das propostas acontece durante a semana, com uma queda bem clara nos finais de semana

* **Posse de imóvel:**
  Não foi observada uma diferença relevante na inadimplência entre clientes com e sem imóvel

---

## 🧠 Conclusões

* A inadimplência varia bastante entre diferentes perfis de clientes
* Nem sempre variáveis patrimoniais são as mais relevantes
* Existem padrões de comportamento que podem ser explorados com mais profundidade

---

## 🚀 Possíveis Melhorias

* Incluir variáveis como score de crédito ou histórico financeiro
* Testar algum modelo preditivo de inadimplência
* Fazer uma segmentação de clientes (clusterização)
* Automatizar a atualização dos dados

---

## 🛠️ Ferramentas Utilizadas

* Power BI
* Power Query
* DAX

---

## 📌 Sobre o Projeto

Este projeto foi feito como prática de análise de dados, simulando um cenário de negócio voltado para risco de crédito e tomada de decisão.
