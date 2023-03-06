# Árvores de Decisão - Métricas 

### Matriz de confusão 
| | A | B | C |
| ------------- | ------------- | ------------- | ------------- |
| A  | 30  | 10 | 20 | 
| B  | 5  | 60 | 5 | 
| C  | 20  | 10 | 60 | 

Diagonal principal = acertos do classificador. Restante = erros da classe da linha. 

### Métricas de Avaliação 
- Taxa de VP = nº de acerto do classificador para cada classe. <br/>
- Taxa de FN = nº de erro do classificador para cada classe. <br/>
Essas métricas são complementares. Ou seja, TFN = 1 - TVP.
- TFP = instâncias que não são da classe considerada, mas que são classificadas como se fossem. 
- TVN = instâncias que não são da classe considerada e que são classificadas como não sendo. <br/>
Essas métricas também são complementares. TVN = 1 - TFP.
- Precisão = taxa de instâncias classificadas corretamente como pertencentes a classe em questão dentre todos os que foram classificados na classe em questão.
Pr = TVP/(TVP+TFP)
- Sensibilidade/Recall = taxa de instâncias corretamente classificadas como pertencentes a classe em questão dentre todos os que realmente são da classe em questão.
Sens = TVP/(TVP+TFN)
- Acurácia = taxa total de intâncias classificadas corretamente. 
Ac = (TVP+TVN)/(TVP+TVN+TFP+TFN)
- F-measure = média harmônica entre precisão e sensibilidade. 
FM = (2*Pr*Sens)/(Pr+Sens)

|    |   TVP  |    TFN |   TFP  |   TVN   |  Precisão  | Recall | F-measure |
| ------------- | ------------- | ------------- | ------------- |------------- | ------------- | ------------- | ------------- |
| A  | 30/60  | 30/60  | 25/135 | 110/135 | 30/(30+25)  |   |   |   |
| B  | 60/70  | 10/70  | 20/130 | 110/130 | 60/(60+20) |   |   |   |
| C  | 60/90  | 30/90  | 25/105 | 80/105  | 60/(60+25)  |   |   |   |

|    |   TVP  |    TFN |   TFP  |   TVN   |  Precisão  | Recall | F-measure |
| ------------- | ------------- | ------------- | ------------- |------------- | ------------- | ------------- | ------------- |
| A  | 0.5  | 0.5  | 0.18 | 0.81 | 30/(30+25)  |   |   |   |
| B  | 0.86  | 0,14  | 0.15 | 110/130 | 60/(60+20) |   |   |   |
| C  | 0.67  | 0,33  | 0.24 | 80/105  | 60/(60+25)  |   |   |   |
