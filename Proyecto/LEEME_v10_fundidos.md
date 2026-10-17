# Monkey Ron v10 — fundidos de la cinemática

Abrir `Monkey_Ron_demo_v10.capx`. Incluye todos los recursos y el video original de v9, sin modificarlo.

Secuencia al tocar la meta:

1. Registrar victoria y bonus una sola vez; congelar controles y tiempo.
2. Fundir el juego a negro durante 0,4 segundos.
3. Iniciar el video cubierto por el negro y esperar su primer fotograma reproducido.
4. Retirar el negro durante 0,4 segundos para revelar la cinemática.
5. En los últimos 0,6 segundos del video, fundir a blanco y bajar gradualmente el audio.
6. Con la pantalla completamente blanca, detener y ocultar el video.
7. Retirar el blanco durante 0,6 segundos para revelar la escena de la meta.
8. Mostrar el resultado de victoria y sus botones. La partida permanece completada; no se reanudan controles.

ESC, ENTER, ESPACIO y el botón SALTAR conservan la salida con fundido a blanco. Repetir la tecla durante el blanco no reinicia la transición. El reloj de los fundidos funciona aunque el tiempo del juego esté detenido. Reintentar limpia las transiciones y recupera el volumen para la siguiente cinemática.

Se conservaron la geometría, las capas anteriores, las animaciones de Ron y los enemigos. Se añadió la capa superior `TransicionFinal` con una cubierta negra/blanca. V9 está respaldada en `Entregas/Historial/Superadas/Monkey_Ron/Antes_fundidos_v10/` desde la raíz del proyecto.

Verificación y capturas de la vista previa real de Construct 2 en `Pruebas_fundidos_v10/resultado.json`. La llegada se prueba reposicionando a Ron junto a la meta únicamente en memoria. No equivale a completar el recorrido ni a probar una exportación de distribución. Audio comprobado por estado de reproducción y volumen, sin escucha humana.

Paquete autónomo: `Monkey_Ron_v10_fundidos.zip` en la carpeta superior. Los recursos están incorporados en el CAPX.
