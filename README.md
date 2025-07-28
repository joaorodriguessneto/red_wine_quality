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

Com base na análise exploratória e na aplicação de modelos de machine learning, foi possível demonstrar que certas características físico-químicas têm impacto direto na avaliação da qualidade dos vinhos tintos. O modelo de Random Forest se destacou como a solução mais eficaz, podendo ser utilizado para auxiliar a vinícola na seleção de lotes com maior potencial de sucesso comercial.
Este projeto reflete a aplicação prática da ciência de dados no setor enológico, promovendo decisões mais embasadas e estratégicas para o desenvolvimento de produtos de maior qualidade.
