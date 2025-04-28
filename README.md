
# 🏦 Análise de Score de Crédito com Machine Learning

Projeto de classificação para prever o score de crédito de clientes bancários usando algoritmos de Machine Learning.

---

## 🚀 **Funcionalidades**
- **Tratamento de dados**: Codificação de variáveis categóricas
- **Modelos treinados**: RandomForest (82% acurácia) e KNN (73% acurácia)
- **Análise de importância**: Identificação das 5 principais características para score
- **Pipeline completo**: Desde importação até deploy do modelo

---

## ⚙️ **Tecnologias Utilizadas**
- **Python 3.11**
- **Pandas**: Manipulação de dados
- **Scikit-Learn**: Modelos de ML e métricas
- **Jupyter Notebook**: Ambiente de análise
- **LabelEncoder**: Transformação de dados categóricos

---

## 📂 **Estrutura do Projeto**
```plaintext
score-credito/
├── dados/
│   └── clientes.csv          # Base com 100k registros e 25 features
├── modelos/
│   ├── random_forest.pkl     # Modelo otimizado
│   └── knn.pkl               # Modelo baseline
└── analise.ipynb             # Notebook com análise completa
```

---

## 🛠️ **Como Executar**
1. **Instale as dependências**:
   ```bash
   pip install pandas scikit-learn jupyter
   ```

2. **Pré-processamento dos dados**:
   ```python
   from sklearn.preprocessing import LabelEncoder
   
   codificador = LabelEncoder()
   for coluna in tabela.columns:
       if tabela[coluna].dtype == "object" and coluna != "score_credito":
           tabela[coluna] = codificador.fit_transform(tabela[coluna])
   ```

3. **Treinamento dos modelos**:
   ```python
   from sklearn.ensemble import RandomForestClassifier
   
   modelo = RandomForestClassifier()
   modelo.fit(X_treino, y_treino)
   ```

4. **Avaliação de performance**:
   ```python
   from sklearn.metrics import accuracy_score
   previsoes = modelo.predict(X_teste)
   print(f"Acurácia: {accuracy_score(y_teste, previsoes):.2%}")
   ```

---

## 📊 **Principais Descobertas**
### Top 5 Características Influentes
| Característica          | Importância |
|-------------------------|-------------|
| Dívida Total            | 11.76%      |
| Mix de Crédito           | 8.45%       |
| Empréstimo Estudantil    | 8.69%       |
| Juros de Empréstimos     | 8.04%       |
| Histórico de Crédito     | 7.45%       |

### Comparativo de Modelos
| Modelo               | Acurácia | Tempo de Treino |
|----------------------|----------|-----------------|
| RandomForest         | 82.4%    | 28 segundos     |
| KNN                  | 73.2%    | 41 segundos     |

---

## 💡 **Recomendações**
1. Priorizar análise de **dívida total** e **histórico de crédito** para aprovação
2. Criar política especial para clientes com empréstimos estudantis
3. Monitorar clientes com mix de crédito acima de 3 produtos
4. Utilizar modelo RandomForest para decisões automatizadas
5. Reavaliar critérios a cada 6 meses com novos dados

---

✨ **Inspiração**: Projeto desenvolvido na aula *Python IA* da [Jornada Python](https://www.youtube.com/@hashtagprogramacao)  

> **Nota**: Documentação completa dos modelos disponível em [Scikit-Learn](https://scikit-learn.org/)


