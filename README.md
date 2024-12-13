Relatório Final: Classificação de Diabetes se é positivo ou negativo

## 1. Descrição do Problema

O objetivo deste projeto foi desenvolver um modelo de machine learning para classificar os dados de uma database de dibetes como diabético ou não diabético. Isso é importante para que as pessoas possam estar tratando a doença ou realizando a prevenção caso seus dados indiquem proximidade a pessoas com diabetes.

### Dataset
- **Fonte:** [Diabetes Dataset](https://www.kaggle.com/datasets/akshaydattatraykhare/diabetes-dataset)
- **Descrição:** O dataset contém colunas de dados como:
  - **BloodPressure:** Pressão sanguínea.
  - **BMI:** Índice de massa corporal.
  - **Age:** Idade.
  - **Outcome:** Resultado (Se é diabético ou não).
.
  
### Pré-Processamento
1. **Leitura e Limpeza:**  
   O dataset foi carregado no formato `.csv`, e os rótulos foram mapeados para:
   - `1` para diabético
   - `0` para não diabético
2. **Divisão em Conjuntos de Treino e Teste:**  
   - 80% para treinamento e 20% para teste.

---

## 2. Resultados dos Modelos

### Modelos Testados
Foram treinados os seguintes modelos para comparação inicial:
- **K-Nearest Neighbors (KNN)**
- **Decision Tree**
- **Random Forest**

### Métricas de Avaliação
Os modelos foram avaliados usando:
- **Accuracy**: Percentual de classificações corretas realizadas pelo modelo.
- **Precision**: Percentual de diabetes identificados que realmente eram diabéticos.
- **Recall**: Percentual de diabetes detectada corretamente.
- **F1 Score**: Média harmônica entre precisão e recall para equilibrar os dois indicadores.

### Resultados dos Modelos Base
| Modelo                | Accuracy  | Precision | Recall   | F1 Score |
|-----------------------|-----------|-----------|----------|----------|
| **Árvore de Decisão** | 1.00000   | 1.00000   | 1.00000  | 1.00000  |
| **KNN**               | 0.75974   | 0.655172  | 0.690909 | 0.672566 |
| **Random Forest**     | 1.00000   | 1.000000  | 1.00000  | 1.00000  |

![image](https://drive.google.com/file/d/10allzTJxbv8ZNA9pjmJUI27QUJwbFqie/view?usp=drive_link)

### Justificativa para o Melhor Modelo
Tanto o **KNN** quanto o **Random Forest** foram os melhores modelos devido às seguintes razões:
1. **Robustez do Random Forest**: Embora ambos tenham apresentado resultados iguais, o Random Forest geralmente é preferido por ser um algoritmo mais robusto e resistente a overfitting. Ele combina múltiplas árvores de decisão, reduzindo o impacto de outliers ou variabilidade nos dados.
2. **Balanceamento Entre Variância e Viés**: Oferece uma boa combinação entre alta precisão e generalização.
3. **Melhor Desempenho Geral**: Tanto o Árvore de Decisão quanto o Random Forest apresentaram métricas perfeitas (provavelmente acurácia, precisão, recall e f1-score), demonstrando sua capacidade de classificar os dados de forma ideal.

---

## 3. Comparação de Hiperparâmetros no Random Forest

Inicialmente, buscamos melhorar o desempenho do **Random Forest** ajustando hiperparâmetros. Foram testadas diferentes combinações de configurações, conforme a tabela abaixo:

| Hiperparâmetros                                        | Accuracy  | Precision | Recall  | F1 Score |
|--------------------------------------------------------|-----------|-----------|---------|----------|
| **n_estimators=50, max_depth=10, min_samples_leaf=1**  |   1.0     |   1.0     |   1.0   |    1.0   |
| **n_estimators=100, max_depth=20, min_samples_leaf=2** |   1.0     |   1.0     |   1.0   |    1.0   |
| **n_estimators=200, max_depth=30, min_samples_leaf=3** |   1.0     |   1.0     |   1.0   |    1.0   |

![image](https://drive.google.com/file/d/1tGyyI6LO1mW7WfcpE9A2OF_RpvvA89Tm/view?usp=drive_link)

### Análise dos Resultados
- Os resultados obtidos indicam que a configuração original do modelo Random Forest apresenta o melhor desempenho para a tarefa de detecção de diabetes. A complexificação do modelo através do ajuste dos hiperparâmetros, neste caso, não se mostrou benéfica.

## 4. Conclusão

O modelo **Random Forest** foi escolhido como o melhor classificador para identificar pessoas com diabetes. Ele demonstrou excelente desempenho, especialmente com seus **hiperparâmetros padrões**. Melhorias futuras podem incluir o aumento dos dados do dataset, pois seus dados são muito nichados, tendo em vista que são dados de mulheres de herança indígena na faixa dos 21 anos.
