# Practica 2 - Capa de Aplicacion HTTP

1. ## ¿Cuál es la función de la capa de aplicación?

    La función de la capa de Aplicación es proveer Servicios de comunicación a los usuarios y a las aplicaciones. Ofrece la interfaz para el usuario. Las aplicaciones que usan la red pertenecen a esta capa al igual que los protocolos que implementan. Hay aplicaciones que no son de red que deben trabajar con aplicaciones/servicios para lograr acceso a la red.

	Define el formato de los mensajes. Existen protocolos que trabajan de forma binaria como ASN y otros que trabajan de forma textual ASCII como HTTP.

	Define la semántica de cada uno de los mensajes.

	Define cómo debe ser el intercambio de mensajes. Qué mensajes se deben intercambiar.

2. ## Si dos procesos deben comunicarse:
    - ### a. ¿Cómo podrían hacerlo si están en diferentes máquinas?

        Si están en diferentes máquinas pueden conectarse mediante la red, ya sea por Cable Ethernet, por Internet Inalámbrico o por alguna computadora actuando como Servidor común

    - ### b. Y si están en la misma máquina, ¿qué alternativas existen?

        Si están en la misma máquina puede usarse un pasaje de mensajes o utilizar la memoria para depositar los datos.

3. ## Explique brevemente cómo es el modelo Cliente/Servidor. Dé un ejemplo de un sistema Cliente/Servidor en la “vida cotidiana” y un ejemplo de un sistema informático que siga el modelo Cliente/Servidor. ¿Conoce algún otro modelo de comunicación?

    Es un modelo en el cual el cliente pone procesamiento de la interfaz y el servidor el resto del procesamiento. Este servidor corre servicios esperando de forma pasiva la conexión. El cliente se conecta al servidor y se comunican a través de este. El servidor necesita estar siempre encendido y con una IP estática. Mientras que el cliente puede conectarse intermitentemente, puede tener IP dinámica y nunca va a comunicarse con otro cliente.

	Un ejemplo en la vida cotidiana sería cualquier tipo de práctica comercial, existen dos figuras relevantes, cada una de las cuales desempeña su propio papel. Una de estas figuras, el Cliente, se dedica a una determinada actividad comercial, ofrece sus productos y desempeña una serie de funciones. Pero esta figura no puede dar servicio a todas sus funciones sin la existencia de otra, El Servidor, quien proporciona al Cliente las materias primas necesarias para el cumplimiento de sus funciones. Además, se ha de garantizar que este flujo de peticiones y de respuestas-de-peticiones se realiza en tiempo real, es decir, que las dos figuras mencionadas han de actuar simultáneamente, de forma que la actividad de uno no se vea perjudicada por la del otro. El Cliente puede realizar peticiones al Servidor (para que le proporcione el material necesario) sin interrumpir su actividad.

	Un ejemplo del mundo informático podría ser el correo electrónico, un servicio de impresión o la World Wide Web (WWW).

4. ## Describa la funcionalidad de la entidad genérica “Agente de usuario” o “User agent”.

    Es una interfaz entre el usuario y la aplicación de red. Por ejemplo: en la WEB, el agente de usuario es el navegador, el cual permite al usuario visualizar las páginas WEB e interactuar con los elementos de la misma. El navegador es un proceso que envía/recibe mensajes por medio de un socket y además brinda la interfaz al usuario.

	Un agente de usuario es una aplicación informática que funciona como cliente en un protocolo de red; el nombre se aplica generalmente para referirse a aquellas aplicaciones que acceden a la World Wide Web. Los agentes de usuario que se conectan a la Web pueden ser desde navegadores web hasta los web crawler de los buscadores, pasando por teléfonos móviles, lectores de pantalla y navegadores en Braille usados por personas con discapacidades.

	Cuando un usuario accede a una página web, la aplicación generalmente envía una cadena de texto que identifica al agente de usuario ante el servidor. Este texto forma parte de la petición a través de HTTP, llevando como prefijo User-Agent: y generalmente incluye información como el nombre de la aplicación, la versión, el sistema operativo, y el idioma. Los bots, como los web crawlers, a veces incluyen también una URL o una dirección de correo electrónico para que el administrador del sitio web pueda contactar con el operador del mismo.

	La identificación de agente de usuario es uno de los criterios de exclusión utilizado por el Estándar de exclusión de robots para impedir el acceso a ciertas secciones de un sitio web.

5. ## ¿Qué son y en qué se diferencian HTML y HTTP?

    **HTML** (HyperText Markup Language) es un lenguaje el cual marca el texto normal para que se transforme en Hipertexto. Básicamente los tags de HTML son usados para marcar texto normal que se convierte en hipertexto y varias páginas pueden ser conectadas con otras formando la web.

    Por otro lado, **HTTP** (HyperText Transfer Protocol) es un protocolo para transferir los hipertextos del servidor web hasta el navegador web. Para intercambiar páginas entre el servidor y el navegador, una sesión de HTTP es seteada usando métodos de protocolo.

6. ## HTTP tiene definido un formato de mensaje para los requerimientos y las respuestas.

    - ### a. ¿Qué información de la capa de aplicación nos indica si un mensaje es de requerimiento o de respuesta para HTTP? ¿Cómo está compuesta dicha información? ¿Para qué sirven las cabeceras?

        Si el mensaje lleva un metodo HTTP podemos decir que es un mensaje de requerimiento, mientras que si lleva un codigo de estado HTTP podemos decir que es un mensaje de respuesta.

        La información que nos indica si un mensaje es de requerimiento o de respuesta para HTTP se encuentra en la primera línea del mensaje, la cual se llama línea de inicio.

        En el caso de un mensaje de requerimiento, la línea de inicio está compuesta por el método HTTP, la URL del recurso solicitado y la versión del protocolo HTTP. En el caso de un mensaje de respuesta, la línea de inicio está compuesta por la versión del protocolo HTTP, el código de estado y una frase descriptiva del código de estado.

    - ### b. ¿Cuál es su formato? (Ayuda: https://developer.mozilla.org/es/docs/Web/HTTP/Headers)

        - #### Mensaje de requerimiento:
            ```
            GET /unadireccion/pagina.html HTTP/1.1
            Host: www.unaescuela.edu
            Connection: close
            User-agent: Mozilla/4.0
            Accept-language: fr
            ```

        - #### Mensaje de respuesta:
            ```
            HTTP/1.1 200 OK
            Connection: close
            Date: Sat, 07 Jul 2007 12:00:15 GMT
            Server: Apache/1.3.0 (Unix)
            Last-Modified: Sun, 6 May 2007 09:23:24 GMT
            Content-Length: 6821
            Content-Type: text/html
            ```

    - ### c. Suponga que desea enviar un requerimiento con la versión de HTTP 1.1 desde curl/7.74.0 a un sitio de ejemplo como www.misitio.com para obtener el recurso /index.html. En base a lo indicado, ¿qué información debería enviarse mediante encabezados? Indique cómo quedaría el requerimiento.

        ```
        GET /index.html HTTP/1.1
        Host: www.misitio.com
        User-agent: curl/7.74.0
        ```

7. ## Utilizando la VM, abra una terminal e investigue sobre el comando curl. Analice para qué sirven los siguientes parámetros (-I, -H, -X, -s).

    - El parámetro **–I** sirve para obtener los Headers de un documento en servidores HTTP, para archivos FTP o FILE obtiene solo el tamaño del archivo y la última fecha de modificación.

	- El parámetro **–H** se utiliza para añadir un Header extra a la petición del servidor. Se pueden especificar cualquier número de Headers adicionales.

	- El parámetro **–X** sirve para especificar un método para la petición cuando se comunica con el servidor HTTP. Este método se va a usar en vez del método que se tendría que utilizar (que por defecto es el GET).

	- El parámetro **–s** sirve para ponerlo en modo silencioso, lo que hace que no muestre un medidor de progreso o mensajes de error. Aun así, va a mostrar la información que fue pedida, a menos que se redireccione.
