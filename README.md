# Projeto Machine Learning: Classificação de Dígitos Manuscritos

## Objetivo

Este projeto visa classificar dígitos manuscritos (de 0 a 9) a partir de imagens digitalizadas. O problema é formalmente uma tarefa de **classificação multi-classe supervisionada**.

### Entrada (IN)

- **Vetores de Características (Features):** Imagens 8x8 pixels transformadas em vetores de 64 dimensões.
- Cada valor no vetor representa a **intensidade de um pixel**.

### Saída (OUT)

- Os dígitos corretos (0, 1, 2, ..., 9).

---

## 🛠️ Ferramentas e Metodologia

Foram utilizadas duas abordagens de classificação supervisionada da biblioteca `scikit-learn`.

### 1. K-Vizinhos Mais Próximos (`KNeighborsClassifier`)

- **Tipo:** Algoritmo baseado em distância, não-paramétrico.
- **Princípio:** Classifica um novo ponto de dados com base na **maioria dos rótulos** de seus k vizinhos mais próximos.
- **Configuração (Padrão):** Utilizado com k=5 vizinhos e métrica de distância Minkowski.

### 2. Floresta Aleatória (`RandomForestClassifier`)

- **Tipo:** Método de _ensemble_ baseado em múltiplas árvores de decisão.
- **Princípio:** Constrói múltiplas árvores e obtém a previsão final por **votação majoritária**.
- **Configuração:** Utilizado com 100 árvores (`n_estimators=100`).

---

## Resultados e Análise

Os modelos foram treinados com 80% dos dados e avaliados com 20%.

### Acurácia dos Modelos

A acurácia (`model.score`) representa a proporção de previsões corretas no conjunto de teste.

| Modelo                       | Acurácia (Score) |
| :--------------------------- | :--------------- |
| **KNN** (`model1`)           | **99,17%**       |
| **Random Forest** (`model2`) | **97,78%**       |

### Discussão

O **KNN superou o Random Forest** em acurácia.

- **Vantagem do KNN:** O algoritmo se beneficiou da **proximidade clara** entre os vetores de imagens dos mesmos dígitos.
- **Erros Comuns:** Os erros mais frequentes envolvem dígitos visualmente semelhantes, como 7 e 9, ou 8 com 1, 5 e 9.

---

## Configuração e Execução

### Dataset

O projeto utiliza o dataset **Digits** (`load_digits()`), que é um conjunto de dados de classificação de acesso rápido (_built-in_) no `scikit-learn`.

### Requisitos

Para rodar o notebook (`digits.ipynb`), você precisará das seguintes bibliotecas:

- `sklearn`
- `matplotlib`
- `seaborn`
- `numpy`

> **Nota:** As especificações de hardware utilizadas no desenvolvimento foram: **CPU AMD Ryzen 5 1500X**, **RAM 16GB DDR4** e **GPU NVIDIA GTX 1660 Super**.

### Como Executar

1. Clone o repositório.
2. Inicie o Jupyter Lab ou Jupyter Notebook e abra o arquivo `digits.ipynb`.

---

## Autor

- **Aluno:** Giovane Batista de Lima e Cirne
- **Instituição:** Universidade do Estado do Rio
