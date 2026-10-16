# Instrucciones de integración y revisión — Monkey Ron v5

Trabaja en Windows con Construct 2. Carpeta de trabajo:
`C:\Users\Soul Hoshi\Documents\ChatGPT\PAL - Desarrollo de videojuegos`

Entrega que debes abrir:
`Entregas\Actuales\Monkey_Ron\Proyecto\Monkey_Ron_demo_v5.capx`

Los recursos ya están incorporados en ese CAPX: no vuelvas a importarlos por duplicado. Guarda los cambios con otro nombre y conserva el original del alumno:
`Juegos de alumnos\JuegoTeamAxel\monkeyron_con_menu.capx`.

## Qué conservar

Mantén el fondo, personaje y título del menú. Los botones deben seguir la estética de madera y pizarra. Conserva `aaron` como controlador invisible con Platform y ScrollTo, sus parámetros y su colisión fija. No lo destruyas al recibir daño ni cambies sus animaciones para representar las nuevas poses. No sustituyas los suelos Solid por Jumpthru.

## Dónde están las imágenes independientes

Dentro de la entrega: `Assets\Monkey_Ron\Demo_v2`, clasificadas en Fondos, Personaje, Coleccionables, HUD, Interfaz, Efectos, Obstaculos, Meta y Audio. Materiales y Menu están al mismo nivel de Demo_v2.

Copias de trabajo en el proyecto principal:
`Menus animados\Assets\Monkey_Ron\Juego\Demo_v2`
`Menus animados\Assets\Monkey_Ron\Juego\Materiales`
`Menus animados\Assets\Monkey_Ron\Menu`

Los PNG transparentes se importan como imágenes completas. No recortes automáticamente sus bordes ni regeneres sus polígonos de colisión. Son imágenes individuales; no son una cuadrícula de sprite sheet.

## Si debes incorporarlos a otro CAPX

| Recursos | Tipo y configuración |
|---|---|
| `Personaje/*.png` | Sprite `RonVisual`, animaciones `quieto`, `correr`, `saltar`, un fotograma cada una. Sin Platform, Solid ni colisión. Cada pose requiere su propio origen a los pies y tamaño indicado en `verificacion_estructural.json`; seguir al controlador con el desplazamiento vertical de sus pies. |
| `Coleccionables/moneda.png` | Imagen de los siete tipos originales Sprite6/7/8/9/11/12/13, animación `Moviendose`, un fotograma. Conservar tamaño 64×64 y colisión de recogida. Añadir Sine vertical de amplitud 6 y período 1,5 s; destruir tras puntuar una vez. |
| `Fondos/patio_jugable.png` | Sprite `PatioDemo` en capa de fondo. Instancias de 2000×1125 en X=0, 2000 y 4000, Y=0, origen superior izquierdo. Sin colisiones. Revisar las uniones jugando. |
| `Materiales/*.png` | Sprites decorativos sobre los sólidos originales, sin colisión. Repetir piezas, evitando estirar una sola textura sobre todo el nivel. El césped marca el borde superior del suelo. |
| `HUD/corazon.png` | Tres sprites en capa HUD con parallax 0,0. Atenuar los perdidos al 22 %; completos al 100 %. |
| `Interfaz/*.png` | Sprites sin colisión y objetos Text encima. Texto editable, coherente con el panel; evitar insertar el texto dentro de la imagen. |
| `Efectos/*.png` | `FXPolvo` y `FXBrillo`, sin colisión. Crear al saltar/aterrizar o recoger moneda. Fade con espera 0,04 s y desvanecimiento 0,28 s, destruir al terminar. |
| `Obstaculos/charco_senalizado.png` | Representación visible sin colisión física. Asociar al disparador Dead, franja 320×32 en X=4093,Y=992. No usar todo el rectángulo de la ilustración como daño. |
| `Meta/bandera_meta.png` | `MetaDemo` al final del recorrido, X=5632,Y=1000, origen a los pies. Su solapamiento activa victoria si hay vida, tiempo y apoyo en el suelo. |
| `Audio/*` | Importar sonidos según los formatos aceptados por la instalación. La entrega incluye OGG y M4A incorporados; WAV sirve de fuente. Reproducir por evento, sin bucle, con volumen moderado. |

No sobrescribas los recursos de Amy. Cada juego tiene sus propias carpetas y botones.

## Lógica y parámetros

`Estado`: 0 jugando, 1 pausa, 2 victoria, 3 derrota, 4 confirmar menú, 5 presentación inicial, 6 ayuda de partida.
Constantes: `VidasIniciales=3`, `TiempoInicial=120`, `ValorMoneda=100`, `BonusSegundo=5`, `TiempoInvulnerable=1.5`.

El tiempo solo disminuye jugando. Pausar usa escala temporal 0 e ignora controles; reanudar y salir al menú restauran 1. Evita alternar pausa dos veces en el mismo evento. La dirección usa 1=derecha/sin espejo y 0=izquierda/con espejo, según el enum nativo de Sprite Set mirrored. Los disparadores deben ir primero en los bloques de eventos.

La posición visible debe seguir los pies del controlador; el desplazamiento calculado para el controlador actual es aproximadamente 102,28 unidades por debajo de su Y. Los orígenes normalizados y tamaños de cada pose están en `verificacion_estructural.json`. No apliques un mismo origen arbitrario a las tres imágenes, porque tienen distinto espacio transparente.

## Prueba obligatoria en Construct 2

1. Abrir el CAPX y comprobar que no solicite plugins o archivos perdidos. Ejecutar desde el menú; verificar Jugar, Cómo jugar, Créditos y cierre con ESC.
2. Recorrer el nivel completo. Verificar que las piernas apoyen sin saltos visuales y que orientación, saltos y aterrizajes funcionen al mantener o soltar las flechas.
3. Recoger las siete monedas: una moneda debe sumar exactamente 100 puntos. Confirmar que todas son alcanzables y que el contador no se repite.
4. Probar ESC, PAUSA y SEGUIR. El reloj y el personaje deben detenerse. Comprobar que los botones de capas ocultas no respondan y que un clic no active dos acciones.
5. Abrir MENÚ, cancelar desde partida y desde pausa, y confirmar salida. Iniciar otra partida y comprobar velocidad normal.
6. Tocar el charco varias veces; verificar una vida por contacto válido, reaparición y 1,5 s de invulnerabilidad. Activar el punto de control antes del tramo difícil y verificar la reaparición posterior.
7. Agotar las vidas y el tiempo por separado. Comprobar derrota y reinicio limpio; llegar a META con y sin todas las monedas y revisar el bonus.
8. Medir lectura de plataformas, uniones del fondo, sonido y rendimiento en el equipo escolar. Ajustar dificultad a partir de una partida completa.
9. Exportar una copia y probar el resultado. Informar versión de Construct 2, navegador, errores reales y qué pruebas se completaron. No confundir las pruebas del modelo XML con ejecución del motor.

## Herramientas de reproducción

En `herramientas`: `construir_demo_monkey.py`, `verificar_logica_demo_monkey.py`, `previsualizar_demo_monkey.py`, `verificar_vista_demo_monkey.cjs` y `empaquetar_demo_monkey.py`. El constructor requiere las imágenes de origen registradas en `monkey_demo_assets_v2.json`; el ZIP es autónomo para abrir el CAPX y revisar sus recursos, pero no incluye esas rutas temporales de generación.

Antes de desarrollar nuevas animaciones, lee `PLAN_Y_CAMBIOS.md`: la carrera actual es una pose, no un ciclo completo. No afirmar que está terminada una animación de varios fotogramas ni que se ha probado en el motor sin hacerlo.


## Revisión v5

La pausa añade CÓMO JUGAR y MENÚ dentro del panel. La ayuda de partida mantiene el reloj detenido y vuelve a pausa mediante botón o ESC. Las monedas se recogen por solapamiento durante el estado de juego, de modo que un contacto iniciado durante la presentación no se pierde al habilitar los controles. Eliminar la moneda sigue impidiendo puntuar dos veces. El detalle del estado actual está en `REEVALUACION_v5.md`.


## Tipografía de v5

Ver `TIPOGRAFIA_Y_ENCUADRE.md`. Los botones del menú tienen texto nativo separado de la pizarra, con Luckiest Guy; las instrucciones utilizan Segoe UI normal. Se conservan las ilustraciones y el título gráfico. Los márgenes de los botones y las dimensiones del texto se comprueban en la entrega.
