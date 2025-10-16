# Desafio de Projeto DIO: Transfer Learning para Classificação de Imagens

## 📄 Descrição do Projeto
Este projeto foi desenvolvido como parte do desafio de projeto da [Digital Innovation One (DIO)](https://www.dio.me/). O objetivo principal é aplicar a técnica de **Transfer Learning** para construir um classificador de imagens eficiente, utilizando a linguagem Python, a biblioteca TensorFlow/Keras e o ambiente Google Colab.

## 🎯 Objetivo
O desafio consiste em:
1.  Construir e treinar uma rede neural profunda utilizando uma arquitetura pré-treinada.
2.  Adaptar o modelo para uma nova tarefa de classificação com um dataset customizado (neste caso, Gatos vs. Cachorros).
3.  Documentar todo o processo de forma clara e estruturada, demonstrando o entendimento dos conceitos de Transfer Learning.

## 🛠️ Tecnologias Utilizadas
- **Linguagem:** Python 3
- **Ambiente:** Google Colab
- **Bibliotecas Principais:** TensorFlow, Keras, Matplotlib, NumPy
- **Modelo Base:** MobileNetV2 (pré-treinado no dataset ImageNet)

## 📁 O Dataset
O dataset utilizado foi o "Cats and Dogs", disponibilizado pelo TensorFlow. Ele contém:
- **Classes:** 2 (Gatos e Cachorros)
- **Imagens de Treino:** 2000 imagens (1000 por classe)
- **Imagens de Validação:** 1000 imagens (500 por classe)
- **Dimensões das Imagens:** Redimensionadas para 160x160 pixels

## 🧠 O Modelo de Transfer Learning

A abordagem de Transfer Learning consiste em aproveitar o conhecimento de um modelo já treinado em um grande dataset (como o ImageNet) e adaptá-lo para uma nova tarefa.

O fluxo do modelo foi:
1.  **Carregamento do Modelo Base:** Foi utilizada a arquitetura **MobileNetV2** sem suas camadas de topo (`include_top=False`).
2.  **Congelamento de Camadas:** As camadas do `base_model` foram congeladas para que seus pesos não fossem atualizados durante o treinamento inicial, preservando o conhecimento adquirido.
3.  **Adição de Novas Camadas:** Uma nova "cabeça" de classificação foi adicionada no topo do modelo base, consistindo em:
    - `GlobalAveragePooling2D`: Para reduzir a dimensionalidade dos mapas de características.
    - `Dropout`: Para regularização e prevenção de overfitting.
    - `Dense (sigmoid)`: A camada de saída para a classificação binária.

## 📈 Resultados
O modelo foi treinado por 10 épocas e alcançou uma **acurácia de validação de 95.5%**. Este resultado demonstra a eficácia do Transfer Learning, que permite atingir alto desempenho com um dataset relativamente pequeno e poucas épocas de treinamento.

A seguir, os gráficos de acurácia e perda durante o treinamento:

![Resultados do Treinamento](images/training_results.png)

**Análise dos Resultados:**
Os gráficos mostram que a acurácia de treino e validação aumentaram de forma consistente, enquanto a perda de ambas diminuiu. A pequena distância entre as curvas de treino e validação indica que o modelo generalizou bem para os dados novos, sem sinais significativos de *overfitting*.

## 🚀 Como Executar o Projeto
1.  Clone este repositório: `git clone https://github.com/SEU-USUARIO/SEU-REPOSITORIO.git`
2.  Abra o notebook `desafio_transfer_learning.ipynb` no Google Colab.
3.  Execute as células em ordem. O dataset será baixado e o modelo será treinado automaticamente.

## ✍️ Autor Luiz Alfredo (Fred Donega)

- **[SEU NOME COMPLETO]**
- **LinkedIn:** [LINK PARA SEU PERFIL NO LINKEDIN]
- **GitHub:** [LINK PARA SEU PERFIL NO GITHUB]
