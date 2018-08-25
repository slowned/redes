
Durante el normal funcionamiento de la red y sus servicios indique para cada caso, que
protocolos de capa de aplicación se utilizan y con que objetivo. (Ver aclaraciones):

(a) Entre los servidores dnsX y mailX
    DNS, cuando mailX hace consultas tipo MX a su resolver
(b) Entre los servidores dnsY y mailX
    Ninguno, porque dnsY no es el resolver de mailX.
(c) Entre los servidores mailY y mailX
    SMTP: cuando se envían e-mails entre ellos
(d) Entre los servidores mailY y pcY1
    SMTP para el envío de mails por parte del usuario. IMAP o POP si usan un cliente de
  correo pesado. HTTP/HTTPS si usan Webmail.


##Dada las siguientes direcciones.
[x] indique si son direcciones de broadcast, de subred, de host o direcciones invalidas.

  * 8.73.0.0/17
  * 43.101.95.47/28
  * 127.0.0.0/8
  * 200.10.10.89/24
  * 90.10.0.0/16
  * 140.20.192.0/22
  * 180.5.23.128/27


##Dada las siguientes direcciones.

  * 182.11.10.128/27
  * 10.0.0.0/26
  * 172.29.0.0/25
  * 4.255.4.0/22
  * 200.46.0.64/27
  * 223.27.50.16/29
  * 172.30.0.0/25
  * 4.255.0.0/22
  * 200.46.0.96/27
  * 200.46.0.128/27

  1. cuales son blockes de direcciones privadas.
  1. cuales son direcciones de clase C.
  1. Cuales direcciones se pueden agrupar mediante CIRD? Justifique indicando el blocke resultante.
  1. Que blocke podria ser utilizado para realizar redes de 70 host. Para cada blocke seleccionado,
    indique la cantidad de redes de 70 host que pueden diferenciarse.
  1. Cuales son direcciones invalidas.


##VERDADERO Y FALSO

1. La funcion del control de flujo de TCP es evitar saturar los dipositivos de red.

1. El control de congestion implementado en UDP es mas eficiente que el de TCP.

1. El protocolo HTTP puede utilizar TCP como UDP como protocolo de transporte, en cambio IMAP y POP3
funcionan solo sobre TCP.

1. El puerto TCP/20 es utilizado por el modo pasivo FTP.

1. El número de secuencia es uno de los campos que comparten los headers de TCP y UDP.
Mirando los headers de TCP y UDP sale la respuesta

1. El saludo de 3 vías de TCP sirve para reservar ancho de banda entre el emisor y el receptor,
entre otras cosas.
Teoría básica.

1. Una PC solamente aceptará tramas cuya MAC address destino sea la de la interfaz de red
de la misma.
Falso. La PC también acepta tramas a la dirección de broadcast (FF:FF:FF:FF:FF:FF)

1. Cuando una PC A que tiene su tabla ARP vacía, se quiere comunicar con otra PC B que
está en otra red, A envía un ARP Request para averiguar la MAC de la IP de B. El default
GW de A es el que detecta la petición por una IP de otra red y responde informando su
dirección MAC.
Esto es un extracto de una pregnta de la práctica.
Si hay dudas al respecto, analizar en una topología, con CORE por ejemplo y usar tcpdump
para capturar los paquetes y entender cómo es el funcionamiento.

1. Una petición ARP puede utilizar tanto TCP como UDP como protocolo de transporte.
Analizar una petición ARP para determinar la respuesta.

1. Un switch separa dominios de broadcast de capa 3.

1. Una RFC es una tecnica de control de congestion.

1. ADSL es una tecnica de acceso de banda ancha donde la tasa de subida es igual a la tasa de bajada.

1. El modelo OSI cuenta con 4 capas distintas.

1. OSPF y RIP son ejemplos de implementaciones procolos de enturamiento de estado de enlace.

1. los switch en determinadas sircunstancias pueden trabajar como un switch.

1. una consulta iterativa en el registro A permite al iniciador (quien genera la sonsulta) optener en
respuesta la direccion IP de un nombre de dominio.


1. el enrutamiento estatico provee escalavilidad y tolerancia a fallos.

1. Un root server es un servidor que responde entre otros registros A y PTR de un determinado dominio

1. Si un data grama UDP no pasa adecuadamente el chequedo de su CRC, el host receptor lo informa al emisor
usando el protocolo ICMP pidiendo la retransfmision del mismo

1. Si no existiera el protoco DNS no funcionaria el protocolo IMAP

1. Si el tamanio de ventana es igual a 1, selective repeat y stop-and-wait funciona de la misma manera

1. El canal de datos del modo pasivo de FTP lo puede iniciar tanto el cliente como el servidor

1. Agregar HUBS en el dominio de broadcast mantiene la cantidad de dominio de colision, mientras
que agregar switch los aumenta.

1. Las tablas de los switch asocian direcciones IP con puertos de switch. Las direcciones IP salen
de los datagramas que pasan por el.

1. Es posible que dos aplicaciones en un servidor esten escuchando en el mismo numero de puerto.

1. Sin el servicio de DNS  no funciona el envio de correo electronico entre los servidores.

1. Utilizar la misma red IP en distintos dominios de broadcast  no produce ningun problema de comunicacion.

1. Utilizar la mismma red IP en distintos dominios de colision dentro del mismo dominio de broadcast
no produce ningun problema de comunicacion.

1. En caso de tener direcciones MAC duplicadas, utilizarlas en distintos dominios de broadcast no produce 
ningun problema de comunicacion.

1. En caso de tener direcciones MAC duplicadas, utilizarlas en distintos dominios de colision dentro del mismo
dominio de broadcast no produce produce ningun problema de comunicacion.

1. Utilizar en un servidor el mismo numero de puerto TCP y UDP para distintos servicios, no produce ningun problema
en el funcionamiento del mismo.

1. OSPF es un protocolo de ruteo dinamico del grupo "Vector de distancia".

1. Luego que un un host en una LAN realice un DHCP DISCOVER, puede recibir mas de un DHCP OFFER.

1. Si se captura el trafico en un enlace punto a punto IPv6 es posible ver el trafijo ARP.

1. HTTP 1.1 a diferencia de HTTP 1.0 mantiene estados.


1. Entre los datos que ofrece un servidor  DHCP ademas de direccione IP y mascara, se encuentra el servidor de DNS,
y el servidor de EMAIL que pertenece a esa red.

1. Las cabeceras HTTp se envian de las misma manera en un requerimiento HTTp, independientemente si se realiza un GET o un POST.

1. En una comuncacion TCP el flag SYN solo se utiliza en uno de los segmentos.

1. El tamanio de la ventana de TCP es fijado en el saludo de 3 vias y no puede ser modificado a lo largo de la comunicacion.

1. Dentro de una red que utiliza ruteo estatico, cada router ve la topologia de la red desde el punto de vista de sus vecinos.

1. No tiene sentido tener en la tabla ARP de una PC MACs de otro PCs que esten en otros redes.




##Ejercicios de parcial.

### CAPA DE APLICACION.

#### **HTTP**

curl -X ?? www.redes.unlp.edu.ar/??

  > HEAD /metodos/ HTTP/??
  > Host: www.redes.unlp.edu.ar
  > User-Agent: curl/7.54.0

  < HTTP/?? 200 OK
  < Server: nginx/1.4.6 (Ubuntu)
  < Date: Wed, 31 Jan 2018 22:22:22 GMT
  < Last-Modified: Sat, 20 Jan 2018 13:02:41 GMT
  < Content-Type: text/html; charset=UTF-8
  < Connection: keep-alive

  a. ¿Qué versiones de HTTP podría estar utilizando el servidor?
  b. ¿Qué método está utilizando? Dicho método, ¿retorna el recurso solicitado?
  c. ¿Cuál es el recurso solicitado?
  d. El recurso solicitado, ¿fue obtenido exitosamente?
  e. Si la solicitud hubiera llevado un encabezado que diga: If-Modified-Since: Sat, 20 Jan 2018 13:02:41 GMT
    ¿Cuál habría sido la respuesta del servidor web? ¿Qué habría hecho el navegador en este caso?
  >

#### **DNS**

  En base a la siguiente salida de dig, conteste las consignas. Justifique en todos los casos.

  1 ;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 4, ADDITIONAL: 4
  2
  3 ;; QUESTION SECTION:
  4 ;ejemplo.com. IN __
  5
  6 ;; ANSWER SECTION:
  7 ejemplo.com. 1634 IN __ 10 srv01.ejemplo.com.
  8 ejemplo.com. 1634 IN __ 5 srv00.ejemplo.com.
  9
  10 ;; AUTHORITY SECTION:
  11 ejemplo.com. 92354 IN __ ss00.ejemplo.com.
  12 ejemplo.com. 92354 IN __ ss02.ejemplo.com.
  13 ejemplo.com. 92354 IN __ ss01.ejemplo.com.
  14 ejemplo.com. 92354 IN __ ss03.ejemplo.com.
  15
  16 ;; ADDITIONAL SECTION:
  17 srv01.ejemplo.com. 272 IN __ 64.233.186.26
  18 srv01.ejemplo.com. 240 IN __ 2800:3f0:4003:c00::1a
  19 srv00.ejemplo.com. 272 IN __ 74.125.133.26
  20 srv00.ejemplo.com. 240 IN __ 2a00:1450:400c:c07::1b

  Complete las líneas donde aparece __ con el registro correcto.

  1.¿Es una respuesta autoritativa? En caso de no serlo, ¿a qué servidor le preguntaría para obtener
  una respuesta autoritativa?
  1.¿La consulta fue recursiva? ¿Y la respuesta?
  1.¿Qué representan los valores 10 y 5 en las líneas 7 y 8.


#### Correo electronico

  Suponga que el servidor de correo __mail1.example.com__ tiene para enviar un correo a pepe@gmail.com.
  **Indique y justifique en todos los casos:**

  * Primer consulta de DNS que debe hacer mail1.example.com.

  * Suponiendo que la consulta anterior devuelve varios resultados, ¿de qué forma elegiría mail1.example.com
  el servidor al cuál entregar el correo? ¿Y si ese servidor no estuviera disponible?

  * Considerando que la consulta anterior retorna un listado de nombres de servidores de correo para
  gmail.com, ¿será necesario realizar una consulta adicional? En caso de responder afirmativamente,
   indique el registro por el cuál será la consulta.

  * El protocolo de aplicación y de transporte, junto con el puerto correspondiente, que deberá utilizar
  el servidor mail1.example.com para entregar el correo a pepe@gmail.com.


### CAPA DE TRANSPORTE
### CAPA DE RED

### CAPA DE ENLACE

Si la PC A está en una red y se quiere comunicar con la PC B que está en otra red:
 * ¿Como se da cuenta la PC A de esto?
 * Si la tabla ARP de la PC A esta vacía, ¿que dirección MAC necesita la PC A para poder comunicarse
con la PC B?
 * En base a lo anterior, ¿que dirección IP destino tiene el requerimiento ARP? ¿Es la dirección IP del
default gateway o es la dirección IP de la PC B? De ser necesario, ejecute de nuevo el experimento
de ser necesario y complete los campos:

		Trama Ethernet: (mac origen: _________________ mac destino: _________________)
		Solicitud ARP: (mac origen: _________________ ip origen: _________________)
		mac destino: _________________ ip destino: _________________)

 * En base a lo anterior, indique la información de capa 2 y 3 del ICMP ECHO REQUEST que la PC A
le envía a la PC B cuando ejecuta un ping, en el segmento de LAN de la PC B.
