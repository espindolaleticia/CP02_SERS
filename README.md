# Avaliação — APIs, Energias Renováveis e Aprendizado de Máquina

## 👥 Integrantes

* Felipe Mitsuo Takahashi Stephano — RM570692
* Laura Godoy Callegari — RM569181
* Letícia Araújo Espindola — RM569308
* Mariana Dreset Carbollan — RM569207
* Milena de Aguiar Lopes Cardoso — RM570599

---

## Sobre o projeto

Este projeto foi desenvolvido para a avaliação de **APIs, Energias Renováveis e Aprendizado de Máquina**.

O objetivo é utilizar dados reais de fontes públicas para desenvolver modelos de **classificação** e **regressão**, aplicados ao contexto de energias renováveis.

Foram utilizadas duas fontes principais de dados:

* **ANEEL SIGA** — dados de empreendimentos de geração de energia.
* **Open-Meteo** — dados meteorológicos históricos.

---

## Tarefa 1 — Classificação de fontes de energia

Nesta etapa, o objetivo é prever a fonte de geração de uma usina utilizando:

* Potência instalada (`potencia_kw`)
* Latitude
* Longitude

### Classes utilizadas

* ☀️ Solar — UFV
* 💨 Eólica — EOL
* 💧 Hidráulica — UHE, PCH e CGH

### Modelos utilizados

* Regressão Logística
* KNN
* Random Forest

Os dados foram separados em **80% para treinamento e 20% para teste**, utilizando divisão estratificada e `random_state=42`.

### Métricas

Foram utilizadas:

* Accuracy
* Precision
* Recall
* F1-Score Macro
* Matriz de confusão

### Resultado

O **Random Forest** apresentou o melhor desempenho geral, alcançando aproximadamente **97,6% de Accuracy** e **0,975 de F1-Score Macro**.

O resultado mostra que potência e localização conseguem ajudar bastante na identificação da fonte de energia, embora não sejam suficientes para garantir uma classificação perfeita em todos os casos.

---

## Tarefa 2 — Regressão da radiação solar

Nesta etapa, foram utilizados dados meteorológicos históricos da cidade de **Petrolina — PE**.

### Período

**01/04/2025 a 30/06/2025**

### Variáveis utilizadas

* Temperatura (`temperatura_c`)
* Umidade (`umidade_pct`)
* Cobertura de nuvens (`nuvens_pct`)
* Velocidade do vento (`vento_kmh`)
* Hora (`hora`)

### Variável alvo

* Radiação solar (`radiacao_w_m2`)

Os dados foram organizados cronologicamente, utilizando os primeiros **80% para treinamento** e os últimos **20% para teste**.

### Modelos utilizados

* Regressão Linear
* KNN Regressor
* Random Forest Regressor

### Métricas

* MAE
* MSE
* R²

### Resultado

O **Random Forest Regressor** apresentou aproximadamente:

* **MAE:** 67,2 W/m²
* **R²:** 0,842

O modelo conseguiu representar bem a variação da radiação solar. A variável **hora** também apresentou grande importância para as previsões.

> A radiação solar utilizada no projeto representa uma variável meteorológica. Ela não corresponde diretamente à quantidade de energia elétrica gerada por uma usina.

---

## Orange Data Mining

Como atividade complementar, os mesmos datasets foram utilizados no **Orange Data Mining**.

Foram realizados testes com:

### Classificação

* Logistic Regression
* KNN
* Random Forest

### Regressão

* Linear Regression
* KNN Regression
* Random Forest Regression

Os arquivos utilizados no Orange estão disponíveis na pasta `orange datasets`.

---

## 📁 Arquivos do projeto

```text
 CP02_SERS
├── 📓 checkpoint_02_energia_renovavel.ipynb
├── 📁 orange datasets
│   ├──  aneel_classificacao_orange.csv
│   └──  meteo_regressao_orange.csv
└── 📄 README.md
```

---

## ▶️ Como executar

1. Clone ou baixe este repositório.
2. Abra o arquivo `checkpoint_02_energia_renovavel.ipynb`.
3. Execute as células do notebook em ordem.
4. Para a atividade no Orange, utilize os arquivos disponíveis na pasta `orange datasets`.

### Principais bibliotecas utilizadas

* Python
* NumPy
* Scikit-learn
* Matplotlib
* Requests

---

## 🔗 Fontes dos dados

* **ANEEL SIGA:** dados públicos sobre empreendimentos de geração de energia elétrica.
* **Open-Meteo:** dados meteorológicos históricos utilizados para a análise de radiação solar.

---

## ✅ Conclusão

O projeto demonstrou a aplicação de técnicas de **Machine Learning** em dados relacionados a energias renováveis.

Na classificação, o Random Forest apresentou o melhor desempenho entre os modelos testados. Na regressão, o Random Forest também apresentou bons resultados para estimar a radiação solar a partir das condições meteorológicas.

A atividade também permitiu comparar os resultados obtidos utilizando **Python/Scikit-learn** e **Orange Data Mining**, reforçando a aplicação prática dos modelos de aprendizado de máquina.
