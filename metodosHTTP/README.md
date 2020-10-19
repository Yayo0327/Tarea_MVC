# Introduccion
### ¿Que es un método HTTP?
HTTP define un conjunto de métodos de petición para indicar la acción que se desea realizar para un recurso determinado. Aunque estos también pueden ser sustantivos, estos métodos de solicitud a veces son llamados HTTP verbs. Cada uno de ellos implementan una semántica diferente, pero algunas características similares son compartidas por un grupo de ellos: ej. un request method puede ser safe, idempotent, o cacheable.
# Marco Teórico
#### GET
El método GET  solicita una representación de un recurso específico. Las peticiones que usan el método GET sólo deben recuperar datos.
###### Ejemplo: 
GET /index.html HTTP/1.1  
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Accept-Language: es-mx
Accept-Encoding: gzip, deflate
Connection: Keep-Alive
#### HEAD
El método HEAD pide una respuesta idéntica a la de una petición GET, pero sin el cuerpo de la respuesta.
###### Ejemplo:
GET /index.html HTTP/1.1  
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Accept-Language: es-mx
Accept-Encoding: gzip, deflate
Connection: Keep-Alive
#### POST
El método POST se utiliza para enviar una entidad a un recurso en específico, causando a menudo un cambio en el estado o efectos secundarios en el servidor.
###### Ejemplo: 
POST /cgi-bin/process.cgi HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Content-Type: text/xml; charset=utf-8
Content-Length: 88
Accept-Language: es-mx
Accept-Encoding: gzip, deflate
Connection: Keep-Alive
#### PUT
El modo PUT reemplaza todas las representaciones actuales del recurso de destino con la carga útil de la petición.
###### Ejemplo:
PUT /index.htm HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Accept-Language: es-mx
Connection: Keep-Alive
Content-type: text/html
Content-Length: 182
#### DELETE
El método DELETE borra un recurso en específico.
###### Ejemplo:
DELETE /hello.htm HTTP/1.1
User-Agent: Mozilla/4.0 (compatible; MSIE5.01; Windows NT)
Host: www.yosoy.dev
Accept-Language: es-mx
Connection: Keep-Alive
#### OPTIONS
El método OPTIONS es utilizado para describir las opciones de comunicación para el recurso de destino.
###### Ejemplo:
curl -X OPTIONS https://yosoy.dev -i

HTTP/1.1 200 OK
Date: Wed, 8 Nov 2017 12:28:53 GMT
Server: Apache/2.2.14 (Win32)
Allow: GET,HEAD,POST,OPTIONS,TRACE
Content-Type: httpd/unix-directory
#### PATCH
El método PATCH  es utilizado para aplicar modificaciones parciales a un recurso.

### Errores de peticiones HTTP
###### 100 Continue:
El navegador puede continuar realizando su petición (se utiliza para indicar que la primera parte de la petición del navegador se ha recibido correctamente).
###### 101 Switching Protocols:
El servidor acepta el cambio de protocolo propuesto por el navegador (puede ser por ejemplo un cambio de HTTP 1.0 a HTTP 1.1).
###### 102 Processing (WebDAV - RFC 2518):
El servidor está procesando la petición del navegador pero todavía no ha terminado (esto evita que el navegador piense que la petición se ha perdido cuando no recibe ninguna respuesta).2​
###### 103 Checkpoint:
Se va a reanudar una petición POST o PUT que fue abortada previamente.
###### 200 OK:
Respuesta estándar para peticiones correctas.
###### 201 Createds:
La petición ha sido completada y ha resultado en la creación de un nuevo recurso.
###### 202 Accepted:
La petición ha sido aceptada para procesamiento, pero este no ha sido completado. La petición eventualmente pudiere no ser satisfecha, ya que podría ser no permitida o prohibida cuando el procesamiento tenga lugar.
###### 203 Non-Authoritative Information (desde HTTP/1.1):
La petición se ha completado con éxito, pero su contenido no se ha obtenido de la fuente originalmente solicitada sino de otro servidor.
###### 204 No Content:
La petición se ha completado con éxito pero su respuesta no tiene ningún contenido (la respuesta puede incluir información en sus cabeceras HTTP).2​
###### 205 Reset Content:
La petición se ha completado con éxito, pero su respuesta no tiene contenidos y además, el navegador tiene que inicializar la página desde la que se realizó la petición (este código es útil por ejemplo para páginas con formularios cuyo contenido debe borrarse después de que el usuario lo envíe).
###### 400 – Bad Request:
Cuando el cliente envía una petición que el servidor no puede comprender, aparece el error 400. Suele sucede cuando los datos enviados por el navegador no cumplen con las normas del protocolo HTTP. Es así que el servidor desconoce como procesar una solicitud que contiene una sintaxis incorrecta.
###### 401 – Authorization Required:
Si el cliente ha solicitado una página web que se encuentra protegida por una contraseña, el servidor devuelve el error 401. En este caso no se devuelve el error de manera típica, sino que aparece una ventana emergente en la cuál se solicita al usuario que ingrese una contraseña para acceder al sitio web. Si tienes la contraseña, podrás visualizar la página web sin problemas. Si no ingresas ninguna contraseña serás direccionado a la página que indica el error.
###### 403 – Forbidden:
Este tipo de error se presenta cuando el servidor comprende la solicitud de cliente, pero por alguna razón no puede completarla. Las causas no se deben a sintaxis incorrecta o un problema de autorización, sino a que el administrador web no permite a los visitantes navegar por el directorio de archivos.
###### 404 – Not Found:
 Este código indica que el servidor no ha encontrado nada en la ubicación especificada por el cliente, ya sea porque la URL no se ha ingresado correctamente o la estructura de URLs permanentes (también conocidas como permalinks) ha sido modificada de tal manera que todos los enlaces han sido movidos a diferentes ubicaciones.
###### 500 – Internal Server Error:
 Se emplea cada vez que el servidor se encuentra con algún tipo de fallo que no le permite completar la solicitud del cliente. Es un código bastante genérico pues se emplea cuando ningún otro código de error sirve para explicar el fallo que se ha presentado.
###### 502 – Bad Gateway:
El código 502 indica un error de comunicación entre dos servidores. Sucede cuando el cliente se conecta a un servidor que actúa como un proxy o un portal que necesita acceder a un servidor ascendente, el cual proporciona un servicio adicional al servidor inicial.
###### 503 – Service Temporarily Unavailable:
Este error puede aparecer cada vez que se da una sobrecarga en el servidor o cuando se está realizando algún mantenimiento programado. El error 503 indica que el servidor no se encuentra disponible de momento. De momento es la palabra clave en este caso pues este tipo de error es usualmente una condición temporal que puede ser resuelta en horas (si se detecta a tiempo).
###### 504 – Gateway Time-Out
El código 504 también incida un error de comunicación entre dos servidores al igual que el error 502. En este caso particular se reconoce que el servidor de menor nivel no ha recibido una respuesta en el tiempo permitido por el servidor ascendente al cual ha accedido.
### Referencias
https://developer.mozilla.org/es/docs/Web/HTTP/Methods