El objetivo de esta tarea implementar un clasificador de dígitos manuscritos. Se utilizará la base de datos
Optical Recognition of Handwritten Digits Data Set, que es una base de datos tomadas del UC Irvine
Machine Learning Repository. Contiene 64 características que corresponden a la cantidad de píxeles
marcados en negro en regiones de 4x4 de la imagen, sin traslape.

Hay 10 clases, las cuales
corresponden al dígito “0” hasta el dígito “9”. Para más información revise la página del repositorio:
http://archive.ics.uci.edu/ml/datasets/Optical+Recognition+of+Handwritten+Digits


Se pide:
1) Teoría:
    1. Defina lo que es una Red Neuronal Artificial, junto con todas sus componentes básicas (neurona,
capa de entrada, capa oculta, capa de salida, pesos, bias, función de activación).
    1. Defina lo que es un minibatch y de qué modo se usa al entrenar la red
    1. ¿Cuál es el número sugerido (heurístico) de neuronas de la capa oculta para una red feedforward de 1 capa oculta?
    1. Explique lo que es el sobreajuste (overfitting) y cómo se previene.
    1. Defina lo que es el accuracy.
    1. Defina la Matriz de Confusión, cómo calcularla, cómo normalizarla y cómo interpretarla.
    1. Defina en qué consiste one hot encoding, y cómo se puede usar en Redes Neuronales
Artificiales.
2) En esta tarea se usarán tres conjuntos de datos: entrenamiento, validación y prueba. El conjunto de
validación se usará con dos finalidades: para evaluar si se produce sobreajuste en la red y para
determinar cuál es la mejor arquitectura. Los archivos de entrenamiento+validación (optdigits.tra) y el
de prueba (optdigits.tes) se entregan por separado.
3) El código base entregado procesa el archivo optdigits.tra, separándolo en entrenamiento y
validación, luego y entrena una red con una capa oculta, imprimiendo el accuracy, calculado sobre el
conjunto de validación, cada 100 iteraciones.
4) Clasificador Multiclase
    1. Modifique el código base para poder medir el tiempo de entrenamiento
    1. Modifique el código base para poder generar un gráfico que muestre la evolución del accuracy
calculado sobre el conjunto de validación a medida que la red se entrena (se puede graficar
después del entrenamiento, almacenando los datos intermedios en un arreglo).
    1. Entrene una red neuronal, ejecutando el código base entregado, el cual considera una función de
activación sigmoidal.
    1. Analice si se produjo sobreajuste a partir del gráfico del accuracy del conjunto de validación.
5) Número de neuronas y función de activación
    1.  Repita el punto 4c) y 4d) variando la cantidad de neuronas en la capa oculta (3 valores distintos
en total), usando función de activación sigmoidal.
    1. Repita el punto 4c) y 4d) variando la cantidad de neuronas en la capa oculta (3 valores distintos
en total), usando función de activación ReLU
6) Pruebas
    1. Modifique el código base para poder leer el conjunto de prueba (archivo optdigits.tes) y aplicarle
one-hot encoding (esto ya se hace para el conjunto de entrenamiento usando LabelBinarizer).
    1. Modifique el código base de modo que pueda calcular la matriz de confusión y el accuracy de
una red ya entrenada sobre el conjunto de prueba.
    1. Evalué la mejor arquitectura obtenida en punto 5) sobre el conjunto de prueba, calculando la
matriz de confusión y el accuracy. Debido a la variabilidad causada por la elección de los pesos
iniciales, entrene la red tres veces (modificando la variable random_state) y calcule la media y
desviación estándar tanto de la matriz de confusión como del accuracy.
7) Análisis
    1. Compare y concluya sobre los resultados obtenidos. Explique los efectos de variar la cantidad de
neuronas en la capa oculta y como esto se ve reflejado en el desempeño de la red. Comente
sobre: tiempo de entrenamiento, capacidad de aprendizaje de la red, sobreajuste y cantidad de
muestras necesarias. Analice el desempeño relativo (compare) al considerar funciones de
activación sigmoidal y ReLU, considerando la velocidad de convergencia y el accuracy obtenido.
Analice la diferencia de accuracy obtenida en el conjunto de validación versus el de prueba.
