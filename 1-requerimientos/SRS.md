# Especificación de Requerimientos de Software (SRS) - Versión 1.0
**Proyecto:** Eco-Runner  
**Autores:** Gamaliel López Pazos, Irving Emiliano Rivera Matus  
**Fecha:** Noviembre 2026  

## 1. Introducción
### 1.1 Propósito
El propósito de este documento es definir de manera clara, completa y verificable los requerimientos funcionales y no funcionales del videojuego educativo **Eco-Runner**, sirviendo como guía técnica para su diseño, programación en Python y validación por parte del equipo de desarrollo.

### 1.2 Alcance
**Eco-Runner** es un videojuego 2D en perspectiva cenital (*top-down*) con estética *pixel art*, desarrollado en **Python** con la librería **Pygame** e inspirado en el Objetivo de Desarrollo Sostenible 11 (Ciudades y Comunidades Sostenibles). El jugador controla a un personaje que recorre distintos escenarios contaminados para recolectar residuos contrarreloj y clasificarlos en contenedores de reciclaje a cambio de monedas.

* **Incluye:** Movimiento del personaje en escenarios (parque urbano, bosque y playa), sistema de recolección de residuos por categoría (plástico, latas, papel y orgánico), temporizador por ronda, mecánica de clasificación en contenedores de colores y sistema de puntuación por monedas.
* **No incluye (en esta versión v1.0):** Modo multijugador en línea, tienda de compras con dinero real ni versión nativa para dispositivos móviles iOS/Android.

### 1.3 Glosario de términos
* **SRS:** Especificación de Requerimientos de Software.
* **ODS 11:** Objetivo de Desarrollo Sostenible número 11 de la ONU ("Ciudades y Comunidades Sostenibles").
* **Python / Pygame:** Lenguaje de programación y biblioteca multimedia 2D utilizados para programar la lógica, colisiones, gráficos y eventos del videojuego.
* **Sprite:** Imagen o conjunto de fotogramas 2D que representan al personaje, los residuos y los contenedores dentro del entorno gráfico.
* **HUD (Heads-Up Display):** Interfaz visual en pantalla que muestra al jugador el tiempo restante, las monedas acumuladas, el nivel actual y el contador de basura recolectada.

## 2. Descripción general
### 2.1 Tipos de usuarios
* **Jugador (Usuario final):** Estudiantes, niños y público general interesados en videojuegos casuales y educación ambiental. Interactúa con el juego controlando al personaje, recolectando basura y clasificándola en los contenedores.
* **Desarrollador / Administrador:** Integrantes del equipo encargados de programar los módulos en Python, integrar los *sprites* y realizar pruebas de funcionamiento.

### 2.2 Restricciones
* El videojuego debe desarrollarse utilizando **Python 3** y la librería **Pygame**, bajo un paradigma de Programación Orientada a Objetos (POO).
* El diseño gráfico debe mantener una estética *pixel art* 2D coherente en todos los mapas y personajes.
* El desarrollo de esta primera versión debe ajustarse al calendario académico del semestre en curso.

### 2.3 Supuestos y dependencias
* Se asume que el equipo del usuario cuenta con teclado o ratón funcional para controlar el desplazamiento y las interacciones del personaje.
* Se supone que el entorno de ejecución cuenta con sistema operativo Windows 10/11 con soporte gráfico estándar para ejecutar aplicaciones creadas con Pygame.

## 3. Requerimientos Específicos
### 3.1 Requerimientos Funcionales
* **RF-01: Desplazamiento del personaje en el escenario**
  * **Descripción:** El sistema debe permitir al jugador mover al personaje protagonista en cuatro direcciones (arriba, abajo, izquierda y derecha) a través de los caminos y áreas transitables de cada mapa mediante las teclas de dirección o WASD.
  * **Prioridad:** Alta
  * **Criterio de aceptación:** Dado que el jugador se encuentra dentro de un nivel activo, cuando presiona una tecla de dirección, entonces el personaje se desplaza en esa dirección respetando las colisiones con edificios, árboles, vallas y límites del mapa.

* **RF-02: Recolección de residuos por categoría**
  * **Descripción:** El sistema debe permitir al jugador recoger distintos tipos de basura dispersos en el mapa (botellas de plástico, latas y papel) al acercarse e interactuar con ellos, eliminando el *sprite* del suelo e incrementando el contador correspondiente en el HUD.
  * **Prioridad:** Alta
  * **Criterio de aceptación:** Dado que el personaje está frente a una botella de plástico y el contador muestra `18/25`, cuando el jugador presiona la tecla de acción, entonces la botella desaparece del escenario y el contador se actualiza inmediatamente a `19/25`.

* **RF-03: Temporizador de cuenta regresiva por nivel**
  * **Descripción:** El sistema debe iniciar un temporizador en cuenta regresiva al comenzar cada nivel (ej. `02:16` minutos) y finalizar la ronda automáticamente si el tiempo llega a `00:00` antes de completar la meta de recolección.
  * **Prioridad:** Alta
  * **Criterio de aceptación:** Dado que un nivel ha iniciado, cuando transcurre cada segundo real, entonces el reloj en el HUD disminuye segundo a segundo; si llega a `00:00` sin cumplir el objetivo, se muestra una pantalla de tiempo agotado con opción de reintentar.

* **RF-04: Clasificación de basura en contenedores de reciclaje**
  * **Descripción:** Al finalizar la fase de recolección o acercarse a la zona de contenedores (azul para plástico, verde para orgánico/vidrio, amarillo para papel/metal), el sistema debe permitir depositar los residuos recolectados en el contenedor correspondiente.
  * **Prioridad:** Alta
  * **Criterio de aceptación:** Dado que el jugador tiene residuos en su inventario, cuando selecciona el contenedor del color correcto para ese residuo, entonces el residuo se deposita con éxito y suma puntos; si elige un contenedor incorrecto, el sistema emite una alerta visual/sonora de error.

* **RF-05: Sistema de recompensa por monedas**
  * **Descripción:** El sistema debe otorgar una cantidad determinada de monedas al jugador por cada residuo recolectado y clasificado correctamente, actualizando el marcador total de monedas en la interfaz.
  * **Prioridad:** Media
  * **Criterio de aceptación:** Dado que el jugador clasifica correctamente un lote de basura en su contenedor, cuando se valida la entrega, entonces el contador de monedas en el HUD incrementa proporcionalmente a los aciertos obtenidos.

* **RF-06: Progresión de escenarios temáticos**
  * **Descripción:** El sistema debe permitir avanzar entre distintos entornos ecológicos (parque urbano, bosque y playa) una vez que el jugador cumple la meta de recolección y clasificación del nivel actual.
  * **Prioridad:** Media
  * **Criterio de aceptación:** Dado que el jugador alcanza la meta de basura recolectada y clasificada en el Nivel 1 (Parque), cuando finaliza la ronda, entonces el sistema desbloquea y carga el siguiente escenario (Bosque o Playa).

### 3.2 Requerimientos No Funcionales
* **RNF-01: Fluidez y tasa de fotogramas (Rendimiento)**
  * **Descripción:** El bucle principal del juego en Pygame debe ejecutarse de manera fluida manteniendo una tasa estable de 60 fotogramas por segundo (FPS) durante el desplazamiento y la recolección de objetos en mapas con múltiples *sprites* activos.
  * **Prioridad:** Alta
  * **Criterio de aceptación:** Al ejecutar el juego en una computadora de gama básica/media, no deben presentarse congelamientos superiores a 0.5 segundos al recoger objetos o cambiar de mapa.

* **RNF-02: Claridad visual de la interfaz (Usabilidad)**
  * **Descripción:** Todos los indicadores del HUD (temporizador, monedas, nivel y contadores de botellas, latas y papel) deben permanecer visibles en la esquina superior derecha e inferior derecha sin obstruir el área central de visión del personaje.
  * **Prioridad:** Media
  * **Criterio de aceptación:** Al iniciar cualquier nivel en resolución estándar (1280x720 o superior), los iconos de residuos y números son legibles sin superponerse con el personaje ni con los contenedores.

* **RNF-03: Compatibilidad y distribución ejecutable**
  * **Descripción:** El proyecto en Python debe poder empaquetarse como un archivo ejecutable independiente (`.exe` mediante PyInstaller) para sistemas operativos Windows 10/11 sin requerir que el usuario final tenga instalado Python ni Pygame.
  * **Prioridad:** Alta
  * **Criterio de aceptación:** Al ejecutar el archivo compilado del juego en una PC sin intérprete de Python instalado, el programa inicia en el menú principal sin errores de dependencias faltantes.
