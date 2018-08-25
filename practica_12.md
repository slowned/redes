# Capa de aplicación

1. Si PC-A desea acceder a www.redes.info.edu.ar, responder:

a. ¿Cuál es el primer protocolo de aplicación que necesita utilizar la PC-A? ¿A quién le hace la consulta?

  > El primer protocolo de aplicacion que utiliza la PC-A es DNS con el registro A para averiguar la direccion
  > ip del domino www.redes.info.edu.ar. La consulta es de la PC-A hacia Svr_DNS que es el servidor DNS local.

b. Indique los mensajes que enviará y recibirá en la consulta anterior.

  > PC-A mensaje consulta la direccion ip para el dominio www.redes.info.edu.ar
  > Svr_DNS mensaje responde la ip de la direccion preguntada

2. La respuesta del paso anterior, ¿es autoritativa? Justifique.

  > Si, porque responde el servidor autorizado.
      **Respuesta authoritative:** es aquella entregada por el servidor oficial
      para el nombre de dominio consultado, es decir, que ningún servidor local,
      raíz ni intermedio respondió con información de caché.

3. Si desde PC-G el usuario roger@redes.info.unlp.edu.ar le envía un mail al usuario rafael@example.com,
contestar:

a. Indique los protocolos de aplicación que será necesario utilizar para que el mail llegue al servidor
de correo del remitente. Tenga en cuenta como se relacionan los distintos protocolos de aplicación
utilizados, respetando el orden de aparición en función de las dependencias entre los mismos. Por
cada mensaje enviado indicar quién lo envía, quién lo recibe, el protocolo utilizado, si se tranporta
con TCP o con UDP y cuales puertos origen y destino se utilizan.

> El user agent del usuario roger averigua la IP del servidor de correo del que ofrece su cuenta
> Para realizar la conexion SMTP y enviar el correo, el servidor de "redes.info.unlp.edu.ar", utiliza
> DNS para averiguar la IP del servidor de correo de "example.com", establece la conexion y envia el
> email. El destinatario, eventualmente revisa su correo con su user agent, que utilizara DNS para
> averiguar la IP del servidor POP3 o IMAP.

b. Indique los protocolos de aplicación que será necesario utilizar para que el mail llegue al servidor de
correo del destinatario. Tenga en cuenta como se relacionan los distintos protocolos de aplicación
utilizados, respetando el orden de aparición en función de las dependencias entre los mismos. Por
cada mensaje enviado indicar quién lo envía, quién lo recibe, el protocolo utilizado, si se tranporta
con TCP o con UDP y cuales puertos origen y destino se utilizan.

4. El usuario rafael, ¿cómo recuperará sus mails desde PC-J? Indique los pasos necesarios para hacerlo.
¿Puede hacerlo desde diferentes PCs? Justifique.


# Capa de transporte

5. Si desde PC-B se establece una sesión TCP al servidor www con los siguiente datos, ¿cómo sería el
saludos de 3 vías?

  PC-B: ISN: 150100       www: ISN: 204500

  PC-B | WWW

  "--(seq:150100)-->"
  "<--(seq:204500; ACK:1501001)--"
  "--(seq:1501001; ACK: 204501)-->"

6. ¿Que responderá cada nodo ante cada una de los siguientes mensajes? Justifique, indicando flags,
puertos, etc, siempre que sea necesario.

PC-B envía un mensaje con el flag SYN seteado al servidor Srv_DHCP al puerto 67.
  saludo de 3 vias
  Srv_DHCP SYN;ACk al puerto > 1024 de la PC-B

PC-B envía un mensaje UDP al servidor Srv_DHCP al puerto 67.
  puerto origen PC-B:>1024
  puerto destino 67
  longitud
  checksum

PC-B envía un mensaje UDP al servidor WWW al puerto 80.
  puerto origen PC-B:>1024
  puerto destino 80
  longitud
  checksum

PC-A envía un mensaje con el flag SYN seteado al servidor WWW al puerto 80.
  saludo de 3 vias

PC-A envía un mensaje con el flag SYN seteado al servidor WWW al puerto 8080.
  saludo de 3 vias


# Capa de red

8. Asignar el direccionamiento IP a las redes del gráfico teniendo en cuenta lo siguiente:
a. Las redes que asigne deben ser válidas. Por ello, primero indique cuales de las siguientes redes, no
pueden ser utilizadas. Explique por qué.

224.0.10.0/23   205.10.0.0/25   192.168.0.0/23  175.100.0.128/27
205.10.0.64/26  10.0.0.0/28   198.5.10.192/27   200.5.113.0/23
10.0.0.0/30   192.168.10.0/24   198.60.0.0/23   192.256.0.0/23
127.0.0.0/8   230.0.0.0/24

b. La red C tiene direccionamiento público. Dicha red/subred es parte de una red clase B.
c. La red F tiene direccionamiento público. Dicha red/subred es parte de una red clase C.
d. Las redes A, B, D, E y las que interconectan routers utilizan direccionamiento privado.
e. La red punto a punto contra Internet (RTR-C — RTR-I), tiene direccionamiento público. Dicha red/subred
es parte de una red clase C.
f. Asignar las redes de manera que se desperdicie la menor cantidad de direcciones y que sea posible
sumarizar las tablas de ruteo.

9. Asignar IP a cada uno de los dispositivos.
10. Determinar las tablas de ruteo de cada uno de los routers (excepto RTR-I) teniendo en cuenta que:
a. Red F llega a las redes A, B, D y E a través de router RTR-D y a la red C a través de RTR-C.
b. RTR-C llega a Red A, B y C a través del RTR-B. A las demás redes RTR-F.
c. RTR-D llega a Red A y B a través de red a través de RTR-A.
d. Todas las redes deben poder navegar por Internet menos Red D.
e. En todos los casos donde no esté especificado, el ruteo debe ser óptimo (entendiendo por óptimo
que tenga la menor cantidad de saltos posibles).
11. Si se desconecta SWT3, ¿cómo quedaría la tabla de ruteo de RTR-D para que la red completa siga
funcionando según las condiciones establecidas?
12. Siguiendo con el punto anterior, ¿es necesario modificar la tabla de ruteo de algún otro router? ¿Cuáles?
13. Si se estuviese ejecutando un protocolo de ruteo dinámico, ¿cómo se solucionaría este problema?


# Capa de enlace
14. Con respecto a la pregunta 1 de la Capa de Aplicación, responder:
a. Suponga que se encuentra analizando los paquetes que entran y salen de la placa de red de PC-A.
¿Qué información (headers) de capa 2, 3 y 4 son transportados en el primer paquete de la comunicación
de cada protocolo necesario para realizar dicha consulta? Indique los paquetes que envía
PC-A y las respuestas que obtiene. Considere que todas las tablas están vacías.
b. Indique cómo quedarían las tablas de los switches Swt-1 y Swt-3 después que finaliza todo el intercambio
de mensajes.
15. Si a continuación del punto anterior, PC-A desea enviar un ping a:
a. PC-J. ¿Cuál es el primer protocolo que usaría?
b. PC-C. ¿Cuál es el primer protocolo que usaría?
16. ¿Cómo quedaría la tabla de Swt-4 después que se produce el siguiente intercambio de mensajes (suponga
que todas las tablas están vacías)? Indicar cómo se modifica la tabla del switch a medida que
pasan los mensajes (considerar que cada punto involucra todo lo necesario para poder enviar únicamente
el mensaje correspondiente).
a. PC-G envía mensaje DNS a Srv_DNS.
b. PC-L envía un echo-request a PC-F.
c. PC-I envía un echo-request a PC-E.
d. RTR-E envía la respuesta de DNS del punto a) a PC-G.
e. PC-G envía un mensaje HTTP un servidor en Internet.
17. Dentro de la Red D, ¿qué nodos recibirán cada uno de los mensajes intercambiados en el punto 3?
18. ¿Cómo quedaría la tabla ARP de RTR-E una vez finalizado todo el intercambio?
