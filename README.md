# capturaTweetCitat
Bot de twitter que recibe un tweet y hace captura de pantalla del tweet citado
## Funcionamiento
La cuenta de twitter del bot es [@CitatBot](https://twitter.com/CitatBot)
Para utilizarlo no es necesario seguirlo, pero es útil, ya que para etiquetarlo te saldrá antes
### Ver tweet citado
La funcionalidad principal es ver el tweet citado por un tweet.
Pongamos que hay un tweet X, que cita un tweet Y. Puedes ver el tweet X, pero el autor del tweet Y te tiene bloqueado.
Responde al tweet X etiquetando al bot (@CitatBot), y el bot se encargará de entrar, hacer captura y responder con ella
### Ver tweet respondido
Pongamos que tienes un tweet X que responde a un tweet Y. Como antes, puedes ver el tweet X, pero no el tweet Y.
Responde al tweet X del mismo modo, y el bot hará lo mismo
Nota: si el tweet X también tiene citado un tweet, esto no funcionará
### Privacidad
Actualmente todo el mundo puede ver cómo solicitas el tweet y el bot te responde. Está en desarrollo una opción que consistirá en pasarle el tweet por MD (mensaje directo) y enviar la captura también por MD.
Sin embargo, como el bote lo hago en ratos libres cuando tengo ganas de programar, ya la vez estoy programando otras cosas, puede tardar un poco
## Preguntas:
### ¿Para qué sirve?
Nunca te has encontrado con un tweet criticando a otro tweet, pero ¿no puedes ver qué dice porque te tiene bloqueado?
¿Has tenido que entrar con ventana de incógnito, o pedir captura de pantalla?
Este bot lo automatiza por ti
Responde a un tweet etiquetando en el bot, y él entrará en el tweet citado a hacer captura

### ¿Puede capturar cualquier tweet?
No. No puede hackear twitter :(
Su funcionamiento es que entra en el tweet sin haber iniciado sesión y le hace captura. Esto significa que puede capturar cualquier tweet de una cuenta **pública**, mientras que los tweets privados no los podrá capturar

### ¿Y no pueden bloquearlo?
Pueden bloquear el bot. Pero seguirá funcionando, ya que la captura la realiza sin haber iniciado sesión

### ¿No es poco ético esto?
No. El bote sólo permite realizar capturas de pantalla en tweets públicos. Son tweets que puedes ver igualmente si cierras la sesión, o si entras desde otra cuenta. Lo que hace este bot es automatizarlo, pero no te da ninguna información que no tengas accesible

## Quiero utilizar el programa
El programa se encuentra bajo la licencia GNU GPLv3 (Licencia Pública General de GNU, versión 3). Puedes consultarla [aquí](https://github.com/oriolmarti97/capturaTweetCitat/blob/master/LICENSE). Se trata de una licencia de [Software Libre](https://www.gnu.org/philosophy/free-sw.es.html) y [copyleft](https://www.gnu.org/licenses/copyleft .html). Fundamentalmente, lo que esto significa es que puedes utilizarlo, modificarlo y redistribuirlo (con o sin modificaciones), siempre que el código conserve la misma licencia
No obliga a avisar al autor de ningún tipo de modificación o redistribución. Sin embargo, te agradeceré que si haces alguna mejora contactes conmigo, de modo que yo también la pueda aplicar.
### ¿Cómo hago para ejecutarlo yo?
Lo primero es, lógicamente, descargar el código fuente.
El programa está pensado para correr en un servidor Ubuntu sin entorno gráfico, ya que es el que utilizo. Sin embargo, debería funcionar en cualquier sistema basado en Unix que tenga instalados los programas **cutycapt** y **xvfp**, así como **python 3** y **pip**. Sin embargo, esta instalación no es necesario hacerla a mano, sino que la puedes hacer utilizando el script [setup.sh](https://github.com/oriolmarti97/capturaTweetCitat/blob/master/setup.sh). Este script requiere tener instalado apt, bash, wget y python 3, que son paquetes que suelen estar instalados en todas partes. Puede modificarlo si necesita
Ejecutándolo tendrá preparado el entorno para ejecutar el programa

Deberá crear un archivo **key.py**, que declare cuatro variables que serán las claves para acceder al bot. Este archivo ha sido añadido conscientemente al .gitignore, porque no quisiera que nadie accediera al bote sin permiso. Las cuatro variables se llamarán consumer_key, consumer_secret, access_token, access_token_secret, y te las proporciona Twitter

Finalmente ejecute el archivo [server.sh](https://github.com/oriolmarti97/capturaTweetCitat/blob/master/server.sh). Este archivo ejecuta infinitamente el bot redirigiendo sus salidas a dos archivos que harán de logs. Si en algún momento un error cierra el bote, volverá a abrirse automáticamente gracias a ello
Por comodidad puedes crear un servicio utilizando el comando systemctl. Puedes encontrar más información en Internet. Esto permite que el bote arranque al arrancar la máquina
