# **UNIDAD_3.1**


### **ALGORITMOS DE BÚSQUEDA**

#### ***TEMAS:***

1.**PROBLEMAS DE BÚSQUEDA**  
Un problema de búsqueda es una formulación matemática que define un estado inicial, un conjunto de acciones posibles, un modelo de transición, una prueba de meta y un costo de camino, con el objetivo de encontrar una secuencia de acciones que lleve de un estado inicial a un estado meta.

2.**ESPACIOS DE ESTADOS**  
Es el conjunto de todos los estados alcanzables desde el estado inicial aplicando cualquier secuencia de acciones válidas.

3.**ESTADO INICIAL**  
Es el estado desde el cual el agente comienza a resolver el problema de búsqueda.

4.**ACCIONES**  
Son las operaciones o movimientos disponibles que el agente puede ejecutar en un estado determinado.

5.**MODELO DE TRANSICIÓN**  
Es la función que describe el resultado de aplicar una acción en un estado específico, devolviendo el estado sucesor.

6.**PRUEBA DE META**  
Es la función que determina si un estado dado es un estado objetivo o meta.

7.**COSTO DEL CAMINO**  
Es el valor numérico acumulado que representa el costo de la secuencia de acciones que llevan a un estado determinado.

8.**SOLUCIÓN**  
Es una secuencia de acciones que parte del estado inicial y llega a un estado meta.

9.**FRONTERA**  
Es el conjunto de nodos que han sido generados pero aún no han sido expandidos durante el proceso de búsqueda.

10.**NODO**  
Es una estructura de datos que contiene un estado, el camino desde el estado inicial hasta él, y el costo acumulado del camino.

11.**AGENTE DE RESOLUCIÓN DE PROBLEMAS**  
Es un agente inteligente que formula un objetivo y busca la secuencia de acciones necesaria para alcanzarlo.

---

### **SISTEMAS DE BÚSQUEDA (CIEGA)**

**BÚSQUEDA NO INFORMADA (CIEGA)**  
Es una estrategia de búsqueda que no utiliza conocimiento adicional sobre el problema más allá de su definición formal, sin estimaciones sobre qué tan cerca está un estado de la meta.

**BÚSQUEDA EN AMPLITUD**  
Es una estrategia que explora todos los nodos de un nivel antes de pasar al siguiente nivel, implementándose con una cola FIFO.

**BÚSQUEDA EN PROFUNDIDAD**  
Es una estrategia que explora una rama hasta el final antes de retroceder, implementándose con una pila LIFO.

**BÚSQUEDA DE COSTO UNIFORME**  
Es una estrategia que expande el nodo con el menor costo acumulado desde el inicio, utilizando una cola de prioridad ordenada por el costo del camino.

**COLA**  
Estructura de datos FIFO (First In, First Out) donde el primer elemento en entrar es el primero en salir, usada en búsqueda en amplitud.

**PILA**  
Estructura de datos LIFO (Last In, First Out) donde el último elemento en entrar es el primero en salir, usada en búsqueda en profundidad.

**COMPLETITUD**  
Propiedad que indica si un algoritmo de búsqueda garantiza encontrar una solución cuando esta existe.

**OPTIMALIDAD**  
Propiedad que indica si un algoritmo de búsqueda garantiza encontrar la solución de menor costo entre todas las posibles.

**COMPLEJIDAD EN TIEMPO**  
Medida del número de nodos generados o expandidos por un algoritmo durante el proceso de búsqueda.

**COMPLEJIDAD EN ESPACIO**  
Medida de la cantidad máxima de nodos que un algoritmo debe almacenar en memoria durante el proceso de búsqueda.

