<div align="center">
  <a href="https://www.wyden.com.br/unidades/unifbv/">
    <img src="https://logodownload.org/wp-content/uploads/2017/09/Unifbv-logo-1.png" alt="Logo UniFBV Wyden" width="120px">
  </a>
  <h1>
    PIBIC - Mapeamento de Encostas com IA e SIG
  </h1>
</div>

Repositório desenvolvido para o projeto de Iniciação Científica (PIBIC) sobre **Mapeamento de Encostas com Inteligência Artificial e SIG**, vinculado à [UniFBV](https://www.wyden.com.br/unidades/unifbv/).

## Projeto de Análise de Risco Geológico em Pernambuco

## 🚀 Objetivo
Desenvolver e comparar modelos de Inteligência Artificial (Aprendizado de Máquina e Aprendizado Profundo) integrados a Sistemas de Informação Geográfica (SIG) para gerar mapas de suscetibilidade a deslizamentos, visando aprimorar a análise de risco geológico em Pernambuco.

## 📖 Acesso rápido
* [💻 Tecnologias](#-Tecnologias)
* [🔧 Ferramentas](#-Ferramentas)
* [⚠ Percurso](#-Percurso)
* [❓ Uso](#-Uso)
* [📋 Documentações](#-Documentações)
* [⚙️ Instalação](#-Instalação)

## 💻 Tecnologias

### Random Forest
É um algoritmo de aprendizado de máquina versátil usado para tarefas de classificação e regressão. No projeto, é utilizado como modelo base para criar mapas de suscetibilidade a partir de um conjunto de fatores predisponentes (declividade, chuva, tipo de solo, etc.).

- **Principais Características**: Alto desempenho, robustez a outliers, capacidade de medir a importância das variáveis.
- **Casos de Uso**: Classificação de pixels do terreno, modelagem de suscetibilidade.
- **Links**:
  - [Artigo de Referência (Nocentini et al., 2024)](https://www.researchgate.net/publication/381321143_Regional-scale_spatiotemporal_landslide_probability_assessment_through_machine_learning_and_potential_applications_for_operational_warning_systems_a_case_study_in_Kvam_Norway)
  - [Documentação Scikit-learn](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html)

### U-Net
U-Net é uma arquitetura de rede neural convolucional (CNN) projetada para segmentação de imagens biomédicas, mas altamente eficaz para segmentação semântica em imagens de sensoriamento remoto. É usada para identificar e delimitar feições como edificações em áreas de risco.

- **Principais Características**: Arquitetura Encoder-Decoder, precisão na segmentação, eficaz com menos dados de treinamento.
- **Casos de Uso**: Extração de edificações em imagens aéreas, identificação de cicatrizes de deslizamentos.
- **Links**:
    - [Artigo de Referência (Francini et al., 2022)](https://www.mdpi.com/2072-4292/14/17/4279)
    - [Artigo Oficial](https://arxiv.org/abs/1505.04597)
      
### Surrogate Models (Modelos Substitutos)
Conceito de usar modelos de machine learning para aproximar e acelerar simulações numéricas complexas. No contexto do projeto, justifica o uso de IA para obter análises de estabilidade de forma muito mais rápida que os métodos tradicionais.

- **Principais Características**: Eficiência computacional, predição em tempo real.
- **Casos de Uso**: Análise rápida de Fator de Segurança (FOS), sistemas de alerta precoce.
- **Links**:
    - [Artigo de Referência (Li et al., 2023)](https://www.mdpi.com/2077-0472/15/14/10793)

## 🔧 Ferramentas

[![QGIS](https://img.shields.io/badge/QGIS-589632?style=for-the-badge&logo=qgis&logoColor=white)](https://www.qgis.org/)
[![ArcGIS](https://img.shields.io/badge/ArcGIS-007AC2?style=for-the-badge)](https://www.esri.com/en-us/arcgis/products/arcgis-pro/overview)
[![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-learn](https://img.shields.io/badge/scikit--learn-F7931A?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![GDAL](https://img.shields.io/badge/GDAL-D36D00?style=for-the-badge)](https://gdal.org/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://docs.github.com/)
[![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)](https://git-scm.com/doc)

### QGIS / ArcGIS
Softwares de Sistema de Informação Geográfica (SIG) essenciais para a manipulação, análise e visualização de dados geoespaciais. Usados para pré-processar os mapas de entrada e visualizar os mapas de suscetibilidade finais.

- **Principais Características**: Processamento de dados vetoriais e raster, análise espacial, elaboração de mapas.
- **Casos de Uso**: Preparação dos dados de declividade, geologia e uso do solo; visualização dos resultados.
- **Links**:
    - [Site Oficial do QGIS](https://www.qgis.org/)
    - [Site Oficial do ArcGIS](https://www.esri.com/arcgis)

### Scikit-learn
Uma das principais bibliotecas de machine learning para Python. Fornece a implementação de algoritmos como o Random Forest, além de ferramentas para pré-processamento e avaliação de modelos.

- **Principais Características**: Ampla gama de algoritmos, documentação robusta, integração com o ecossistema Python.
- **Casos de Uso**: Treinamento e teste do modelo de Random Forest.
- **Links**:
    - [Scikit-learn Site](https://scikit-learn.org/)

### TensorFlow / PyTorch
Frameworks de deep learning utilizados para construir e treinar modelos de redes neurais complexas, como a U-Net.

- **Principais Características**: Flexibilidade, suporte a GPU para aceleração, vastas comunidades.
- **Casos de Uso**: Implementação e treinamento do modelo U-Net para segmentação de imagens.
- **Links**:
    - [TensorFlow Site](https://www.tensorflow.org/)
    - [PyTorch Site](https://pytorch.org/)

## ⚠ Percurso

<table>
  <thead>
    <tr align="left">
      <th>Nº</th>
      <th>Etapas</th>
      <th>Materiais de Apoio</th>
    </tr>
  </thead>
  <tbody align="left">
    <tr>
      <td>01</td>
      <td>Levantamento bibliográfico e definição dos métodos</td>
      <td align="center">
        <a href="URL_PARA_SEU_DRIVE_OU_PASTA">
            <img align="center" alt="Material de Apoio" src="https://img.shields.io/badge/Ver%20Material-30A3DC?style=for-the-badge">
        </a>
      </td>
    </tr>
    <tr>
      <td>02</td>
      <td>Coleta e pré-processamento de dados geoespaciais</td>
      <td align="center">
        <a href="URL_PARA_SEU_DRIVE_OU_PASTA">
            <img align="center" alt="Material de Apoio" src="https://img.shields.io/badge/Ver%20Material-E94D5F?style=for-the-badge">
        </a>
      </td>
    </tr>
    <tr>
      <td>03</td>
      <td>Treinamento e teste dos modelos de machine learning</td>
      <td align="center">
        <a href="URL_PARA_SEU_DRIVE_OU_PASTA">
            <img align="center" alt="Material de Apoio" src="https://img.shields.io/badge/Ver%20Material-30A3DC?style=for-the-badge">
        </a>
      </td>
    </tr>
    <tr>
        <td>04</td>
      <td>Integração com GIS e análise espacial dos resultados</td>
      <td align="center">
        <a href="URL_PARA_SEU_DRIVE_OU_PASTA">
            <img align="center" alt="Material de Apoio" src="https://img.shields.io/badge/Ver%20Material-E94D5F?style=for-the-badge">
        </a>
      </td>
    </tr>
    <tr>
        <td>05</td>
      <td>Redação e apresentação dos resultados (relatório/artigo)</td>
      <td align="center">
        <a href="URL_PARA_SEU_DRIVE_OU_PASTA">
            <img align="center" alt="Material de Apoio" src="https://img.shields.io/badge/Ver%20Material-30A3DC?style=for-the-badge">
        </a>
      </td>
    </tr>
  </tbody>
  <tfoot></tfoot>
</table>

---

## ❓ Uso

1.  **Processamento de Dados:** Scripts em `scripts/data_processing` para preparar os dados geoespaciais.
2.  **Treinamento dos Modelos:** Notebooks em `notebooks/` para treinar os modelos Random Forest e U-Net.
3.  **Resultados:** Mapas e análises gerados podem ser encontrados na pasta `results/`.

## 📋 Documentações
- Os principais artigos que fundamentam este projeto podem ser encontrados na pasta `papers/`.

## 🖇️ Contribua
[![Star](https://img.shields.io/github/stars/SEU_USUARIO/SEU_REPOSITORIO?style=social)](https://github.com/SEU_USUARIO/SEU_REPOSITORIO/stargazers)
[![Forks](https://img.shields.io/github/forks/SEU_USUARIO/SEU_REPOSITORIO?style=social)](https://github.com/SEU_USUARIO/SEU_REPOSITORIO/forks)
[![GitHub Issues](https://img.shields.io/github/issues/SEU_USUARIO/SEU_REPOSITORIO?style=social)](https://github.com/SEU_USUARIO/SEU_REPOSITORIO/issues/)

## ✒️ Membros contribuintes:

<a>
<div align="center">Desenvolvido no âmbito do Programa de Iniciação Científica (PIBIC).</div>
</a>

## 📌 Versão

v1.0

## 📄 Licença

Este projeto está sob a licença [MIT](https.choosealicense.com/licenses/mit/).
