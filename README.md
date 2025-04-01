# SignalAndSistemProject
Genre reconigtion of musics, using concepts from signals and systems lessons

## 📂 Estrutura do Projeto

- **Augmentation Audios**: Módulo relacionado à limpeza e pré-processamento do áudio. *(Obs: Ayres mencionou que não é necessário se preocupar com esta etapa).*
- **FeatureExtract**: Responsável pela extração de características do áudio e conversão dos dados para `.csv`.

## 🔍 Extração de Features

A extração é dividida em três domínios principais:

### 1️⃣ Domínio do Tempo
#### 🔹 Low-Level Features
   - **Energy**: Mede a energia total do sinal em um determinado intervalo de tempo.
   - **Zero-Cross-Rate**: Indica a taxa de cruzamentos por zero do sinal de áudio.
   - **Amplitude Envelope**: Representa a variação da amplitude ao longo do tempo.

#### 🔹 High-Level Features
   - **Tempo (ritmo)**: Determina a pulsação principal do áudio, útil para análise rítmica.

### 2️⃣ Domínio da Frequência
#### 🔹 Low-Level Feature
   - **Média das Frequências Ponderadas**: Calcula a média das frequências, ponderadas pela amplitude de cada amostra em cada quadro de análise. Utiliza a Transformada Rápida de Fourier (FFT).

#### 🔹 High-Level Feature
   - **MFCC (Mel-Frequency Cepstral Coefficients)**: Extrai os coeficientes cepstrais de frequência mel, calculando estatísticas como média e desvio padrão.

### 3️⃣ Features em Imagens de Espectrogramas
Além das características extraídas diretamente dos sinais de áudio, o projeto também analisa espectrogramas para extrair descritores baseados em **Histogram of Oriented Gradients (HOG)**.

#### 🔹 Extração de HOG de Espectrogramas
O método `get_hog(spectrogram)` realiza os seguintes passos:
   1. Redimensiona a imagem do espectrograma.
   2. Calcula os **Histogram of Oriented Gradients (HOG)**.
   3. Retorna estatísticas da feature extraída.

