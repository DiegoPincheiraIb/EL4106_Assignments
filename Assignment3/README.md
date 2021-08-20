**ES:**

El objetivo de esta tarea es analizar y visualizar datos usando las bibliotecas de software pandas, numpy
y matplotlib. Se utilizará el set de datos **HTRU2 Data Set**, el cual forma parte del UC Irvine Machine Learning Repository:
- El set de datos a usar contiene **8 características**
obtenidas analizando señales de radiotelescopios. 
- El dataset contiene una novena columna, la que
indica la **clase** de cada muestra. 
- Las clases son **uno (pulsar)** y **cero (no-pulsar)**. Hay 1639 ejemplos
positivos y 16259 negativos. 

Se pide utilizar la metodología de clasificación estadística SVM para entrenar y validar un clasificador de
pulsares. El trabajo a ser realizado incluye analizar detalladamente el efecto en el rendimiento del
clasificador mediante la utilización de distintos tipos de kernels. En esta tarea tendrán que entrenar y
calibrar 4 clasificadores SVM binarios, que utilicen distintos tipos de Kernels/grados en caso polinomial.

Se pide:
1) Teoría:
    1. Explique de manera genérica el funcionamiento de los clasificadores SVM.
    2. Indique en qué consisten los kernels lineal, polinomial y gaussiano
    3. ¿Cuál es el efecto de mover el parámetro C?
    4. Explique en qué consiste grid search y cross-validation
    5. Indique de qué modo el re-muestrear el dataset (oversampling, undersampling) puede ayudar en
casos en que el dataset está desbalanceado, o en casos en que hay demasiadas muestras.
    6. Indique qué tan apropiado es el uso de la curva ROC y de la curva precisión/recall cuando el
dataset está desbalanceado
2) Implementar un código que lea el dataset. Se recomienda usar pandas.
3) Re-muestrear los datos de la clase negativa, de modo que contenga 1639 muestras (la misma
cantidad de muestras que la clase positiva).
4) Dividir la base de datos en 3 conjuntos representativos: entrenamiento (60%), validación (20%) y
prueba (20%). Compruebe la representatividad de éstos, verificando si la proporción de cada clase
se mantiene cercana a la proporción del conjunto completo.
5) Entrenar un clasificador SVM lineal que permita discriminar pulsares de no-pulsares. Para obtener un
buen clasificador, se debe usar una grilla para buscar los mejores hiper parámetros para el
clasificador. Se recomienda usar la función GridSearchCV( ) con 5 folds, considerando distintos
valores del parámetro C (5 valores distintos). El clasificador base SVM a usar se puede construir así:
svm.SVC(kernel=’linear’, probability=False)
6) Evaluar sobre el conjunto de validación y generar la matriz de confusión. Se recomienda usar
metrics.confusión_matrix( )
7) Generar una curva ROC que muestre el desempeño del clasificador y calcular el área bajo la curva.
Se recomienda usar las funciones decision_function( ), metrics.roc_curve( ) y metrics.auc( )
8) Generar una curva precisión-recall y calcular el average precision. Se recomienda usar las funciones
decision_function( ), metrics.precision_recall_curve( ) y metrics.average_precision_score( )
9) Repetir los pasos (5), (6), (7), (8) para SVM con kernel polinomial, usar dos grados distintos del
polinomial, y RBF (Radial Basis Function). En este último caso usar una grilla de búsqueda que
contenga 5 valores del parámetro C y 4 valores del parámetro sigma.
10) Evaluar el mejor clasificador obtenido sobre el conjunto de prueba, reportando las métricas indicadas
en (6), (7) y (8).
