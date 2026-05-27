# Practica 1 - Introducción

1. ## ¿Qué es una red? ¿Cuál es el principal objetivo para construir una red?

    Una red es un conjunto de computadoras o dispostivos interconectados que tiene como objetivo compartir recurtos, información y servicios o hasta otros dispositivos para que sean utilizados.

2. ## ¿Qué es Internet? Describa los principales componentes que permiten su funcionamiento.

    Internes es un conjunto descentralizado de redes de comunicación interconectadas que utilizan la familia de protocolos TCP/IP, lo cual garantiza que las redes físicas heterogéneas que la componen constituyan una red lógica única de alcance mundial.

    Los componentes de Internet son:
    - Servidores
    - Líneas de comunicación entre nodos de Internet
    - Clientes y programas o software para hacer que la red funcione
    - Protocolo TCP/IP

3. ## ¿Qué son las RFCs?

    Los Request for Comments, más conocidos por sus siglas RFC, son una serie de publicaciones del grupo de trabajo de ingeniería de internet que describen diversos aspectos del funcionamiento de Internet y otras redes de computadoras, como protocolos, procedimientos, etc. y comentarios e ideas sobre estos.​ Cada RFC constituye un monográfico o memorando que ingenieros o expertos en la materia han hecho llegar al IETF, el consorcio de colaboración técnica más importante en Internet, para que este sea valorado por el resto de la comunidad. De hecho, la traducción literal de RFC al español es "Petición de comentarios".

4. ## ¿Qué es un protocolo?

    Un protocolo es el conjunto de conductas y normas a conocer, respetar y cumplir no solo en el medio oficial ya establecido, sino también en el medio social, laboral, etc.

    Define el formato, el orden de los mensajes intercambiados y las acciones que se llevan a cabo en la transmisión y/o recepción de un mensaje u otro evento.

    Un protocolo de red es el conjunto de reglas que especifican el intercambio de datos u órdenes durante la comunicación entre las entidades que forman parte de una red. Permiten la comunicación y están implementados en las componentes.


5. ## ¿Por qué dos máquinas con distintos sistemas operativos pueden formar parte de una misma red?

    Las máquinas con distintos sistemas operativos pueden formar parte de una misma red ya que esos sistemas respetan los protocolos y saben cómo comunicarse mediante una red independientemente de cómo funcione su sistema.

6. ## ¿Cuáles son las 2 categorías en las que pueden clasificarse a los sistemas finales o End Systems? Dé un ejemplo del rol de cada uno en alguna aplicación distribuida que corra sobre Internet.

    En la jerga de las redes de computadoras, las computadoras que usamos a diario a menudo se denominan hosts o sistemas finales. Se les conoce como "hosts" porque albergan (ejecutan) programas a nivel de aplicación, como un navegador web, un programa de servidor o un programa de correo electrónico. También se conocen como "sistemas finales" porque se encuentran en el "borde" de Internet.

    A veces, los hosts se dividen en dos categorías: clientes y servidores. De manera informal, los clientes suelen ser PC de escritorio o estaciones de trabajo, mientras que los servidores son máquinas más potentes.

    Un programa cliente es un programa que se ejecuta en un sistema final que solicita y recibe un servicio de un programa servidor que se ejecuta en otro sistema final como lo son los navegadores de Internet sobre los programas de servidores web o servidores de correo.

7. ## ¿Cuál es la diferencia entre una red conmutada de paquetes de una red conmutada de circuitos?

    La conmutación de circuitos es un tipo de comunicación que establece o crea un canal dedicado (o circuito) durante la duración de una sesión. Después de que es terminada la sesión (ej. una llamada telefónica) se libera el canal y éste podrá ser usado por otro par de usuarios.

    En los sistemas basados en conmutación de paquetes, la información/datos a ser transmitida previamente es ensamblada en paquetes. Cada paquete es entonces transmitido individualmente y éste puede seguir diferentes rutas hacia su destino. Una vez que los paquetes llegan a su destino, los paquetes son otra vez re-ensamblados.

    Mientras que la conmutación de circuitos asigna un canal único para cada sesión, en los sistemas de conmutación de paquetes el canal es compartido por muchos usuarios simultáneamente. La mayoría de los protocolos de WAN tales como TCP/IP, X.25, Frame Relay, ATM, son basados en conmutación de paquetes.

    La conmutación de paquetes es más eficiente y robusto para datos que pueden ser enviados con retardo en la transmisión (no en tiempo real), tales como el correo electrónico, páginas web, archivos, etc.

    En el caso de aplicaciones como voz, video o audio la conmutación de paquetes no es muy recomendable a menos que se garantice un ancho de banda adecuado para enviar la información. Pero el canal que se establece no garantiza esto, debido a que puede existir tráfico y nodos caídos durante el recorrido de los paquetes. Estos son factores que ocasionen que los paquetes tomen rutas distintas para llegar a su destino. Por eso se dice que la ruta que toman los paquetes es "probabilística", mientras que, en la conmutación de circuitos, esta ruta es "determinística".

8. ## Analice qué tipo de red es una red de telefonía y qué tipo de red es Internet.

    La red de telefonía es una red conmutada de circuitos, ya que se establece un canal dedicado durante la duración de una sesión. Después de que es terminada la sesión (ej. una llamada telefónica) se libera el canal y éste podrá ser usado por otro par de usuarios.

    Internet es una red conmutada de paquetes, ya que la información/datos a ser transmitida previamente es ensamblada en paquetes. Cada paquete es entonces transmitido individualmente y éste puede seguir diferentes rutas hacia su destino. Una vez que los paquetes llegan a su destino, los paquetes son otra vez re-ensamblados.

9. ## Describa brevemente las distintas alternativas que conoce para acceder a Internet en su hogar.

    Actualmente se contrata a un proveedor de internet (ISP) el cual instala un modem al cual mediante ethernet o de manera inalámbrica los dispositivos pueden conectarse a la red. La conexión que nos proveen puede ser por ADSL, fibra óptica, cable coaxial entre otras.

    Antiguamente se utilizaba la red de telefonía para poder conectarse a internet.

10. ## ¿Qué ventajas tiene una implementación basada en capas o niveles?

    El modelo en capas divide la complejidad en componentes más pequeños, las capas de abajo ocultan la complejidad a las de arriba y utiliza servicios de estas. Los cambios de una capa no deberían afectar a las demás si la interfaz se mantiene.

    Facilita el desarrollo, evolución de las componentes de red asegurando interoperabilidad. Facilita aprendizaje, diseño, y administración de las redes.

11. ## ¿Cómo se llama la PDU de cada una de las siguientes capas: Aplicación, Transporte, Red y Enlace?

    - La capa de aplicación usa el término de Datos como PDU.
    - La capa de transporte utiliza Segmento como PDU.
    - La capa de red utiliza Paquete como PDU.
    - La capa de enlace utiliza los Bits como PDU cuando se transmiten datos por el medio.

12. ## ¿Qué es la encapsulación? Si una capa realiza la encapsulación de datos, ¿qué capa del nodo receptor realizará el proceso inverso?

    Encapsulación o encapsulamiento se refiere al proceso por el cual, cada capa de la pila de protocolos (excepto la de aplicación), añade información adicional (denominada información de cabecera) al PDU recibido de la capa superior, formando así, el PDU correspondiente a la capa receptora.

    Los PDUs sirven para gobernar el comportamiento completo del protocolo en sus funciones de establecimiento y unión de la conexión, control de flujo, control de errores, etc.

    La capa que realiza el encapsulamiento en el nodo emisor va a ser la encargada de hacer el proceso inverso en el nodo receptor.

13. ## Describa cuáles son las funciones de cada una de las capas del stack TCP/IP o protocolo de Internet.

    - ### Capa Aplicación

        Ésta es la capa más alta dentro de la estructura jerárquica del protocolo TCP/IP incluye las aplicaciones y los procesos con los que intercambia datos la capa de transporte. TCP/IP tiene en esta capa protocolos que soportan servicios de conexión remota, correo electrónico y transferencia de archivos. De todos los protocolos de aplicación los más conocidos son:

        - **Telnet** (Network Terminal Protocol). Es un protocolo que permite establecer conexiones con terminales remotos, de tal manera que se puedan ejecutar en ellos comandos de configuración y control.

        - **HTTP** (Hipertext Transfer Protocol). Es un estándar de Internet que permite la transmisión de gran variedad de archivos de texto, gráficos, sonidos e imágenes. HTTP regula el proceso mediante el cual navegadores como Netscape, Mozilla o Internet Explorer solicitan información a los servidores web.

        - **DNS** (Domain Name Service). Esta aplicación convierte nombres de dispositivos y de nodos de red en direcciones IP. Por ejemplo, el nombre www.mcgraw-hill.es, se convierte en la dirección 198.45.24.91. Los servidores de red proporcionan servicios esenciales para las comunicaciones entre ordenadores. A diferencia de lo que ocurre con muchos programas de aplicación, estos servicios no facilitan el acceso al usuario final. Para más información se aconseja consultar el estándar RFC 1122.

    - ### Capa de Transporte

        En esta capa se encuentran definidos el protocolo TCP y el protocolo UDP (User Datagram Protocol). TCP permite enviar los datos de un extremo a otro de la conexión con la posibilidad de detectar errores y corregirlos. UDP, por el contrario, reduce al máximo la cantidad de información incluida en la cabecera de cada datagrama, ganando con ello rapidez a costa de sacrificar la fiabilidad en la transmisión de datos. Ciertas aplicaciones prefieren utilizar en la capa de transporte el protocolo UDP, aunque éste no haga corrección ni detección de errores. Como estas aplicaciones necesitan transmitir pequeñas cantidades de datos, resulta más eficaz reenviar los datagramas defectuosos que no sobrecargar cada uno con información de control en la cabecera. Si se requiere más fiabilidad en los datos transmitidos las aplicaciones recurren en la capa de transporte al protocolo TCP. Al revés que UDP, es un protocolo orientado a conexión, y el formato de los datos que maneja es muy distinto al de los datagramas. Para TCP los datos son una secuencia o trama continua de bytes, cada comunicación es seleccionada en la trama mediante segmentos.

    - ### Capa de Internet

        La capa Internet se encuentra justo encima de la capa de acceso a red. En este nivel el protocolo IP es el gran protagonista. Existen varias versiones del protocolo IP: IPv4 es en la actualidad el más empleado. El número de equipos que IPv4 puede direccionar comienza a quedarse corto. Para poner remedio a esta situación se ha desarrollado la versión IPv6, con una capacidad de direccionamiento muy superior a IPv4, pero totalmente incompatible. El protocolo IP se ha diseñado para redes de paquetes conmutados no orientadas a conexión, lo cual quiere decir que cuando dos equipos quieren conectarse entre sí no intercambian información para establecer la sesión. IP tampoco se encarga de comprobar si se han producido errores de transmisión, confía esta función a las capas superiores. Todo ello se traduce en que los paquetes de datos contienen información suficiente como para propagarse a través de la red sin que haga falta establecer conexiones permanentes. Para el protocolo IP un datagrama es el formato que debe tener un paquete de datos en la capa de red. La estructura de un datagrama: las seis primeras palabras de la cabecera y el punto desde el que se comienzan a transmitir los datos. Las cinco (o seis) primeras palabras de 32 bits contienen la información necesaria para que el datagrama se propague por la red, y a continuación se adjuntan los datos. La lógica de funcionamiento del protocolo IP es simple: para cada datagrama consulta la dirección origen (palabra 4) y la compara con la dirección destino (palabra 5). Si resulta que origen y destino se corresponden con equipos (hosts) de la misma red, el datagrama se envía directamente de un equipo a otro. Si, por el contrario, los equipos pertenecen a redes distintas, se hace necesaria la intervención de una puerta de enlace o gateway que facilite el envío a redes diferentes. El paso de datos de una red a otra a través de una puerta de enlace es conocido como «salto» (hop). Un datagrama puede realizar varios saltos a través de diversas redes hasta alcanzar su destino. El camino que siguen los datos enviados por un equipo a otro no tiene por qué ser siempre el mismo. La búsqueda del camino más adecuado a cada momento se denomina enrutamiento. De hecho, a las puertas de enlace se les denomina enrutadores (routers).

    - ### Capa de Acceso a Red

        La capa de acceso a red se encuentra en el nivel más bajo. En ésta capa se define cómo encapsular un datagrama IP en una trama que pueda ser transmitida por la red, siendo en una inmensa mayoría de redes LAN una trama Ethernet. Otra función importante de esta capa es la de asociar las direcciones lógicas IP a direcciones físicas de los dispositivos adaptadores de red (NIC). Dentro de la capa de acceso a red opera el protocolo ARP (Address Resolution Protocol) que se encarga precisamente de asociar direcciones IP con direcciones físicas Ethernet. El estándar RFC 826 describe su funcionamiento. Existe otra recomendación: la RFC 894 es el estándar para la transmisión de datagramas IP sobre redes Ethernet. Especifica cómo se encapsulan datagramas del protocolo IP para que puedan transmitirse en una red Ethernet.

14. ## Compare el modelo OSI con la implementación TCP/IP

    - ### Similitudes:
        - Ambos se dividen en capas.
        - Ambos tienen capas de aplicación, aunque incluyen servicios distintos.
        - Ambos tienen capas de transporte similares.
        - Ambos tienen capa de red similar, pero con distinto nombre.
        - Se supone que la tecnología es de conmutación de paquetes
          (no de conmutación de circuitos).
        - Es importante conocer ambos modelos

    - ### Diferencias:
        - TCP/IP combina las funciones de la capa de presentación y de sesión en la capa de aplicación.
        - TCP/IP combina las capas de enlace de datos y la capa física del modelo OSI en una sola capa.
        - TCP/IP es más simple porque tiene menos capas.
        - Los protocolos TCP/IP son los estándares en torno a los cuales se desarrolló Internet, de modo que la credibilidad del modelo TCP/IP se debe en gran parte a sus protocolos.
        - El modelo OSI es un modelo “más” de referencia, teórico, aunque hay implementaciones.
