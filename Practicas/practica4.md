# Práctica 4 - Capa de Aplicación Correo Electrónico

1. ## ¿Qué protocolos se utilizan para el envío de mails entre el cliente y su servidor de correo? ¿Y entre servidores de correo?

    Para el envío de correos electrónicos, se utilizan principalmente dos protocolos:

    - **SMTP (Simple Mail Transfer Protocol)**: Es el protocolo estándar para el envío de correos electrónicos a través de Internet. SMTP se utiliza tanto para la comunicación entre el cliente de correo y su servidor de correo como para la comunicación entre servidores de correo. Este protocolo se encarga de la transferencia de mensajes desde el cliente al servidor y entre servidores, asegurando que los correos lleguen a su destino.

    - **ESMTP (Extended Simple Mail Transfer Protocol)**: Es una extensión de SMTP que añade funcionalidades adicionales, como la autenticación de usuarios y la capacidad de enviar mensajes con formatos más complejos. ESMTP es compatible con SMTP, pero ofrece características mejoradas para una mayor seguridad y eficiencia en el envío de correos electrónicos.

2. ## ¿Qué protocolos se utilizan para la recepción de mails? Enumere y explique características y diferencias entre las alternativas posibles

    Para la recepción de correos electrónicos, se utilizan principalmente dos protocolos:

    - **POP3 (Post Office Protocol version 3)**: Es un protocolo utilizado para la recepción de correos electrónicos. POP3 permite a los usuarios descargar sus correos electrónicos desde el servidor a su dispositivo local. Una vez que los correos son descargados, generalmente se eliminan del servidor, lo que significa que no se pueden acceder desde otros dispositivos. POP3 es sencillo y fácil de configurar, pero no es ideal para usuarios que necesitan acceder a sus correos desde múltiples dispositivos.

    - **IMAP (Internet Message Access Protocol)**: Es otro protocolo utilizado para la recepción de correos electrónicos. A diferencia de POP3, IMAP permite a los usuarios acceder y gestionar sus correos electrónicos directamente en el servidor. Esto significa que los correos permanecen en el servidor y pueden ser accedidos desde múltiples dispositivos sin necesidad de descargarlos. IMAP también ofrece características avanzadas como la organización de correos en carpetas y la sincronización en tiempo real entre dispositivos.

    En resumen, la principal diferencia entre POP3 e IMAP radica en cómo manejan los correos electrónicos: POP3 descarga y elimina los correos del servidor, mientras que IMAP mantiene los correos en el servidor y permite el acceso desde múltiples dispositivos.

3. ## Utilizando la VM y teniendo en cuenta los siguientes datos, abra el cliente de correo (Thunderbird) y configure dos cuentas de correo. Una de las cuentas utilizará POP para solicitar al servidor los mails recibidos para la misma mientras que la otra utilizará IMAP. Al ingresar a cada una de las cuentas, seleccionar Manual config y luego de configurar las mismas según lo indicado, ignorar advertencias por uso de conexión sin cifrado.

    - Datos para POP

        - Cuenta de correo: alumnopop@redes.unlp.edu.ar
        - Nombre de usuario: alumnopop
        - Contraseña: alumnopoppass
        - Puerto: 110

    - Datos para IMAP

        - Cuenta de correo: alumnoimap@redes.unlp.edu.ar
        - Nombre de usuario: alumnoimap
        - Contraseña: alumnoimappass
        - Puerto: 143

    - Datos comunes para ambas cuentas
        - Servidor de correo entrante (POP/IMAP):
            - Nombre: mail.redes.unlp.edu.ar
            - SSL: None
            - Autenticación: Normal password
        - Servidor de correo saliente (SMTP):
            - Nombre: mail.redes.unlp.edu.ar
            - Puerto: 25
            - SSL: None
            - Autenticación: Normal password

    - ### a. Verificar el correcto funcionamiento enviando un email desde el cliente de una cuenta a la otra y luego desde la otra responder el mail hacia la primera.
    - ### b. Análisis del protocolo SMTP
        - #### i. Utilizando Wireshark, capture el tráfico de red contra el servidor de correo mientras desde la cuenta alumnopop@redes.unlp.edu.ar envía un correo a alumnoimap@redes.unlp.edu.ar
        - #### ii. Utilice el filtro SMTP para observar los paquetes del protocolo SMTP en la captura generada y analice el intercambio de dicho protocolo entre el cliente y el servidor para observar los distintos comandos utilizados y su correspondiente respuesta. Ayuda: filtre por protocolo SMTP y sobre alguna de las líneas del intercambio haga click derecho y seleccione Follow TCP Stream. . .

    - ### c. Usando el cliente de correo Thunderbird del usuario alumnopop@redes.unlp.edu.ar envíe un correo electrónico alumnoimap@redes.unlp.edu.ar el cual debe tener: un asunto, datos en el body y una imagen adjunta.
        - #### i. Verifique las fuentes del correo recibido para entender cómo se utiliza el header “Content-Type: multipart/mixed“ para poder realizar el envío de distintos archivos adjuntos.
        - #### ii. Extraiga la imagen adjunta del mismo modo que lo hace el cliente de correo a partir de los fuentes del mensaje.
