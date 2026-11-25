# PROYECTO_INTEGRADOR_ECO_RUNNER
Videojuego educativo 2D en Python (Pygame) inspirado en el ODS 11: Recolecta, Corre, Clasifica y Gana.
<div align="center">

  <img src="3-pantallas/logo-ecorunner.png.jpg" alt="Logo Eco-Runner: Mundo Sano" width="340"/>

  # 🌱 ECO-RUNNER: MUNDO SANO — Videojuego Educativo Ambiental
  *Recolecta · Corre · Clasifica · Gana — Inspirado en el ODS 11 (Ciudades y Comunidades Sostenibles)*

  <br/>

  ![Lenguaje](https://img.shields.io/badge/LENGUAJE-PYTHON_3-3776AB?style=for-the-badge&logo=python&logoColor=white)
  ![Librería](https://img.shields.io/badge/MOTOR-PYGAME-2E7D32?style=for-the-badge)
  ![Género](https://img.shields.io/badge/GÉNERO-2D_TOP--DOWN_PIXEL_ART-1565C0?style=for-the-badge)
  ![ODS 11](https://img.shields.io/badge/IMPACTO-ODS_11_SOSTENIBILIDAD-F57C00?style=for-the-badge)

  <br/>

  *PROYECTO INTEGRADOR EN DESARROLLO · FASES DE ANÁLISIS, DISEÑO UML Y PROTOTIPADO DE PANTALLAS*

  <br/>

  [DESCRIPCIÓN](#descripción-del-proyecto) &nbsp;·&nbsp;
  [ESTRUCTURA](#estructura-del-repositorio) &nbsp;·&nbsp;
  [MECÁNICA](#mecánica-y-tecnologías) &nbsp;·&nbsp;
  [PERSONAJE](#diseño-del-personaje) &nbsp;·&nbsp;
  [PANTALLAS](#diseño-de-pantallas) &nbsp;·&nbsp;
  [EQUIPO](#equipo-de-desarrollo)

</div>

---

![Descripción](https://img.shields.io/badge/01-DESCRIPCIÓN_DEL_PROYECTO-2E7D32?style=for-the-badge)

## Descripción del proyecto

**Eco-Runner: Mundo Sano** es un videojuego 2D en perspectiva cenital (*top-down*) con estética *pixel art* desarrollado en **Python** mediante la librería **Pygame**, diseñado para fomentar la cultura del reciclaje y el cuidado de los espacios públicos en alineación con el **Objetivo de Desarrollo Sostenible 11 (Ciudades y Comunidades Sostenibles)**.

El jugador recorre distintos escenarios contaminados (parque urbano, bosque y playa) para recolectar residuos contrarreloj y clasificarlos correctamente en los contenedores de reciclaje a cambio de monedas.

---

![Estructura](https://img.shields.io/badge/02-ESTRUCTURA_DEL_REPOSITORIO-1565C0?style=for-the-badge)

## Estructura del repositorio

El proyecto documenta las primeras fases del ciclo de vida del desarrollo de software:

```text
PROYECTO_INTEGRADOR_ECO_RUNNER/
├── README.md                        # Documentación principal y presentación del proyecto
├── 1-requerimientos/                # Fase 1: Especificación de Requerimientos (IEEE 830)
│   └── SRS.md                       # Requerimientos funcionales, no funcionales y criterios de aceptación
├── 2-uml/                           # Fase 2: Modelado y Arquitectura del Sistema
│   └── diagramas.md                 # Diagramas de Casos de Uso, Clases y Secuencia
└── 3-pantallas/                     # Fase 3: Diseño de Interfaces (UI/UX) y Arte Conceptual
    ├── logo-ecorunner.png.jpg
    ├── 01-inicio.png.jpeg
    ├── 02-seleccion-nivel.png.jpeg
    ├── 03-juego-principal.png.jpeg
    ├── 04-clasificacion.png.jpg
    ├── 05-resultados.png.jpg
    └── 06-personaje.png.jpg
```
---
![Mecánica](https://img.shields.io/badge/03-MECÁNICA_Y_TECNOLOGÍAS-F57C00?style=for-the-badge)

## Mecánica y tecnologías

| Componente | Descripción |
| :--- | :--- |
| **Lenguaje y motor** | **Python 3 + Pygame** (gestión de *sprites*, detección de colisiones *hitbox*, bucle de juego a 60 FPS y renderizado de mapas 2D) |
| **Ciclo de juego** | **1. Recolecta** residuos en el mapa → **2. Corre** contra el temporizador → **3. Clasifica** en contenedores (Azul, Verde, Amarillo) → **4. Gana** monedas |
| **Escenarios** | Parque Urbano, Bosque y Playa (progresión por niveles) |
| **Modelado y UI** | Diagramas UML en **Mermaid** y galería de recursos visuales respaldada en **Google Drive** |

---

![Personaje](https://img.shields.io/badge/04-DISEÑO_DEL_PERSONAJE-2E7D32?style=for-the-badge)

## Diseño del personaje

| Vista conceptual (*Sprite Sheet*) | Características y rol |
| :---: | :--- |
| <img src="3-pantallas/06-personaje.png.jpg" alt="Diseño del personaje Eco-Runner" width="260"/> | **Protagonista (Eco-Runner):**<br>• **Estilo:** *Pixel art* 2D estructurado en *sprites* para **Pygame** (4 direcciones de movimiento: arriba, abajo, izquierda y derecha).<br>• **Indumentaria:** Playera verde ecológica con emblema de reciclaje y bolsa recolectora para almacenar residuos durante la ronda. |

---

![Pantallas](https://img.shields.io/badge/05-DISEÑO_DE_PANTALLAS-1565C0?style=for-the-badge)

## Diseño de pantallas

* **Enlace a todas las imágenes y diseño en Google Drive:** [Ver carpeta completa aquí](https://drive.google.com/drive/folders/1cHeQo8Ro_NuCf2HpUFBt1dOh6esDGxwZ?usp=drive_link)

| Pantalla | Vista previa | Descripción funcional |
| :--- | :---: | :--- |
| **1. Inicio** | <img src="3-pantallas/01-inicio.png.jpeg" width="220"/> | Menú principal con título del juego, botón de iniciar partida y opciones. |
| **2. Selección de Nivel** | <img src="3-pantallas/02-seleccion-nivel.png.jpeg" width="220"/> | Elección de escenario ecológico (Parque Urbano, Bosque o Playa). |
| **3. Juego Principal** | <img src="3-pantallas/03-juego-principal.png.jpeg" width="220"/> | Vista cenital con HUD en español (tiempo, nivel y contadores de residuos). |
| **4. Clasificación** | <img src="3-pantallas/04-clasificacion.png.jpg" width="220"/> | Interacción con contenedores de reciclaje por color para depositar la basura recolectada. |
| **5. Resultados** | <img src="3-pantallas/05-resultados.png.jpg" width="220"/> | Resumen de residuos clasificados, monedas ganadas y avance al siguiente nivel. |

---

![Equipo](https://img.shields.io/badge/06-EQUIPO_DE_DESARROLLO-1B2631?style=for-the-badge)

## Equipo de desarrollo

| Integrante | Rol en el proyecto | Usuario GitHub | Perfil y contacto |
| :--- | :--- | :--- | :--- |
| **Gamaliel López Pazos** | Análisis de requerimientos (SRS), lógica de juego en Python/Pygame y HUD | `@Gamalopez-18` | [github.com/Gamalopez-18](https://github.com/Gamalopez-18) |
| **Irving Emiliano Rivera Matus** | Modelado UML (Casos de uso, Clases, Secuencia) y diseño de interfaces/personaje | `@Kuruboy` | [github.com/Kuruboy](https://github.com/Kuruboy) |
