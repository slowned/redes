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


##Dada las siguientes direcciones,
[x] indique si son direcciones de broadcast, de subred, de host o direcciones invalidas.

  * 8.73.0.0/17
  * 43.101.95.47/28
  * 127.0.0.0/8
  * 200.10.10.89/24
  * 90.10.0.0/16
  * 140.20.192.0/22
  * 180.5.23.128/27

##Dada las siguientes direcciones..

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
1. El número de secuencia es uno de los campos que comparten los headers de TCP y UDP.
Mirando los headers de TCP y UDP sale la respuesta
1. Una PC solamente aceptará tramas cuya MAC address destino sea la de la interfaz de red
de la misma.
Falso. La PC también acepta tramas a la dirección de broadcast (FF:FF:FF:FF:FF:FF)
1. El saludo de 3 vías de TCP sirve para reservar ancho de banda entre el emisor y el receptor,
entre otras cosas.
Teoría básica.
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
1. El puerto TCP/20 es utilizado por el modo pasivo FTP.
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
1. El protocolo HTTP puede utilizar TCP como UDP como protocolo de transporte, en cambio IMAP y POP3
funcionan solo sobre TCP.
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
1. La funcion dell control de flujo de TCP es evitar saturar los dipositivos de red.
1. OSPF es un protocolo de ruteo dinamico del grupo "Vector de distancia".
1. Luego que un un host en una LAN realice un DHCP DISCOVER, puede recibir mas de un DHCP OFFER.
1. Si se captura el trafico en un enlace punto a punto IPv6 es posible ver el trafijo ARP.
1. HTTP 1.1 a diferencia de HTTP 1.0 mantiene estados.
1. El control de congestion implementado en UDP es mas eficiente que el de TCP.
