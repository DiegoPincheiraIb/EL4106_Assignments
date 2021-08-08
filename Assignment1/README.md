**ES:**

El objetivo de esta tarea es analizar y visualizar datos usando las bibliotecas de software pandas, numpy
y matplotlib. Se utilizará el set de datos** HTRU2 Data Set**, el cual forma parte del UC Irvine Machine Learning Repository:
- El set de datos a usar contiene **8 características**
obtenidas analizando señales de radiotelescopios. 
- El dataset contiene una novena columna, la que
indica la **clase** de cada muestra. 
- Las clases son **uno (pulsar)** y **cero (no-pulsar)**. Hay 1639 ejemplos
positivos y 16259 negativos. 

Se pide realizar los siguientes pasos:
1. Teoría:
    1. Indique en qué consiste un histograma
    2. Explique la distribución gaussiana y sus parámetros
    3. Indicar en qué consiste el skewness
    4. Indicar en qué consiste la kurtosis
    5. Indicar la relación entre el skewness, la kurtosis y los tests de gaussianidad
    6. Indicar en qué consiste la matriz de correlación, cómo se calcula, y cómo se interpretan los
    valores negativos, cercanos a cero y positivos
    
2. Leer los datos; se debe utilizar la siguiente lista para las columnas: ['mean_prof','std_prof','exkurt_prof','skew_prof','mean_curve','std_curve','exkurt_curve','skew_curve','class']

3. Separar los datos en un subconjunto con los datos con clase positiva (pulsar) y otro con clase
negativa (no-pulsar)
4. Para cada característica, generar histogramas superpuestos para los datos de la clase negativa y de
la clase positiva. Para esto, se recomienda usar plt.hist() con alpha=0.8.
5. Calcular el skewness y kurtosis de los datos, tanto para los datos con clase positiva como para
aquellos con clase negativa, usando las funciones de pandas
6. A partir de los histogramas, skewness y kurtosis, analizar el nivel de gaussianidad de cada
característica, tanto para los datos de clase positiva como para los de clase negativa.
7. Programar una función que, dados datos de entrada, calcule la matriz de correlación.
8. Calcular la matriz de correlación de los datos (incluyendo la clase), usando tanto la función
programada anteriormente como la función de correlación existente en pandas. Verificar que los
resultados de ambos cálculos sean similares.
9. Indicar por orden cuáles son las características más correlacionadas con la clase
10. Indicar por orden cuáles son los 5 pares de características distintas más correlacionadas entre sí.
11. Graficar las dos características más correlacionadas en un scatter plot
12. Indicar por orden cuáles son los 5 pares de características distintas menos correlacionadas entre sí.
13. Graficar las dos características menos correlacionadas en un scatter plot
