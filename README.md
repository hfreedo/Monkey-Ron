# 🐵 Monkey Ron — Aventura en la Escuela (Monkey Games)

<p align="center">
  <img src="Portadas/Portada_Monkey_Ron_Monkey_Games_PC_Demo_v1.png" alt="Portada Monkey Ron - Monkey Games" width="760">
</p>

<p align="center">
  <a href="https://github.com/hfreedo/Monkey-Ron/releases/latest/download/Monkey_Ron_demo_v5.capx">
    <img src="https://img.shields.io/badge/🎮_Descargar_Proyecto_Construct_2-Monkey__Ron__demo__v5.capx-2ea44f?style=for-the-badge" alt="Descargar CAPX v5">
  </a>
  <a href="https://github.com/hfreedo/Monkey-Ron/releases/latest/download/Monkey_Ron_actual.zip">
    <img src="https://img.shields.io/badge/📦_Descargar_Paquete_Completo-Monkey__Ron__actual.zip-0969da?style=for-the-badge" alt="Descargar ZIP Completo">
  </a>
</p>

---

## 👋 ¡Bienvenidos al repositorio oficial de Monkey Ron!

Este repositorio contiene el proyecto actualizado de **Monkey Ron** (desarrollado en **Construct 2** por el equipo **Monkey Games** / Team Axel), junto con todos sus recursos gráficos, sonidos, vistas previas de pantallas y los materiales listos para imprimir para la feria/exposición escolar.

---

## 📥 1. ¿Cómo descargar el juego? (Guía para alumnos)

Tienes **tres formas sencillas** de descargar los archivos según lo que necesites hacer:

1. **Solo quiero abrir el juego actualizado en Construct 2 (Recomendado):**
   - Haz clic en el botón verde superior **🎮 Descargar Proyecto Construct 2 (`Monkey_Ron_demo_v5.capx`)** o entra en [`Proyecto/Monkey_Ron_demo_v5.capx`](Proyecto/Monkey_Ron_demo_v5.capx) y pulsa **Download raw file**.
2. **Quiero el paquete completo de la entrega (`.zip` con proyecto + imágenes + vistas):**
   - Haz clic en el botón azul **📦 Descargar Paquete Completo (`Monkey_Ron_actual.zip`)** o visita la sección [**Releases (Lanzamientos)**](https://github.com/hfreedo/Monkey-Ron/releases).
3. **Quiero descargar todo el repositorio (incluyendo manuales, stickers, portanombres y versiones originales):**
   - Arriba a la derecha en esta página de GitHub, haz clic en el botón verde **`<> Code`** y selecciona **`Download ZIP`**. Extrae el archivo `.zip` en tu computadora.

> [!IMPORTANT]
> **Consejo antes de editar en Construct 2:** Cuando abras `Monkey_Ron_demo_v5.capx`, guarda primero una copia con otro nombre (por ejemplo, `Monkey_Ron_demo_v5_prueba.capx`) para conservar siempre intacta la versión base.

---

## 🖼️ 2. Vista previa de las pantallas (Demo v5)

| Menú Principal | Partida y HUD |
|:---:|:---:|
| ![Menú Principal](Proyecto/Vista/menu.png) | ![Partida en curso](Proyecto/Vista/juego.png) |

| Menú de Pausa | Pantalla de Victoria |
|:---:|:---:|
| ![Menú de Pausa](Proyecto/Vista/pausa.png) | ![Pantalla de Victoria](Proyecto/Vista/victoria.png) |

💡 *Puedes inspeccionar las 12 pantallas interactivas abriendo el archivo [`Proyecto/Vista/Vista_demo.html`](Proyecto/Vista/Vista_demo.html) en tu navegador luego de descargar el repositorio.*

---

## 🎮 3. Controles y Reglas de la Demo v5

### Controles
- **Flechas Izquierda / Derecha (`←` / `→`):** Mover a Ron por el patio escolar.
- **Flecha Arriba (`↑`):** Saltar obstáculos y subir a las plataformas.
- **Tecla `ESC` o botón `PAUSA`:** Pausar la partida, consultar las instrucciones (`CÓMO JUGAR`), reiniciar o volver al menú.

### Reglas del juego implementadas
- **Vidas:** Comienzas con **3 corazones**. Tocar el charco con conos resta 1 corazón, te devuelve al último punto seguro y te da **1,5 segundos de invulnerabilidad** con parpadeo.
- **Tiempo:** Tienes **120 segundos** para llegar a la meta. El reloj se detiene automáticamente cuando abres la Pausa o la Ayuda.
- **Monedas y Puntuación:** Hay **7 monedas doradas** en el recorrido (**100 puntos** cada una). No es obligatorio juntarlas todas para ganar, ¡pero suman para tu récord!
- **Punto de Control (Checkpoint):** Al cruzar el tramo entre `X = 3000` y `X = 3400`, se guarda tu progreso para reaparecer en `X = 3104, Y = 896`.
- **Meta y Bonus de Victoria:** Al llegar a la **bandera META** (`X = 5632`) con vida y tiempo restantes, ganas la partida y recibes un **bonus de +5 puntos por cada segundo restante**.

---

## 🛠️ 4. ¿Qué incluye la versión `v5` y cómo funciona por dentro?

Si vas a revisar o modificar el proyecto en **Construct 2**, ten en cuenta cómo está armado:

| Sistema | Cómo está implementado en `Monkey_Ron_demo_v5.capx` |
|---|---|
| **Física vs. Dibujo del Personaje** | El objeto original `aaron` maneja la física y las colisiones (permanece invisible para que cambiar de pose no trabe al personaje). El sprite `RonVisual` sigue a `aaron` y muestra las poses (`quieto`, `correr`, `saltar`). |
| **Escenario y Cámara** | La capa de juego tiene `Parallax 1,1` para acompañar el movimiento, mientras que el HUD y los paneles tienen `Parallax 0,0` para quedarse fijos en pantalla. |
| **Audio corregido** | Los 6 efectos de sonido (`salto`, `aterrizaje`, `moneda`, `daño`, `victoria`, `derrota`) están registrados en `sounds-folder` en formatos WAV, OGG y M4A listos para Construct 2. |
| **Tipografía** | Los botones usan la fuente temática **Luckiest Guy** sobre pizarra vacía (`boton_pizarra_vacio.png`), permitiendo editar los textos directamente en Construct 2. |

### 📋 Próximos pasos recomendados para el equipo en clase
1. **Abrir y probar en Construct 2:** Recorrer `Menú → Partida → Pausa → Cómo jugar → Victoria / Derrota` para verificar todos los saltos y monedas.
2. **Completar los Créditos:** Escribir los nombres reales de los integrantes del equipo en el panel de Créditos.
3. **Ajustar dificultad si hace falta:** Probar con compañeros y ajustar la posición de monedas o la variable `TiempoInicial` si el recorrido resulta muy fácil o muy difícil.

Para más detalles técnicos, consulta:
- 📄 [`Proyecto/PLAN_Y_CAMBIOS.md`](Proyecto/PLAN_Y_CAMBIOS.md) — Explicación detallada de cada mejora y reglas.
- 📄 [`Proyecto/REEVALUACION_v5.md`](Proyecto/REEVALUACION_v5.md) — Estado de cada sistema y lista de verificación.
- 📄 [`Proyecto/TIPOGRAFIA_Y_ENCUADRE.md`](Proyecto/TIPOGRAFIA_Y_ENCUADRE.md) — Fuentes y tamaños de texto.

---

## 🖨️ 5. Materiales Imprimibles para la Exposición (`Imprimibles_Monkey_Games/`)

Todos los materiales gráficos del stand de **Monkey Games** están listos en formato **PDF A4** (para imprimir al 100 % sin escalar) y cuentan con archivos editables `.svg`:

| Material | Archivo PDF listo para imprimir (A4) | Vista previa / Instrucciones |
|---|---|---|
| **1. Portanombre de Mesa (v4)** | [`Portanombre_Monkey_Ron_Monkey_Games_A4_v4.pdf`](Imprimibles_Monkey_Games/01_Portanombres/Imprimir/Portanombre_Monkey_Ron_Monkey_Games_A4_v4.pdf) | Plegable doble cara con espacio para el nombre del alumno. [Ver vista previa](Imprimibles_Monkey_Games/01_Portanombres/Vista_previa/Cara_Monkey_Ron.png) |
| **2. Plancha de Stickers (v1)** | [`Plancha_Stickers_Monkey_Games_A4_v1.pdf`](Imprimibles_Monkey_Games/02_Stickers/Imprimir/Plancha_Stickers_Monkey_Games_A4_v1.pdf) | 9 stickers por hoja A4 (Insignia, Moneda y Ron). [Leer guía](Imprimibles_Monkey_Games/02_Stickers/LEEME.md) |
| **3. Manual de Juego (v2)** | [`Manual_Monkey_Ron_Cuadernillo_A4_v2.pdf`](Imprimibles_Monkey_Games/03_Manual_de_Juego/Imprimir/Manual_Monkey_Ron_Cuadernillo_A4_v2.pdf) · [Versión Digital](Imprimibles_Monkey_Games/03_Manual_de_Juego/Digital/Manual_Monkey_Ron_12x18_v2.pdf) | Librito de 4 páginas (12 × 18 cm) con controles, objetivo y consejos. [Leer guía de plegado](Imprimibles_Monkey_Games/03_Manual_de_Juego/LEEME.md) |
| **4. Credenciales del Equipo (v1)** | [`Credencial_Monkey_Games_90x120_v1_A4.pdf`](Imprimibles_Monkey_Games/04_Credenciales/Imprimir/Credencial_Monkey_Games_90x120_v1_A4.pdf) | 4 credenciales de 9 × 12 cm por hoja A4 con nombre y rol. [Leer guía](Imprimibles_Monkey_Games/04_Credenciales/LEEME.md) |
| **5. Portada Promocional** | [`Portada_Monkey_Ron_Monkey_Games_12x18_A4_v1.pdf`](Imprimibles_Monkey_Games/05_Portada_Imprimible/Imprimir/Portada_Monkey_Ron_Monkey_Games_12x18_A4_v1.pdf) | Portada lista para recortar a 12 × 18 cm. [Leer guía](Imprimibles_Monkey_Games/05_Portada_Imprimible/LEEME.md) |

---

## 📂 6. Estructura de carpetas del repositorio

```text
Monkey-Ron/
├── Proyecto/                         # Versión vigente mejorada (Demo v5)
│   ├── Monkey_Ron_demo_v5.capx       # ⭐ Archivo principal para abrir en Construct 2
│   ├── Assets/                       # Sprites, fondos, sonidos y fuente Luckiest Guy
│   ├── Vista/                        # Vista previa HTML y capturas de las 12 pantallas
│   ├── PLAN_Y_CAMBIOS.md             # Resumen de mejoras y reglas de juego
│   └── REEVALUACION_v5.md            # Estado técnico de los sistemas en v5
├── Proyecto_Original/                # Primeras versiones creadas por los alumnos
│   ├── monkeyronn.capx               # Proyecto original base
│   └── monkeyron_con_menu.capx       # Primera versión con menú integrado
├── Menu_Animado/                     # Video MP4 y render de referencia del menú
├── Portadas/                         # Ilustraciones de portada en alta resolución
└── Imprimibles_Monkey_Games/         # PDFs A4 y editables SVG para el stand escolar
    ├── 01_Portanombres/
    ├── 02_Stickers/
    ├── 03_Manual_de_Juego/
    ├── 04_Credenciales/
    └── 05_Portada_Imprimible/
```
