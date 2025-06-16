# 🧠 ADNI CNN Dense Classifier

Este projeto aplica redes neurais convolucionais (CNNs) para classificar imagens de ressonância magnética (MRI) do cérebro usando a base de dados **ADNI (Alzheimer’s Disease Neuroimaging Initiative)**. O objetivo é auxiliar na detecção de estágios relacionados à Doença de Alzheimer: CN (Cognitivamente Normal), MCI (Comprometimento Cognitivo Leve) e AD (Doença de Alzheimer).

---

## 🧪 Tecnologias Utilizadas

- **Python 3.x**
- **TensorFlow / Keras**
- **NumPy**
- **Pandas**
- **Matplotlib / Seaborn**
- **NiBabel** (para manipulação de arquivos .nii)
- **Google Colab** (ambiente de execução)

---

## 📁 Estrutura do Projeto

```
.
├── ADNI_CNN_Dense.ipynb         # Notebook principal com o pipeline completo
├── README.md                    # Este arquivo
├── data/
│   ├── ADNI1_Annual_2_Yr_3T.csv # CSV com IDs das imagens e respectivos grupos
│   └── ADNI1_Annual/            # Diretório com imagens .nii
└── output/
    └── ADNI_Separado/           # Diretório onde são salvas as imagens .png organizadas por grupo
```

---

## 🚀 Etapas do Pipeline

### 1. Leitura e Tratamento dos Metadados

O arquivo CSV contém as seguintes colunas relevantes:
- `Image Data ID` — ID das imagens .nii
- `Group` — Classificação: CN, MCI, AD

### 2. Conversão dos Arquivos .nii

As imagens volumétricas `.nii` são convertidas para imagens bidimensionais `.png`, fatia por fatia (slice axial), com o uso da biblioteca NiBabel.

### 3. Organização em Diretórios

As imagens `.png` são armazenadas em pastas separadas por classe (`CN`, `MCI`, `AD`) e por ID de imagem.

### 4. Construção e Treinamento do Modelo

Uma CNN é construída com as seguintes camadas:
- Camadas `Conv2D` e `MaxPooling2D`
- `Flatten`, `Dense`, `Dropout`
- Otimizador: Adam
- Função de perda: Categorical Crossentropy

### 5. Avaliação

O modelo é avaliado com:
- Acurácia
- Matriz de Confusão
- F1-score, Precision, Recall

---

## 💾 Como Executar

### Google Colab

1. Faça upload do notebook e monte seu Google Drive:
```python
from google.colab import drive
drive.mount('/content/drive')
```

2. Ajuste os caminhos de entrada e saída de acordo com sua estrutura de pastas no Drive.

3. Execute as células sequencialmente.

---

## 📊 Resultados Esperados

- Alta acurácia para classificar os grupos CN, MCI e AD
- Visualização de imagens convertidas
- Matriz de confusão e métricas de desempenho

---

## 🔧 Instalação Local (Opcional)

Se desejar rodar localmente (não recomendado para grandes volumes de imagens .nii):

```bash
pip install numpy pandas matplotlib seaborn nibabel tensorflow scikit-learn
```

---

## 📎 Observações Importantes

- Os dados da ADNI exigem registro e autorização para uso. Acesse: [adni.loni.usc.edu](http://adni.loni.usc.edu)
- As imagens médicas são sensíveis. Este projeto é exclusivamente para fins acadêmicos e de pesquisa.

---

## 📌 Exemplo de Uso (Função de Conversão)

```python
nii_to_png("caminho/para/imagem.nii", "caminho/saida/imagem")
```

---

## 📄 Licença

Este projeto está licenciado sob os termos da **MIT License**.

---

## 👤 Autor

Desenvolvido por **Sharles Maurício Mariano**  
Contato: [LinkedIn](https://www.linkedin.com) | [GitHub](https://github.com)

© 2025 — Projeto acadêmico para aplicações de IA em neuroimagem.
