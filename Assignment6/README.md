El objetivo de esta tarea implementar un clasificador de dígitos manuscritos. Se utilizará la base de datos
Optical Recognition of Handwritten Digits Data Set, que es una base de datos tomadas del UC Irvine
Machine Learning Repository. 

Contiene 64 características que corresponden a la cantidad de píxeles
marcados en negro en regiones de 4x4 de la imagen, sin traslape. Hay 10 clases, las cuales
corresponden al dígito “0” hasta el dígito “9”. 

Para más información revise la página del repositorio:
http://archive.ics.uci.edu/ml/datasets/Optical+Recognition+of+Handwritten+Digits

Se pide:

1) Marco teórico
    1. Defina brevemente en qué consiste una capa convolucional
    1. Defina brevemente en qué consiste max-pooling
    1. Defina brevemente en qué consiste dropout
2) Descargue el código desde la dirección web indicada. Ejecute un primer entrenamiento para
asegurarse de que el sistema funcione
3) Describa la arquitectura de la red usada como base
4) El código usado como base sólo considera conjuntos de entrenamiento y prueba. Modifíquelo de
modo que, a partir del conjunto de entrenamiento original, se puedan obtener nuevos conjuntos de
entrenamiento y validación. Se recomienda que la validación contenga un 25% de los datos
originales de entrenamiento.
5) Implemente un código que permita imprimir los accuracies y losses en los conjuntos de
entrenamiento, validación y prueba, una vez que el sistema ha sido entrenado.
6) Implemente un código que permita calcular e imprimir el tiempo de entrenamiento
7) Implemente un código que permita graficar el accuracy y loss obtenidos durante el entrenamiento.
Puede hacer este gráfico después de que el entrenamiento ha sido realizado.
8) Realizar las siguientes pruebas y reportar accuracies y losses para cada una sobre los conjuntos de
entrenamiento y validación:
    1. Arquitectura 1: usando red original:
i. Entrenar con 2 épocas (no es necesario graficar)
ii. Entrenar con 6 épocas (no es necesario graficar)
iii. Entrenar con 12 épocas, graficar accuracy y loss para ambos conjuntos
    1. Arquitectura 2: red sin la segunda capa convolucional:
i. Entrenar con 2 épocas (no es necesario graficar)
ii. Entrenar con 6 épocas (no es necesario graficar)
iii. Entrenar con 12 épocas, graficar accuracy y loss para ambos conjuntos
    1. Arquitectura 3: red sin dropout
i. Entrenar con 2 épocas (no es necesario graficar)
ii. Entrenar con 6 épocas (no es necesario graficar)
iii. Entrenar con 12 épocas, graficar accuracy y loss para ambos conjuntos
9) Para cada una de las tres arquitecturas, indique el número de épocas que obtuvo mejor desempeño
según el accuracy del conjunto de validación
10) Compare las tres arquitecturas de red (cada una con el número de épocas con el mejor desempeño),
según el accuracy del conjunto de prueba
11) Analice la velocidad de entrenamiento obtenida por las tres arquitecturas de red (usando 12 épocas)
12) A partir de los gráficos obtenidos para la red original y la red con una capa convolucional menos
(usando 12 épocas), indique cuál es el efecto que genera sacar una capa convolucional.
13) A partir de los gráficos obtenidos para la red original y la red sin dropout (usando 12 épocas), indique
cuál es el efecto que genera el uso de dropout.
14) Genere un código que permita graficar los pesos (máscaras) de la primera capa convolucional. Si
usa algún código como base para este punto en particular, referéncielo.
15) Modifique el tamaño de las máscaras de la primera capa para que tengan tamaño 7x7. Grafique los
pesos antes de entrenar y después de entrenar, usando 12 épocas.
