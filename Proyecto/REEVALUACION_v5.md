# Monkey Ron — reevaluación del proyecto integrado

16 de octubre de 2026. Archivo que debes usar: **Monkey_Ron_demo_v5.capx**. El fondo y los demás recursos están dentro del proyecto; no es necesario importarlos otra vez. Las versiones anteriores y la entrega del alumno permanecen conservadas.

## Estado de assets y funcionalidad

En esta tabla, «incorporado» significa presente en el CAPX y enlazado mediante sus eventos. La ejecución en el motor sigue pendiente.

| Sistema | Assets aplicados | Funcionalidad en el CAPX | Qué falta |
|---|---|---|---|
| Menú principal | Fondo, personaje y título anteriores; botones de madera/pizarra; escudo existente | Jugar, Cómo jugar, Créditos, cierre de panel y restauración del tiempo de juego al volver | Completar los autores reales. Ajustes de audio opcionales. |
| Fondo de partida | Patio escolar de 1672×941, tres instancias de 2000×1125 | Capa de fondo; no interviene en colisiones | Revisar las uniones en movimiento. No se presenta como panorama continuo sin costuras. |
| Suelo y plataformas | Ladrillo, piedra, tierra y césped; 274 piezas visuales reutilizadas | Colisiones Solid originales conservadas debajo de la decoración | Medir rendimiento y revisar lectura durante saltos. |
| Personaje | Tres PNG transparentes: quieto, correr, saltar | Sprite visible sigue al controlador invisible; dirección y colisión independientes de las poses | Ciclo de carrera, anticipación y aterrizaje con varios fotogramas. Las tres poses actuales no son una animación completa. |
| Vida | Tres corazones en el HUD; perdidos atenuados | Tres impactos disponibles, reaparición, punto de control e invulnerabilidad de 1,5 s | No hay barra continua de salud: esta demo usa vidas discretas. Una barra sería necesaria si se introduce daño gradual o salud numérica adicional. |
| Puntos y monedas | Moneda dorada, contador y destello | 100 puntos por moneda, contador 0/7 y bonus de victoria; cada moneda se elimina una vez | Giro de moneda con varios fotogramas y texto flotante +100, como pulido posterior. |
| Tiempo | Tarjeta y contador del HUD | 120 segundos, detenido en pausa y ayuda; derrota al agotarse | Ajustar duración después de partidas reales de alumnos. |
| Botones durante partida | PAUSA/SEGUIR y MENÚ con texto editable | Pausa por ESC o clic; salida confirmada; cancelar recupera partida o pausa anterior | Probar clics y foco del navegador dentro del motor. |
| Panel de pausa | CONTINUAR, REINICIAR, CÓMO JUGAR y MENÚ | Reanudar, reiniciar limpio, abrir ayuda o pedir salida | Las cuatro acciones están enlazadas; comprobar ejecución real. |
| Ayuda durante partida | Panel temático y VOLVER A PAUSA | Estado propio con tiempo detenido; regresar mediante botón o ESC | Sin faltante de contenido básico. |
| Daño | Charco visible con conos, parpadeo y sonido | Franja de contacto junto al suelo; resta una vida y devuelve a punto seguro | Comprobar saltabilidad y claridad del obstáculo jugando. |
| Victoria | Bandera META y panel de resultado | Llegar con vida y tiempo, monedas opcionales, bonus una vez, reintento o menú | Animación celebratoria como mejora posterior. |
| Derrota | Panel temático y botones reutilizados | Distingue falta de vidas y tiempo agotado; reinicio o menú | Sin faltante de pantalla básica. |
| Efectos y audio | Polvo, destello y seis sonidos en WAV/OGG/M4A | Salto, aterrizaje, recogida, daño, victoria y derrota | Efectos con secuencias de varios fotogramas y control de volumen/silencio. |

## Correcciones específicas de esta revisión

1. Se incorporan los botones **CÓMO JUGAR** y **MENÚ** dentro del panel de pausa, además de los accesos del HUD.
2. La ayuda de partida tiene estado 6; no consume tiempo ni reanuda automáticamente. El botón y ESC regresan a pausa.
3. Recoger monedas usa solapamiento mientras se juega, en lugar de depender únicamente del instante inicial de colisión. Así se contempla una moneda que ya se estaba tocando al terminar la presentación o al reanudar. Su destrucción impide puntuación repetida.
4. Se mantienen las correcciones previas de cámara: parallax 1,1 para escenario y objetos físicos, 0,0 para HUD y paneles. El fondo original estirado queda oculto.

## Comprobaciones y alcance

- Veintidós pruebas del modelo de eventos XML pasan; las cuatro nuevas cubren ayuda desde pausa, menú desde pausa y recogida de monedas después de presentación/pausa.
- Doce composiciones de pantalla cargan sin imágenes perdidas, errores JavaScript ni desbordamiento vertical de texto. No son una exportación jugable.
- El inventario registra los recursos y sus hashes; las imágenes nuevas se verifican contra los PNG incorporados al CAPX.
- El empaquetado comprueba ZIP/XML, conservación del original, posiciones y comportamientos de los suelos y colisiones originales. Los sonidos se decodifican y el paquete se prueba desde otra carpeta de extracción.

**No se ha abierto, ejecutado ni exportado esta revisión en Construct 2.** Las pruebas de modelo no validan la física, el orden real de selección de objetos, los clics simultáneos, el sonido en el navegador ni la dificultad del recorrido. No se deben dar estos puntos por aprobados.

## Orden recomendado para cerrar la demo

1. Abrir v5 en Construct 2 y recorrer menú → partida → pausa → ayuda → partida → victoria. Probar también salida cancelada, derrota por vidas, derrota por tiempo y reintento. Registrar versión del motor y errores.
2. Jugar el recorrido completo y recoger las siete monedas. Ajustar posiciones y tiempo con resultados reales; verificar el punto de control y el salto del charco.
3. Medir rendimiento en el equipo escolar y revisar costuras del patio. Si procede, sustituir la repetición por un fondo continuo y optimizar texturas y piezas decorativas.
4. Producir y revisar cuadro a cuadro las animaciones de carrera y aterrizaje; después añadir +100 flotante, giro de moneda y celebración final. Mantener estable el controlador físico.
5. Completar créditos, añadir volumen/silencio y comprobar la exportación final en el navegador de uso.

`PLAN_Y_CAMBIOS.md` explica las reglas y el plan general; `GUIA_PARA_OTRA_IA.md` contiene rutas, configuración e instrucciones para continuar.


## Corrección de carga de audio

Se corrigió el registro del audio: Construct 2 utiliza `sounds-folder`, en plural. El CAPX anterior registraba los archivos en una etiqueta incorrecta y el motor mostraba “Audio filename cannot be found in project”. La nueva comprobación revisa cada acción Audio Play contra los sonidos registrados y verifica que los archivos existan dentro del CAPX. El resultado actual es 22 pruebas PASS del modelo y estructura; sigue pendiente confirmar la apertura en el motor.


## Tipografía de v5

Ver `TIPOGRAFIA_Y_ENCUADRE.md`. Los botones del menú tienen texto nativo separado de la pizarra, con Luckiest Guy; las instrucciones utilizan Segoe UI normal. Se conservan las ilustraciones y el título gráfico. Los márgenes de los botones y las dimensiones del texto se comprueban en la entrega.
