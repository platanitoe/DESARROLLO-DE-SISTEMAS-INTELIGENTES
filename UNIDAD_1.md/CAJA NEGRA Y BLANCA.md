---
tags:
aliases:
  - White Box vs Black Box
  - Pruebas de caja
created: 2026-09-30
---

#  Pruebas de Caja Blanca y Caja Negra

> [!abstract] Idea clave
> Las pruebas de software se dividen según **si el tester conoce o no el código interno**.
> - **Caja blanca** → ves el código.
> - **Caja negra** → solo ves entradas y salidas.

---

##  Comparación general

| Aspecto         | Caja Blanca          | Caja Negra           |
| --------------- | -------------------- | -------------------- |
| ¿Ve el código?  | Sí                   | No                   |
| Base de pruebas | Estructura interna   | Entradas y salidas   |
| Quién la hace   | Desarrollador        | Tester / QA          |
| Nivel típico    | Unitario             | Sistema / aceptación |
| Mide            | Cobertura del código | Funcionalidad        |

---

## Caja Blanca

> [!info] Definición
> Se examina el **código interno**, la lógica y la estructura del programa para diseñar los casos de prueba.

### Características
- Requiere conocimientos de programación.
- Mide **cobertura** (qué % del código se ejecuta).
- Se enfoca en rutas, ramas, condiciones y bucles.
- Típicamente a nivel **unitario**.

### Técnicas principales
- **Sentencias:** cada línea se ejecuta al menos una vez.
- **Ramas:** cada `if`/`while` se evalúa en True y False.
- **Condiciones:** cada condición booleana en True y False.
- **Caminos:** todas las rutas posibles del flujo.
- **Bucles:** 0, 1, 2, N iteraciones.
- **MC/DC:** condiciones múltiples (software crítico).

### Niveles de cobertura
> [!note] De menor a mayor exigencia
> `Sentencias → Ramas → Condiciones → Caminos → MC/DC`

### Herramientas
| Lenguaje | Herramienta |
|---|---|
| Java | JaCoCo |
| Python | coverage.py, pytest-cov |
| JavaScript | Istanbul / NYC |
| C/C++ | gcov, lcov |
| .NET | dotCover |

###  Ventajas
- Detecta errores ocultos en lógica compleja.
- Cobertura medible y objetiva.
- Útil en software crítico.

###  Desventajas
- Costosa, requiere perfil técnico.
- No detecta requisitos faltantes.
- 100% cobertura ≠ 100% correcto.

---

##  Caja Negra

> [!info] Definición
> Solo se prueban **entradas y salidas**, sin ver el código.

### Características
- No requiere conocer la implementación.
- Se basa en **requisitos y especificaciones**.
- La aplica el tester / QA.
- Nivel de **sistema** o **aceptación**.

### Técnicas principales
- **Partición de equivalencia:** agrupar entradas similares.
- **Valores límite:** probar bordes (min, max, min±1).
- **Tabla de decisión:** combinaciones de condiciones.
- **Transición de estados:** flujos entre estados.
- **Casos de uso:** escenarios reales de usuario.

###  Ventajas
- No requiere conocimiento técnico.
- Detecta fallos desde la perspectiva del usuario.
- Aplicable a cualquier sistema.

###  Desventajas
- No garantiza cobertura del código.
- Puede dejar rutas internas sin probar.
- Depende de buenos requisitos.

---

##  Comparación rápida

| Aspecto | Caja Blanca | Caja Negra |
|---|---|---|
| Enfoque | Código | Comportamiento |
| Entrada | Estructura interna | Requisitos |
| Detección | Errores de lógica | Errores funcionales |
| Automatización | Alta (unit tests) | Media (E2E, UI) |
| Costo | Alto | Medio |

---

##  Buenas prácticas

1. **Combinar ambas** para cobertura completa.
2. En caja blanca, apuntar a **cobertura de ramas**, no solo sentencias.
3. En caja negra, usar **valores límite** y **partición de equivalencia**.
4. Automatizar en **CI/CD** (ejecutar en cada commit).
5. No obsesionarse con 100% cobertura: costo/beneficio.
6. Probar **casos límite** y **excepciones**.

---
