### Questão 1

Com suporte mínimo aceitável de 0.3, um itemset é considerado frequente se aparece em pelo menos 3 das 10 transações.

Para encontrar os itemsets frequentes, aplicamos o algoritmo Apriori em três etapas:

1. Geração dos itemsets frequentes de tamanho 1 (frequência absoluta maior ou igual a 3):

<table><thead><tr><th>Itemset</th><th>Suporte</th></tr></thead><tbody><tr><td>Leite</td><td>2/10</td></tr><tr><td>Café</td><td>2/10</td></tr><tr><td>Cerveja</td><td>2/10</td></tr><tr><td>Pão</td><td>5/10</td></tr><tr><td>Manteiga</td><td>3/10</td></tr><tr><td>Arroz</td><td>3/10</td></tr><tr><td>Feijão</td><td>2/10</td></tr></tbody></table>

2. Geração dos itemsets frequentes de tamanho 2 a partir dos itemsets frequentes de tamanho 1:
<table><thead><tr><th>Itemset</th><th>Suporte</th></tr></thead><tbody><tr><td>{Pão, Manteiga}</td><td>3/10</td></tr><tr><td>{Pão, Arroz}</td><td>3/10</td></tr><tr><td>{Pão, Feijão}</td><td>2/10</td></tr></tbody></table>

3. Geração dos itemsets frequentes de tamanho 3 a partir dos itemsets frequentes de tamanho 2:

Não há itemsets frequentes de tamanho 3.

A partir dos itemsets frequentes, podemos gerar as regras de associação que atendem ao suporte mínimo e à confiança mínima de 0.8.

As regras geradas a partir dos itemsets frequentes são:

<table><thead><tr><th>Regra</th><th>Suporte</th><th>Confiança</th></tr></thead><tbody><tr><td>{Pão} =&gt; {Manteiga}</td><td>3/10</td><td>3/5 = 0.6</td></tr><tr><td>{Manteiga} =&gt; {Arroz}</td><td>3/10</td><td>3/3 = 1.0</td></tr><tr><td>{Arroz} =&gt; {Manteiga}</td><td>3/10</td><td>3/3 = 1.0</td></tr><tr><td>{Feijão} =&gt; {Pão}</td><td>2/10</td><td>2/2 = 1.0</td></tr><tr><td>{Pão} =&gt; {Feijão}</td><td>2/10</td><td>2/5 = 0.4</td></tr></tbody></table>

Portanto, o número de itemsets frequentes de tamanho 1, 2 e 3 são, respectivamente, 7, 3 e 0. E o número de regras de associação geradas é 6.

### Questão 2
https://colab.research.google.com/drive/1jP5Z-5DEinhrplyffkZ1mXsaPuC7TcPb?usp=sharing

### Questão 3
https://colab.research.google.com/drive/1rFehMpocx0coref81ztPr-5tQ0-xzg8D?usp=sharing

### Questão 4
https://colab.research.google.com/drive/1gSbfairfyihGox65_-F5o5LKd7xGw1pA?usp=sharing

### Questão 5

O artigo "A Literature Survey on Association Rule Mining Algorithms" é uma revisão da literatura que apresenta uma análise comparativa dos algoritmos de 
mineração de regras de associação mais populares na literatura acadêmica. A mineração de regras de associação tem como objetivo encontrar 
relações interessantes entre conjuntos de itens em grandes conjuntos de dados transacionais, o que pode ser útil em diversas aplicações, como análise 
de mercado, marketing, recomendação de produtos, entre outras.

O trabalho apresenta uma revisão dos algoritmos mais conhecidos e discute suas principais características, vantagens e desvantagens. Os algoritmos apresentados 
incluem o Apriori, Eclat, FP-growth, entre outros. 

Algoritmos baseados em Apriori: 
- Apriori: é um dos algoritmos mais populares e foi o primeiro a ser proposto na literatura. Ele é baseado na geração de itemsets frequentes e possui uma alta 
escalabilidade. Ele realiza uma busca exaustiva que gera candidatos a regras de associação usando o princípio da monotonicidade. É amplamente utilizado devido 
à sua simplicidade e eficiência.
- Eclat: é outro algoritmo que se baseia na geração de itemsets frequentes, mas utiliza uma abordagem de pesquisa em profundidade em vez de uma abordagem em
largura. Ele realiz uma busca vertical que gera candidatos a regras de associação usando o princípio de closure. É conhecido por sua eficiência 
em conjuntos de dados densos.
- FP-growth: é um algoritmo baseado em árvore que usa uma estrutura de dados chamada FP-tree para extrair regras de associação. É conhecido por sua eficiência
 em conjuntos de dados esparsos.
 
Algoritmos baseados em árvore: 
- C4.5: é um algoritmo de árvore de decisão que usa uma heurística chamada ganho de informação para selecionar os atributos mais relevantes para a classificação. 
Pode ser usado para extrair regras de associação.
- CART: é um algoritmo de árvore de decisão que usa uma heurística chamada impureza de Gini para selecionar os atributos mais relevantes para a classificação. 
Também pode ser usado para extrair regras de associação.
- CHAID: é um algoritmo de árvore de decisão que usa uma abordagem baseada em testes estatísticos para selecionar os atributos mais relevantes para a classificação. 
Também pode ser usado para extrair regras de associação.

O paper também discute técnicas para melhorar a eficiência dos algoritmos, como a poda de ramos e a redução de dados, essenciais para melhorar a eficiência e 
escalabilidade dos algoritmos de mineração de regras de associação, tornando-os mais adequados para lidar com grandes volumes de dados e extrair padrões úteis e 
relevantes.

- Redução de dimensionalidade: técnicas como Análise de Componentes Principais (PCA) podem ser usadas para reduzir a dimensionalidade do conjunto de dados, 
tornando-o mais eficiente para ser processado por algoritmos de mineração.

- Pré-processamento de dados: técnicas como normalização, discretização e remoção de outliers podem ser aplicadas para melhorar a qualidade do conjunto de dados 
e torná-lo mais adequado para ser processado pelos algoritmos de mineração.

- Paralelização: os algoritmos de mineração de regras de associação podem ser paralelizados para acelerar o processamento em sistemas de computação distribuída 
ou multiprocessados.

- Amostragem de dados: em conjuntos de dados muito grandes, pode ser eficiente trabalhar com amostras aleatórias para identificar padrões relevantes, em vez de 
processar todo o conjunto de dados.

- Algoritmos híbridos: algoritmos híbridos combinam diferentes técnicas para melhorar a eficiência e precisão dos resultados de mineração de regras de associação.

- Uso de técnicas de aprendizado de máquina: técnicas de aprendizado de máquina, como redes neurais e árvores de decisão, podem ser usadas para pré-processar 
ou pós-processar os resultados da mineração de regras de associação, melhorando a qualidade dos resultados e a eficiência do algoritmo.

O artigo aborda, também, os desafios e limitações dos algoritmos de mineração de regras de associação, incluindo o problema da explosão combinatória, a falta de 
escalabilidade em grandes conjuntos de dados e a necessidade de se lidar com dados incompletos ou ruidosos. Eles são uma ferramenta poderosa para a descoberta de 
padrões em grandes conjuntos de dados. A combinação de técnicas eficazes de mineração de dados e a compreensão dos desafios e limitações pode ajudar a maximizar 
a utilidade desses algoritmos na análise de dados.

- Explosão combinatória: o número de possíveis regras de associação aumenta exponencialmente com o tamanho do conjunto de dados, tornando a análise de todos os 
possíveis padrões impraticável.

- Escalabilidade: muitos algoritmos de mineração de regras de associação não são escaláveis para grandes conjuntos de dados, o que pode tornar o processo de 
mineração demorado e ineficiente.

- Dados incompletos ou ruidosos: a presença de dados incompletos ou ruidosos pode levar a resultados imprecisos ou errôneos na mineração de regras de associação.

- Alta dimensionalidade: conjuntos de dados com alta dimensionalidade podem tornar a mineração de regras de associação complexa e demorada.

- Seleção de parâmetros: muitos algoritmos de mineração de regras de associação exigem a seleção de parâmetros, o que pode ser um desafio para usuários que não 
têm experiência em análise de dados.

- Interpretação dos resultados: a interpretação dos resultados da mineração de regras de associação pode ser difícil, especialmente quando se trata de regras 
complexas ou de padrões de baixa frequência.

Outras técnicas propostas incluem a utilização de algoritmos paralelos e distribuídos para melhorar a escalabilidade, o uso de técnicas de pré-processamento de 
dados, como a redução de dimensionalidade, a utilização de algoritmos híbridos e o uso de técnicas de aprendizado de máquina para melhorar a qualidade dos resultados.

Por fim, o artigo conclui que a escolha do algoritmo de mineração de regras de associação deve ser feita com base nas características do conjunto de dados e nas 
necessidades do usuário, e que a combinação de diferentes técnicas e algoritmos pode levar a melhores resultados. Os algoritmos baseados em apriori são os mais 
utilizados na prática, devido à sua simplicidade e eficiência. No entanto, os algoritmos baseados em árvore podem ser mais eficazes em certos casos, como em 
conjuntos de dados com atributos discretos.
