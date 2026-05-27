# 🍷 Tech Challenge Fase 2 — Classificação da Qualidade de Vinhos

## Descrição do Projeto

Projeto desenvolvido como parte do **Tech Challenge Fase 2** da Pós-Graduação em Data Analytics (FIAP/POS TECH). O objetivo é construir um modelo de Machine Learning capaz de prever a qualidade de vinhos tintos com base em suas características físico-químicas.

A variável de qualidade (nota de 0 a 10) foi transformada em classificação **binária**:
- **Alta Qualidade (1):** nota ≥ 7
- **Baixa/Média Qualidade (0):** nota < 7

## Dataset

- **Fonte:** [Wine Quality Dataset — Kaggle](https://www.kaggle.com/datasets/uciml/red-wine-quality-cortez-et-al-2009)
- **Amostras:** 1.599 vinhos tintos
- **Variáveis:** 11 características físico-químicas + 1 variável alvo (quality)

### Variáveis do Dataset

| Variável | Descrição |
|----------|-----------|
| `fixed acidity` | Acidez fixa |
| `volatile acidity` | Acidez volátil |
| `citric acid` | Ácido cítrico |
| `residual sugar` | Açúcar residual |
| `chlorides` | Cloretos |
| `free sulfur dioxide` | Dióxido de enxofre livre |
| `total sulfur dioxide` | Dióxido de enxofre total |
| `density` | Densidade |
| `pH` | pH |
| `sulphates` | Sulfatos |
| `alcohol` | Teor alcoólico |
| `quality` | Nota de qualidade (0–10) |

## Estrutura do Repositório

```
wine-quality-classification/
│
├── data/                   # Base de dados utilizada
│   └── winequality-red.csv
├── notebooks/              # Notebook com análise e modelagem
│   └── wine_quality_classification_v2.ipynb
├── src/                    # Scripts auxiliares
├── results/                # Gráficos e métricas dos modelos
│   ├── distribuicao_quality_original.png
│   ├── distribuicao_quality_binaria.png
│   ├── distribuicao_variaveis.png
│   ├── distribuicao_por_classe.png
│   ├── boxplots_outliers.png
│   ├── matriz_correlacao.png
│   ├── correlacao_com_quality.png
│   ├── comparacao_metricas.png
│   ├── matrizes_confusao.png
│   ├── curvas_roc.png
│   ├── feature_importance.png
│   ├── coeficientes_logistica.png
│   └── matriz_normalizada.png
├── requirements.txt        # Bibliotecas utilizadas
└── README.md               # Descrição do projeto
```

## Pipeline de Análise

### 1. Compreensão do Problema
- Interpretação do contexto da indústria vitivinícola
- Definição da variável alvo binária (quality ≥ 7)
- Verificação de dados faltantes (nenhum encontrado) e duplicatas

### 2. Análise Exploratória de Dados (EDA)
- Distribuição de todas as variáveis físico-químicas
- Análise de correlações com justificativas técnicas
- Detecção de outliers via boxplots e método IQR
- Análise de balanceamento: **86.4%** classe 0 vs **13.6%** classe 1 (desbalanceado)

### 3. Pré-processamento
- Remoção de registros duplicados
- Divisão treino/teste estratificada (80/20)
- Padronização com `StandardScaler`
- **Feature Engineering:** criação de 4 novas variáveis (acidez total, razão SO₂, álcool/acidez, álcool/densidade)
- **SMOTE** para balanceamento das classes no conjunto de treino

### 4. Desenvolvimento de Modelos
Três modelos foram treinados e comparados:

| Modelo | Descrição |
|--------|-----------|
| **Regressão Logística** | Modelo linear baseline |
| **Random Forest** | Ensemble de árvores de decisão |
| **Gradient Boosting** | Ensemble com boosting sequencial |

### 5. Avaliação dos Modelos
Métricas utilizadas:
- **Accuracy** — proporção de acertos gerais
- **Precision** — dos que o modelo disse ser alta qualidade, quantos realmente são
- **Recall** — dos vinhos de alta qualidade, quantos o modelo identificou
- **F1-Score** — média harmônica entre precision e recall
- **AUC-ROC** — capacidade de discriminação do modelo

**Melhor modelo: Regressão Logística** com AUC = 0.90, demonstrando excelente capacidade de discriminação.

### 6. Interpretação dos Resultados

**Variáveis mais influentes na qualidade do vinho:**
- 🍷 **Teor alcoólico (alcohol)** — principal indicador de alta qualidade
- ⚗️ **Acidez volátil (volatile acidity)** — impacto negativo na qualidade
- 🧪 **Sulfatos (sulphates)** — correlação positiva com qualidade
- 🍋 **Ácido cítrico (citric acid)** — contribui para frescor e qualidade

**Implicações para produção:**
- Monitorar e otimizar o teor alcoólico durante a fermentação
- Controlar rigorosamente a acidez volátil para evitar degradação
- Ajustar níveis de sulfatos para preservação e qualidade
- Manter ácido cítrico em níveis adequados para equilíbrio

## Tecnologias Utilizadas

- **Python 3.14**
- **Pandas / NumPy** — manipulação de dados
- **Matplotlib / Seaborn** — visualizações
- **Scikit-learn** — modelagem e avaliação
- **Imbalanced-learn (SMOTE)** — balanceamento de classes
- **Jupyter Notebook** — desenvolvimento interativo

## Como Executar

1. Clone o repositório:
```bash
git clone https://github.com/seu-usuario/wine-quality-classification.git
cd wine-quality-classification
```

2. Crie e ative o ambiente virtual:
```bash
python -m venv venv
# Windows
.\venv\Scripts\Activate
# Linux/Mac
source venv/bin/activate
```

3. Instale as dependências:
```bash
pip install -r requirements.txt
```

4. Execute o notebook:
```bash
jupyter notebook notebooks/wine_quality_classification_v2.ipynb
```

## Autores

- Marcelo Abbade

## Referências

- [Wine Quality Dataset — UCI/Kaggle](https://www.kaggle.com/datasets/uciml/red-wine-quality-cortez-et-al-2009)
- P. Cortez, A. Cerdeira, F. Almeida, T. Matos and J. Reis. *Modeling wine preferences by data mining from physicochemical properties.* Decision Support Systems, 2009.
