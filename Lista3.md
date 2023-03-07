# Árvores de Decisão - Métricas 
#### Questão 01
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

Cálculos
|    |   TVP  |    TFN |   TFP  |   TVN   |  Precisão  |    Recall    | F-measure |
| ------------- | ------------- | ------------- | ------------- |------------- | ------------- | ------------- | ------------- |
| A  | 30/60  | 30/60  | 25/135 | 110/135 | 30/(30+25)  |  30/(30+30) |  (2*0.55*0.5)/(0.55+0.5)   |
| B  | 60/70  | 10/70  | 20/130 | 110/130 | 60/(60+20)  |  60/(60+10) |  (2*0.75*0.86)/(0.75+0.86) |   
| C  | 60/90  | 30/90  | 25/105 | 80/105  | 60/(60+25)  |  60/(60+30) |  (2*0.71*0.67)/(0.71+0.67) |   

Resultados
|    |   TVP  |    TFN |   TFP  |   TVN   |  Precisão  | Recall | F-measure |
| ------------- | ------------- | ------------- | ------------- |------------- | ------------- | ------------- | ------------- |
| A  | 0.5   | 0.5   | 0.18 | 0.81 | 0.55  |  0.5  |  0.52 |   
| B  | 0.86  | 0.14  | 0.15 | 0.85 | 0.75  | 0.86  |  0.8 |   
| C  | 0.67  | 0.33  | 0.24 | 0.76 | 0.71  |  0.67 |  0.69 |   

#### Questão 02
A precisão indica quantas das instâncias classificadas como positivas são realmente positivas. Uma alta precisão significa que o modelo tem uma baixa taxa de falsos positivos, o que é importante em casos em que as consequências de uma classificação incorreta são graves. <br/>
A sensibilidade indica quantas das instâncias positivas foram detectadas corretamente pelo modelo. Uma alta sensibilidade é importante em casos em que a identificação de todas as instâncias positivas é crucial, como no diagnóstico de uma doença. <br/>
Sendo assim, a interpretação dos resultados de precisão e recall depende do contexto em que o modelo de classificação está sendo usado e das consequências das classificações incorretas. É importante avaliar ambas as métricas para ter uma visão mais completa do desempenho do modelo.

#### Questão 03
P(y|x) = P(y) * P(x|y) / P(x)

Onde:

- P(y|x) é a probabilidade posteriori da classe y dado a entrada x.
- P(y) é a probabilidade a priori da classe y, ou seja, a probabilidade de que a classe y ocorra independentemente dos valores observados dos atributos de entrada.
- P(x|y) é a probabilidade condicional da entrada x dado a classe y, ou seja, a probabilidade de observar a entrada x dado que a classe y é verdadeira.
- P(x) é a probabilidade marginal da entrada x, ou seja, a probabilidade de observar a entrada x independentemente da classe. <br/>
A probabilidade marginal P(x) pode ser ignorada, pois ela é constante para todas as classes e não afeta a classificação final.

