# Fashion Recommendation System with MobileNetV2

Este projeto implementa um sistema de recomendação visual para produtos de moda utilizando aprendizado de máquina e visão computacional.

## Funcionalidades

### 1. **Carregamento e filtragem de dados**
- O script carrega um arquivo CSV contendo metadados dos produtos.
- Filtra colunas relevantes: `id`, `articleType`, `baseColour`, `gender`.
- Verifica se as imagens correspondentes existem e mantém apenas os registros válidos.

### 2. **Extração de características visuais**
- Utiliza o modelo MobileNetV2 (sem pesos pré-treinados) para extrair vetores de características das imagens.
- As imagens são redimensionadas para 224x224 e processadas com `preprocess_input`.

### 3. **Codificação de metadados textuais**
- Aplica `LabelEncoder` para transformar os campos `articleType`, `baseColour` e `gender` em vetores numéricos.

### 4. **Combinação de características**
- Combina os vetores visuais e textuais em um único vetor para cada produto.
- Calcula a matriz de similaridade usando `cosine_similarity`.

### 5. **Recomendações visuais**
- A função `show_similar(index, top_n)` exibe os produtos mais semelhantes visualmente a um item de referência.

### 6. **Busca automática em lojas online**
- A função `buscar_na_amazon(index)` gera e abre um link de busca no Amazon com base no tipo e cor do produto.
- A função `buscar_no_google_shopping(index)` faz o mesmo para o Google Shopping.

### 7. **Seleção aleatória de produtos**
- O script seleciona 3 produtos aleatórios e aplica as funções de recomendação e busca online para cada um.

## Requisitos
- Python 3
- TensorFlow
- Pandas, NumPy, scikit-learn, OpenCV, Matplotlib

## Execução
Execute o script em um ambiente com suporte a bibliotecas de ML e acesso às imagens e metadados do dataset.
