## 📝 Licença

Projeto acadêmico – PIBIC. Uso restrito a pesquisa.



# ⛰️ Pipeline de Previsão de Deslizamentos – RMR

Sistema completo de Machine Learning e Deep Learning para previsão de risco de deslizamento na Região Metropolitana do Recife (RMR), combinando variáveis de **relevo** com **gatilhos pluviométricos**.

---

## 📁 Estrutura do Projeto

```
projeto_deslizamento/
│
├── config.yaml                  ← ⭐ Controla TODO o comportamento do sistema
├── main.py                      ← Orquestrador central (train | infer | evaluate)
├── requirements.txt
├── Dockerfile
│
├── data/
│   ├── Mestre_2018_2022G.gpkg   ← Eventos geoespaciais (Deslizamento + Lona)
│   ├── pontos_seguros.gpkg      ← Eventos seguros (controle)
│   └── apac_data_linha.csv      ← Série histórica pluviométrica (APAC)
│
├── models/                      ← Artefatos gerados após treino
│   ├── features_config.pkl      ← Nomes e ordem das features
│   ├── scaler_deep.pkl          ← StandardScaler ajustado no treino
│   ├── modelo_randomforest.pkl
│   ├── modelo_xgboost.pkl
│   ├── modelo_lightgbm.pkl
│   ├── modelo_gradientboosting.pkl
│   ├── modelo_logisticregression.pkl
│   ├── modelo_mlp.keras
│   ├── modelo_residual.keras
│   └── modelo_widedeep.keras
│
├── reports/                     ← Saídas automáticas
│   ├── predictions.csv
│   ├── relatorio_final.html
│   ├── metrics.json
│   ├── pipeline.log
│   ├── lazypredict_ranking.csv
│   └── plots/
│       ├── confusion_matrix_ml_*.png
│       ├── confusion_matrix_dl_*.png
│       ├── feature_importance_rf.png
│       ├── deep_training_history_*.png
│       ├── model_comparison.png
│       ├── roc_curves.png
│       └── deep_training_history_*.png
│
├── src/
│   ├── __init__.py
│   ├── logger.py               ← Logging centralizado (console + arquivo rotativo)
│   ├── utils.py                ← load_config, save/load artefatos, ensure_dirs
│   ├── data_cleaning.py        ← Carrega e valida GPKG + APAC CSV, integra dados
│   ├── data_split.py           ← Train/test split estratificado + StandardScaler
│   ├── model_training.py       ← ML + Deep Learning + LazyPredict benchmark
│   ├── model_tuning.py         ← Funções objetivo Optuna (ML e DL)
│   ├── model_registry.py       ← features_config, MLflow, metrics.json
│   ├── model_loader.py         ← Carrega .pkl e .keras dinamicamente
│   ├── inference.py            ← Predição única e ensemble (average/weighted/vote)
│   └── evaluation.py           ← Métricas, plots, relatório HTML
│
└── app/
    └── app.py                  ← Interface Streamlit com mapa Folium interativo
```

---

## 🎯 Classes Previstas

| Código | Classe | Significado |
|--------|--------|-------------|
| **0** | 🔴 Emergência (Deslizamento) | Ocorrência confirmada de deslizamento |
| **1** | 🟠 Atenção (Lona) | Área coberta – risco identificado |
| **2** | 🟢 Ponto Seguro | Área estável, sem risco |

---

## ⚙️ Instalação

### Pré-requisitos
- Python 3.10+
- Git

### Instalação local

```bash
# 1. Clone o repositório
git clone https://github.com/seu-usuario/projeto-deslizamento.git
cd projeto-deslizamento

# 2. Crie ambiente virtual
python -m venv .venv
source .venv/bin/activate        # Linux/macOS
.venv\Scripts\activate           # Windows

# 3. Instale dependências
pip install -r requirements.txt

# 4. Coloque os arquivos de dados em data/
cp Mestre_2018_2022G.gpkg data/
cp pontos_seguros.gpkg    data/
cp apac_data_linha.csv    data/
```

### Com Docker

```bash
docker build -t deslizamento .
docker run -p 8501:8501 -v $(pwd)/data:/app/data deslizamento
```

---

## 🚀 Uso

### 1. Treinar todos os modelos

```bash
python main.py train
```

Executa em sequência:
- Carga e integração dos dados (GPKG + APAC)
- Split estratificado 80/20
- LazyPredict benchmark (ranking automático)
- 5 modelos ML com Optuna (RandomForest, XGBoost, LightGBM, GradientBoosting, LogisticRegression)
- 3 arquiteturas DL com Optuna (MLP, Residual, WideDeep)
- Geração de todos os gráficos e relatório HTML
- Registro no MLflow

### 2. Inferência sobre novos dados

```bash
python main.py infer
```

Carrega os modelos salvos em `models/` e prediz sobre novos dados.
Para apontar para seus dados, edite o bloco `carregar_novos_dados()` em `main.py`.

### 3. Reavaliar modelos existentes

```bash
python main.py evaluate
```

Reavalia os modelos já treinados sobre o conjunto de teste, regera gráficos e relatório.

### 4. Interface Web (Streamlit)

```bash
streamlit run app/app.py
```

Abre o dashboard interativo em `http://localhost:8501` com:
- Mapa Folium com marcadores coloridos por classe
- Upload de arquivos CSV ou GeoPackage
- Ensemble configurável (average / weighted / vote)
- Gráficos interativos Plotly
- Download das predições

### 5. Visualizar experimentos MLflow

```bash
mlflow ui --backend-store-uri mlruns
```

---

## ⭐ config.yaml

Todas as configurações do sistema estão centralizadas em `config.yaml`. Principais seções:

```yaml
treino:
  proporcao_teste: 0.20    # proporção do conjunto de teste
  folds_cv: 5              # folds da validação cruzada no Optuna

optuna:
  num_trials_ml: 30        # trials por modelo ML
  num_trials_dl: 10        # trials por arquitetura DL

deep_learning:
  epocas: 80
  batch_size: 32
  paciencia_es: 10         # early stopping patience

inferencia:
  modo_ensemble: "weighted"       # average | weighted | vote
  limiar_confianca: 0.60          # abaixo → flag baixa confiança

mlflow:
  registrar_modelos: true
```

---

## 📊 Modelos Treinados

### Machine Learning (5 modelos)

| Modelo | Otimização |
|--------|-----------|
| RandomForest | Optuna TPE (30 trials) |
| XGBoost | Optuna TPE (30 trials) |
| LightGBM | Optuna TPE (30 trials) |
| GradientBoosting | Optuna TPE (30 trials) |
| LogisticRegression | Optuna TPE (30 trials) |

### Deep Learning (3 arquiteturas)

| Arquitetura | Descrição |
|-------------|-----------|
| MLP | Dense + BatchNorm + Dropout, L2, otimizado |
| Residual | Skip connections, 2 blocos profundos |
| WideDeep | Caminho largo (features brutas) + caminho profundo fundidos |

---

## 📈 Métricas de Avaliação

Todas calculadas no conjunto de teste (20% estratificado):

- Acurácia e Acurácia Balanceada
- Precisão, Recall e F1 (Macro e Weighted)
- F1 por classe (Deslizamento / Lona / Seguro)
- Matthews Correlation Coefficient (MCC)
- Cohen's Kappa
- ROC-AUC Multiclasse (OvR)

---

## 🗂️ Dados

### Fontes

| Arquivo | Origem | Conteúdo |
|---------|--------|----------|
| `Mestre_2018_2022G.gpkg` | PIBIC/UFPE | 273 pontos de ocorrência (2018–2022) |
| `pontos_seguros.gpkg` | PIBIC/UFPE | 300 pontos de controle (áreas estáveis) |
| `apac_data_linha.csv` | APAC-PE | ~107k registros diários por posto |

### Features de Relevo (do Mestre)

`relevo_sombreado`, `orientacao`, `divisores`, `longitude`, `latitude`,
`TWI`, `SPI`, `TRI`, `energia_gravitacional`

### Features Pluviométricas (agregadas do APAC)

Derivadas de: `Chuva_mm`, `chuva_3d_sum`, `chuva_7d_sum`, `chuva_30d_sum`,
`vulnerabilidade_5d`, `consec_chuva`, `consec_seco`, `intensidade_num`, `estacao_num`

Agregadas como `_mean`, `_max`, `_std` por posto e aplicadas como mediana regional.

---

## 🔒 Decisões de Design

| Decisão | Motivo |
|---------|--------|
| Sem SMOTE | Dataset pequeno; SMOTE introduziria amostras artificiais de relevo |
| Sem imputação | Dados originais sem NaN; NaN surgem apenas de junções → tratados pontualmente |
| Scaler só no treino | Evita data leak para o conjunto de teste |
| Interseção de colunas GPKG | `pontos_seguros` tem mais colunas que `Mestre`; usar interseção evita NaN estrutural |
| Medianas regionais APAC | Sem coordenadas vinculadas aos pontos; mediana representa gatilho regional |

---

Co-outhored-by: Bethania Queiros <berhania.queiroz@proferssores.unifbv.edu.br>

## 📝 Licença

Projeto acadêmico – PIBIC. Uso restrito a pesquisa.
