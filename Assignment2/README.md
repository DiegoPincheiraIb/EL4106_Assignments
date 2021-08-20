**ES:**

El objetivo de esta tarea es implementar un clasificador de pulsares.(un tipo de estrellas).
Se utilizará el set de datos **HTRU2 Data Set**, el cual forma parte del UC Irvine Machine Learning Repository:
- El set de datos a usar contiene **8 características**
obtenidas analizando señales de radiotelescopios. 
- El dataset contiene una novena columna, la que
indica la **clase** de cada muestra. 
- Las clases son **uno (pulsar)** y **cero (no-pulsar)**. Hay 1639 ejemplos
positivos y 16259 negativos. 

Se les pide **programar, entrenar y calibrar un clasificador bayesiano para determinar en forma probabilística si un candidato corresponde a un pulsar o no**. 

La regla de decisión del mencionado clasificador está dada por:

𝑃(𝑐𝑎𝑟𝑎𝑐𝑡𝑒𝑟í𝑠𝑡𝑖𝑐𝑎𝑠|𝑝𝑢𝑙𝑠𝑎𝑟)/𝑃(𝑐𝑎𝑟𝑎𝑐𝑡𝑒𝑟í𝑠𝑡𝑖𝑐𝑎𝑠|𝑛𝑜_𝑝𝑢𝑙𝑠𝑎𝑟)≥ Θ

El umbral Θ depende de los costos asociados a cada decisión (𝑐𝑛𝑜𝑝𝑢𝑙𝑠𝑎𝑟 y 𝑐𝑝𝑢𝑙𝑠𝑎𝑟) y de las probabilidades
a priori:

Θ =
cnopulsarP(pulsar)/
cpulsarP(no_pulsar)


En este caso concreto, las distribuciones de probabilidad de ambos conjuntos, las verosimilitudes, no se
tienen, por lo que deberán estimarlas de 2 maneras: 
- Calculando histogramas normalizados.
- Calculando un modelo gaussiano a partir de un conjunto de entrenamiento de cada clase.


La tarea se debe realizar usando Python. Si bien se puede usar la biblioteca pandas sólo para leer y
manejar los datos, **los clasificadores deben ser programados desde cero**. Es decir, **no se puede usar
scikit-learn, scipy, tensorflow o herramientas similares**. Si es posible usar las funciones en el paquete
numpy.
Se pide:
1) Base de Datos:
    1. Explique la función y posibles subconjuntos de los conjuntos de entrenamiento y prueba.
    2. Dividir la base de datos en 2 conjuntos representativos: entrenamiento (80%) y prueba (20%).
Compruebe la representatividad de éstos, verificando si la proporción de ambas clases se
mantiene cercana a la proporción del conjunto completo. Se recomienda hacer una permutación
al azar (shuffle) de los datos de cada clase antes de definir los conjuntos de entrenamiento y
prueba.
2) Modelo con histogramas:
    1. Explique la aproximación Naive Bayes y cuál es la suposición que se asume al utilizarla.
    2. Utilice Naive Bayes y encuentre los histogramas de cada clase a partir de las muestras del
conjunto de entrenamiento. Elija un número de bins (celdas) que le parezca apropiado a priori
(recuerde que la verosimilitud es una función de densidad de probabilidades, por lo que su
integral suma 1).
    3. Encontrar las verosimilitudes en ambas clases para cada muestra del conjunto de prueba,
usando los histogramas.
    4. Mover Θ: clasificar el conjunto de prueba y calcular la Tasa de Verdaderos Positivos y Tasa de
Falsos Positivos cada vez para luego generar la curva ROC (TVP vs TFP). Recuerde que Θ
puede tomar valores entre 0 e ∞, pero no todo el rango entrega información importante. Se
recomienda agregar el punto (TVP=0,TFP=0) a la curva ROC para poder visualizarla.
    5. Mover Θ: clasificar el conjunto de prueba y calcular las métricas precision y recall cada vez para
luego generar la curva precisión/recall. Recuerde que Θ puede tomar valores entre 0 e ∞, pero
no todo el rango entrega información importante. Se recomienda agregar el punto
(precisión=1,recall=0) para poder visualizarla.
    6. Analice el efecto de cambiar la cantidad de bins en los histogramas. ¿Tiene la cantidad óptima
de bins alguna relación con el número de muestras del conjunto de entrenamiento? Comente.
3) Modelo gaussiano:
    1. Investigue y encuentre la función de densidad de probabilidad de una gaussiana
multidimensional, explique las variables que la caracterizan.
    2. Entrenar un modelo gaussiano multidimensional para cada clase, encontrando la media y
covarianza, a partir del conjunto de entrenamiento. Puede basarse en las funciones np.mean( ) y
np.cov( ) de numpy.
    3. Encontrar las verosimilitudes en ambas clases para cada muestra del conjunto de prueba,
usando las gaussianas.
    4. Mover Θ, clasificar el conjunto de prueba y calcular la Tasa de Verdaderos Positivos y Tasa de
Falsos Positivos cada vez para luego generar la curva ROC (TVP vs TFP).
    5. Mover Θ, clasificar el conjunto de prueba y calcular las métricas precision y recall cada vez para
luego generar la curva precisión/recall.
4) Comparación:
    1. Compare ambas curvas ROC y comente ventajas y desventajas de ambos métodos.
    2. Compare ambas curvas precisión/recall y comente ventajas y desventajas de ambos métodos.
    3. Implemente una función llamada tarea1(entrenamiento,prueba) que reciba como parámetro una
matriz del conjunto de entrenamiento y otra del conjunto de prueba, que genere como salida un
gráfico de las curvas ROC y precisión/recall generadas con ambos modelos.
