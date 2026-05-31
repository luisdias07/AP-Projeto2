# Classificação Automática de Imagens de CPRE com Aprendizagem Profunda

Repositório correspondente ao Projeto de Grupo (Módulo 2) da disciplina de Aprendizagem Profunda (AP). Este projeto foca-se no desenvolvimento e comparação de modelos de *Deep Learning* para a classificação automática de imagens fluoroscópicas de Colangiopancreatografia Retrógrada Endoscópica (CPRE).

**GitHub Repository:** [https://github.com/luisdias07/AP-Projeto2](https://github.com/luisdias07/AP-Projeto2)

## 👥 Elementos do Grupo
* [Luís Miguel Dias]
* [Henrique Teixeira]
* [Filipe Ferreira]
* [Teresa Torres]
---

## 🎯 Objetivo
Avaliar o desempenho de quatro arquiteturas distintas:
1. **MobileNetV2** (Melhor modelo do estudo)
2. **DenseNet169**
3. **EfficientNet-B7**
4. **DeiT-III**

As imagens são classificadas em quatro categorias diagnósticas:
* `Biliary_Leaks` (Fugas de bílis)
* `Lithiasis` (Cálculos biliares)
* `Stricture` (Estenoses dos ductos)
* `Normal` (Achados normais)

---

## 🛠️ Instalação e Requisitos

É fortemente recomendada a utilização de um ambiente virtual (Python 3.8+) com suporte a GPU (CUDA).

1. **Clonar o repositório ou extrair o ficheiro ZIP:**
   ```bash
   git clone [https://github.com/luisdias07/AP-Projeto2.git](https://github.com/luisdias07/AP-Projeto2.git)
   cd AP-Projeto2

2. **Instalar as dependências:**
   pip install -r requirements.txt

3. **Organização do Dataset**
O projeto utiliza o dataset MIQR-CC. Para executar os scripts, garanta que as imagens estão na pasta data/ na raiz do projeto, respeitando a divisão original (treino, validação e teste):
AP-Projeto2/
├── data/
│   ├── train/
│   ├── val/
│   └── test/
├── models/             
├── requirements.txt
├── README.md
├── train.py            
├── evaluate.py         
└── gradcam.py

**Instruções de Execução e Reprodutibilidade**

1. **Treinar os Modelos**
   python train.py --model mobilenetv2 --epochs 60 --batch_size 4 --lr 1e-4

2. **Avaliação e Extração de Métricas (Teste)**
   python evaluate.py --model mobilenetv2 --checkpoint models/best_mobilenetv2.pth --data_dir data/test

3. **Interpretabilidade Visual (Grad-CAM)**
   python gradcam.py --model mobilenetv2 --checkpoint models/best_mobilenetv2.pth --image_path data/test/Biliary_Leaks/exemplo.png
