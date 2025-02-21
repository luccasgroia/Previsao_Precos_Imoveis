# Projeto: Previsão de Preços de Imóveis

## 1. Introdução
Este projeto tem como objetivo prever os preços de imóveis (SalePrice) com base em diversas características fornecidas em um dataset do Kaggle. A motivação é ajudar compradores, vendedores e investidores a estimar o valor de propriedades de maneira mais objetiva e baseada em dados.

---

## 2. Coleta de Dados
- **Fonte**: [House Prices - Advanced Regression Techniques (Kaggle)](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)
- **Arquivos**:
  - `train.csv`: Conjunto de treino com as variáveis explicativas e a variável alvo `SalePrice`.
  - `test.csv`: Conjunto de teste com as variáveis explicativas (sem `SalePrice`).
  - `sample_submission.csv`: Arquivo para padronizar o envio de previsões, contendo `Id` e `SalePrice` (inicialmente vazio).

---

## 3. Modelagem

### 3.1. Pré-processamento
1. **Separação do Target**: A coluna `SalePrice` é separada do `train.csv`.
2. **One-Hot Encoding**: Conversão de variáveis categóricas para variáveis dummies (0/1).
3. **Alinhamento**: Uso do `align` para garantir que `train` e `test` tenham as mesmas colunas após a codificação.
4. **Tratamento de Valores Ausentes**: Uso de `SimpleImputer` (mediana) para preencher `NaN`.

### 3.2. Treinamento do Modelo
- **Modelo**: Regressão Linear (LinearRegression).
- **Biblioteca**: `scikit-learn`.
- **Divisão de Dados**: `train_test_split` com 80% para treino e 20% para validação.

### 3.3. Avaliação
- **Métricas**:  
  - **RMSE (Root Mean Squared Error)**  
  - **R² (Coeficiente de Determinação)**
- **Resultado** (exemplo):  
  - RMSE = 34680.71  
  - R² = 0.84  

---

## 4. Visualização dos Resultados

Para verificar a qualidade das previsões, geramos um gráfico de dispersão comparando os valores reais de `SalePrice` e os valores preditos:

Exemplo de Gráfico
![image](https://github.com/user-attachments/assets/0a21e8b9-6e64-4866-9c3e-18f767ed3c6a)


Observamos que a maior parte dos pontos se aproxima da linha vermelha (que representa `valor real = valor predito`), indicando que o modelo de Regressão Linear está captando bem a relação entre as variáveis.

---

## 5. Conclusões

- **Desempenho**: Com R² = 0.84, o modelo explica boa parte da variação no preço dos imóveis.
- **Limitações**:  
  - Possibilidade de outliers ou variáveis não capturadas que influenciam o preço.
  - Modelos mais complexos (como Gradient Boosting, Random Forest) podem melhorar o desempenho.
- **Próximos Passos**:  
  - Ajuste de hiperparâmetros e validação cruzada.  
  - Engenharia de atributos (feature engineering).  
  - Comparar diferentes algoritmos.

---

## 6. Referências

- [Scikit-learn Documentation](https://scikit-learn.org/)
- [Pandas Documentation](https://pandas.pydata.org/)
- [Kaggle: House Prices - Advanced Regression Techniques](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)
