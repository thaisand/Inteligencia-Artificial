# Lista 3
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

*Cálculos* 
|    |   TVP  |    TFN |   TFP  |   TVN   |  Precisão  |    Recall    | F-measure |
| ------------- | ------------- | ------------- | ------------- |------------- | ------------- | ------------- | ------------- |
| A  | 30/60  | 30/60  | 25/135 | 110/135 | 30/(30+25)  |  30/(30+30) |  (2*0.55*0.5)/(0.55+0.5)   |
| B  | 60/70  | 10/70  | 20/130 | 110/130 | 60/(60+20)  |  60/(60+10) |  (2*0.75*0.86)/(0.75+0.86) |   
| C  | 60/90  | 30/90  | 25/105 | 80/105  | 60/(60+25)  |  60/(60+30) |  (2*0.71*0.67)/(0.71+0.67) |   

*Resultados*
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

O algoritmo de Naive Bayes assume que as características (ou atributos) dos dados de entrada são independentes entre si, o que simplifica o cálculo da probabilidade condicional de cada classe dada as características observadas. É chamado de "naive" (ingênuo) porque essa suposição de independência nem sempre é verdadeira na prática, mas ainda assim pode fornecer bons resultados em muitos casos.

O algoritmo envolve os seguintes passos:

1. Coletar um conjunto de dados de treinamento com exemplos rotulados (exemplos de entrada e suas classes correspondentes).
2. Calcular a probabilidade a priori de cada classe, ou seja, a probabilidade de cada classe ocorrer independentemente das características observadas.
3. Calcular a probabilidade condicional de cada classe dado as características observadas, ou seja, a probabilidade de cada classe ocorrer dado os valores observados 4. dos atributos de entrada.
5. Multiplicar as probabilidades condicionais de cada classe para obter a probabilidade posteriori de cada classe para uma nova entrada.
6. Classificar a nova entrada como a classe com a maior probabilidade posteriori.


A fórmula geral para calcular a probabilidade posteriori de uma classe dado uma entrada x é dada por:

P(y|x) = P(y) * P(x|y) / P(x)

Onde:

- P(y|x) é a probabilidade posteriori da classe y dado a entrada x.
- P(y) é a probabilidade a priori da classe y, ou seja, a probabilidade de que a classe y ocorra independentemente dos valores observados dos atributos de entrada.
- P(x|y) é a probabilidade condicional da entrada x dado a classe y, ou seja, a probabilidade de observar a entrada x dado que a classe y é verdadeira.
- P(x) é a probabilidade marginal da entrada x, ou seja, a probabilidade de observar a entrada x independentemente da classe. <br/>
A probabilidade marginal P(x) pode ser ignorada, pois ela é constante para todas as classes e não afeta a classificação final.

*Cálculos*

- Jogar: 

P(Jogar = Sim) = 9/14 = 0,64 <br/>
P(Jogar = Não) = 5/14 = 0,36

- Aparência:

P(Aparência = Chuva | Jogar = Sim) = 3/9 = 0,33 <br/>
P(Aparência = Chuva | Jogar = Não) = 2/5 = 0,4

P(Aparência = Nublado | Jogar = Sim) = 4/9 = 0,44 <br/>
P(Aparência = Nublado | Jogar = Não) = 0/5 = 0

P(Aparência = Sol | Jogar = Sim) = 2/9 = 0,22 <br/>
P(Aparência = Sol | Jogar = Não) = 3/5 = 0,6

- Temperatura: 

P(Temperatura = Fria | Jogar = Sim) = 3/9 = 0,33 <br/>
P(Temperatura = Fria | Jogar = Não) = 1/5 = 0,2

P(Temperatura = Quente | Jogar = Sim) = 2/9 = 0,22 <br/>
P(Temperatura = Quente | Jogar = Não) = 2/5 = 0,4

P(Temperatura = Agradável | Jogar = Sim) = 4/9 = 0,44 <br/>
P(Temperatura = Agradável | Jogar = Não) = 2/5 = 0,4

- Umidade:

P(Umidade = Normal | Jogar = Sim) = 6/9 = 0,67 <br/>
P(Umidade = Normal | Jogar = Não) = 1/5 = 0,2

P(Umidade = Alta | Jogar = Sim) = 3/9 = 0,33 <br/>
P(Umidade = Alta | Jogar = Não) = 4/5 = 0,8

- Ventando:

P(Ventando = Sim | Jogar = Sim) = 3/9 = 0,33 <br/>
P(Ventando = Sim | Jogar = Não) = 3/5 = 0,6

P(Ventando = Não | Jogar = Sim) = 6/9 = 0,67 <br/>
P(Ventando = Não | Jogar = Não) = 2/5 = 0,4

- Jogar = Sim | Aparência = Chuva, Temperatura = Fria, Umidade = Normal, Ventando = Sim:

P(Jogar = Sim | Aparência = Chuva, Temperatura = Fria, Umidade = Normal, Ventando = Sim) =  <br/>
P(Jogar = Sim) * P(Aparência = Chuva | Jogar = Sim) * P(Temperatura = Fria | Jogar = Sim) * P(Umidade = Normal | Jogar = Sim) * P(Ventando = Sim | Jogar = Sim) = <br/>
0,64 * 0,33 * 0,33 * 0,67 * 0,33 = 0,01541

- Jogar = Não | Aparência = Chuva, Temperatura = Fria, Umidade = Normal, Ventando = Sim:

P(Jogar = Não | Aparência = Chuva, Temperatura = Fria, Umidade = Normal, Ventando = Sim) = <br/>
P(Jogar = Não) * P(Aparência = Chuva | Jogar = Não) * P(Temperatura = Fria | Jogar = Não) * P(Umidade = Normal | Jogar = Não) * P(Ventando = Sim | Jogar = Não) = <br/>
0,36 * 0,4 * 0,2 * 0,2 * 0,6 = 0,00346

*Resultados*

0,01541 > 0,00346  <br/>
Ou seja, a probabilidade posteriori de Jogar = Sim é maior do que a probabilidade posteriori de Jogar = Não. Portanto, o Naive Bayes classifica o registro "Aparência = Chuva, Temperatura = Fria, Umidade = Normal, Ventando = Sim" como Jogar = Sim.

#### Questão 04
<https://colab.research.google.com/drive/1m89JHdVUcMWbThgrIKJ1uXu2wc2Ck7_R?usp=sharing>

#### Questão 05
<https://colab.research.google.com/drive/1ArrN3rwya0bhPPnrfBRQk2WkHPkyawil?usp=sharing>
