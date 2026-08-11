<div align="center">
  <a href="https://www.wyden.com.br/unidades/unifbv/">
    <img src="logo.PNG" alt="UniFBV Wyden" width="120px">
  </a>
  <p align="center"><img src="logo.png" width="500"></p>
  <h1>
    PIBIC - Mapeamento de Encostas com IA e SIG[cite: 3]
  </h1>
</div>

Repositório desenvolvido para o projeto de Iniciação Científica (PIBIC) sobre **Mapeamento de Encostas com Inteligência Artificial e SIG**, vinculado à [UniFBV](https://www.wyden.com.br/unidades/unifbv/)[cite: 3].

## 📌 Análise de Risco Geológico em Pernambuco[cite: 2]
**Equipe do Projeto:**
* **Pesquisador:** Leonardo H. S. Correia[cite: 2]
* **Orientadora:** Dra. Betânia Queiroz[cite: 2]
* **Coordenador do curso:** Adriano Pereira[cite: 2]
* **Data:** JUN/2026[cite: 2]

---

## 🚨 O Problema
* Eventos extremos estão cada vez mais frequentes e intensos devido às mudanças climáticas[cite: 2].
* O estado de Pernambuco possui elevada suscetibilidade a deslizamentos, principalmente na Região Metropolitana do Recife (RMR)[cite: 2].
* As fortes chuvas de maio de 2022 provocaram mais de 130 mortes e deixaram milhares de desabrigados, inundando 17% da área urbanizada do Recife[cite: 2].
* O mapeamento atual depende de análises manuais, que são lentas e sujeitas a erros[cite: 2].
* Os métodos tradicionais não conseguem acompanhar a dinâmica urbana e climática atual[cite: 2].

## 💡 A Solução e Objetivo
A solução proposta pela pesquisa é a **integração de Inteligência Artificial (IA) e Sistemas de Informação Geográfica (SIG)** para automatizar o mapeamento de áreas suscetíveis a deslizamentos[cite: 2].

O **objetivo** é identificar o modelo mais adequado para o mapeamento eficiente e automatizado em Pernambuco, realizando uma comparação rigorosa entre diferentes arquiteturas de Machine Learning e Deep Learning[cite: 2].

---

## 🧠 Modelos Avaliados[cite: 2]
O projeto compara as seguintes tecnologias[cite: 2]:
* **Machine Learning:** Random Forest (RF), Support Vector Machine (SVM) e XGBoost[cite: 2].
* **Deep Learning:** Redes Neurais Convolucionais (CNN), U-Net, Transfer Learning e LSTM[cite: 2].

**Critérios de Comparação:**
* **Desempenho:** Acurácia, F1-score, AUC, IoU e Índice Kappa[cite: 2].
* **Necessidade de Dados:** A quantidade mínima de dados necessária para um treinamento efetivo[cite: 2].
* **Tempo:** Tempo gasto no treinamento e no processamento para a geração dos mapas[cite: 2].
* **Aplicabilidade:** Facilidade de uso, potencial de integração com o SIG e viabilidade de aplicação em cenários reais[cite: 2].

---

## 💻 Ecossistema e Ferramentas[cite: 2]
* **Ecossistema SIG:** Processamento espacial avançado para análise de estabilidade construído sobre o ArcGIS e o QGIS (versão 3.40.12, manipulando algoritmos e arquivos KMZ/GPKG do projeto)[cite: 2].
* **Cloud Computing:** Uso do Google Earth Engine para processamento de Big Data em escala regional[cite: 2].
* **Modelagem em Python:** Utilização das bibliotecas Scikit-learn, TensorFlow e OpenCV para treinamento supervisionado[cite: 2].
* **Validação Rigorosa:** Auditoria de acurácia utilizando Matrizes de Confusão, Curva ROC e Índice Kappa[cite: 2].

**Fontes de Dados:**
* **Dados Topográficos e Climáticos:** APAC, CEMADEN e Topodata para análise de declividade, níveis de chuva e curvatura[cite: 2].
* **Sensoriamento Remoto:** Imagens de satélites Sentinel-1 (SAR) e Sentinel-2, combinadas com dados LiDAR e ortoimagens de alta resolução[cite: 2].

---

## ⚠ Metodologia (Percurso)[cite: 2]
O fluxo analítico do projeto está estruturado em 7 etapas principais[cite: 2]:
1. **Revisão Sistemática:** Levantamento de artigos e estudos científicos focados em IA, SIG e mapeamento de riscos de deslizamentos[cite: 2].
2. **Levantamento de Dados:** Coleta de imagens de satélite, modelos topográficos, dados geológicos, dados pluviométricos e inventário de deslizamentos ocorridos[cite: 2].
3. **Pré-Processamento:** Realização de correções radiométricas, recorte da área de estudo, normalização, geração de variáveis preditoras (declividade, curvatura, etc.) e preparo das amostras[cite: 2].
4. **Construção dos Modelos:** Definição arquitetural e implementação dos modelos de Machine Learning (RF, SVM, XGBoost) e Deep Learning (CNN, U-Net, etc.)[cite: 2].
5. **Treinamento:** Divisão do dataset (treino, validação e teste) seguida do treinamento dos modelos com ajuste de hiperparâmetros[cite: 2].
6. **Avaliação:** Avaliação do desempenho de cada modelo através de métricas (AUC, F1-score, IoU, Kappa) e análise comparativa[cite: 2].
7. **Mapas de Risco:** Geração final dos mapas de suscetibilidade e risco de deslizamentos em ambiente SIG para apoio e tomada de decisão[cite: 2].

---

## 🚀 Trabalhos Futuros[cite: 2]
A pesquisa abre caminhos para as seguintes expansões[cite: 2]:
* **Dados Climáticos e Monitoramento em Tempo Real:** Integrar variáveis de umidade do solo e previsões meteorológicas dinâmicas para a criação de alertas operacionais[cite: 2].
* **Expansão Geográfica e Resiliência Regional:** Replicar a metodologia em outros municípios pernambucanos, adaptando os modelos às realidades geomorfológicas locais[cite: 2].
* **Avanços em Deep Learning:** Avaliar com maior profundidade o uso de Visão Computacional Avançada (CNNs) e Transfer Learning aplicados a imagens de satélite de altíssima resolução[cite: 2].
* **Impacto Social e Políticas Públicas:** Garantir a aplicabilidade direta dos modelos gerados na gestão pública, visando promover justiça social e ações proativas de prevenção[cite: 2].

---

## 📚 Referências Principais[cite: 2]
* **Liu (2023):** Integração de Machine Learning com SIG para mapeamento de suscetibilidade a deslizamentos induzidos por chuva[cite: 2].
* **Ghorbanzadeh (2022):** Utilização de modelos de Deep Learning (CNN) e a base Landslide4Sense para detecção automática de cicatrizes de deslizamentos[cite: 2].
* **Francini (2022):** Aplicação da rede U-Net com imagens aéreas e dados SIG para identificar áreas edificadas em zonas de alto risco[cite: 2].
* **He (2024):** Revisão sistemática e abrangente sobre aplicações de IA nos eixos de detecção, mapeamento de suscetibilidade e previsão de deslocamentos[cite: 2].
* **Coutinho (2025):** Panorama detalhado da geotecnia e dos movimentos gravitacionais de massa no Brasil, abordando causas, consequências e soluções[cite: 2].
* **Marengo (2023):** Análise aprofundada do evento extremo de chuvas de maio de 2022 no Recife, cobrindo inundações e deslizamentos fatais[cite: 2].
* **Nocentini (2024):** Avaliação espaço-temporal de probabilidade de deslizamentos em escala regional através de machine learning[cite: 2].
* **USGS / Highland & Bobrowsky (2008):** Manual de deslizamentos - guia fundamental para a compreensão da
