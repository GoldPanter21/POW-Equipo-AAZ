# Registro de entorno y ejecución inicial

## Identificación

- **Contribución prevista:** galería Multimedia con Personajes, Mapas y Diseños.
- **Responsable / usuario de GitHub:** PENDIENTE.
- **Fecha y hora de ejecución:** PENDIENTE de confirmar por quien ejecutó.
- **Repositorio:** [GoldPanter21/POW-Equipo-AAZ](https://github.com/GoldPanter21/POW-Equipo-AAZ).
- **SHA base comunicado por el ejecutor:** `7ed325393f82872c2be94ff2ada46948efa19152`.
- **Commit base:** [Ver commit](https://github.com/GoldPanter21/POW-Equipo-AAZ/commit/7ed325393f82872c2be94ff2ada46948efa19152).
- **Rama desde la que se compiló y ejecutó:** PENDIENTE de confirmar.
- **Cambios locales al compilar:** PENDIENTE de revisar en Changes de GitHub Desktop; describir cualquier cambio, si existe.
- **Método de compilación e instalación:** PENDIENTE de confirmar que la app instalada procede de esta copia en Android Studio.

## Dispositivo observado

Datos transcritos de la captura Device Info proporcionada por el ejecutor:

| Dato | Valor |
|---|---|
| Fabricante | Xiaomi |
| Identificador de modelo | 22021211RG |
| Nivel de API | 34 |
| Versión Android correspondiente a la API | Android 14 |
| Valor completo mostrado por Android Studio | 34-ext22 |
| Extensión de SDK indicada | 22 |
| Resolución física | 1080 × 2400 píxeles |
| Resolución en dp | 393 × 873 dp |
| Densidad lógica reportada | 440 dpi |
| ABI preferida | arm64-v8a |
| Alimentación mostrada | USB |

`ext22` indica la extensión de SDK; el nivel de API sigue siendo 34. La versión Android 14 se obtiene de la correspondencia de API 34. No se ha confirmado un nombre comercial adicional para el modelo.

## Configuración de la aplicación observada

- **Versión visible:** PRE-ALPHA - v1.0.0.18.
- **Modo visible:** Modo local (sin sesión).
- **Orientación de la captura:** vertical.
- **Idioma de los textos visibles:** español.
- **Conectividad efectiva durante la ejecución:** PENDIENTE; el icono Wi-Fi de la captura no acredita acceso a servicios externos.
- **Tamaño de fuente y de visualización:** PENDIENTE de registrar.

## Entorno de desarrollo

- **Sistema operativo de la computadora y versión:** PENDIENTE.
- **Versión de Android Studio:** PENDIENTE.
- **JDK usado por Gradle:** PENDIENTE.
- **SDK de compilación utilizado:** PENDIENTE.

El SDK utilizado para compilar y el nivel de API del teléfono son datos distintos y deben registrarse por separado.

## BASE-01: menú antes de implementar la galería

**Ejecución reportada:** el responsable indicó que ejecutó el juego antes de implementar el menú de galería.

**Observación respaldada por la captura:** la aplicación muestra el menú principal con Mundo libre, Modo historia, Multijugador, Ajustes, Coleccionables y Titulación por combate. No se observa una opción Galería o Multimedia en esa pantalla.

**Estado del registro:** menú inicial documentado mediante captura; trazabilidad completa de compilación pendiente de confirmar con los campos anteriores. Esta evidencia no valida otras pantallas ni las futuras pruebas de la galería.

### Evidencias

- Captura original del menú:
  <img width="1080" height="2400" alt="Screenshot_20261001_012808" src="https://github.com/user-attachments/assets/18011a71-c432-4bcb-bba7-8bacc293db17" />
- Captura de Android Studio Device Info: Xiaomi 22021211RG, API 34-ext22.
<img width="381" height="378" alt="Captura de pantalla 2026-10-01 075249" src="https://github.com/user-attachments/assets/eac65dfa-6456-43db-aa65-b7d718210667" />

## BASE-02: flujo existente cercano

https://github.com/user-attachments/assets/74af76e9-e0c6-45be-8c57-069d5eeed958

## Herramientas de apoyo

Se utilizó Codex para organizar este registro, transcribir las capturas aportadas y explicar el SHA y la API. La ejecución del juego fue reportada por el integrante; Codex no ejecutó ni validó funcionalmente la aplicación.
