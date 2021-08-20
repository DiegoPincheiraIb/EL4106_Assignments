El objetivo de esta tarea es utilizar distintos algoritmos de clustering y analizar su desempeño. Se
utilizará la base de datos Mice Protein Expression Data Set, que es una base de datos tomadas del UC
Irvine Machine Learning Repository. Contiene niveles de expresión de 77 proteínas medidas en
fracciones nucleares de células en la corteza cerebral. Hay 38 ratones de control y 34 ratones trisómicos
(síndome de Down). Dado que algunos ratones fueron estimulados para aprender y/o inyectados con
memantina, hay 8 clases en total. 

La base de datos se puede bajar desde la siguiente dirección:
https://archive.ics.uci.edu/ml/datasets/Mice+Protein+Expression


Para poder realizar el trabajo, se usará el siguiente código base (basado en scikit-learn):
https://scikit-learn.org/stable/auto_examples/cluster/plot_kmeans_digits.html#sphx-glr-auto-examplescluster-plot-kmeans-digits-py

Se pide utilizar tres algoritmos de clustering en este trabajo: **k-means, DBSCAN y clustering
aglomerativo**.

1) Marco teórico:
    1. Explique en qué consiste el algoritmo k-means, y la inicialización kmeans++
    2. Explique en qué consiste el algoritmo DBSCAN
    3. Explique en qué consiste el algoritmo clustering aglomerativo
    4. Explique brevemente la métrica completeness
    5. Explique brevemente la métrica homogeneity
    6. Explique brevemente la métrica v-measure
    7. Explique la métrica silhouette
Implemente un código que lea la base de datos. Se recomienda usar la biblioteca Pandas. Se debe
eliminar la columna BCL2_N, dado que contiene muchos valores NaN. Asimismo, las filas que contienen
valores NaN deben ser eliminadas. Finalmente, para esta tarea, se recomienda no usar scale( ) sobre los
datos.
2) Modifique la función bench_k_means( ) agregando una columna extra, correspondiente al número de
clusters.
3) Implemente una nueva función bench_DBSCAN( ), tomando como base la función
bench_k_means( ) modificada en el punto anterior. Notar que:
    1. DBSCAN no posee la variable inertia_, esto debe ser manejado por el alumno.
    2. DBSCAN no asigna todas las muestras a un cluster, las muestras no asociadas tienen label
“-1”. Debido a esto, la función bench_DBSCAN( ) debe entregar la opción de: (i) calcular las
métricas sólo con los datos asociados, o (ii) calcular las métricas usando todos los datos,
asumiendo que los datos no asociados conforman un cluster extra. Dicha opción debe ser
implementada usando una variable extra (True/False) que se le entrega a la función.
    3. El algoritmo DBSCAN no genera una cantidad predeterminada de clusters.
    4. Dados algunos parámetros, es posible que DBSCAN no encuentre clusters, o bien encuentre
uno solo, lo cual imposibilita calcular las métricas. Decida una estrategia para manejar estos
casos. 
    5. La función bench_DBSCAN( ) puede ser usada para calcular las métricas tanto de DBSCAN
como de clustering aglomerativo.
4) Hacer pruebas con distintas variantes de algoritmos:
    1. K-Means (con inicialización al azar)
    2. K-means++
    3. DBSCAN con épsilon por defecto
    4. DBSCAN con épsilon 0.7
    5. DBSCAN con épsilon 0.2
    6. DBSCAN con épsilon por defecto, agregando outliers a cluster extra
    7. DBSCAN con épsilon 0.7, agregando outliers a cluster extra
    8. DBSCAN con épsilon 0.2, agregando outliers a cluster extra
    9. Clustering aglomerativo
    10. Repetir todas las pruebas anteriores, después de usar PCA sobre los datos para reducirlos a
2 dimensiones.
5) Analice los resultados obtenidos:
    1. Compare los algoritmos aplicados en base a las métricas indicadas en el marco teórico
(completeness, homogeneity, v-measure, silhouette), indicando: (i) cuál variante es mejor
según cada métrica y (ii) cuál variante es peor según cada métrica.
    2. Indique en cuáles casos no fue posible calcular las métricas de DBSCAN.
    3. Analice el número de clusters obtenidos por DBSCAN y su efecto sobre las métricas.
    4. Analice el efecto de considerar o no los outliers de DBSCAN como un cluster extra y su
efecto sobre las métricas.
