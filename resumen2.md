#Capa de Aplicacion

La capa de aplicación da soporte a las aplicaciones de red; incluye los
protocolos HTTP (Web), SMTP (email) y FTP (transferencias de archivos) entre
otros.


  * ##HTTP:80
  * ##FTP
  * ##TFTP
  * ##DNS:53

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
      hasta obtener la respuesta.


  * ##Correo electronico
      * ###SMTP:25
      * ###IMAP
      * ###POP


#Capa de transporte
  * ##UDP:69
  * ##TCP


#Capa de Red


#Capa de enlace
