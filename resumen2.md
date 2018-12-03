VER BIEN LOS FLAGGS DE LA CONEXION TCP flags [SA]

 * ACK – The ACK flag, which stands for “Acknowledgment”, is used to acknowledge the successful receipt of a packet. As we can see from the diagram above, the receiver sends an ACK as well as a SYN in the second step of the 3-way handshake process to tell the sender that it received its initial packet.
 * FIN – The FIN flag, which stands for “Finished”, means there is no more data from the sender. Therefore, it is used in the last packet sent from the sender.
 * URG – The URG flag is used to notify the receiver to process the urgent packets before processing all other packets. The receiver will be notified when all known urgent data has been received. See RFC 6093 for more details.
 * PSH – The PSH flag, which stands for “Push”, is somewhat similar to the URG flag and tells the receiver to process these packets as they are received instead of buffering them.
 * RST – The RST flag, which stands for “Reset”, gets sent from the receiver to the sender when a packet is sent to a particular host that was not expecting it.
 * ECE – This flag is responsible for indicating if the TCP peer is ECN capable. See RFC 3168 for more details.
 * CWR – The CWR flag, which stands for Congestion Window Reduced, is used by the sending host to indicate it received a packet with the ECE flag set. See RFC 3168 for more details.
 * NS (experimental) – The NS flag, which stands for Nonce Sum, is still an experimental flag used to help protect against accidental malicious concealment of packets from the sender. See RFC 3540 for more details.



# INTRODUCCION

Servicio	Puerto
Web	80
SSH	22
DNS	53
Web Seguro	443
POP3	110
IMAP	143
SMTP	25

  * Que son las RFCs?.
       un estandar.
      Cada una de ellas individualmente es un documento cuyo contenido es una propuesta oficial
      para un nuevo protocolo de la red Internet. Cualquiera puede enviar una propuesta de RFC
      a la IETF (Grupo de Trabajo en Ingeniería de Internet), pero es ésta la que decide
      finalmente si el documento se convierte en una RFC o no. Si luego resulta lo suficientemente
      interesante, puede llegar a convertirse en un estándar de Internet.


  * Como se llaman las PDU de las siguientes capas?.
      unidad de dato de protocolo, se utilizan para el intercambio de datos entre unidades
      disparejas , dentro de una capa de modelo OSI.

      OSI(open system iterconection) es una norma universal para protocolos de comunicacion,
      divide las tareas en 7 niveles:

      CAPA | PDU
      --- | ---
      Aplicacion | Mensaje
      Transporte | Segmento
      Red | Datagrama
      Enlace | Marco
      Fisica | PDU-1

      | Modelo OSI         | Modelos TCP/IP |
      |--------------------|----------------|
      | Aplicacion         | Aplicacion     |
      | Presentacion       |                |
      | Session            |                |
      | Segmento           | Transporte     |
      | Red                | Red            |
      | Enlace             | Enlace         |
      | FIsico             | Fisico         |


  * OSI y TCP/IP.
      * ambos estan divididos en niveles o capas.
      * ambos tienen capa de aplicaciones pero brindan servicios distintos.
      * ambos tienen capa de transporte y de red similares.
      * TCP/IP combina la capa de presentacion y de sesion en la capa de Aplicacion.
      * OSI fue definido antes de implementar los protocolos, por lo que algunas funcionalidades
        necesarias no existen o fallan. En cambio TCP/IP se creo despues que los protocolos, por
        lo que se amolda a ellos perfectamente

  * Que es un protocolo?.
      Un protocolo de comunicaciones es el conjunto de reglas normalizada para la representación,
      señalización, autenticación y detección de errores necesario para enviar información
      a través de un canal de comunicación.

  * ¿Qué ventajas tiene una implementación basada en capas o niveles?
      La ventaja de utilizar este tipo de implementación es que cada capa permite la identificación
      y relación de las partes complejas del sistema, al estar éste modulado es mas facil el
      mantenimiento y actualizacion del mismo. Cada capa en combinación con las capas inferiores,
      implementa alguna función y presta algún servicio.

# Capa de Aplicacion

  > La capa de aplicación da soporte a las aplicaciones de red; incluye los
  > protocolos HTTP (Web), SMTP (email) y FTP (transferencias de archivos) entre
  > otros.


  * ## HTTP:80 (Hyper Text Transfer Protocol, command curl)
      > Protocolo de capa de aplicacion que da soporte a transferencia de objetos de la web.
      > Define los mensajes __solicitud y respuesta__ que pueden enviarse, formato y orden,
      > se implementa en cliente y servidor.

      * **HTTP 1.0 vs HTTP 1.1:**
          ambos usan TCP para la capa de transporte, la diferencia es que HTTP 1.0 utiliza
          conecciones no persistentes y HTTP 1.1 puede manejar tanto persistentes como no
          persistentes.

          **Conexion no persistente**, la conexion se cierra una vez TCP asegura la transmision. Asi
          cada conexion establecida solo permite solicitar un objeto. Suelen utilizarse varias
          conexion paralelas para mejorar los tiempos.

          **Conexion Persistentes**, el server mantiene la conexion avierta a la espera de una
          nueva solicitud. Tipicamente el server cierra la conexion al permanecer inactiva
          durante un timeout.


  * ## FTP

     (File Transfer Protocol) permite transferir archivos desde y hasta un host
    remoto, con autentificación por medio de usuario y contraseña.

     El funcionamiento del protocolo FTP trabaja en un modelo cliente/servidor, pero se distingue de los
    demás servicios por el hecho de usar una conexión para el protocolo de control (Out-Of-Band Control) y
    otra conexión para la transferencia de datos. El protocolo FTP se ejecuta sobre TCP porque requiere un
    protocolo de transporte que le brinde detección de errores (confiabilidad).

    > 20/tcp data port
    > 21/tcp control port

   * **Modo activo (servidor):** el servidor siempre crea el canal de datos en su puerto 20, mientras que del
   lado del cliente el canal de datos se asocia a un puerto  mayor a 1024. El cliente le dice al servidor
   por el canal de control que puerto usara.

   * **Modo pasivo:** el cliente se conecta al con el servidor, este le manda por el canal de control, el puero mayor
   a 1024 del servidor al q debe conectarse el cliente. Tras cada envio se cierra el canal de datos.

  * ##  TFTP (trivial file transfer protocol)
       Es un protocolo de transferencia de archivos muy simple que trabaja sobre UDP, al no ser
       orientado a conexiones, no tiene autenticacion de usuario, encriptacion, y no puede listar
       contenido de directorios. Los archivos se transmiten en segmentos de 512 bytes, exepto el
       ultimo que debe ser inferior para indicar el fin de la transmision.

  * ## DNS:53 (command dig)

    * **A:** direccion IP.
    **NS:** servidores de nombres que tiene autoridad para el dominio.
    * **SOA:** indica que los registros siguientes de la base de datos conrresponden
    a informacion autoritativa
    * **PTR:** indica el dominio de la ip consultada.
    * **AAA:** igual que **A** pero para **IPV6**.
    * **CNAME:** permine identificar alias o subdominios equivalentes.
    * **MX:** servidor de correo electronico para el dominio.


      **Servidor DNS** es una base de datos distribuida implementada en una
    jerarquía de servidores de nombres.

      **DNS** protocolo de capa de aplicación que permite a los hosts y
    servidores DNS comunicarse para proveer el servicio de traducción, entre la
    dirección mnemónica y la dirección IP.
      Un host hace su solicitud a un servidor local de nombres, que, si no posee
    la traducción, se transforma en un cliente consultando a un servidor raíz
    de nombres *root server*. Si el *root server* conoce al servidor autorizado
    de nombres para el dominio que se intenta resolver, envía la solicitud
    terminando la cadena; si lo desconoce, consulta a servidores intermedios
    hasta que eventualmente alguno lo conozca. En cada uno de los paso, los
    servidor podrían tener registrado el IP del dominio consultado o mantenerlo
    en cache por una consulta anterior, ofreciendo una respuesta directa.

        TLD:    .com  .org .net .info
        g-TDL: .ar .tv .bo

      **Respuesta authoritative:** es aquella entregada por el servidor oficial
      para el nombre de dominio consultado, es decir, que ningún servidor local,
      raíz ni intermedio respondió con información de caché.

      **Consulta DNS Recursiva:** Un host realiza una consulta a un servidor,
      éste se encarga de obtener la respuesta y entregarsela al
      host.

      **Consulta DNS Iterativa:** Un *name server* realiza una consulta a un
      servidor; si este no tiene la respuesta le devuelve la IP del próximo
      servidor. El name server original se encarga de realizar nuevas solicitudes

         > Típicamente, un local name server realiza consultas iterativas, y el resto recursivas
         > ya que tienen mayor volúmen de consultas que el local name server.

     **RESOLVER :**
      Se denomina resolver a la parte del cliente del DNS, encargada de iniciar y secuenciar la
      consulta. Usualmente trabaja en modo iterativo.

    **/etc/hosts**

        >el archivo hosts de un ordenador es usado por el sistema operativo para guardar la
        >correspondencia entre dominios de Internet y direcciones IP.
        >Antiguamente cuando no había servidores DNS que resolvieran los dominios, el
        >archivo hosts era el único encargado de hacerlo, pero dejó de utilizarse cuando
        >Internet empezó a crecer en nombres de dominio. En la actualidad tambien es usado
        > para bloquear contedino de internet como la publicidad web.


  * ## Correo electronico

      * ### SMTP:25

          > Envio de emails.

      * ### IMAP

          > Recepcion de  email, mantiene copias de los emails en el servidor, permitiendo
          >organizarlos en carpetas.

      * ### POP

          > Recepcion de emails, borra los mensajes tras bajarlo del servidor siendo
          >imposible consultarlos de otro equipo.

  * ## DNS relacion con SMTP

          >   DNS básicamente sirve de soporte para el resto de los protocolos de aplicación. Al
          >  escribir un mail, el user agent busca la IP del servidor de correos del dominio que
          >  ofrece la cuenta (servidor SMTP de yahoo.com) para realizar la conexión SMTP y enviar
          >  el correo. El servidor de yahoo, utiliza luego DNS para averiguar la IP del servidor
          >  de correo de hotmail.com, establace la conexión y envía el email. El destinatario,
          >  eventualmente revisa su correo con su user agent, que utilizará DNS para averiguar
          >  la IP del servidor POP3 o IMAP.

# **Capa de transporte**

  >La función de la capa de Transporte es proveer de una comunicación lógica entre
  >procesos de aplicación corriendo en diferentes hosts, permitiendo el envío de segmentos
  >de datos como si estuviesen conectados directamente, sin intermediarios ni
  >preocupaciones por la infraestructura de envío de mensajes.

  * **La PDU de la capa de transporte es el segmento. Sin embargo, en algunos
  contextos suele utilizarse el término Datagrama, indique cuándo.**

  > Un datagrama es una cabecera + datos, tal que la cabecera ofrece la información
  > necesaria para que los datos puedan ser encaminados y alcancen un destino.

  > Se suele hablar de Datagrama en referencia a los segmentos en el protocolo UDP -
  > Protocolo de Datagrama de Usuario-. Sin embargo, como datagrama es el nombre
  > formal de los PDU de la capa de Red -protocolo IP- es preferible evitar esta
  > denominación.


  * ## UDP:69

    **¿Qué sucede si llega un datagrama UDP a un host que no tiene a ningún proceso esperando en el puerto destino de dicho datagrama?**
    > Se retorna un mensaje ICMP indicando el fracaso.

    ### cabecera del segmento UDP

      * puerto origen
      * puerto destino
      * longitud
      * suma de comprobacion

  * ## TCP

    **¿Qué sucede si llega un segmento TCP a un host que no tiene a ningún proceso esperando en el puerto destino de dicho segmento?**
    > Se retorna un response TCP con el flag RESET seteado en 1 indicando que dicha conexion no debe ser utilizada.

    * ### Saludo de 3 vias

       > El cliente realiza una conexión enviando un paquete SYN al servidor, en el servidor se comprueba
       > si el puerto está abierto (si existe un proceso escuchando por ese puerto), si el puerto no
       > esta abierto se le envía al cliente un paquete de respuesta RCT, esto significa un rechazo de
       > intento de conexión. Si el puerto esta abierto, el servidor responde con un paquete SYN/ACK.
       > Entonces el cliente respondería al servidor con un ASK, completando así la conexión

       * ### FLAGS

          * #### SYN:
          * #### ReSeT: si el servidor no tiene ningun proceso escuchando en el puerto.
          * #### ACK: recepcion correcta.
          * #### NACK: recepcion corrupta.
          * #### FIN: pedido de cierre de conexion.
          * #### TIME_WAIT: perdido de cierre desde el cliente, en espera de respuesta.
          * #### CLOSE_WAIT: pedido de cierre desde el servidor, en espera de respuesta.
          * #### SYN_WAIT:

    * ### Cierre de conexion

        ---FIN--->
        <---ACK---
        <---FIN---
        ---ACK--->



  * ### TCP vs UDP

      * Confiabilidad
          > Asegura la entrega de todos los paquetes enviados, permitiendo mantener en el receptor
          > el orden en que le fueron enviados y detectar errores en la recepciion(mediante el checksum).

      * Multiplexacion

           > Extender la comunicacion host-host que ofrece IP permitiendo diferenciar los procesos en el
           > receptor y en el emisor, de modo que varios procesos en un host se comuniquen con varios procesos
           > en otros hosts, sin confundir los paquetes (utilizando direcciones IP y numeros de puerto que
           > identifican a los procesos).

           TCP: Socket (IP Orig, Port Orig, IP Dest, Port Dest)
           UDP: Socket (IP Dest, Port Dest)

      * Orientado a la conexion
          > controlar la velocidad de transmision del emisor para no sobrecargar la red.

          TCP: SI
          UDP: NO

      * Controles de congestion
          > Controlar la velocidad de transmision del emisor para no sobrecargar la red

      * Controles de flujo
          > Controlar la velocidad de transmision del emisor para no sobrecargar al receptor (segun
          > el tamanio de su buffer, ventana de recepcion)


      **¿Es posible usar TCP en comunicaciones multicast?**

       >  No es posible establecer comunicaciones multicast sobre TCP, las mismas se realizan
       >  sobre UDP debido a que no son comunicaciones punto a punto.
       >  Con TCP antes de comenzar el envío de datos, debería establecerse una comunicación
       >  mediante el handshake de tres vías. Ese establecimiento de conexión es
       >  cardinalidad uno a uno, lo que no resultaría práctico para el establecimiento de conexión
       >  uno a muchos (lo que es, en forma sencilla, la idea de multicast). Por esto, se utiliza UDP
       >  para multicasting, debido a que no es necesario un establecimiento de conexión previo al
       >  envío de datos.

    * Netstat

       >   El comando netstat imprime información sobre las conexiones de red, tablas de routeo,
       >  estadísticas sobre las interfaces de red y membresía multicast.

       >  Por defecto, muestra una lista de los sockets abiertos, indicando protocolo en uso, IP, port
       >  local y remoto, y estado de la conexión.

    * Protocolos ARK's

       > Los protocolos ARQ son protocolos utilizados para el control de errores en la transmisión de datos,
       > garantizando la integridad de los mismos.

       * Selective Repeat

          > Protocolo ARQ con pipelining. Tanto el emisor como el
          > receptor manejan una ventana, enviando el receptor ACK's individuales para cada
          > segmento. Esto evita retransmisiones innecesarias, dado que el receptor no descarta
          > tantos segmentos y puede pedir la retransmisión de uno específico.
          >
          > En el emisor, la ventana puede contener segmentos con y sin ACK's -desplazará la
          > ventana cuando los primeros estén con ACK. Deberá manejar timers individuales para
          > cada paquete sin ACK.
          >
          > Si la ventana del receptor se desplaza completa y recibe un segmento anterior a la
          > ventana -retransmisión-, el receptor debe reenviar el ACK correspondiente -o el emisor
          > seguirá reenviándolo cada vez que venza su timer, trabando al desplazamiento de su
          > ventana-.

       * Stop and Wait

         >  Protocolo ARQ para el control de errores en la comunicación entre dos hosts basado en el envío de tramas o
         >  paquetes, de modo que una vez se envía un paquete no se envía el siguiente paquete hasta que no se recibe
         >  el correspondiente ACK (confirmación de la recepción) y en caso de recibir un NACK (rechazo de la recepción)
         >  se reenvía el paquete anterior.

       * Go Back-N

         >  Protocolo ARQ con pipelining (es decir, soporta múltiples segmentos en tránsito pendientes de
         > confirmación, implementando buffers en el emisor; el rango de los números de secuencia debe
         > aumentarse), por esto el emisor puede transmitir varios paquetes sin esperar ningún reconocimiento,
         > pero tiene restringido el número máximo N de paquetes no reconocidos en el entubado, llamado
         > ventana del emisor. El emisor también tiene un timer para controlar el timeout. La recepción
         > del ACK de un segmento, confirma a todos los anteriores pendientes -acuse de recibo acumulado-.
         > El vencimiento del timer para un segmento implica Best Effort Delivery:

      * Best Effort Delivery

          > El mecanismo de mejor esfuerzo o entrega de mejor esfuerzo (Best-effort delivery, en inglés) designa
          > un tipo de servicio de red en el que la red no puede garantizar que los datos lleguen a su destino,
          > ni ofrecer al usuario una determinada calidad de servicio (QoS) en sus comunicaciones.

          > En una red de «mejor esfuerzo» (best-effort network) todos los usuarios reciben el mejor servicio
          > posible en ese momento, lo que significa que obtendrán distintos anchos de banda y tiempos de respuesta
          > en función del volumen de tráfico en la red.la retransmisión de todos los segmentos siguientes
         > en la ventana. La ventana se desplaza a medida qu se reciben ACK's. El receptor envía el ACK sólo
         > del segmento recibido correctamente de mayor númeo de secuencia en orden -es decir, que no le falte
         > ninguno-. Puede generar acuses duplicados. No preisa buffers, ya que descarta los segmentos fuera de
         > orden y duplicados (al descartar re envía el ACK el mayor número de secuencia que recibió).

# Capa de Red

  **Clase**  | **Dir publicas** | **Dir privadas**
  A | 1.0.0.0 - 126.0.0.0 | 10.x.x.x
  B | 128.0.0.0 - 191.255.0.0 | 172.16.x.x - 172.31.x.x
  C | 192.0.0.0 - 223.255.255.0 | 192.168.x.x


  > La capa de Red permite la conexión desde un host origen a un host destino. En TCP/IP está
  > implementada en el protocolo IP, e interviene en cada host y encaminador intermedio (router).
  > El PDU es el datagrama, que encapsula los segmentos de Transporte agregándole las direcciones
  > IP origen y destino.

  > Ofrece dos tipos de servicios:

  > * Retransmisión (forwarding): Los datagramas que llegan a un router son dirigidos a la
  > interfaz de salida apropiada.
  > * Encaminamiento (routing): Determina el camino que toman los paquetes desde el origen
  > al destino (según diferentes algoritmos de routeo).

  * **Ruteo Estatico**
      > Redes que cambian lentamente en el tiempo, por ejemplo un administrador edita manualmente
      > la tabla de ruteo de un router.

      > **Ventaja:** algoritmo de ruteo mas simple. Apropiado si el trafico de red es predecible.
      > los cambios se reflejan ni bien el administrador modifica la tabla
      > **Desventaja:** precisa configuracion manual, se vuelve inmanejable en redes grandes cambiantes
      > propenso a errores.

  * **Ruteo Dinamico**
      > Las rutas cambian constantemente de acuerdo a la carga de  la red o bien por cambios en la topologia
      > Puede ejecutarse el algoritmo de ruteo dinamico periodicamente o por cambios en la topologia. Si el
      > router detecta un cambio, recalcula su tabla y propaga cambios a los vecinos para que se recalculen.

      > **Ventaja:** Reaccion rapida ante cambios en la red, precisa poca configuracion.
      > **Desventaja:** Procesamiento extra por el algoritmo. Los cambios detectados por un router pueden
      > tardar en informarse al resto.

      > los algoritomos de ruteo dinamico se dividen en ESTADO DE ENLACE (conoce solo sus vecinos) y
      > VECTOR DE DISTANCIA (conoce toda la topologia)

  * **Subred**
       >   Una subred es un rango de direcciones lógicas. Cuando una red se vuelve muy grande, conviene
       >  dividirla en subredes, para reducir el tamaño de los dominios de broadcast, y hacer la red más
       >  manejable.

  **¿Qué es CIDR (Class Interdomain routing)? ¿Por qué resulta útil?**
    > CIDR encaminamiendo Inter-dominio sin clase, es una mejora en la forma de interpretar las direcciones
    > IP. Su introduccion permitio una mayos flexibilidad al dividir rangos de direcciones IP en redes separadas.
    > De esta manera permitio.
      * Un uso mas eficiente de la cada vez mas escasas direcciones IPV4.

  **VLSM** (Mascara de subred de longitud variable) tecnica utilizada por CIDR para la asignacion de prefijos
    de longitud arbitraria.

  **PING (funcionamiento)**
    > Utiliza el protocolo ICMP para solicitar a un host/gateway una respuesta de echo. Envía un
    > datagrama ECHO_REQUEST al IP indicado. Útil para controlar que una interfaz este funcionando
    > o que hay conectividad. Al terminar, muestra algunas estadísticas como cantidad de paquetes
    > perdidos, TTL mínimo/medio/máximo...

  ## DHCP
  El protocolo de configuración dinámica de host, protocolo de tipo cliente/servidor mediante el cual
  un servidor asigna IP dinamicamente  para que puedan comunicarse con otras redes IP.
  Este servidor posee una lista de direcciones IP dinámicas y las va asignando a los clientes conforme
  éstas van quedando libres, sabiendo en todo momento quién ha estado en posesión de esa IP

  Asignación manual o estática
Asigna una dirección IP a una máquina determinada. Se suele utilizar cuando se quiere controlar la
asignación de dirección IP a cada cliente, y evitar, también, que se conecten clientes no identificados.

Asignación automática
Asigna una dirección IP a una máquina cliente la primera vez que hace la solicitud al servidor DHCP
y hasta que el cliente la libera. Se suele utilizar cuando el número de clientes no varía demasiado.

Asignación dinámica
El único método que permite la reutilización dinámica de las direcciones IP. El administrador de la
red determina un rango de direcciones IP y cada dispositivo conectado a la red está configurado para
solicitar su dirección IP al servidor cuando la tarjeta de interfaz de red se inicializa.
El procedimiento usa un concepto muy simple en un intervalo de tiempo controlable. Esto facilita
la instalación de nuevas máquinas clientes.


NAT
es un mecanismo utilizado por routers IP para intercambiar paquetes entre dos redes que asignan
mutuamente direcciones incompatibles. Consiste en convertir, en tiempo real, las direcciones
\utilizadas en los paquetes transportados

IPV6
1. ¿Por qué no es necesario el campo Header Length en IPv6?
1. ¿En qué se diferencia el checksum de IPv4 e IPv6? Y en cuánto a los campos checksum de TCP y UDP,
¿sufren alguna modificación?
1. Transforme las siguientes direcciones MACs en Identificadores de Interfaces de 64 bits.
00:1b:77:b1:49:a1
e8:1c:23:a3:21:f4
1. . ¿Cuál de las siguientes direcciones IPv6 no son válidas?
2001:0:1019:afde::1
2001::1871::4
3ffg:8712:0:1:0000:aede:aaaa:1211
3::1
::
2001::
3ffe:1080:1212:56ed:75da:43ff:fe90:affe
3ffe:1080:1212:56ed:75da:43ff:fe90:affe:1001
1. ¿Cuál sería una abreviatura correcta de 3f80:0000:0000:0a00:0000:0000:0000:0845?
3f80::a00::845
3f80::a:845
3f80::a00:0:0:0:845:4567
3f80:0:0:a00::845
3f8:0:0:a00::845. ¿Es necesario el protocolo ICMP en IPv6? ¿Cumple las mismas funciones que en IPv4?

# Capa de enlace

  > La Capa de Enlace tiene la responsabilidad de transferir datagramas desde un nodo al
  > nodo adyacente a través de un enlace individual (direccionamiento físico), contrastando
  > con la capa de Transporte que ofrece comunicación entre hosts remotos.
  > Define el formato de los "frames" que se intercambian entre los nodos a los extremos del
  > enlace y las acciones que llevan a cabo para transmitir y recibir frames. Ofrece servicios de:

  * Entramado y acceso al medio. Encapsula al datagrama en el frame
  (fragmentando de ser necesario). Incluye direcciones MAC -físicas, según el NIC
  (placa de red)-. Controla el acceso al medio si es compartido, coordinando las
  transmisiones de los nodos.

  * Transferencia confiable. Basado en confirmaciones y retransmisiones como
  TCP. Si el enlace no es confiable para evitar
  retransmisiones a nivel de red o aplicación -se utiliza en wireless por ejemplo,
  pero no con fibra óptica, coaxial ni algunas versiones de par trenzado para no
  sobrecargar duplicando funciones-.

  * Control de flujo.

  * Detección de Errores. Producidos por atenuación de la señal o ruido
  electromagnético. Muy común; se implementa en hardware y es más sofisticado
  que el realizado por capas superiores.

  * Corrección de Errores (algunos protocolos; ATM permite la detección sólo en el
  header).

  * Conexiones Full-Dulpex y Half-Duplex. En las primeras un nodo puede
  transmitir y recibir a la vez; en las segundas no.

  * MAC (6 bytes)
      necesaria para
tabla ARP
ARP request
ARP replay
