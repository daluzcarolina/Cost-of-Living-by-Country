#  Custo de Vida por País — Análise Exploratória e Modelagem Preditiva

> **Onde no mundo o seu dinheiro rende mais?**  
> Uma análise exploratória e modelo preditivo do custo de vida em mais de 100 países, investigando padrões entre aluguel, alimentação, poder de compra — e o que esses índices revelam sobre a economia global.

---

## Contexto

Entender como o custo de vida varia ao redor do mundo é essencial para decisões sobre onde morar, trabalhar ou expandir negócios. Este projeto parte de dados do índice Numbeo 2024 para explorar correlações entre os principais componentes do custo de vida e, em seguida, treina um modelo de **Random Forest** para prever o índice de aluguel com base nas demais variáveis.

---

## Perguntas Investigadas

- Quais países têm o maior e menor custo de vida?
- Como aluguel, alimentação e restaurantes se correlacionam com o custo geral?
- O poder de compra local acompanha o custo de vida?
- Como o Brasil se posiciona no contexto global?
- É possível prever o índice de aluguel a partir dos outros índices com um modelo de ML?

---

##  Dataset

| Atributo | Detalhe |
|---|---|
| **Fonte** | [Kaggle — Cost of Living Index by Country 2024](https://www.kaggle.com/datasets/myrios/cost-of-living-index-by-country-by-number-2024) |
| **Origem dos dados** | Numbeo — maior base colaborativa de qualidade de vida do mundo |
| **Referência do índice** | Nova York (EUA) = 100 |

### Variáveis do dataset

| Coluna | Descrição |
|---|---|
| `Country` | Nome do país |
| `Cost of Living Index` | Índice geral de custo de vida |
| `Rent Index` | Custo de aluguel |
| `Groceries Index` | Custo de alimentação / mercado |
| `Restaurant Price Index` | Preços em restaurantes |
| `Local Purchasing Power Index` | Poder de compra local |

>  Índice acima de 100 = mais caro que Nova York. Abaixo de 100 = mais barato.

---

## Tecnologias Utilizadas

![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0-150458?logo=pandas&logoColor=white)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.4-F7931E?logo=scikit-learn&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.8-11557c)
![Seaborn](https://img.shields.io/badge/Seaborn-0.13-4c72b0)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)

---

## Estrutura da Análise

```
1. Carregamento e inspeção inicial (shape, dtypes, nulos)
2. Análise descritiva (describe, histogramas por variável)
3. Análise exploratória (scatter plots: custo de vida × aluguel, alimentação, poder de compra)
4. Análise de destaques (país com maior e menor custo de vida)
5. Recorte Brasil (posicionamento do país no índice global)
6. Modelagem preditiva (Random Forest para prever Rent Index)
7. Avaliação do modelo (MSE, R², validação cruzada com 5 folds)
```

---

##  Principais Resultados

###  Extremos globais
A análise identificou os países com maior e menor custo de vida no mundo em 2024. Os países mais caros concentram-se na **Europa Ocidental e Oceania**, enquanto os mais baratos estão no **Sul da Ásia e África**.

###  Correlações encontradas
Os scatter plots revelaram correlações positivas entre o custo de vida geral e os índices de aluguel, alimentação e restaurantes — confirmando que esses componentes se movem juntos. A relação com o **poder de compra local** é mais dispersa, indicando que países caros **nem sempre** oferecem poder de compra proporcional.

### 🇧🇷 Posição do Brasil
O Brasil apresenta um custo de vida abaixo da média global, mas com poder de compra local relativamente baixo em comparação a países com índices similares — evidenciando uma pressão econômica real sobre a população.

###  Modelo Preditivo — Random Forest
O modelo foi treinado para prever o **Rent Index** com base nos demais índices, usando pipeline com pré-processamento automático (StandardScaler + OneHotEncoder).

| Métrica | Descrição |
|---|---|
| **R² Score** | Mede o quanto o modelo explica a variância do aluguel |
| **MSE (Mean Squared Error)** | Erro médio quadrático nas previsões |
| **Cross-Validation (5 folds)** | Valida a consistência do modelo em diferentes subconjuntos dos dados |

> O scatter plot de "Valores Reais vs. Previsões" demonstra boa aderência do modelo, com pontos próximos à diagonal ideal.

---

##  Visualizações Produzidas

- **Histogramas** de todos os índices — distribuição por variável
- **Scatter plots** — custo de vida × aluguel, alimentação e poder de compra
- **Scatter com hue** — custo de vida × aluguel colorido por poder de compra local
- **Gráfico de previsões** — valores reais vs. predições do Random Forest

---

##  Como Executar

### Pré-requisitos
- Python 3.8+
- Jupyter Notebook

### Instalação

```bash
# Clone o repositório
git clone https://github.com/daluzcarolina/Cost-of-Living-by-Country.git
cd Cost-of-Living-by-Country

# Instale as dependências
pip install pandas numpy matplotlib seaborn scikit-learn jupyter

# Abra o notebook
jupyter notebook cost-of-living-by-country.ipynb
```

>  O dataset original está disponível no [Kaggle](https://www.kaggle.com/datasets/myrios/cost-of-living-index-by-country-by-number-2024). Faça o download e coloque o CSV na pasta antes de rodar.

---

## Estrutura do Projeto

```
Cost-of-Living-by-Country/
│
├── cost-of-living-by-country.ipynb   # Notebook com análise completa + modelo ML
└── README.md                          # Documentação do projeto
```

---

## Próximos Passos

- [ ] Adicionar mapa coroplético interativo com Plotly para visualização geográfica
- [ ] Incluir análise por região/continente com agrupamento manual
- [ ] Testar outros algoritmos (XGBoost, Regressão Ridge) e comparar métricas
- [ ] Criar dashboard complementar em Power BI

---

## Referências

- [Numbeo — Cost of Living](https://www.numbeo.com/cost-of-living/)
- [Kaggle — Cost of Living Index by Country 2024](https://www.kaggle.com/datasets/myrios/cost-of-living-index-by-country-by-number-2024)

---

## Autora

**Carolina Luz**  
Analista de Dados | Python · SQL · Power BI

[![LinkedIn](https://img.shields.io/badge/LinkedIn-carolinaluz-0077B5?logo=linkedin)](https://linkedin.com/in/carolinaluzsilva)
[![GitHub](https://img.shields.io/badge/GitHub-daluzcarolina-181717?logo=github)](https://github.com/daluzcarolina)
[![Email](https://img.shields.io/badge/Email-carolinaluz97@gmail.com-D14836?logo=gmail)](mailto:carolinaluz97@gmail.com)

---

>  *Este projeto faz parte do meu portfólio de análise de dados. Feedbacks são bem-vindos!*
