# 🧠 Projeto: Diagnóstico de Falhas em Rolamentos com Espectrogramas

Projeto do uso de **técnicas de aprendizado profundo (autoencoders e ResNet)** aplicadas a **espectrogramas** gerados a partir de sinais de vibração de rolamentos. O objetivo é detectar e classificar automaticamente falhas como:

- Trincas na pista interna
- Trincas na pista externa
- Esferas danificadas

---

## 📂 Estrutura do Projeto

```text
bearing-fault-autoencoder/
│
├── data/                               # Arquivos .mat dos datasets (CWRU, HUST)
├── images/                             # Espectrogramas gerados
│   ├── CWRU/
│   └── HUST/
├── notebooks/                          # Jupyter Notebooks com etapas principais
│   ├── generate_spectograms/           # Geração automática de espectrogramas
│   ├── train_autoencoder/              # Treinamento com ResNet18
│   ├── evaluate_autoencoder/           # Avaliação com reconstrução
│   └── classifier_faults_resnet18/     # Classificação das falhas baseado nos espectogramas
└── README.md
```

---

## 📦 Requisitos

- Python 3.8+
- PyTorch
- torchvision
- numpy
- matplotlib
- scikit-learn

---

## 📊 Base de Dados

- **CWRU (Case Western Reserve University):** dataset público com falhas simuladas em rolamentos.
- **HUST Bearing Dataset:** inclui diferentes tipos de rolamento, diâmetro de falha e variação de carga.

Os arquivos `.mat` devem estar na pasta `data/`.

---

## ⚒️ Etapas do Projeto

### 1. Gerar espectrogramas

Cria imagens PNG em subpastas organizadas por classe.

### 2. Treinamento do Autoencoder

Treinamento com imagens da classe `normal`. Reconstruções ruins indicam falha.

### 3. Avaliação com Reconstrução

Gera curva ROC, erros de reconstrução.

### 4. Classificação Supervisionada

Treinamento com CWRU + HUST usando ResNet18. Avaliação com matriz de confusão e métricas.

---

## 📈 Resultados

- **AUC (Autoencoder):** ~0.89
- **Acurácia (ResNet18):** ~79% com dataset combinado
- **Classes:** `normal`, `inner`, `outer`, `ball`

---

## 🧠 Modelos Utilizados

- Autoencoder convolucional não supervisionado
- ResNet18 com fine-tuning para classificação

---

## 📌 Objetivo da Pesquisa

Investigar o uso de autoencoders para **detecção de anomalias com poucos dados rotulados**, e aplicar modelos supervisionados (ResNet) para classificação precisa das falhas.

---

## 👨‍💼 Autor

Pedro Mariani Coelho  
Mestrando em Computação Aplicada
