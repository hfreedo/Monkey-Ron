# Monkey Ron v9 — cinemática de meta

Abrir `Monkey_Ron_demo_v9.capx` en Construct 2. El CAPX incluye todos los recursos, también el MP4 original proporcionado y su alternativa WebM. No requiere importar los videos por separado.

Al alcanzar la bandera estando en el suelo, la partida registra el bonus una sola vez, congela controles y tiempo y reproduce la cinemática de 10 segundos con audio. Al finalizar aparece el resultado de victoria con puntos, monedas y bonus. No se superpone el sonido anterior de victoria.

Se puede saltar con ESC, ENTER, ESPACIO o el botón SALTAR. Si el navegador exige un gesto para reproducir, pulsar sobre el video permite iniciarlo. Un error de reproducción o 30 segundos de espera llevan al resultado, conservando el puntaje. Reintentar permite ver la cinemática de nuevo al completar la siguiente partida; Menú vuelve al menú principal.

Base: v8 guardada por el usuario. Se conservaron las capas originales, colisiones, animaciones de Ron y enemigos. Respaldo: `Entregas/Historial/Superadas/Monkey_Ron/Antes_cinematica_v9/Monkey_Ron_demo_v8.capx` desde la raíz del proyecto.

## Comprobación

CAPX abierto y ejecutado en Construct 2. Vista previa real probada en Microsoft Edge con 14 comprobaciones satisfactorias: reproducción y audio habilitado, final natural, bonus único, congelación de puntos y tiempo, reinicio, menú, saltos por teclado/botón y salida por espera agotada. Sin errores JavaScript. Capturas e informe: `Pruebas_cinematica_v9/`.

Para probar la llegada se reposicionó al jugador junto a la meta únicamente en memoria. No se probó un recorrido completo del nivel ni una exportación de distribución. La comprobación de audio confirma pista presente y reproducción sin silenciar; no incluye escucha humana.

ZIP autónomo: `Monkey_Ron_v9_cinematica.zip` en la carpeta superior. Contiene CAPX, guía e informes; los recursos están incorporados al CAPX.
