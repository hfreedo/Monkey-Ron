# 🐵 Monkey Ron — Aventura en la Escuela (Monkey Games)

<p align="center">
  <img src="Portadas/Portada_Monkey_Ron_Retail_PC_Demo_v2.png" alt="Portada Monkey Ron - Monkey Games Retail" width="760">
</p>

<p align="center">
  <a href="https://github.com/hfreedo/Monkey-Ron/releases/latest/download/Monkey_Ron_demo_v8.capx">
    <img src="https://img.shields.io/badge/🎮_Descargar_Proyecto_Construct_2-Monkey__Ron__demo__v8.capx-2ea44f?style=for-the-badge" alt="Descargar CAPX v8">
  </a>
  <a href="https://github.com/hfreedo/Monkey-Ron/releases/latest/download/Monkey_Ron_actual_v8.zip">
    <img src="https://img.shields.io/badge/📦_Descargar_Paquete_Completo-Monkey__Ron__v8.zip-0969da?style=for-the-badge" alt="Descargar ZIP Completo">
  </a>
</p>

---

## 👋 ¡Bienvenidos al repositorio oficial de Monkey Ron!

Este repositorio contiene la versión más reciente del proyecto **Monkey Ron** (desarrollado en **Construct 2** por el equipo **Monkey Games** / Team Axel): la **Demo v8**, que incorpora el **ciclo completo de animaciones cuadro por cuadro del personaje Ron** (quieto, correr, saltar y agacharse), nuevos enemigos, física calibrada, menús con pausa y la colección completa de materiales imprimibles listos para el stand escolar.

---

## 📥 1. ¿Cómo descargar el juego? (Guía para alumnos)

Tienes **tres opciones** según lo que necesites:

1. **Quiero abrir directamente la versión más nueva en Construct 2 (⭐ Recomendado):**
   - Haz clic en el botón verde superior **🎮 Descargar Proyecto Construct 2 (`Monkey_Ron_demo_v8.capx`)** o entra en [`Proyecto/Monkey_Ron_demo_v8.capx`](Proyecto/Monkey_Ron_demo_v8.capx) y pulsa **Download raw file**.
2. **Quiero descargar el paquete completo con proyecto y assets:**
   - Haz clic en el botón azul **📦 Descargar Paquete Completo** o visita la sección [**Releases (Lanzamientos)**](https://github.com/hfreedo/Monkey-Ron/releases).
3. **Quiero descargar todo el repositorio (imprimibles, manuales v3, stickers, GIFs y versiones anteriores):**
   - Arriba a la derecha en esta página de GitHub, haz clic en el botón verde **`<> Code`** y selecciona **`Download ZIP`**. Luego descomprime el archivo en tu computadora.

> [!IMPORTANT]
> **Consejo antes de editar en Construct 2:** Abre `Monkey_Ron_demo_v8.capx` y guárdalo como una copia (por ejemplo, `Monkey_Ron_demo_v8_mis_pruebas.capx`) antes de realizar cambios.

---

## ✨ 2. Novedades de la Demo v8 (Animaciones del Personaje y Agacharse)

La **versión v8** reemplaza las poses estáticas anteriores por un sistema dinámico de animación cuadro a cuadro y una nueva mecánica de juego:

| Animación en el juego | Fotogramas | Comportamiento en pantalla |
|---|:---:|---|
| **Quieto (`quieto`)** | 8 frames | Bucle continuo natural a 150 ms/cuadro cuando Ron está quieto en el suelo. |
| **Correr (`correr`)** | 8 frames | Ciclo de carrera fluido coordinado con el avance del jugador. |
| **Saltar (`saltar`)** | 6 frames | Se activa al iniciar el salto y sostiene la pose en el aire hasta tocar suelo. |
| **Agacharse (`agacharse`)** | 6 frames | **¡Nueva mecánica!** Mantén pulsada la **Flecha Abajo (`↓`)** en el suelo para agacharte. |

### 🔍 ¿Cómo funciona agacharse en Construct 2?
- **Reducción de colisión:** La altura del cuerpo físico invisible (`aaron`) pasa de `204 px` a **`160 px`**, permitiendo que Ron pase por debajo de obstáculos o techos bajos.
- **Control seguro:** Mientras estés agachado, el movimiento y el salto se bloquean temporalmente.
- **Detección de techo (Clearance):** Al soltar la flecha abajo, Ron **solo se levanta si no hay un techo sólido encima**, evitando que el personaje quede atrapado dentro de las plataformas.

---

## 🎮 3. Controles y Reglas de la Partida

### Controles
- **Flechas Izquierda / Derecha (`←` / `→`):** Desplazar a Ron por el escenario.
- **Flecha Arriba (`↑`):** Saltar plataformas y evitar obstáculos.
- **Flecha Abajo (`↓`):** Agacharse en el suelo para reducir altura.
- **Tecla `ESC` o botón `PAUSA`:** Detener la partida, revisar el panel de ayuda (`CÓMO JUGAR`), reiniciar o volver al menú.

### Reglas del juego
- **3 Vidas (Corazones):** Tocar obstáculos de daño resta un corazón, activa **1,5 s de invulnerabilidad** con parpadeo y te sitúa en el punto seguro más cercano.
- **Tiempo límite:** 120 segundos para completar el recorrido escolar.
- **Monedas doradas (7 en total):** Cada moneda otorga **100 puntos**.
- **Bandera META y Checkpoint:** Reaparición intermedia registrada en `X = 3104` y llegada victoriosa en `X = 5632` con bonus por tiempo restante.

---

## 🖼️ 4. Vista previa de Pantallas

| Menú Principal | Partida y HUD |
|:---:|:---:|
| ![Menú Principal](Proyecto/Vista/menu.png) | ![Partida en curso](Proyecto/Vista/juego.png) |

| Menú de Pausa | Pantalla de Victoria |
|:---:|:---:|
| ![Menú de Pausa](Proyecto/Vista/pausa.png) | ![Pantalla de Victoria](Proyecto/Vista/victoria.png) |

---

## 🎨 5. Nuevos Assets Gráficos y Animaciones Incluidas

Dentro de la carpeta [`Proyecto/Assets/Monkey_Ron/`](Proyecto/Assets/Monkey_Ron/) encontrarás:
- **`Personaje/Animaciones_v8/`:** Fotogramas PNG transparentes individuales organizados en carpetas (`quieto/`, `correr/`, `saltar/`, `agacharse/`) y el mapa de colisiones `Colisiones_Ron_v8.png`.
- **`Animaciones_GIF/`:** Archivos `.gif` originales con todas las secuencias (`iddle ron.gif`, `run ron.gif`, `salto ron.gif`, `agacha ron.gif`, `hechizo.gif`, `Iddle examen.gif`, `Walking examen.gif`).
- **`Enemigos/Examen/`:** Ilustración y diseño del nuevo enemigo temático escolar (`Examen_enemigo_v1.png`).

---

## 🖨️ 6. Materiales Imprimibles para la Exposición (`Imprimibles_Monkey_Games/`)

Todos los archivos listos para imprimir en **PDF A4** al 100 %:

| Material | Archivo PDF listo para imprimir (A4) | Vista previa / Instrucciones |
|---|---|---|
| **1. Portanombre de Mesa (v4)** | [`Portanombre_Monkey_Ron_Monkey_Games_A4_v4.pdf`](Imprimibles_Monkey_Games/01_Portanombres/Imprimir/Portanombre_Monkey_Ron_Monkey_Games_A4_v4.pdf) | Plegable doble cara con espacio para el nombre del alumno. [Ver vista previa](Imprimibles_Monkey_Games/01_Portanombres/Vista_previa/Cara_Monkey_Ron.png) |
| **2. Colección Completa de Stickers (v2)** | [`Stickers_Monkey_Games_Coleccion_completa_A4_v2.pdf`](Imprimibles_Monkey_Games/02_Stickers/Imprimir/Stickers_Monkey_Games_Coleccion_completa_A4_v2.pdf) | **6 motivos nuevos:** Insignia, Moneda, Ron, Ron con Bandera, Pulgar Arriba y Señalando (2 hojas A4). [Leer guía](Imprimibles_Monkey_Games/02_Stickers/LEEME.md) |
| **3. Manual de Juego (v3)** | [`Manual_Monkey_Ron_Cuadernillo_A4_v3.pdf`](Imprimibles_Monkey_Games/03_Manual_de_Juego/Imprimir/Manual_Monkey_Ron_Cuadernillo_A4_v3.pdf) · [Versión Digital v3](Imprimibles_Monkey_Games/03_Manual_de_Juego/Digital/Manual_Monkey_Ron_12x18_v3.pdf) | Cuadernillo de 4 páginas (12 × 18 cm) con avatares ilustrados, controles, objetivo y consejos. [Leer guía](Imprimibles_Monkey_Games/03_Manual_de_Juego/LEEME.md) |
| **4. Credenciales del Equipo (v1)** | [`Credencial_Monkey_Games_90x120_v1_A4.pdf`](Imprimibles_Monkey_Games/04_Credenciales/Imprimir/Credencial_Monkey_Games_90x120_v1_A4.pdf) | 4 credenciales de 9 × 12 cm por hoja A4 con nombre y rol para completar. [Leer guía](Imprimibles_Monkey_Games/04_Credenciales/LEEME.md) |
| **5. Portada Retail y Cuadro (v2)** | [`Portada_Monkey_Ron_Monkey_Games_12x18_A4_v2.pdf`](Imprimibles_Monkey_Games/05_Portada_Imprimible/Imprimir/Portada_Monkey_Ron_Monkey_Games_12x18_A4_v2.pdf) · [Portada Digital v2](Portadas/Portada_Monkey_Ron_Retail_PC_Demo_v2.png) | Carátula retail para exhibidor o caja de 12 × 18 cm. [Leer guía](Imprimibles_Monkey_Games/05_Portada_Imprimible/LEEME.md) |

---

## 📂 7. Estructura de carpetas del repositorio

```text
Monkey-Ron/
├── Proyecto/
│   ├── Monkey_Ron_demo_v8.capx       # ⭐ PROYECTO PRINCIPAL (Demo v8 con animaciones y agacharse)
│   ├── Monkey_Ron_demo_v5.capx       # Versión anterior de referencia
│   ├── Assets/                       # Biblioteca de Sprites, Animaciones v8, Enemigos y Fuentes
│   │   ├── Monkey_Ron/Animaciones_GIF/ # GIFs originales (correr, quieto, salto, agacharse, examen)
│   │   ├── Monkey_Ron/Enemigos/      # Ilustraciones de enemigos (Examen)
│   │   └── Monkey_Ron/Personaje/     # Cuadros PNG individuales de cada animación
│   ├── Vista/                        # Vista interactiva HTML y capturas de pantalla
│   └── PLAN_Y_CAMBIOS.md             # Documentación técnica de desarrollo
├── Proyecto_Original/                # Versiones históricas entregadas por los alumnos
├── Portadas/                         # Portada Retail v2 y artes promocionales
└── Imprimibles_Monkey_Games/         # PDFs A4 y SVGs editables para el stand escolar
```
