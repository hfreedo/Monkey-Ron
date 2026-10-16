# Monkey Ron — mejora de la demo v5

Entrega del 16 de octubre de 2026. Abrir `Monkey_Ron_demo_v5.capx` en Construct 2 y guardar una copia antes de editar. El proyecto original del alumno se conserva. Esta entrega contiene modificaciones nativas del proyecto, imágenes separadas y una vista HTML de sus pantallas.

## Lo encontrado y la solución preparada

| Hallazgo en el juego | Cambio en esta copia |
|---|---|
| Las monedas desaparecían sin puntuación ni respuesta clara. | Moneda dorada con estrella, movimiento vertical suave, 100 puntos, destello y sonido de recogida. |
| Cambiar de pose alteraba la colisión del personaje. | El objeto original `aaron` conserva la física y queda invisible; `RonVisual` representa las poses sin colisión. |
| El salto forzaba la orientación a la derecha y había una condición simultánea de subir y caer. | Dirección conservada y poses elegidas según suelo y movimiento; se elimina esa condición contradictoria. |
| La zona `Dead` era completamente transparente y destruía al jugador, dejando la partida sin continuación. | Charco azul con conos, pérdida de una vida, reaparición e invulnerabilidad temporal. Su disparador es una franja baja junto al suelo para permitir saltarlo. |
| Faltaban objetivo final, derrota y reintento. | Bandera META, victoria, derrota por vidas o tiempo y botones para reiniciar o regresar al menú. |
| Ayuda y créditos no tenían acciones completas. | Paneles funcionales con instrucciones y créditos editables. |
| Faltaban indicadores y pausa. | Corazones, puntos, monedas, reloj, PAUSA/SEGUIR, MENÚ y confirmación de salida. |
| La capa original de juego tenía parallax 0,0. | Se ajusta a 1,1 para que objetos físicos y monedas acompañen al escenario; solo la interfaz permanece fija. |
| Fondo de partida muy estirado y materiales poco coherentes. | Fondo nuevo de patio escolar repetido en tres tramos; tierra, césped y ladrillo con remate de piedra. Las plataformas finas tienen cuerpo de ladrillo para contrastar con el patio. |

Se mantienen el fondo, personaje y título del menú que ya gustaban al docente. Los botones de madera y pizarra se prolongan al HUD y a las pantallas especiales. No se añadieron nombres inventados a los créditos.

## Reglas propuestas para una demo breve

- Comenzar con tres vidas y 120 segundos; presentación inicial de un segundo.
- Flechas izquierda/derecha para moverse y arriba para saltar. ESC o el botón permite pausar.
- Siete monedas opcionales de 100 puntos cada una; no se exige recogerlas todas para terminar.
- Llegar a la bandera, situada hacia X=5632, estando en el suelo y con vida y tiempo disponibles.
- Bonus de victoria: cinco puntos por cada segundo entero restante, aplicado una vez.
- Un daño resta un corazón y devuelve al último punto seguro; 1,5 segundos de invulnerabilidad y parpadeo evitan daño encadenado.
- Punto de control al recorrer el suelo entre X=3000 y X=3400. Reaparición en X=3104, Y=896.
- Cero vidas o tiempo agotado muestra derrota. Si el tiempo se agota al tocar la meta, tiene prioridad la derrota.
- Pausa detiene el reloj y la física. Salir al menú requiere confirmación; cancelar recupera el estado anterior. Reiniciar restaura tiempo, vidas y monedas.

Los parámetros de plataforma del alumno se conservan: velocidad 500, salto 650 y gravedad 1500. La altura teórica de salto es aproximadamente 141 unidades. El hueco de 320 unidades del tramo final tiene un alcance teórico suficiente a velocidad máxima, pero esto debe comprobarse jugando: las cifras no prueban que el recorrido sea cómodo ni que todas las monedas sean alcanzables.

## Assets incluidos y uso

| Carpeta dentro de `Assets/Monkey_Ron` | Contenido y empleo |
|---|---|
| `Menu` | Arte anterior de menú y botones temáticos; conservar el fondo, personaje, título y escudo existentes. |
| `Materiales` | Ladrillo, piedra, tierra y césped. Decoración sin colisión sobre los sólidos originales. |
| `Demo_v2/Fondos` | Patio escolar de partida, opaco y sin título ni personaje; tres instancias con proporciones próximas a las de la imagen. |
| `Demo_v2/Personaje` | Poses transparentes quieto, correr y saltar, orientadas a la derecha; representación independiente de la física. |
| `Demo_v2/Coleccionables` | Moneda transparente, una imagen con oscilación nativa; todavía no es un giro con múltiples fotogramas. |
| `Demo_v2/HUD` | Corazón completo; los perdidos se atenúan mediante opacidad. |
| `Demo_v2/Interfaz` | Panel y botón vacíos para poner texto editable de Construct encima. |
| `Demo_v2/Efectos` | Polvo al saltar/aterrizar y destello al recoger monedas, creados por evento y eliminados con Fade. |
| `Demo_v2/Obstaculos` | Charco señalizado, asociado a la zona de daño. |
| `Demo_v2/Meta` | Bandera visible de final de demo. |
| `Demo_v2/Audio` | Seis efectos breves: salto, aterrizaje, moneda, daño, victoria y derrota; copias WAV, OGG y M4A. |

Las doce imágenes nuevas se generaron y están incorporadas en el CAPX. `inventario_assets.json` registra dimensiones, transparencia y huellas. `prompts.json` conserva las instrucciones de generación. Las tres poses del personaje son un fotograma por estado; no se presenta una animación completa de carrera.

## Plan de mejora y orden de trabajo

1. **Validación en el motor, antes de ampliar contenido.** Abrir el CAPX, comprobar dependencias, ejecutar el menú y recorrer la demo completa con teclado. Revisar apoyos, saltos, monedas altas, daño y meta. Ajustar posiciones si una prueba real lo requiere.
2. **Ajustar dificultad con alumnos.** Observar tres partidas sin ayuda, contar saltos fallidos y tiempo de llegada. Modificar `TiempoInicial` y posiciones de monedas según los resultados. Añadir un aviso o flecha al punto de control si pasa inadvertido.
3. **Animación del personaje.** Preparar una carrera de 6–8 fotogramas, reposo de 2–4, anticipación de salto y aterrizaje de 2–3. Igualar tamaño aparente, eje de cadera y apoyo de los pies; revisar rodillas y zapatillas cuadro a cuadro. Mantener independiente la colisión estable de `aaron`.
4. **Respuesta al jugar.** Ampliar el polvo a una secuencia de 4–6 fotogramas, añadir un pequeño indicador de +100 y un brillo al activar el punto de control. Ensayar tolerancia breve al borde y salto almacenado solo después de comprobar la física actual. Estas mejoras adicionales no están implementadas en esta entrega.
5. **Pulido y rendimiento.** Revisar uniones del fondo y lectura de plataformas en movimiento. Actualmente hay 274 piezas decorativas que reutilizan imágenes. Medir en el equipo escolar; si hace falta, optimizar copias de texturas en el editor y sustituir repeticiones por Tiled Background manteniendo los sólidos originales. Añadir volumen/silencio y créditos definitivos.

## Verificación realizada y límite

- CAPX descomprimible, XML legible y referencias de imágenes comprobadas.
- Parámetros físicos conservados y arte principal del menú idéntico al origen.
- Veintidós comprobaciones del **modelo de eventos XML**: puntuación única, daño e invulnerabilidad, pausa y reloj, reinicio, victoria/derrota, confirmación de salida, dirección y paneles del menú. Detalle en `pruebas_logica.json`.
- Composiciones de doce pantallas extraídas del CAPX, revisables en `Vista/Vista_demo.html`. Sus valores del HUD son ejemplos.

**Pendiente:** abrir, ejecutar y exportar en Construct 2. El modelo no ejecuta su motor, su física ni su sistema real de selección de objetos. La vista HTML tampoco es un juego ejecutable. No se garantiza aún un recorrido completo ni compatibilidad de exportación.


## Revisión v5

La pausa añade CÓMO JUGAR y MENÚ dentro del panel. La ayuda de partida mantiene el reloj detenido y vuelve a pausa mediante botón o ESC. Las monedas se recogen por solapamiento durante el estado de juego, de modo que un contacto iniciado durante la presentación no se pierde al habilitar los controles. Eliminar la moneda sigue impidiendo puntuar dos veces. El detalle del estado actual está en `REEVALUACION_v5.md`.


## Corrección de carga de audio

Se corrigió el registro del audio: Construct 2 utiliza `sounds-folder`, en plural. El CAPX anterior registraba los archivos en una etiqueta incorrecta y el motor mostraba “Audio filename cannot be found in project”. La nueva comprobación revisa cada acción Audio Play contra los sonidos registrados y verifica que los archivos existan dentro del CAPX. El resultado actual es 22 pruebas PASS del modelo y estructura; sigue pendiente confirmar la apertura en el motor.


## Tipografía de v5

Ver `TIPOGRAFIA_Y_ENCUADRE.md`. Los botones del menú tienen texto nativo separado de la pizarra, con Luckiest Guy; las instrucciones utilizan Segoe UI normal. Se conservan las ilustraciones y el título gráfico. Los márgenes de los botones y las dimensiones del texto se comprueban en la entrega.
