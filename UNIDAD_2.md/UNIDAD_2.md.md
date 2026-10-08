# ==**Act_2.1 Dos ejemplos de T, P y E==**

### Ejemplo 1: Detección de intrusos

- **T:** Detectar si una persona no autorizada entra a un lugar.
- **P:** Porcentaje de intrusos detectados correctamente.
- **E:** Videos o imágenes de cámaras de seguridad con ejemplos de entradas autorizadas y no autorizadas.

### Ejemplo 2: Detección de fraude

- **T:** Identificar si una transacción bancaria es fraudulenta.
- **P:** Porcentaje de fraudes detectados correctamente.
- **E:** Historial de transacciones bancarias clasificadas como normales o fraudulentas.

### Proyecto: Detección de URLs seguras

- **T:** Determinar si una URL es segura o maliciosa.
- **P:** Porcentaje de URLs clasificadas correctamente.
- **E:** Base de datos de URLs conocidas como seguras y maliciosas. (deteccion de tres comando de creaciones realizadas)

# ==**Act_2.2 Tres artefactos Machine Learning==**

**Supervisado**: Enseñar a una computadora utilizando datos que se sabe una respuesta o respuestas conocidad. Como estudiar un ejercicio que tiene la respuesta

En correos spam y los normales. El modelo recibe correros nuevos y trata de clasificarlos.

Es cuando la computadora aprende con ejemplos que ya tienen la respuesta y utiliza lo aprendido para resolver casos nuevos.

**Sin supervisar**: Los datos no tienen una respuesta o categoria indicada de esta. La computadora analizaa los datos y busca si misma caracteristicas similares

Es cuando la computadora recibe información sin categorías establecidas y busca por sí sola cuáles datos se parecen para formar grupos o descubrir patrones.


**Por refuerzo**: Una computadora aprende mediante pruebas y errores. Una accion con recompensa. Eso quiere decir que aprende con acciones que le ayudan 

Es cuando la computadora aprende experimentando, tomando decisiones y observando si obtiene una recompensa o una penalización por lo que hizo.


# ==**Act_2.3 Glosario (Todo con base de Machine Learning)==**


1. Pandas
Esta diseñado especificamente para la manipulacion y el analisis de datos en el penguaje Python. Permite cargar, limpiar, explorar y transformar datos tabulares antes de entrenar cualquier modelo

2. Matplotlib
Una biblioteca de Python diseñada para crear visualizaciones de datos de alta calidad y evolucionado para convertiirse en una de las herramienras comunidad de visualización más utilizadas en la comunidad científica y de datos.

3. Scikit-learn (Investigar que datos de prueba maneja)
Optimiza la inteligencia artificial y el modelado estadistico con ML y una interfaz coherente

-Conjuntos de datos pequeños (Toy Datasets)
-Conjuntos de datos del mundo rela (Real-world Datasets)
-Generadores de datos sinteticos

3. Google Colab
Es un laboratorio de programacion accesible para todo el mundo, directamente desde el navegador. 
En realidad, Colab es una versión en la nube de Jupyter Notebook integrada en el ecosistema de Google.

4. Arbol de decision
Es un algoritmo de aprendizaje automatico superviisado que predice resultados dividiendo los datos en partes mas pequeñas mediante preguntas de tipo si o no. En ML funciona con datos, analizan caracteristicaas para tomar decisiones y predecir resultados

5. Matriz de confusion
Es un metodo de visualizacion parra los resultados del algoritmmo clasificador.  Ayuda a evaluar el rendimiento del modelo de clasificación en el aprendizaje automático comparando los valores previstos con los valores reales de un conjunto de datos. 

Estas matrices se utilizan con frecuencia para evaluar los resultados predictivos en machine learning y ciencia de datos, ya sea para propósitos académicos o comerciales.


6. Sobreajuste
Es un error de Machine Learning que ocurre cuando un modelo aprende demasiado los datos de entrenamiento y memoriza detalles específicos o ruido en lugar de entender la regla general

------
Falso Positivo: Es un resultado que indica de forma erronea la presencia de una condiccion, enfermedad o evento que en realisdad no existe

Falso negativo: Es un resultado de una prueba o diagnostico que indica de forma equivocada la ausencia de una afeccion, enfermedad o estado cuando en realidad si esta presente

---
# ==**Act_2.4 Definiciones==**

|                               | DEFINICION                                                                   | COMO FUNCIONA                                                                                                                                  | CASO DE USO                                                                                                                                              |
| ----------------------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ARBOL DE DECISION             | Modelo jerárquico de preguntas que lleva a una predicción en las hojas.      | Divide los datos según la característica que mejor separa las clases (mayor ganancia de información); se recorre desde la raíz hasta una hoja. | Determinar si un cliente potencial comprará un producto en función de su historial de navegación y datos demográficos                                    |
| REGRESION LOGISTICA           | Clasificador que estima probabilidades usando una función sigmoidea (0 a 1). | Combina las variables linealmente y aplica la sigmoide; ajusta coeficientes maximizando la verosimilitud.                                      | Predecir si un estudiante abandonará o no sus estudios universitarios en función de sus necesidades de orientación académica                             |
| K VECINOS MAS CERCANOS (k-NN) | Clasifica según los k datos más cercanos; no construye modelo.               | Calcula distancias, encuentra los k vecinos y vota (clasificación) o promedia (regresión).                                                     | Recomendar puntos de interés (gasolineras, restaurantes, bancos) más cercanos al usuario en aplicaciones de navegación o sistemas de tráfico inteligente |
| NAIVE BAYES                   | Clasificador probabilístico basado en el teorema de Bayes.                   | Asume independencia entre variables y calcula P(clase\|X) multiplicando probabilidades; elige la mayor.                                        | Filtrar correos electrónicos no deseados (spam) clasificando cada mensaje como "spam" o "no spam" .                                                      |
| SVM                           | Busca el hiperplano que separa las clases con el mayor margen.               | Usa kernels para proyectar datos no separables a mayor dimensión y encontrar la separación óptima.                                             | Clasificación de textos e imágenes, incluyendo bioinformática y detección de objetos en imágenes                                                         |
| BOSQUE ALEATORIO              | Conjunto de árboles de decisión que votan la predicción final.               | Cada árbol se entrena con muestras y features aleatorios; al predecir votan o promedian.                                                       | Predecir si un atleta ganará una medalla olímpica analizando múltiples variables de rendimiento deportivo                                                |
| RED NEURONAL                  | Modelo de capas de neuronas artificiales interconectadas.                    | Propaga datos hacia adelante con funciones de activación y ajusta pesos con retropropagación.                                                  | Reconocimiento de voz en asistentes como Google Voice o Siri, y análisis de imágenes médicas para detección de tumores                                   |

----
# ==**Act_2.5 Arquitectura==**

Front
Bootstrop-Material Desing

Backend         Modelo 
Django           Machine Learning- Redes Neuronales

API
Django

BD
Posgresql

# Algortimos de Machine Learning

Arbol de desicion 




