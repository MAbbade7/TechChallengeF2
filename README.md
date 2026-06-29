# 🍷 Tech Challenge Fase 2 — Classificação da Qualidade de Vinhos

## 👥 Equipe

| Nome | RM |
|------|-----|
| Marcelo Abbade | RM373613 |
| André Vieira | RM370784 |
| Lívia De Oliveira | RM370348 |
| Allan Diniz | RM373478 |
| Matheus Gueicha | RM371344 |

> **Pós-Graduação em Data Analytics — FIAP/POS TECH**

---

## Descrição do Projeto

Projeto desenvolvido como parte do **Tech Challenge Fase 2** da Pós-Graduação em Data Analytics (FIAP/POS TECH). O objetivo é construir um modelo de Machine Learning capaz de prever a qualidade de vinhos tintos com base em suas características físico-químicas.

A variável de qualidade (nota de 0 a 10) foi transformada em classificação **binária**:
- **Alta Qualidade (1)**: nota ≥ 7
- **Baixa/Média Qualidade (0)**: nota < 7

---

## Dataset

- **Fonte**: [Wine Quality Dataset — Kaggle](https://www.kaggle.com/datasets/uciml/red-wine-quality-cortez-et-al-2009)
- **Amostras brutas**: 1.599 vinhos tintos
- **Após remoção de duplicatas**: 1.359 amostras (240 duplicatas exatas removidas — 15,01%)
- **Variáveis**: 11 características físico-químicas + 1 variável alvo (`quality`)

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
| `quality` | Nota de qualidade (0–10) → variável alvo |

---

## Estrutura do Repositório

```
TechChallengeF2/
├── data/
│   └── winequality-red.csv          # Dataset original
├── notebooks/
│   └── wine_quality_classification_v2.ipynb  # Notebook principal
├── src/                              # Scripts auxiliares (se necessário)
├── results/                          # Gráficos e visualizações gerados
│   ├── distribuicao_quality.png
│   ├── distribuicao_binaria.png
│   ├── histogramas_features.png
│   ├── boxplots_outliers.png
│   ├── matriz_correlacao.png
│   ├── correlacao_quality.png
│   ├── duplicatas_analise.png
│   ├── matriz_normalizada.png
│   ├── feature_importance_consolidada.png
│   ├── matrizes_confusao.png
│   └── curvas_roc.png
├── docs/
│   ├── apresentacao_executiva.html   # Apresentação com storytelling da EDA
│   └── roteiro_video.md             # Roteiro do vídeo executivo
├── requirements.txt                  # Dependências do projeto
└── README.md                         # Este arquivo
```

---

## Pipeline do Projeto

### 1. Compreensão do Problema
- Análise inicial do dataset (shape, tipos, estatísticas descritivas)
- Verificação de valores nulos (nenhum encontrado)
- Criação da variável binária `quality_label` (≥ 7 = Alta, < 7 = Baixa/Média)

### 2. Tratamento de Duplicatas
- Identificadas **240 duplicatas exatas** (15,01% do dataset)
- Análise comparativa da distribuição de qualidade: duplicados vs. únicos
- **Decisão: remoção** — para evitar data leakage e viés no treinamento
- Dataset final: **1.359 registros**

### 3. Análise Exploratória (EDA)
- Histogramas de todas as variáveis
- Boxplots por classe para detecção de outliers (método IQR)
- Matriz de correlação com análise de multicolinearidade
- Análise de balanceamento de classes (~86% classe 0, ~14% classe 1)
- Justificativas estatísticas para cada observação

### 4. Pré-processamento
- Separação treino/teste (80/20) com estratificação
- Padronização com `StandardScaler` (fit apenas no treino)
- Feature engineering: 4 novas variáveis criadas
  - `total_acidity` = fixed acidity + volatile acidity
  - `sulfur_ratio` = free sulfur dioxide / total sulfur dioxide
  - `alcohol_density_ratio` = alcohol / density
  - `acidity_alcohol` = volatile acidity × alcohol
- Balanceamento com **SMOTE** (aplicado apenas no treino)

### 5. Modelagem
Três modelos treinados e comparados:

| Modelo | Descrição |
|--------|-----------|
| **Regressão Logística** | Modelo linear interpretável |
| **Random Forest** | Ensemble de árvores de decisão |
| **Gradient Boosting** | Boosting sequencial de árvores |

- Validação cruzada estratificada (5 folds) em cada modelo

### 6. Avaliação
- Métricas: Accuracy, Precision, Recall, F1-Score, AUC-ROC
- Matrizes de confusão (absolutas e normalizadas)
- Curvas ROC comparativas
- Comparação visual dos modelos

### 7. Interpretação
- Feature importance (Random Forest e Gradient Boosting)
- Coeficientes da Regressão Logística
- **Variáveis mais influentes**: `alcohol`, `volatile acidity`, `sulphates`
- Implicações práticas para a produção de vinhos

---

## Principais Resultados

- **Melhor modelo**: Regressão Logística (AUC ≈ 0.90)
- **Variáveis mais importantes**:
  - 🍷 **Álcool** — principal preditor de alta qualidade
  - ⚗️ **Acidez volátil** — impacto negativo na qualidade
  - 🧪 **Sulfatos** — associados a vinhos de melhor qualidade
- **Desbalanceamento tratado** com SMOTE, melhorando recall da classe minoritária

---

## Como Executar

### Pré-requisitos
- Python 3.10+
- pip

### Instalação

```bash
# Clone o repositório
git clone https://github.com/MAbbade7/TechChallengeF2.git
cd TechChallengeF2

# Crie e ative o ambiente virtual
python -m venv venv
# Windows:
.\venv\Scripts\Activate
# Linux/Mac:
source venv/bin/activate

# Instale as dependências
pip install -r requirements.txt

# Execute o notebook
jupyter notebook notebooks/wine_quality_classification_v2.ipynb
```

---

## Tecnologias Utilizadas

- **Python 3.14**
- **Pandas** — manipulação de dados
- **NumPy** — operações numéricas
- **Matplotlib / Seaborn** — visualizações
- **Scikit-learn** — modelagem e métricas
- **Imbalanced-learn** — SMOTE para balanceamento

---

## Referências

- Cortez, P., Cerdeira, A., Almeida, F., Matos, T., & Reis, J. (2009). *Modeling wine preferences by data mining from physicochemical properties.* Decision Support Systems, 47(4), 547-553.
- [Wine Quality Dataset — Kaggle](https://www.kaggle.com/datasets/uciml/red-wine-quality-cortez-et-al-2009)
- [Scikit-learn Documentation](https://scikit-learn.org/)
- [Imbalanced-learn Documentation](https://imbalanced-learn.org/)

---

## 👥 Autores

Desenvolvido por **Marcelo Abbade**, **André Vieira**, **Lívia De Oliveira**, **Allan Diniz** e **Matheus Gueicha** — Pós-Graduação em Data Analytics, FIAP/POS TECH.
