# Letria: ficha de idea

**Unidad de aprendizaje:** Desarrollo de aplicaciones móviles nativas

**Entrega:** 1 del proyecto, Parte 1 (idea original de la aplicación)

**Equipo:** 

Orozco Aguilar Angel Isai 

Sánchez Valadez Zyanya Maxi 

Tellez Giron Angel Ricardo

**Fecha de la ficha:** 4 de octubre de 2026

**Estado:** nombre provisional; hipótesis sin validar con usuarios.

---

## 1. Ruta elegida y motivo

**Ruta:** idea propia desarrollada desde cero.

**Motivo:** la aplicación necesita controlar tres reglas propias: definiciones bilingües, evaluación por letra y días de práctica. Construirla desde cero permite concentrar el trabajo en esas reglas, sin adaptarse a las restricciones de un proyecto base.

**Plataforma:** Android nativo como primera plataforma.

## 2. Problema (en una frase)

Una persona que comienza a aprender inglés puede reconocer el significado de una palabra, pero tener dificultades para escribirla correctamente y mantener una práctica diaria.

## 3. Usuario y contexto

- **Quién:** Persona hispanohablante de nivel superior con inglés inicial.
- **Dónde y cuándo:** Usaría el teléfono en tiempos libres.
- **Duración:** Sesiones de tres a cinco minutos.

> El perfil y el tiempo de uso son hipótesis de diseño, no resultados observados.

## 4. Alternativa actual

Se consideran como alternativas por investigar los diccionarios, los traductores, las tarjetas de vocabulario y los ejercicios de escritura. Falta identificar cuáles usa realmente el público objetivo y cómo le ayudan a corregirse cuando se equivoca al escribir.

## 5. Tarea principal

Leer una definición, escribir la palabra en el otro idioma y corregirla con pistas hasta acertarla. El primer acierto de la fecha completa la meta diaria.

## 6. Criterio de éxito

La tarea se considera lograda cuando:

1. La respuesta coincide con la palabra objetivo.
2. Todas sus letras aparecen en verde.
3. La aplicación confirma el acierto.

La fecha queda completada **una sola vez**, aunque se acierten más palabras ese mismo día.

## 7. Alcance de la primera versión

Lo que **sí entra**:

- Android nativo.
- Catálogo local de 30 pares de vocabulario revisados.
- Ambos modos de idioma: definición en español con respuesta en inglés, y definición en inglés con respuesta en español.
- Seis intentos por reto.
- Pistas por letra (verde, amarillo y rojo).
- Resultado con traducción y ejemplo.
- Racha local, historial de días y repaso sencillo de palabras vistas.
- Estados alternos: carga, lista vacía, error y datos inválidos.
- Datos y zona horaria guardados de forma local.

> La cantidad de palabras (30) y de intentos (6) son decisiones propuestas, no valores validados.

## 8. Funciones aplazadas

Se dejan fuera de forma deliberada:

- Cuentas y sincronización.
- Clasificaciones y competencias.
- Definiciones automáticas.
- Varios niveles de dificultad.
- Recordatorios.
- Repaso adaptativo.
- Protección contra cambios manuales del reloj del dispositivo.

El selector de nivel y el icono de audio que aparecen en los bosquejos corresponden a posibles ampliaciones, no a la primera versión.

## 9. Reglas principales

### Modos de juego

| Modo | Se muestra | El usuario responde |
|---|---|---|
| Definición en español | Definición en español | En inglés |
| Definición in English | Definición en inglés | En español |

La longitud de la respuesta se muestra en casillas.

### Evaluación por letra

**Comprobar** evalúa la palabra completa.

| Color | Significado |
|---|---|
| Verde | Letra y posición correctas |
| Amarillo | La letra existe, pero en otra posición |
| Rojo | Sin coincidencia disponible |

Los estados no dependen solo del color: también se acompañan con texto y símbolos.

### Letras repetidas

Se asignan primero los verdes y después los amarillos. Cada aparición de una letra en la palabra objetivo solo puede coincidir una vez. Una copia sobrante recibe rojo.

### Intentos

- Una entrada inválida o incompleta **no consume intento**.
- Una respuesta válida pero incorrecta conserva su fila y abre el siguiente intento.
- Al agotar los intentos se revela la solución, no se suma racha y se permite practicar otra palabra.

### Racha

La racha cuenta **fechas**, no palabras.

- El primer acierto del día completa la fecha y suma un día de racha.
- Otros aciertos del mismo día y el cambio de modo no añaden días.
- Ambos modos comparten el mismo progreso.
- Abrir la aplicación, escribir intentos o ver la solución revelada no completan el día.
- Un día completo sin acertar rompe la continuidad; el siguiente acierto inicia una racha de un día.

## 10. Evidencia e hipótesis pendiente de validar

### Evidencia disponible

Al 4 de octubre de 2026 **no se cuenta con entrevistas, encuestas ni pruebas de uso documentadas**. Los bosquejos muestran el diseño propuesto, no su eficacia. La idea es, por tanto, una **hipótesis sin validar**.

### Hipótesis pendientes

1. Las pistas por letra ayudan a las personas a corregir su escritura.
2. Una meta diaria de una sola palabra favorece que la persona regrese a practicar.

### Plan de validación (aún no realizado)

| Elemento | Propuesta |
|---|---|
| Método | Observación de uso con cinco estudiantes |
| Tarea | Resolver un reto por cada modo de idioma |
| Registro | Fecha, método, respuestas, tiempos y comprensión de colores y rachas |
| Meta | Al menos cuatro de cinco completan un reto e interpretan las reglas sin ayuda |

> La meta es un umbral propuesto. No se presenta como un resultado obtenido.

## 11. Historia de usuario

**Como** persoma hispanohablante que está aprendiendo vocabulario básico de inglés, **quiero** escribir una palabra a partir de su definición y recibir pistas sobre cada letra **para** corregir mi respuesta y completar una práctica diaria breve.

## 12. Criterios de aceptación

Cada criterio puede ejecutarse y responderse con sí o no, sin interpretación.

### CA-01. Primer acierto del día
- **Dado** el modo de definición en español, el reto "Edificio donde vive una persona." con objetivo `HOUSE`, una racha de cuatro días consecutivos hasta ayer y hoy sin aciertos,
- **cuando** se envía `HOUSE` con Comprobar,
- **entonces** las cinco letras son verdes, aparece "¡Palabra correcta!", la racha pasa a cinco días y hoy queda completado una sola vez.

### CA-02. Colores verificables
- **Dado** el objetivo `HOUSE` y un intento disponible,
- **cuando** se envía `SHARE`,
- **entonces** S y H son amarillas, A y R son rojas y E es verde. Se consume un intento y la partida continúa.

### CA-03. Modo inverso
- **Dado** el modo de definición en inglés, la pista "A building where someone lives." y objetivo `CASA`,
- **cuando** se envía `CASA`,
- **entonces** las cuatro letras son verdes y se confirma el acierto.

### CA-04. Racha sin duplicados
- **Dado** que hoy ya está completado y la racha es de cinco días,
- **cuando** se acierta otra palabra en cualquiera de los modos,
- **entonces** la racha sigue en cinco y hoy conserva un solo registro.

### CA-05. Entrada incompleta
- **Dado** un reto de cinco letras y seis intentos restantes,
- **cuando** se escribe `HOU`,
- **entonces** se informa que faltan dos letras, no se evalúan colores y se mantienen los seis intentos.

### CA-06. Letras repetidas
- **Dado** el objetivo `APPLE`,
- **cuando** se envía `PAPAL`,
- **entonces** las posiciones 1 a 5 son amarilla, amarilla, verde, roja y amarilla, respectivamente.

### CA-07. Solución revelada
- **Dado** el último intento de un reto y hoy aún sin aciertos,
- **cuando** se envía una palabra válida incorrecta,
- **entonces** se muestra la solución y la opción de practicar otra palabra, sin completar hoy.

### CA-08. Estados alternos
- **Dado** un catálogo en carga, un Repaso vacío o una lectura fallida,
- **cuando** se abre la pantalla correspondiente,
- **entonces** aparece, respectivamente: carga con envío deshabilitado; lista vacía con el botón Empezar; o error con los botones Reintentar y Volver al inicio. Ningún estado suma racha.

> Son criterios esperados, pendientes de ejecutar sobre una aplicación implementada.

## 13. Diseño: tipografía y paleta

- **Tipografía propuesta:** Arial Regular y Bold, sujeta a disponibilidad o sustitución al implementar en Android.
- **Colores de interfaz:** morado `#6D28D9` y azul `#2563EB`.
- **Verde, amarillo y rojo:** reservados exclusivamente para el estado de las letras.

## 14. Material visual

Los bosquejos de las pantallas principales, los estados alternos (carga, lista vacía, error y datos inválidos), el esquema de la pantalla de juego y el diagrama del recorrido del usuario se encuentran en `docs/imagenes_idea/`. Son bosquejos conceptuales; no son capturas de una aplicación implementada.
