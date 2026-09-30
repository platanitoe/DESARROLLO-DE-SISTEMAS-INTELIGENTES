# Tarea 1.3 — Preguntas contestadas

## Paso 3

¿Las clases están balanceadas? No. Hay 357 benignos (62.7%) y 212 malignos (37.3%). Los malignos son el **37.3%** del total.

## Paso 8

La primera pregunta usa puntos_concavos (≤ 0.049). Sí coincide con la gráfica del Paso 4: los malignos tienden a tener más puntos cóncavos. No usó las 10 medidas, solo las más útiles: puntos_concavos, dimension_fractal y area.

## Paso 10

Exactitud del modelo: 93.0%. Un modelo que dijera "benigno" a todos tendría ~62.7%. Sí, el nuestro es mucho mejor.

## Paso 10 (discusión)

El error más grave es el **falso negativo**. Mandar a casa a alguien con cáncer es mucho peor que asustar a alguien sano con pruebas extra. En medicina, mejor pecar de precavido.

## Actividad 1 — T, P, E

- **T:** clasificar tumores como benignos o malignos con 10 medidas.
    
- **P:** qué tan seguido acierta en pacientes nuevos y cuántos malignos se le escapan.
    
- **E:** 569 casos ya diagnosticados por especialistas.
    

## Actividad 2 — Supervisado

La línea `modelo.fit(X_entrena, y_entrena)` es la clave. Le pasamos las medidas **y** las respuestas correctas, así el modelo aprende la relación entre ambas.

## Actividad 3 — Una regla

Si puntos_concavos ≤ 0.049, y dimension_fractal ≤ 0.055, y puntos_concavos ≤ 0.023 → **benigno**.

## Actividad 4 — Los errores

Exactitud 93.0%. Falsos positivos: 6. Falsos negativos: 6.  
No lo usaría tal cual en el hospital. Los 6 falsos negativos significan 6 pacientes con cáncer sin detectar. Sirve como apoyo, pero el médico siempre debe revisar.

## Actividad 5 — Cambiar random_state

Sí cambia la exactitud, poquito. Pasa porque random_state decide cómo se reparten los pacientes entre entrenamiento y prueba. Con otra semilla, toca otros casos y los números cambian.

## Actividad 6 — Profundidad

Elegiría **3**. Es la que mejor acierta en prueba (0.930). Las más profundas memorizan los datos de entrenamiento (100% ahí) pero empeoran con pacientes nuevos. Eso es sobreajuste.


# Tarea 1.4 — Preguntas contestadas

## Paso 3

El rango de prolina va de 278 a 1680 (rango 1402). El rango de tono va de 0.48 a 1.71 (rango 1.23). La prolina es **~1140 veces más grande**. Por eso hay que escalar.

## Paso 4

A simple vista se ven **2 o 3 grupos**. El más claro está arriba a la derecha (alta intensidad de color y flavonoides) y otro abajo a la izquierda. Diría 2 grupos claros, quizá 3.

## Paso 6

El codo está en **k = 3**, y la silueta más alta también se da con **k = 3**. Coincide parcialmente con lo que vi en el Paso 4 (yo veía 2, pero el análisis con las 13 medidas sugiere 3).

## Paso 9 — Describir los grupos

- **Grupo 0:** vinos con bajo alcohol, valores promedio en casi todo. **Nombre:** "Clásicos equilibrados".
    
- **Grupo 1:** color muy intenso, tono bajo, mucho ácido málico. **Nombre:** "Intensos y oscuros".
    
- **Grupo 2:** mucho alcohol, prolina, fenoles y flavonoides. **Nombre:** "Robustos y concentrados".
    

## Paso 10

El algoritmo nunca vio la variedad y aun así **172 de 178 vinos (96.6%)** quedaron agrupados con los de su misma variedad. Eso confirma que **la química del vino está muy relacionada con la variedad de uva**. Sin las etiquetas, el algoritmo redescubrió la estructura real.

## Actividad 1 — T, P, E

- **T:** agrupar 178 vinos por similitud química.
    
- **P:** difícil de medir, no hay respuesta correcta. Se usan inercia y silueta, más la interpretación humana.
    
- **E:** 178 análisis químicos, **sin etiquetas**.  
    Es más difícil que en el Ejercicio 1 porque allá había una respuesta correcta con la que comparar; aquí no.
    

## Actividad 2 — Supervisado vs. no supervisado

- Ejercicio 1: modelo.fit(X_entrena, y_entrena) → usa medidas **y** etiquetas.
    
- Ejercicio 2: modelo.fit(X_escalado) → usa **solo medidas**.  
    Esa es toda la diferencia.
    

## Actividad 3 — Elegir k

El codo y la silueta apuntan a **k = 3**. Mi estimación a simple vista fue 2 o 3, así que coincidió bastante bien.

## Actividad 4 — Interpretación

(Copiar lo del Paso 9)

- Grupo 0 → "Clásicos equilibrados"
    
- Grupo 1 → "Intensos y oscuros"
    
- Grupo 2 → "Robustos y concentrados"
    

## Actividad 5 — Experimentar con k

- **Con k = 2:** los grupos son más grandes y generales. Probablemente los grupos 0 y 2 se junten, y el 1 quede solo (es el más distinto).
    
- **Con k = 4:** los grupos se dividen más. El grupo 2 probablemente se parte en dos, uno con vinos más extremos. Se separan mejor las variedades.
    

## Actividad 6 — Reflexión sobre escalar

Imagina agrupar personas por **edad** (0–100) y **glucosa** (0–5 g/L). Una diferencia de 20 años parece enorme comparada con 2 g/L de glucosa. K-means le daría más peso a la edad solo porque sus números son más grandes. Al **escalar** ambas a la misma escala, las dos pesan igual y el agrupamiento tiene sentido. Eso mismo pasó con la prolina y el tono.