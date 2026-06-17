# Practica 3 - Capa de Aplicación DNS (Domain Name Server)

1. ## Investigue y describa cómo funciona el DNS. ¿Cuál es su objetivo?

    DNS son las iniciales de Domain Name System (sistema de nombres de dominio) y es una tecnología basada en una base de datos que sirve para resolver nombres en las redes, es decir, para conocer la dirección IP de la máquina donde está alojado el dominio al que queremos acceder.

    La resolución de nombres utiliza una estructura en árbol, mediante la cual los diferentes servidores DNS de las zonas de autoridad se encargan de resolver las direcciones de su zona, y si no se lo solicitan a otro servidor que creen que conoce la dirección.

2. ## ¿Qué es un root server? ¿Qué es un generic top-level domain (gtld)?

    Un servidor raíz (root server en inglés) es un servidor de nombres para la zona raíz del Sistema de nombres de dominio de Internet (DNS). Los servidores de nombres raíz son una parte fundamental de Internet, ya que son el primer paso en la traducción (resolución) de los nombres de host legibles en direcciones IP que se utilizan en la comunicación entre los hosts de Internet.

    Un dominio de nivel superior o TLD (del inglés top-level domain) es la más alta categoría de los FQDN que es traducida a direcciones IP por los DNS oficiales de Internet. Los nombres servidos por los DNS oficiales son administrados por la Internet Corporation for Assigned Names and Numbers (ICANN). Alternativamente a los DNS oficiales, hay una serie de servicios de DNS alternativos, como es OpenNIC.

    Un dominio de nivel superior genérico (generic Top Level Domain o gTLD) es una de las categorías de dominios de nivel superior que mantiene la Internet Assigned Numbers Authority (IANA) para su uso en el sistema de nombres de dominio de Internet. Es visible para los usuarios de Internet como el sufijo al final de un nombre de dominio (ej: .com).

3. ## ¿Qué es una respuesta del tipo autoritativa?

    Un servidor DNS autoritativo es aquel que tiene una respuesta en su base de datos local para un dominio sobre el que se le pregunte. Es en estos proveedores donde se crean los registros DNS que después conformarán el contenido de lo que es un servidor DNS.

4. ## ¿Qué diferencia una consulta DNS recursiva de una iterativa?

    En una consulta recursiva, un cliente solicita a un servidor DNS que obtenga por sí mismo la respuesta completa (es decir, dado el dominio mi.dominio.com, el cliente espera recibir la dirección IP correspondiente). Por otro lado, dada una consulta iterativa, el servidor DNS no otorga una respuesta completa: para el caso de mi.dominio.com, el primer servidor al que se le realiza la consulta (un servidor raíz), retorna las direcciones IP de los servidores de nivel superior (TDL) responsables del dominio .com. De este modo, el cliente ahora debe realizar una nueva consulta a uno de estos servidores, el cual toma nota del sufijo .dominio.com y responde con la IP del servidor DNS correspondiente, por ejemplo dns.dominio.com. Finalmente, el cliente envía una nueva consulta a dns.dominio.com para obtener la dirección IP de mi.dominio.com

5. ## ¿Qué es el resolver?

    Un resolver es una parte del sistema operativo que se encarga de realizar las consultas a un servidor DNS, interpretarlas y devolverlas al programa que ha efectuado la consulta. Los servidores DNS también pueden incorporar un resolver, que gestiona las consultas que un servidor DNS debe hacer.

    Un resolver siempre suele hacer consultas recursivas exclusivamente.

6. ## Describa para qué se utilizan los siguientes tipos de registros de DNS

    - ### a. A

        El registro “A” hace referencia a la Dirección y es el tipo más básico de sintaxis de DNS. Indica la dirección de IP real de un dominio.


    - ### b. MX

        El registro “MX” o intercambio de correo es principalmente una lista de servidores de intercambio de correo que se debe utilizar para el dominio.


    - ### c. PTR

        El registro “PTR” significa “Punto de Terminación de Red”. La sintaxis de DNS es responsable del mapeo de una dirección IPv4 para el CNAME en el alojamiento.

    - ### d. AAAA

        El registro “AAAA” (también conocido como dirección IPv6) indica el nombre de alojamiento a una dirección IPv6 de 128 bits. Las direcciones DNS normales se mapean para direcciones IPv4 de 32 bits.


    - ### e. SRV

        Un registro “SRV” significa “Servicio”. Se utiliza para la definición de un servicio TCP en el que opera el dominio.

    - ### f. NS

        El registro “NS” significa Servidor de nombres e indica que nombre del servidor es el autorizado para el dominio.

    - ### g. CNAME

        El registro “CNAME” significa nombre canónico y su función es hacer que un dominio sea un alias para otro. El CNAME generalmente se utiliza para asociar nuevos subdominios con dominios ya existentes de registro A.

    - ### h. SOA

        Un registro “SOA” significa “Comienzo de Autoridad”. Evidentemente, es uno de los registros DNS más importantes, dado que guarda información esencial, como la fecha de la última actualización del dominio y otros cambios y actividades.

    - ### i. TXT

        Un registro “TXT” significa “Texto”. Esta sintaxis de DNS permite que los administradores inserten texto en el registro DNS. A menudo se utiliza para denotar hechos o información sobre el dominio.

7. ## En Internet, un dominio suele tener más de un servidor DNS, ¿por qué cree que esto es así?

    Los dominios suelen tener más de un servidor ya que puede haber una falla y al tener varios servidores se evita el perder el dominio.

8. ## Cuando un dominio cuenta con más de un servidor, uno de ellos es el primario (o maestro) y todos los demás son secundarios (o esclavos). ¿Cuál es la razón de que sea así?

    Los dominios se implementan como clusters de servidores donde un servidor maestro guarda la información sobre una zona determinada del espacio de nombres de dominio en su propia base de datos. Cuando la información de un servidor de nombres que no procede de los archivos de zona propios, sino que son de segunda o de tercera mano, este servidor se convierte en secundario o esclavo para esta información.

    Esto se produce cuando un servidor no puede resolver la petición con la información de su base de datos y ha de recurrir a la información disponible en otro servidor de nombres (resolución recursiva).

    La información que contienen los servidores esclavos puede no ser segura ya que pueden haber cambiado las entradas en el archivo de zona en el ínterin.

9. ## Explique brevemente en qué consiste el mecanismo de transferencia de zona y cuál es su finalidad

    Es uno de los varios mecanismos disponibles para replicar bases de datos DNS a través de un conjunto de servidores DNS. Se producirá una transferencia de zona durante cualquiera de los siguientes escenarios:

    - Al iniciar el servicio DNS en el servidor DNS secundario.
    - Cuando caduca el tiempo de actualización.
    - Cuando se guardan los cambios en el archivo de zona principal y hay una notificación lista.

    Una transferencia de zona utiliza el protocolo TCP para el transporte, y toma la forma de una transacción de cliente-servidor. El cliente que solicita una transferencia de zona puede ser un servidor esclavo o servidor secundario, que solicita datos de un servidor maestro, a veces llamado un servidor primario. La parte de la base de datos que se replica es una zona.

10. ## Imagine que usted es el administrador del dominio de DNS de la UNLP (unlp.edu.ar). A su vez, cada facultad de la UNLP cuenta con un administrador que gestiona su propio dominio (por ejemplo, en el caso de la Facultad de Informática se trata de info.unlp.edu.ar). Suponga que se crea una nueva facultad, Facultad de Redes, cuyo dominio será redes.unlp.edu.ar, y el administrador le indica que quiere poder manejar su propio dominio. ¿Qué debe hacer usted para que el administrador de la Facultad de Redes pueda gestionar el dominio de forma independiente? (Pista: investigue en qué consiste la delegación de dominios). Indicar qué registros de DNS se deberían agregar

    Para que el administrador de la Facultad de Redes pueda gestionar su dominio de forma independiente, se debe definir el espacio de dominio y su administración y luego es necesario delegarlo al servidor unlp.edu.ar de manera distribuida. La delegación consiste en saber las direcciones IP de los servidores que se encargan de resolver (o sub-delegar) las zonas de manera autoritativa.

    Para esto, se deben agregar registros NS (Name Server) en el servidor unlp.edu.ar que apunten a los servidores DNS de la Facultad de Redes, y también se deben agregar registros A (Address) para asociar los nombres de los servidores DNS de la Facultad de Redes con sus respectivas direcciones IP. De esta manera, cuando alguien intente resolver un dominio bajo redes.unlp.edu.ar, el servidor unlp.edu.ar sabrá que debe consultar a los servidores DNS de la Facultad de Redes para obtener la información necesaria.

11. ## Responda y justifique los siguientes ejercicios

    - ### a. En la VM, utilice el comando dig para obtener la dirección IP del host <www.redes.unlp.edu.ar> y responda

        ``` bash
        dig www.redes.unlp.edu.ar

        ; <<>> DiG 9.16.27-Debian <<>> www.redes.unlp.edu.ar
        ;; global options: +cmd
        ;; Got answer:
        ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 31965
        ;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

        ;; OPT PSEUDOSECTION:
        ; EDNS: version: 0, flags:; udp: 1232
        ; COOKIE: 421d32ee557125dc010000006a32ceb4ef70070642f2a4d4 (good)
        ;; QUESTION SECTION:
        ;www.redes.unlp.edu.ar.		IN	A

        ;; ANSWER SECTION:
        www.redes.unlp.edu.ar.	300	IN	A	172.28.0.50

        ;; Query time: 4 msec
        ;; SERVER: 172.28.0.29#53(172.28.0.29)
        ;; WHEN: Wed Jun 17 13:43:32 -03 2026
        ;; MSG SIZE  rcvd: 94
        ```
        - #### i. ¿La solicitud fue recursiva? ¿Y la respuesta? ¿Cómo lo sabe?

            Si, la solicitud fue recursiva ya que el flag rd (recursion desired) está presente en la respuesta. La respuesta también es recursiva, dado que el flag ra (recursion available) también está presente.

        - #### ii. ¿Puede indicar si se trata de una respuesta autoritativa? ¿Qué significa que lo sea?

            Sí, se trata de una respuesta autoritativa, dado que el flag aa (authoritative answer) está presente en la respuesta. Esto significa que el servidor DNS que respondió a la consulta es el servidor autoritativo para el dominio www.redes.unlp.edu.ar, lo que implica que tiene la información más actualizada y confiable sobre ese dominio.

        - #### iii. ¿Cuál es la dirección IP del resolver utilizado? ¿Cómo lo sabe?

            La dirección IP del resolver utilizado es 172.28.0.29. Esto se puede saber porque en la sección "SERVER" de la respuesta se indica que el servidor que respondió a la consulta es 172.28.0.29.

    - ### b. ¿Cuáles son los servidores de correo del dominio redes.unlp.edu.ar? ¿Por qué hay más de uno y qué significan los números que aparecen entre MX y el nombre? Si se quiere enviar un correo destinado a redes.unlp.edu.ar, ¿a qué servidor se le entregará? ¿En qué situación se le entregará al otro?

        ```bash
        dig mx redes.unlp.edu.ar +short

        5 mail.redes.unlp.edu.ar.
        10 mail2.redes.unlp.edu.ar.
        ```

        Los servidores de correo del dominio redes.unlp.edu.ar son mail.redes.unlp.edu.ar y mail2.redes.unlp.edu.ar. Hay más de uno para garantizar la disponibilidad y redundancia en caso de que uno de los servidores falle. Los números que aparecen entre MX y el nombre indican la prioridad del servidor de correo, siendo el número más bajo el de mayor prioridad. Si se quiere enviar un correo destinado a redes.unlp.edu.ar, se le entregará al servidor mail.redes.unlp.edu.ar, ya que tiene la prioridad más alta (5). Si ese servidor no está disponible, entonces se le entregará al otro servidor mail2.redes.unlp.edu.ar, que tiene una prioridad de 10.

    - ### c. ¿Cuáles son los servidores de DNS del dominio redes.unlp.edu.ar?

        ```bash
        dig ns redes.unlp.edu.ar +short

         <<>> DiG 9.16.27-Debian <<>> ns redes.unlp.edu.ar
        ;; global options: +cmd
        ;; Got answer:
        ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 53762
        ;; flags: qr aa rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 3

        ;; OPT PSEUDOSECTION:
        ; EDNS: version: 0, flags:; udp: 1232
        ; COOKIE: 44e2d76afeea13e7010000006a32d0e48f9bc325212df687 (good)
        ;; QUESTION SECTION:
        ;redes.unlp.edu.ar.		IN	NS

        ;; ANSWER SECTION:
        redes.unlp.edu.ar.	86400	IN	NS	ns-sv-b.redes.unlp.edu.ar.
        redes.unlp.edu.ar.	86400	IN	NS	ns-sv-a.redes.unlp.edu.ar.

        ;; ADDITIONAL SECTION:
        ns-sv-a.redes.unlp.edu.ar. 604800 IN	A	172.28.0.30
        ns-sv-b.redes.unlp.edu.ar. 604800 IN	A	172.28.0.29

        ;; Query time: 4 msec
        ;; SERVER: 172.28.0.29#53(172.28.0.29)
        ;; WHEN: Wed Jun 17 13:52:52 -03 2026
        ;; MSG SIZE  rcvd: 150

        ```

    - ### d. Repita la consulta anterior cuatro veces más. ¿Qué observa? ¿Puede explicar a qué se debe?

        Se puede observar:

        - Cambia el ID de la consulta
        - Cambuia el orden de los servidores de DNS que aparecen en la respuesta
        - Cammbia COOKIE
        - El TTL y NS son los mismos
        - Cambia el valor When de la consutla
        - Cmabia el Query time

        Esto se debe a que el servidor DNS está utilizando un mecanismo de balanceo de carga para distribuir las consultas entre los servidores de DNS disponibles. Al cambiar el orden de los servidores de DNS en la respuesta, el servidor DNS puede dirigir las consultas a diferentes servidores en cada consulta, lo que ayuda a distribuir la carga y mejorar el rendimiento del sistema DNS. Además, el cambio en el ID de la consulta y la COOKIE es parte del proceso normal de generación de consultas DNS para garantizar la seguridad y la integridad de las respuestas.

    - ### e. Observe la información que obtuvo al consultar por los servidores de DNS del dominio. En base a la salida, ¿es posible indicar cuál de ellos es el primario?

        No, no es posible indicar cuál de los servidores de DNS es el primario solo con la información obtenida al consultar por los servidores de DNS del dominio. La consulta por los servidores de DNS (registro NS) solo proporciona información sobre los servidores que están autorizados para el dominio, pero no indica cuál de ellos es el primario o maestro. Para determinar cuál es el servidor primario, se necesitaría consultar el registro SOA (Start of Authority) del dominio, que contiene información sobre el servidor primario y otros detalles relacionados con la zona DNS.

    - ### f. Consulte por el registro SOA del dominio y responda

        ```bash
        redes@debian:~$ dig soa redes.unlp.edu.ar

        ; <<>> DiG 9.16.27-Debian <<>> soa redes.unlp.edu.ar
        ;; global options: +cmd
        ;; Got answer:
        ;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 62922
        ;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

        ;; OPT PSEUDOSECTION:
        ; EDNS: version: 0, flags:; udp: 1232
        ; COOKIE: 9c32fc9c6b3ef0c1010000006a32d244730fd906c6047124 (good)
        ;; QUESTION SECTION:
        ;redes.unlp.edu.ar.		IN	SOA

        ;; ANSWER SECTION:
        redes.unlp.edu.ar.	86400	IN	SOA	ns-sv-b.redes.unlp.edu.ar. root.redes.unlp.edu.ar. 2020031700 604800 86400 2419200 86400

        ;; Query time: 4 msec
        ;; SERVER: 172.28.0.29#53(172.28.0.29)
        ;; WHEN: Wed Jun 17 13:58:44 -03 2026
        ;; MSG SIZE  rcvd: 123
        ```


        - #### i. ¿Puede ahora determinar cuál es el servidor de DNS primario?

            Sí, ahora se puede determinar que el servidor de DNS primario es ns-sv-b.redes.unlp.edu.ar, ya que es el servidor que aparece en el registro SOA como el servidor de nombres principal para la zona redes.unlp.edu.ar.

        - #### ii. ¿Cuál es el número de serie, qué convención sigue y en qué casos es importante actualizarlo?

            El número de serie es 2020031700. La convención que sigue es YYYYMMDDNN, donde YYYY es el año, MM es el mes, DD es el día y NN es un número de dos dígitos que se incrementa cada vez que se realiza una actualización en el mismo día. Es importante actualizar el número de serie cada vez que se realice un cambio en la zona DNS, ya que los servidores secundarios utilizan este número para determinar si necesitan actualizar su copia de la zona. Si el número de serie no se actualiza correctamente, los servidores secundarios pueden no recibir las actualizaciones y servir información obsoleta a los clientes.

        - #### iii. ¿Qué valor tiene el segundo campo del registro? Investigue para qué se usa y cómo se interpreta el valor.



        - #### iv. ¿Qué valor tiene el TTL de caché negativa y qué significa?

    - ### g. Indique qué valor tiene el registro TXT para el nombre saludo.redes.unlp.edu.ar. Investigue para qué es usado este registro.

    - ### h. Utilizando dig, solicite la transferencia de zona de redes.unlp.edu.ar, analice la salida y responda.

        - #### i. ¿Qué significan los números que aparecen antes de la palabra IN? ¿Cuál es su finalidad?

        - #### ii. ¿Cuántos registros NS observa? Compare la respuesta con los servidores de DNS del dominio redes.unlp.edu.ar que dio anteriormente. ¿Puede explicar a qué se debe la diferencia y qué significa?

    - ### i. Consulte por el registro A de <www.redes.unlp.edu.ar> y luego por el registro A de <www.practica.redes.unlp.edu.ar>. Observe los TTL de ambos. Repita la operación y compare el valor de los TTL de cada uno respecto de la respuesta anterior. ¿Puede explicar qué está ocurriendo? (Pista: observar los flags será de ayuda).

    - ### j. Consulte por el registro A de <www.practica2.redes.unlp.edu.ar>. ¿Obtuvo alguna respuesta? Investigue sobre los códigos de respuesta de DNS. ¿Para qué son utilizados los mensajes NXDOMAIN y NOERROR?
