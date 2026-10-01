# Plan y registro de QA — Galería multimedia

**Estado: QA en curso.** Existe evidencia visual de apertura de la galería, contenido de las tres categorías y regreso al menú. Las pruebas adicionales y la trazabilidad de la compilación siguen pendientes.

## 1. Identificación

| Campo | Valor |
|---|---|
| Responsable | NyaSanchez |
| Repositorio | [POW-Equipo-AAZ](https://github.com/GoldPanter21/POW-Equipo-AAZ) |
| Issue | [#2 — Add a local multimedia gallery to the Android main menu](https://github.com/GoldPanter21/POW-Equipo-AAZ/issues/2) |
| Rama de implementación | `feature/multimedia-gallery` |
| Rama de documentación académica | `docs/examen-parcial1` |
| Pull request | PENDIENTE: agregar enlace al PR dirigido a `gabrielhuav/PolitecnicoOpenWorld:main` |
| Fecha del registro | 1 de octubre de 2026 |

## 2. Cambio y alcance

Se añadió la opción **Multimedia** al menú principal de Android. La galería permite consultar imágenes existentes del juego en tres categorías, con dos elementos por categoría:

| Categoría | Elementos |
|---|---|
| Personajes | Prankedy y Charro Negro |
| Mapas | Escenario ESCOM y Escenario CECyT 9 |
| Diseños | Edificio de ESCOM y Edificios del CIC |

Cada elemento incluye imagen, nombre y descripción. La implementación reutiliza recursos locales del proyecto e incorpora textos en español e inglés.

El propósito es permitir que los jugadores consulten una selección del arte del juego desde el menú principal.

El alcance excluye reproducción de audio o video, descargas, cargas de archivos, cambios al servidor y modificaciones a las reglas del juego. La contribución no atribuye al equipo la creación del arte reutilizado.

## 3. Versiones y trazabilidad

| Referencia | SHA |
|---|---|
| Base anterior al cambio | `7ed325393f82872c2be94ff2ada46948efa19152` |
| Commit publicado de la galería | `385e966dbc0e4ea3f9397914d8452bd62c74e25c` |
| SHA asociado de forma comprobada a la app del video | PENDIENTE de confirmar |
| SHA final entregado | PENDIENTE de confirmar al terminar QA |

- [Consultar commit base](https://github.com/GoldPanter21/POW-Equipo-AAZ/commit/7ed325393f82872c2be94ff2ada46948efa19152).
- [Consultar implementación publicada y archivos modificados](https://github.com/GoldPanter21/POW-Equipo-AAZ/commit/385e966dbc0e4ea3f9397914d8452bd62c74e25c).

El SHA publicado identifica el código en GitHub. El video por sí solo no demuestra qué revisión se compiló. Debe confirmarse que la app grabada se construyó con los mismos archivos del commit indicado, sin modificaciones adicionales.

Si no puede establecerse esa relación, se recompilará la rama publicada y se repetirá el recorrido, registrando su SHA y evidencia.

Si después del QA cambia el código, se repetirán los casos afectados y se documentará la relación entre el SHA probado y el final.

## 4. Entorno

| Campo | Valor |
|---|---|
| Dispositivo | Xiaomi 22021211RG, físico |
| Android | Android 14 |
| Nivel de API mostrado por Android Studio | `34-ext22`: API 34, extensión 22 |
| Resolución | 1080 × 2400 píxeles |
| Resolución lógica | 393 × 873 dp |
| Densidad | 440 dpi |
| ABI preferida | `arm64-v8a` |
| Orientación observada | Vertical |
| Idioma observado | Español |
| Versión visible de la app | PRE-ALPHA — v1.0.0.18 |
| Modo visible | Local, sin sesión |
| Conectividad durante el video | No se acredita una prueba sin conexión |
| Tamaño de fuente y visualización | PENDIENTE: registrar configuración exacta |
| TalkBack | PENDIENTE de probar |
| Sistema operativo del equipo de desarrollo | Windows; versión exacta pendiente |
| Android Studio | PENDIENTE: versión |
| JDK configurado para Gradle | PENDIENTE: versión |
| Compilación e instalación | La responsable informó ejecución satisfactoria; pendiente adjuntar registro de compilación y vincularlo al SHA |

## 5. Criterios de aceptación

- **CA-01 — Acceso y contenido:** Multimedia abre inicialmente en Personajes. Las tres categorías muestran sus dos imágenes, nombres y descripciones correctos, incluso después de selecciones repetidas.
- **CA-02 — Funcionamiento local:** con el menú accesible y la conectividad desactivada, la galería muestra sus recursos sin requerir descargas.
- **CA-03 — Navegación:** tanto Atrás de Android como el control visible permiten regresar al menú. Al reabrir la galería, la categoría inicial es Personajes.
- **CA-04 — Estado:** después de enviar la app brevemente a segundo plano y regresar, se conserva la categoría seleccionada mientras el proceso sigue activo.
- **CA-05 — Accesibilidad:** los controles y el contenido tienen etiquetas útiles y permanecen legibles y utilizables con texto ampliado.
- **CA-06 — Regresión:** el recorrido Menú → Ajustes → Atrás de Android → Menú conserva su funcionamiento.

## 6. Riesgos

| Riesgo | Consecuencia | Cobertura |
|---|---|---|
| R-01: recursos ausentes o categorías incorrectas | Imágenes vacías, equivocadas o duplicadas | MM-01, MM-02 y MM-03 |
| R-02: navegación incorrecta | Salida involuntaria de la app o imposibilidad de volver al menú | MM-04 |
| R-03: pérdida de estado | Categoría inesperada o pantalla vacía al regresar del fondo | MM-05 |
| R-04: problemas de accesibilidad o adaptación | Controles inaccesibles o texto recortado | MM-06 y MM-07 |
| R-05: regresión en el menú existente | Ajustes deja de abrir o regresar correctamente | MM-08 |
| R-06: carga de imágenes | Demoras o cierres durante el recorrido | MM-01 y MM-03; sin mediciones de memoria todavía |

## 7. Evidencias

### E-01 — Menú anterior al cambio

[Captura del menú base sin entrada Multimedia](https://github.com/user-attachments/assets/18011a71-c432-4bcb-bba7-8bacc293db17).

### E-02 — Dispositivo y API

[Captura de Device Info en Android Studio](https://github.com/user-attachments/assets/eac65dfa-6456-43db-aa65-b7d718210667).

### E-03 — Recorrido de Ajustes antes del cambio

[Video de referencia de Ajustes y regreso al menú](https://github.com/user-attachments/assets/74af76e9-e0c6-45be-8c57-069d5eeed958).

Se observa el acceso a Ajustes, las secciones Mapa, Controles y Jugabilidad, y el regreso al menú. Esta evidencia corresponde a la base; no sustituye la prueba de regresión después de implementar la galería.

### E-04 — Recorrido de la galería implementada

Archivo: `Screen_recording_20261001_090103.mp4`.

**PENDIENTE: insertar aquí el video subido a GitHub.**

Duración aproximada: 12 segundos. Se observa:

| Momento aproximado | Contenido |
|---|---|
| 00:00–00:02 | Menú principal con la nueva opción Multimedia |
| 00:03–00:05 | Personajes: Prankedy y Charro Negro |
| 00:06–00:07 | Mapas: Escenario ESCOM y Escenario CECyT 9 |
| 00:08–00:09 | Diseños: Edificio de ESCOM y Edificios del CIC |
| 00:10–00:12 | Regreso al menú principal |

No se observa un cierre inesperado durante este recorrido. La grabación no acredita funcionamiento sin conexión, TalkBack, segundo plano, selecciones repetidas ni regresión de Ajustes.

## 8. Registro de ejecución inicial

### EJ-01 — Recorrido grabado

| Campo | Registro |
|---|---|
| Responsable de ejecución | NyaSanchez |
| Fecha/hora | 01/10/2026, aproximadamente 09:01, según nombre del archivo y reloj visible |
| Evidencia | E-04 |
| Dispositivo/API | Xiaomi 22021211RG / API 34-ext22 |
| App | v1.0.0.18 visible |
| Configuración | Español, vertical, modo local sin sesión |
| SHA probado | PENDIENTE: confirmar relación con el commit publicado |
| Precondiciones | App con galería instalada y menú accesible |
| Datos | Los seis elementos del inventario |
| Resultado observado | Se abre Multimedia, se visualizan las tres categorías y se regresa al menú |
| Defectos observados | Ninguno visible en este recorrido limitado |
| Decisión | Conservar evidencia y completar los casos pendientes |

## 9. Casos de prueba

Los casos usan el entorno de la sección 4, salvo que indiquen una variación. Cada nueva ejecución debe registrar autor, fecha/hora, SHA, versión de app, configuración, resultado real, estado, evidencia, defecto y decisión.

**Pendiente** significa que falta ejecutar o documentar. **Parcial** significa que solo se acredita una parte del caso. Ninguno de esos estados cuenta como caso completamente aprobado.

### MM-01 — Apertura y contenido

- **Criterio/riesgo:** CA-01; R-01 y R-06.
- **Precondiciones/datos:** menú accesible y seis elementos del inventario.
- **Pasos:**
  1. Abrir Multimedia.
  2. Revisar Personajes.
  3. Seleccionar Mapas y revisar ambos elementos.
  4. Seleccionar Diseños y revisar ambos elementos.
  5. Volver a Personajes y comprobar su contenido.
- **Esperado:** dos elementos correctos por categoría, nombres y descripciones visibles, sin imágenes vacías ni cierre inesperado.
- **Ejecución:** EJ-01.
- **Resultado real:** se observan las tres categorías con sus seis imágenes. No se observa el paso final de volver a Personajes.
- **Estado:** PARCIAL.
- **Evidencia:** E-04.
- **Defecto:** ninguno observado en los pasos visibles.
- **Decisión:** completar el paso restante y confirmar el SHA probado.

### MM-02 — Galería sin conexión

- **Criterio/riesgo:** CA-02; R-01.
- **Precondiciones/datos:** menú accesible; no abrir la galería previamente en esa sesión.
- **Pasos:**
  1. Desactivar Wi-Fi y datos móviles, mostrando esa configuración.
  2. Abrir Multimedia.
  3. Visitar las tres categorías.
  4. Salir y volver a abrir.
  5. Restaurar la conectividad.
- **Esperado:** los seis recursos aparecen sin descargas ni errores propios de la galería.
- **Autor/fecha/SHA/evidencia:** PENDIENTES.
- **Resultado real:** PENDIENTE.
- **Estado:** PENDIENTE.
- **Defecto y decisión:** pendientes de ejecución.

### MM-03 — Selecciones repetidas

- **Criterio/riesgo:** CA-01; R-01 y R-06.
- **Precondiciones/datos:** galería abierta en Personajes.
- **Pasos:**
  1. Seleccionar Mapas → Diseños → Personajes.
  2. Repetir el ciclo cinco veces.
  3. Pulsar Personajes tres veces adicionales.
  4. Revisar el contenido final.
- **Esperado:** dos elementos correctos por categoría, sin duplicados, pantalla vacía ni cierre inesperado.
- **Autor/fecha/SHA/evidencia:** PENDIENTES.
- **Resultado real:** PENDIENTE.
- **Estado:** PENDIENTE.
- **Defecto y decisión:** pendientes de ejecución.

### MM-04 — Atrás y reingreso

- **Criterio/riesgo:** CA-03; R-02.
- **Precondiciones/datos:** galería abierta con Diseños seleccionado.
- **Pasos:**
  1. Usar Atrás de Android y comprobar el menú.
  2. Reabrir Multimedia y comprobar Personajes.
  3. Seleccionar Mapas.
  4. Usar Volver al menú.
  5. Reabrir y comprobar Personajes.
- **Esperado:** ambos controles regresan al menú sin salir de la app; cada reingreso comienza en Personajes.
- **Ejecución disponible:** EJ-01.
- **Resultado real:** el video acredita un regreso al menú, pero no distingue con certeza el control utilizado ni muestra reingreso.
- **Estado:** PARCIAL.
- **Evidencia:** E-04.
- **Defecto:** ninguno observado en el regreso visible.
- **Decisión:** ejecutar la secuencia completa y registrar el SHA.

### MM-05 — Segundo plano y recuperación

- **Criterio/riesgo:** CA-04; R-03.
- **Precondiciones/datos:** galería abierta en Mapas.
- **Pasos:**
  1. Enviar la app a segundo plano.
  2. Esperar aproximadamente diez segundos sin cerrar su proceso.
  3. Regresar desde aplicaciones recientes.
  4. Revisar categoría e imágenes.
- **Esperado:** se conserva Mapas y aparecen sus dos elementos.
- **Autor/fecha/SHA/evidencia:** PENDIENTES.
- **Resultado real:** PENDIENTE.
- **Estado:** PENDIENTE.
- **Defecto y decisión:** pendientes de ejecución.
- **Límite:** este caso no acredita recuperación después de finalizar el proceso.

### MM-06 — Texto ampliado y TalkBack

- **Criterio/riesgo:** CA-05; R-04.
- **Precondiciones/datos:** registrar el tamaño de fuente inicial y la configuración de TalkBack.
- **Pasos:**
  1. Aumentar la fuente del sistema y registrar el valor elegido.
  2. Abrir Multimedia y recorrer las categorías.
  3. Activar TalkBack.
  4. Recorrer y activar controles mediante el lector.
  5. Comprobar nombres, selección de categorías y acceso al contenido.
  6. Restaurar la configuración inicial.
- **Esperado:** controles utilizables, texto legible y etiquetas comprensibles.
- **Autor/fecha/SHA/evidencia:** PENDIENTES.
- **Resultado real:** PENDIENTE.
- **Estado:** PENDIENTE.
- **Defecto y decisión:** pendientes de ejecución.

### MM-07 — Configuración alternativa de pantalla

- **Criterio/riesgo:** CA-05; R-04.
- **Precondiciones/datos:** registrar el tamaño de visualización inicial; mantener la fuente normal para distinguir este caso de MM-06.
- **Pasos:**
  1. Aumentar el tamaño de visualización del sistema.
  2. Registrar el ajuste utilizado.
  3. Abrir Multimedia y recorrer las categorías.
  4. Desplazar el contenido cuando sea necesario.
  5. Comprobar acceso a las imágenes y al control de regreso.
  6. Restaurar la configuración.
- **Esperado:** contenido accesible, sin superposiciones que impidan utilizar controles.
- **Autor/fecha/SHA/evidencia:** PENDIENTES.
- **Resultado real:** PENDIENTE.
- **Estado:** PENDIENTE.
- **Defecto y decisión:** pendientes de ejecución.
- **Límite:** esta variación en el Xiaomi no acredita compatibilidad con otras versiones de Android.

### MM-08 — Regresión de Ajustes

- **Criterio/riesgo:** CA-06; R-05.
- **Precondiciones/datos:** app con galería instalada; evidencia base E-03 disponible.
- **Pasos:**
  1. Desde el menú, abrir Ajustes.
  2. Visitar Mapa, Controles y Jugabilidad.
  3. Volver a Mapa.
  4. Usar Atrás de Android.
  5. Comparar el regreso al menú con la base.
- **Esperado:** las secciones abren y se regresa al menú sin cierre inesperado.
- **Autor/fecha/SHA/evidencia:** PENDIENTES.
- **Resultado real:** PENDIENTE en la versión modificada.
- **Estado:** PENDIENTE.
- **Defecto y decisión:** pendientes de ejecución.
- **Nota:** E-03 demuestra el comportamiento anterior; no aprueba esta regresión.

## 10. Compilación, pruebas automáticas y checks

| Verificación | Estado | Evidencia |
|---|---|---|
| Ejecución manual de la galería | Informada por la responsable y visible en E-04 | Pendiente enlazar E-04 y confirmar SHA |
| `:app:assembleDebug` | PENDIENTE de registro verificable | PENDIENTE |
| `:app:testDebugUnitTest` | PENDIENTE de ejecución documentada | PENDIENTE |
| `:shared:testAndroidHostTest` | PENDIENTE de ejecución documentada | PENDIENTE |
| Checks del PR, incluido detekt según el workflow | PENDIENTES | PENDIENTE |
| Revisión técnica de un compañero | PENDIENTE | PENDIENTE |

La existencia de pruebas unitarias en el código no demuestra que se hayan ejecutado correctamente.

## 11. Defectos y repetición de pruebas

No se identifican defectos visibles en el recorrido limitado E-04. Esto no implica ausencia de defectos en los casos pendientes.

Si se detecta un fallo, registrar:

| Campo | Registro |
|---|---|
| ID del defecto y caso relacionado | PENDIENTE si aparece un fallo |
| Autor, fecha y SHA | PENDIENTE |
| Pasos de reproducción | PENDIENTE |
| Esperado frente a resultado real | PENDIENTE |
| Impacto y evidencia | PENDIENTE |
| Issue o comentario asociado | PENDIENTE |
| Commit de corrección | PENDIENTE |
| SHA y resultado de la repetición | PENDIENTE |
| Regresión posterior | PENDIENTE |
| Decisión de cierre | PENDIENTE |

## 12. Revisión entre integrantes

Un compañero debe revisar el cambio y reproducir al menos un caso, indicando SHA, dispositivo/API, resultado y evidencia en el PR.

La responsable también debe revisar una contribución de otro integrante y reproducir al menos un caso de esa implementación.

| Participación | Enlace y resultado |
|---|---|
| Revisión recibida en el PR de galería | PENDIENTE |
| Revisión realizada por NyaSanchez en otro PR | PENDIENTE |

## 13. Dictamen y reversión

**Dictamen actual: mantener el PR como borrador mientras se completa QA.**

Antes de recomendar integración:

- Completar al menos seis casos distintos con resultados reales y evidencia.
- Resolver la vinculación entre app probada y SHA.
- Publicar las evidencias y el enlace del PR.
- Revisar los resultados de los checks.
- Atender defectos y repetir los casos afectados.
- Obtener la revisión técnica de un compañero.
- Documentar el SHA final y su relación con el probado.

Los riesgos todavía abiertos incluyen funcionamiento sin conexión, navegación completa, conservación de estado, accesibilidad, adaptación de pantalla y regresión de Ajustes.

Para revertir la implementación, crear un commit de reversión del cambio de la galería y comprobar la compilación y el menú. Se conservarán los registros académicos y evidencias.

## 14. Uso de asistencia de IA

Se utilizó Codex como apoyo para preparar la implementación, proponer casos de prueba, revisar evidencia visual y redactar documentación. La ejecución en el dispositivo fue realizada por la responsable. Las pruebas pendientes y la revisión de compañeros deben completarse y registrarse por sus ejecutores.
