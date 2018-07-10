# INTRODUCCION
  * Que son las RFCs?.
      Primero los RFC eran comentarios y aportes; luego se hizo un estandar.
      Cada una de ellas individualmente es un documento cuyo contenido es una propuesta oficial
      para un nuevo protocolo de la red Internet. Cualquiera puede enviar una propuesta de RFC
      la la IETF (Grupo de Trabajo en Ingeniería de Internet), pero es ésta la que decide
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
      |-------------------:|----------------|
      | Aplicacion         | Aplicacion     |
      | Presentacion       |                |
      | Session            |                |
      |-------------------:|----------------|
      | Segmento           | Transporte     |
      |-------------------:|----------------|
      | Red                | Red            |
      |-------------------:|----------------|
      | Enlace             | Enlace         |
      |-------------------:|----------------|
      | FIsico             | Fisico         |


  * OSI y TCP/IP.
      * ambos estan divididos en niveles o capas.
      * ambos tienen capa de aplicaciones pero brindan servicios distintos.
      * ambos tienen capa de transporte y de red similares.
      * TCP/IP combina la capa de presentacion y de sesion en la capa de Aplicacion.
      * TCP/IP combina la capa de enlace de datos y la capa fisica del modelo OSI en una sola capa.
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

#Capa de Aplicacion

  > La capa de aplicación da soporte a las aplicaciones de red; incluye los
  > protocolos HTTP (Web), SMTP (email) y FTP (transferencias de archivos) entre
  > otros.


  * ## HTTP:80 (Hyper Text Transfer Protocol, command curl)
      > Protocolo de capa de aplicacion que da sopoerte a transferencia de objetos de la web.
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

         >   (File Transfer Protocol) permite transferir archivos desde y hasta un host
         > remoto, con autentificación por medio de usuario y contraseña.

        >  El funcionamiento del protocolo FTP trabaja en un modelo cliente/servidor, pero se distingue de los
        > demás servicios por el hecho de usar una conexión para el protocolo de control (Out-Of-Band Control) y
        > otra conexión para la transferencia de datos. El protocolo se ejecuta sobre TCP porque requiere un
        > protocolo de transporte que le brinde detección de errores (confiabilidad).

         > 20/tcp data port
         > 21/tcp control port

         * Modo activo (servidor): el servidor siempre crea el canal de datos en su puerto 20, mientras que del
         lado del cliente el canal de datos se asocia a un puerto  mayor a 1024. El cliente le dice al servidor 
         por el canal de control que puerto usara.

         * Modo pasivo: el cliente se conecta al con el servidor, este le manda por el canal de control, el puero mayor
         a 1024 del servidor al q debe conectarse el cliente

  * ## TFTP
  * ## DNS:53 (command dig)

        > Los name server mantienen registros de recursos (RR) con un mapeo __hostname__<==>__IP__
        > en una cuadrupla (name, value, type, TTL)

      **A:** direccion IP.
      **NS:** servidores de nombres que tiene autoridad para el dominio.
      **SOA:** indica que los registros siguientes de la base de datos conrresponden
      a informacion autoritativa
      **PTR:** indica el dominio de la ip consultada.
      **AAA:** igual que **A** pero para **IPV6**.
      **CNAME:** permine identificar alias o subdominios equivalentes.
      **MX:** servidor de correo electronico para el dominio.


      **Servidor DNS** es una base de datos distribuida implementada en una
    jerarquía de servidores de nombres.

      **DNS protocolo** de nivel de aplicación que permite a los hosts y dichos
    servidores comunicarse para proveer el servicio de traducción, entre la
    dirección mnemónica y la dirección IP.
      Un host hace su solicitud a un servidor local de nombres, que, si no posee
    la traducción, se transforma en un cliente consultando a un servidor raíz
    de nombres *root server*. Si el *root server* conoce al servidor autorizado
    de nombres para el dominio que se intenta resolver, envía la solicitud
    terminando la cadena; si lo desconoce, consulta a servidores intermedios
    hasta que eventualmente alguno lo conozca. En cada uno de los paso, los
    servidor podríam tener registrado el IP del dominio consultado o mantenerlo
    en cache por una consulta anterior, ofreciendo una respuesta directa.

        TLD:    .com  .org .net .info
        g-TDL

      **Respuesta authoritative:** es aquella entregada por el servidor oficial
      para el nombre de dominio consultado, es decir, que ningún servidor local,
      raíz ni intermedio respondió con información de caché.

      **Consulta DNS Recursiva:** Un host realiza una consulta a un servidor,
      éste se encarga de obtener la resolución de IP y devuelve la respuesta al
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
          >  escribir un mail, el user agent busca la IP del servidor de correos del dominio que ofrece
          >  la cuenta (servidor SMTP de yahoo.com) para realizar la conexión SMTP y enviar el
          >  correo. El servidor de yahoo, utiliza luego DNS para averiguar la IP del servidor de
          >  correo de hotmail.com, establace la conexión y envía el email. El destinatario,
          >  eventualmente revisa su correo con su user agent, que utilizará DNS para averiguar la IP
          >  del servidor POP3 o IMAP.

#Capa de transporte
  * ##UDP:69
  * ##TCP


#Capa de Red


#Capa de enlace
