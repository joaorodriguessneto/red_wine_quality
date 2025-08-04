![Imagem inicial](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img/imagem_inicial_readme_small.png)
# 🍷 Projeto de análise de dados sobre a qualidade de vinhos tintos com previsão da qualidade (modelo de classificação). 

## 🔍 Observações Relevantes sobre o Projeto:

#### Este projeto foi desenvolvido com a intenção de simular um cenário real dentro de uma empresa de análise de dados voltada ao setor vitivinícola. O contexto apresentado é fictício, e a empresa EnoInsights Analytics, bem como seu CEO, foram criados exclusivamente para fins ilustrativos.

#### Fique à vontade para explorar todo o código e as análises realizadas ao longo do projeto. O Jupyter Notebook contendo a EDA, visualizações e modelagem preditiva está disponível neste repositório.




## 🎯 Desafio: Predição da Qualidade de Vinhos Tintos



#### O setor vitivinícola está cada vez mais interessado em aplicar ciência de dados para aprimorar a qualidade dos vinhos e entender os fatores que influenciam a nota atribuída por especialistas. No cenário apresentado, a empresa EnoInsights Analytics foi contratada por uma vinícola do Vale do Douro com o objetivo de construir um modelo que seja capaz de prever se um vinho tinto receberá uma avaliação positiva ou negativa, com base apenas em suas propriedades físico-químicas.
#### Como cientista de dados da empresa, fui responsável por estruturar todo o processo, da análise exploratória até a aplicação de modelos de machine learning.


## ❓ Questionamentos do CEO:

  * Quais características químicas estão mais fortemente associadas aos vinhos de melhor qualidade?

  * Vinhos com teor alcoólico mais alto tendem a receber notas mais elevadas?

  * A acidez (fixa ou volátil) influencia negativamente a percepção de qualidade?

  *  * João, acabamos de analisar uma nova amostra de vinho com os seguintes parâmetros laboratoriais:

          * Fixed Acidity: 7.4
          * Volatile Acidity: 1.23
          * Citric Acid: 0.83
          * Residual Sugar: 1.9
          * Chlorides: 0.076
          * Free Sulfur Dioxide: 11.0
          * Total Sulfur Dioxide: 34.0
          * Density: 0.998
          * pH: 3.73
          * Sulphates: 0.94
          * Alcohol: 13.0

        Com base nesses dados, conseguimos prever com o seu modelo qual seria a provável classificação de qualidade desse vinho?


## 📖 Dicionário de dados fornecido pela empresa: 

  * fixed acidity - Refere-se à acidez resultante da presença de ácidos orgânicos pouco voláteis, como málico, lático, tartárico ou cítrico, encontrados no vinho;
  * volatile acidity - Refere-se ao nível de acidez causado por ácidos leves, principalmente o ácido acético, que conferem ao vinho aromas e sabores semelhantes ao do vinagre;
  * citric acid - Concentração de ácido cítrico encontrada no vinho;
  * residual sugar - Nível de açúcar não fermentado da uva que ainda está presente no vinho;
  * chlorides - concentração de cloretos(sais) no vinho;
  * free sulfur dioxide - concentração de dióxido de enxofre livre no vinho, refere-se as falta de ligação com outras moléculas;
  * total sulfur dioxide - concentração de dióxido de enxofre total no vinho, refere-se ao livres mais a parte que possui ligação com outras moléculas;
  * density - densidade do vinho;
  * pH - nível de ph do vinho;
  * sulphates - concentração de sulfatos no vinho;
  * alcohol - nível de concentração de álcool no vinho.
  * quality: nota de qualidade atribuída por especialistas 

 Obs: a variável quality foi transformada em binária para fins de classificação:

  * 0 = qualidade ruim (nota ≤ 5)

  * 1 = qualidade boa (nota > 5)

    

## 🛠️ Abordagem Atual da Empresa (Método utilizado atualmente) 


* #### Atualmente, a empresa Beautiful Houses define os preços dos imóveis com base em uma média dos valores praticados no mercado e, em muitas ocasiões, também se apoia na intuição do diretor executivo e da equipe de negócios. 


* #### Como cientista de dados da empresa, nosso objetivo é aprimorar esse processo, tornando-o mais preciso e baseado em evidências. Para isso, será desenvolvido um modelo de machine learning utilizando regressão linear múltipla, capaz de estimar o valor dos imóveis com base em suas características, como área, número de banheiros, entre outras variáveis relevantes. 


## 💡 Estratégia de Solução      



1. Importação e inspeção inicial dos dados
2. Análise estatística e visualizações exploratórias
3. Estudo de correlação entre variáveis
4. Criação de variável-alvo binária
5. Normalização dos dados (para o modelo KNN)
6. Treinamento de diferentes modelos:

    - DummyClassifier (baseline)
    - Decision Tree
    - K-Nearest Neighbors (KNN)
    - Random Forest

7. Avaliação dos modelos por acurácia, matriz de confusão, precisão, recall e F1-score
8. Análise da importância das variáveis (feature importance)
9. Geração de insights e recomendações

## 🧠 Principais insights da análise exploratória 


#### Após a análise realizada, foi possível identificar que as características que mais influenciam na qualidade dos vinhos, dentro do conjunto de dados analisado, como: a acidez fixa, a densidade, o teor de ácido cítrico, o dióxido de enxofre total e o teor alcoólico.


* ###  Acidez Fixa

![boxplot acidez fixa](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/boxplot_acidez_fixa.png)

#### O boxplot acima representa a distribuição dos valores de acidez fixa nos vinhos analisados. A mediana da acidez encontra-se em torno de 7,9, enquanto a maior concentração de valores (entre o primeiro e o terceiro quartil) varia aproximadamente de 7,1 a 8,7. Observa-se também a presença de diversos outliers acima de 12, indicando amostras com níveis significativamente mais altos de acidez fixa.

![grafico de barras](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/grafico_barras_acidez_fixa.png)

#### A análise da acidez fixa nos vinhos tintos, com base no boxplot e no histograma, mostra que a maioria das amostras está concentrada entre os valores 6,4 e 8,4, com mediana em torno de 7,9. Observa-se também a presença de outliers acima de 12, indicando uma distribuição assimétrica à direita. Esses resultados reforçam a importância da acidez fixa como variável relevante para a qualidade do vinho e destacam a necessidade de atenção ao tratar valores extremos no pré-processamento dos dados.

* ###  Densidade

![grafico de barras](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/grafico_frequencia_densidade.png)

#### O gráfico acima apresenta a distribuição da densidade nos vinhos tintos, mas devido à grande quantidade de valores únicos e à proximidade entre eles, o resultado ficou visualmente poluído, dificultando a interpretação dos dados. O excesso de barras estreitas e sobreposição nos rótulos do eixo X compromete a clareza da visualização. Para melhorar a leitura e tornar a análise mais compreensível, optei por agrupar os valores por faixas (dezenas), o que permite observar padrões e tendências de forma mais clara e objetiva, sem perder informações relevantes.

![grafico de barras](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/grafico_barras_densidade_milesimo.png)

#### Como o gráfico anterior estava poluído devido à grande quantidade de variações pontuais, optei por agrupar os valores de densidade em faixas milésimas (0.001), facilitando a visualização. A distribuição resultante é aproximadamente simétrica, com a maioria das amostras concentradas entre 0.995 e 0.998, e pico em 0.997. Isso indica que esse é o intervalo mais frequente. À medida que nos afastamos desse centro, a frequência diminui, formando um padrão semelhante a uma curva normal.

* ###  Ácido Cítrico

![grafico de barras](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/grafico_qualidade_acidocitrico.png)

#### A partir do gráfico acima, é possível observar que vinhos com concentração de ácido cítrico entre 0.7 e 0.8 tendem a alcançar qualidade 6. Por outro lado, vinhos com nível 1 de ácido cítrico apresentam, em sua maioria, menor qualidade.

* ###  Álcool

![grafico de barras](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/grafico_qualidade_alcool.png)

#### O gráfico mostra que, de forma geral, a qualidade média dos vinhos aumenta conforme o teor alcoólico. Nas faixas iniciais (entre 8.4% e 10.0% de álcool), a qualidade média varia entre 4.5 e 5.5. A partir de 10.0%, há uma tendência de crescimento, com destaque para vinhos entre 11.5% e 13.5%, que apresentam as maiores médias de qualidade, frequentemente acima de 6.0.

* ###  Correlação

![grafico de correlação](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/grafico_correlacao.png)

#### A matriz de correlação mostra que, entre as variáveis numéricas, o álcool apresenta a correlação positiva mais forte com a qualidade do vinho (0.48), indicando que teores alcoólicos mais altos tendem a estar associados a vinhos melhor avaliados. Já a acidez volátil possui a correlação negativa mais significativa (-0.39), sugerindo que níveis elevados desse composto estão relacionados a vinhos de menor qualidade. Outras variáveis, como sulfatos (0.25) e ácido cítrico (0.23), também mostram correlação positiva, ainda que moderada. Em contrapartida, fatores como densidade, cloretos e os dióxidos de enxofre possuem correlações fracas ou próximas de zero com a qualidade, indicando menor influência direta sobre essa variável. Esses resultados ajudam a identificar quais características químicas têm maior impacto na avaliação final dos vinhos.

## 🔀 Modelo de Classificação

* ### Modelo DummyClassifier

![métrica dummy](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/metricas_dummy.png)

O modelo apresenta acurácia e precisão de 53,54%, indicando que pouco mais da metade das previsões positivas são corretas. O recall de 100% mostra que ele identifica todos os casos positivos, sem deixar nenhum passar. Com um F1-score de 69,74%, há um bom equilíbrio entre precisão e recall, mas o fato de detectar todos os positivos pode indicar que o modelo está superajustado (overfitting), ou seja, ele pode estar memorizando os exemplos positivos do treino e gerando muitos falsos positivos. É importante avaliar e ajustar o modelo para evitar esse comportamento.

![matriz de confusão dummy](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/matriz_confusao_dummy.png)

* ### Modelo Árvore de Decisão

![métrica arvore](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/metricas_arvore.png)

O modelo apresenta uma acurácia de 69,38%, indicando que quase sete em cada dez previsões estão corretas. A precisão é alta, 81,25%, mostrando que a maioria das classificações positivas é correta. Porém, o recall está em 55,64%, indicando que o modelo identifica pouco mais da metade dos casos positivos reais. Com um F1-score de 66,05%, há um equilíbrio moderado entre precisão e recall. Esse comportamento sugere que o modelo é conservador ao prever positivos, priorizando evitar falsos positivos, mas perdendo vários positivos reais.

![matriz de confusão arvore](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/matriz_confusao_arvore.png)

* ### Modelo KNN

![métrica knn](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/metricas_knn.png)

O modelo apresenta uma acurácia de 72,50%, indicando que quase três quartos das previsões estão corretas. A precisão e o recall estão equilibrados, com 74,13% e 74,71%, respectivamente, mostrando que o modelo consegue identificar bem os positivos e tem uma taxa razoável de acertos nas previsões positivas. O F1-score, que representa esse equilíbrio, está em 74,42%. Esses resultados indicam um desempenho consistente e superior tanto à baseline quanto ao modelo de árvore, demonstrando que o modelo atual é mais eficaz na tarefa de classificação.

![matriz de confusão knn](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/matriza_confusao_knn.png)

* ### Modelo Random Forest

![métrica random forest](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/metricas_random_forest.png)

O modelo KNN apresentou uma acurácia de 76,88%, indicando que quase 77% das previsões foram corretas. A precisão de 78,08% mostra que a maioria das classificações positivas feitas pelo modelo é correta. O recall, em 78,99%, indica que o modelo identifica a maior parte dos casos positivos reais. Com um F1-score de 78,53%, o modelo demonstra um bom equilíbrio entre precisão e recall, refletindo um desempenho consistente.
Esse foi o melhor modelo entre os testados, apresentando resultados superiores às outras abordagens. Portanto, o KNN foi escolhido para prever a classificação dos vinhos, garantindo maior confiabilidade e eficiência na tarefa de classificação.

![matriz de confusão random forest](https://github.com/joaorodriguessneto/red_wine_quality/blob/main/img_readme/matriz_confusao_random_forest.png)


## 📊 Resultados Relevantes

  * A variável alcohol apresentou a maior correlação positiva com a qualidade (0.48)
  * A acidez volátil mostrou correlação negativa (-0.39)
  * O modelo Random Forest alcançou a maior acurácia: 76,87%, superando os modelos anteriores
  * As variáveis mais relevantes na previsão foram: alcohol, volatile acidity, sulphates, citric acid

## 📋 Respostas ao CEO

  * Álcool | Sulfatos | Ácido Cítrico*
  * O teor alcoólico é a variável mais fortemente relacionada à qualidade positiva.
  *    *A Acidez Volátil refere-se principalmente ao ácido acético (o mesmo do vinagre) e outros compostos voláteis que podem evaporar facilmente. Ela é um indicador de deterioração microbiana ou fermentação descontrolada.
        Um nível elevado de acidez volátil dá ao vinho aromas e sabores avinagrados ou agressivos, o que é considerado defeito sensorial.
       
        *Já a Acidez Fixa, é um conjunto de ácidos não voláteis presentes naturalmente nas uvas ou formados na fermentação, como o ácido tartárico, málico e cítrico.
        Ela contribui para a frescura, vivacidade e estrutura do vinho. Mas, em excesso, pode deixar o vinho agressivo ou “duro”

 * Com base nas características fornecidas pelo CEO referentes à nova amostra de vinho incluindo parâmetros físico-químicos como: teor alcoólico, acidez, sulfatos, dióxido de enxofre e etc. O modelo de classificação Random Forest previu que o vinho será classificado como bom. Isso indica que, segundo o modelo, a amostra possui atributos compatíveis com vinhos que obtêm uma nota superior a 5.0 na escala de qualidade, sinalizando uma avaliação sensorial positiva.



## ✔️ Conclusão

A partir da análise exploratória dos dados e da implementação de algoritmos de machine learning, foi possível evidenciar a correlação significativa entre variáveis físico-químicas e a avaliação da qualidade dos vinhos tintos. O modelo Random Forest apresentou superioridade em métricas de desempenho, demonstrando alta capacidade preditiva e robustez frente aos dados, sendo indicado como ferramenta para otimização do processo de seleção de lotes com potencial comercial elevado.
Este estudo exemplifica a aplicação avançada de técnicas de ciência de dados e aprendizado de máquina no domínio enológico, possibilitando a tomada de decisão baseada em evidências quantitativas e promovendo a melhoria contínua na qualidade e competitividade dos produtos.
