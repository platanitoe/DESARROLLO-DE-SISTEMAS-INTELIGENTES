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

#### **ACTIVIDAD DE CLASE  TAREA_3.1**



![[Captura de pantalla 2026-10-08 181017.png|366]]![[Captura de pantalla 2026-10-08 182003.png|366]]
![[Captura de pantalla 2026-10-08 182431.png|368]]
![[Captura de pantalla 2026-10-08 182619.png|370]]

## Imagen 1 

**Observación**: El camino amarillo es muy irregular y en zigzag, baja por la parte inferior izquierda y rodea varios obstáculos antes de llegar a la meta. Esto ocurre porque Best-First-Search solo usa la heurística h(n) (sin costo acumulado g(n)), por lo que no garantiza optimalidad y toma decisiones "miopes" que producen rutas largas y torcidas.

---

## Imagen 2 

**Observación**: La búsqueda se lanza desde ambos extremos (inicio y meta) al mismo tiempo (bi-directional), y las dos fronteras se encuentran. El camino resultante es mucho más directo y limpio que en la imagen 1, atravesando la parte central. Sin embargo, sigue siendo una ruta no óptima garantizada, solo "buena" según la heurística.

---

## Imagen 3 


**Observación**: El camino es más ordenado y eficiente que en Best-First-Search. A* expande menos nodos (más celestes concentrados alrededor del camino) porque equilibra el costo real recorrido con la estimación hacia la meta. Aun así, el uso de Manhattan con diagonales no es ideal (debería usarse Octile), por lo que el camino no es perfectamente óptimo.

---

## Imagen 4 

**Observación**: Mapa más pequeño y simétrico. El camino amarillo rodea elegantemente el obstáculo central en forma de cruz. Se nota la expansión bidireccional: la frontera verde claro se extiende desde ambos lados hasta encontrarse. El resultado es visualmente limpio, pero Best-First-Search no garantiza optimalidad; simplemente encuentra una solución razonable rápido.

---

14/10/2026
## EL PROBLEMA DE LA BÚSQUEDA CIEGA

> [!info] Descripción
> La búsqueda ciega explora el espacio de estados **sin usar información** sobre qué tan cerca está de la meta. Prueba caminos uno por uno (como BFS o DFS), pero no sabe si va bien o mal. Por eso puede perder mucho tiempo explorando zonas inútiles.

---

### ¿QUÉ ES UNA HEURÍSTICA?

> [!info] Descripción
> Una heurística es una **"pista" o estimación** que ayuda a decidir qué camino parece más prometedor. No garantiza la solución óptima por sí sola, pero guía la búsqueda hacia la meta de forma más inteligente y rápida.

---

### **LA PISTA: DISTANCIA DE MANHATTAN**

> [!note] Descripción
> Es una forma de medir cuánto falta para llegar a la meta en una cuadrícula, contando **solo movimientos horizontales y verticales** (sin diagonales). Es como calcular la distancia caminando por las calles de una ciudad cuadriculada.

---

### **TRES NÚMEROS PARA CADA CASILLA**

> [!abstract] Descripción
> Cada casilla del tablero guarda **tres valores** que resumen su situación en la búsqueda:
> - **g:** lo que ya costó llegar hasta aquí.
> - **h:** lo que se estima que falta para la meta.
> - **f = g + h:** el costo total estimado del camino que pasa por esta casilla.

---

### g:

> [!example] Descripción
> **Costo real acumulado** desde el inicio hasta la casilla actual. Es un dato objetivo, no una estimación.

### h:

> [!example] Descripción
> **Heurística:** estimación del costo que falta desde esta casilla hasta la meta. Es subjetiva (depende de la heurística elegida).

### f = g + h:

> [!example] Descripción
> **Costo total estimado** si se pasa por esta casilla. Es el número que usa el algoritmo **A\*** para decidir qué casilla explorar primero: siempre elige la de menor **f**.


## **ACTIVIDAD_3.2**

. COMPARA EN LA PAGINA DOS ALGORITMOS (A*) Y UN CIEGO. CONTESTAR LAS SIGUIENTES PREGUNTAS

---

## ¿Qué longitud tiene cada algoritmo?

> [!question] Respuesta
> Los tres algoritmos encuentran **exactamente la misma longitud**, porque todos garantizan el camino más corto en una cuadrícula sin pesos.
>
> - **A\***: longitud óptima
> - **BFS**: longitud óptima
> - **Dijkstra**: longitud óptima
>
> La longitud **no es la diferencia clave** entre ellos. La diferencia está en **cómo llegan** a esa longitud.

---

## ¿Cuánto tiempo tardó cada algoritmo?

> [!question] Respuesta
> Aquí sí hay diferencias notables:
>
> - **A\***: el **más rápido**. La heurística Manhattan lo guía directo hacia la meta.
> - **BFS**: **tiempo intermedio**. Explora por capas, como una onda desde el inicio.
> - **Dijkstra**: el **más lento**. Sin pista, explora casi todo el mapa antes de encontrar la meta.
>
> El tiempo depende también de **cuántos obstáculos** haya y de **qué tan lejos** esté la meta.

---

## ¿Qué diferencia observas?

## ¿Qué diferencia observas?

> [!abstract] Respuesta
> La diferencia fundamental es **el uso o no de una heurística**.
>
> **A\*** sí usa heurística (distancia de Manhattan), por eso garantiza el camino óptimo visitando **pocos nodos** y con **velocidad alta**. Su exploración está **dirigida hacia la meta**.
>
> **BFS** no usa heurística, pero sí garantiza el camino óptimo. Visita **muchos nodos** y su velocidad es **media**. Explora **por capas, como una onda** que se expande desde el inicio.
>
> **Dijkstra** tampoco usa heurística y también garantiza el camino óptimo. Es el que visita **más nodos** y tiene **velocidad baja**, porque explora **en todas las direcciones según el costo**.
