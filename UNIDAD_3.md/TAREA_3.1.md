
![[DSI.jpg]]

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

### **PREGUNTAS**

¿Cuántas casillas exploró **amplitud**? ¿Y **profundidad**?  
Amplitud exploró 81 casillas y profundidad exploró 31 casillas.

¿Cuántos **pasos** tiene el camino de amplitud? ¿Y el de profundidad? ¿Cuál es el más corto?  
El camino de amplitud tiene 2 pasos y el de profundidad tiene 10 pasos. El más corto es el de amplitud.

En una frase: ¿por qué el camino de amplitud nunca es más largo que el de profundidad?  
Porque amplitud explora por niveles (primero todo lo que está a 1 paso, luego a 2, etc.), así que la primera vez que llega a la meta lo hace por el camino más corto posible.

Con el orden nuevo, ¿cuántos **pasos** tiene el camino de amplitud? ¿Y el de profundidad? ¿Cuál de los dos algoritmos cambió mucho su resultado y por qué crees que pasó?  
Con el orden nuevo, amplitud sigue con 2 pasos, pero profundidad baja a 4 pasos. El que cambió mucho fue profundidad, porque su resultado depende directamente del orden en que prueba las acciones: al cambiar el orden, explora primero hacia la meta.

En el laberinto 2, ¿cuántas casillas exploró amplitud y cuántas profundidad? ¿Cuántos pasos tiene el camino de cada una?  
En el laberinto 2, amplitud exploró 54 casillas con un camino de 15 pasos, y profundidad exploró 35 casillas con un camino de 19 pasos.

Con los resultados de los dos laberintos: ¿se puede decir que profundidad siempre explora menos casillas que amplitud, o que siempre explora más? Explica con tus datos.  
No se puede afirmar que profundidad siempre explore menos o más. En el laberinto 1 exploró menos (31 vs 81), pero en el laberinto 2 también exploró menos (35 vs 54). Sin embargo, en el laberinto 1 su camino fue mucho más largo (10 vs 2 pasos). Depende del mapa y del orden de acciones.

¿Cuántos **pasos** y cuánto **costo** tiene el camino de amplitud? ¿Y el de costo uniforme?  
Amplitud: 4 pasos, costo 12. Costo uniforme: 6 pasos, costo 8.

Amplitud encontró el camino con menos pasos, pero no el más barato. ¿Por qué? ¿Cuándo preferirías costo uniforme?  
Amplitud no considera el costo de cada casilla, solo cuenta pasos, por eso elige la ruta corta pero con lodo (costo alto). Preferiría costo uniforme cuando el costo de moverse importa (tráfico, terreno difícil, gasolina, tiempo real, etc.).

¿Cuántas combinaciones probó la búsqueda? ¿Cuántos modelos entrenó en total? ¿Cuál fue la mejor combinación y su exactitud?  
Combinaciones probadas: 48. Modelos entrenados: 48 × 5 = 240. Mejor combinación: criterion="gini", max_depth=3, min_samples_leaf=1. Mejor exactitud: aproximadamente 0.916.

Con 5 hiperparámetros y 10 valores cada uno, ¿cuántas combinaciones hay y cuánto tiempo estimado tardaría? Después prueba con 3 hiperparámetros: ¿cuánto tarda?  
Con 5 hiperparámetros y 10 valores: 100,000 combinaciones y el tiempo estimado suele ser de miles de horas (depende del equipo). Con 3 hiperparámetros y 10 valores: 1,000 combinaciones, mucho más rápido (minutos u horas).

Grid search es una búsqueda ciega. Con lo que viste en esta actividad, ¿cuál es su ventaja y cuál su problema?  
Ventaja: es exhaustivo y seguro, siempre encuentra la mejor combinación dentro de la rejilla. Problema: es muy caro, porque el número de combinaciones crece exponencialmente con cada hiperparámetro nuevo.