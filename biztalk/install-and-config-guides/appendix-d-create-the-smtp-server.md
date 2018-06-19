---
title: 'Apéndice D: crear el servidor SMTP | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7441ba9-a498-42ec-a04d-7f2731407373
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f4d4acc35f5cb38be5f783ee7c4017c8ada83e2
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2018
ms.locfileid: "22300140"
---
# <a name="appendix-d-create-the-smtp-server"></a>Apéndice D: Crear el servidor SMTP
Cree el servidor SMTP usado por Correo electrónico de base de datos de SQL Server.  
  
Se requiere Correo electrónico de base de datos de SQL Server para configurar alertas de BAM cuando se usa alguna de las siguientes versiones de SQL: 

* [!INCLUDE[sqlserver2016_md](../includes/sqlserver2016-md.md)]
* [!INCLUDE[sqlserver2014](../includes/sqlserver2014-md.md)]
* [!INCLUDE[sqlserver2012](../includes/sqlserver2012-md.md)] 
  
 Correo electrónico de base de datos de SQL Server usa un servidor SMTP para enviar las alertas de BAM. El servidor SMTP se incluye con Internet Information Services (IIS). SMTP se puede instalar en modo local o en el servidor BizTalk Server u otro servidor que tenga IIS instalado.  
  
> [!IMPORTANT]
>  Normalmente, los sistemas operativos cliente como Windows 10, Windows 7, etc., no incluyen funcionalidades de servidor SMTP. Puede conectarse a un servidor SMTP en un servidor Windows Server con la característica *Correo electrónico SMTP* de IIS. La característica *Correo electrónico SMTP* NO es un servidor SMTP, que es necesario para Correo electrónico de base de datos de SQL Server. Por tanto, en este tema no se incluyen los pasos para instalar y configurar un servidor SMTP en sistemas operativos cliente.  

## <a name="install-and-configure-the-smtp-server"></a>Instalar y configurar el servidor SMTP  
  
Estos pasos se aplican a:

* Windows Server 2016
* Windows Server 2012 R2
* Windows Server 2012
  
### <a name="install-smtp-server"></a>Instalar el servidor SMTP  
   
1.  En **Administrador del servidor**, seleccione **Panel** en el panel de la izquierda.  
  
3.  Seleccione **Agregar roles y características**. También se puede abrir **Agregar roles y características** desde el menú **Administrar** de la esquina superior derecha.  
  
4.  En **Antes de comenzar**, seleccione **Siguiente**.  
  
5.  Seleccione **Instalación basada en características o en roles** y, después, seleccione **Siguiente**.  
  
6.  Seleccione **Seleccionar un servidor del grupo de servidores**, el servidor deseado y, después, **Siguiente**. En la ventana **Selección del servidor** se muestra una lista de los servidores que se han agregado con la opción **Agregar servidor** en el **Administrador del servidor**. De forma predeterminada, se selecciona el servidor local.  
  
7.  En **Roles del servidor**, seleccione **Siguiente**.  
  
8.  En **Características**, active **Servidor SMTP**. Si el sistema se lo pide, seleccione **Agregar características**. Seleccione **Siguiente**.  
  
9. En **Confirmación**, seleccione **Reiniciar automáticamente el servidor de destino en caso necesario** y, después, seleccione **Instalar**. Cuando haya finalizado, seleccione **Cerrar**.  

### <a name="configure-the-smtp-server"></a>Configurar el servidor SMTP  
 Siga estos pasos para configurar el servidor virtual SMTP con el Administrador de IIS 6.0:  
  
1.  Abra el Administrador de IIS. Para ello, vaya a Inicio, busque **inetmgr6.exe** y ábralo.  
  
2.  Expanda el nombre del equipo. Haga clic con el botón derecho en **[Servidor virtual SMTP 1]** y seleccione **Propiedades**.  
  
3.  En la pestaña **Acceso**, haga clic en el botón **Retransmisión**.  
  
4.  Seleccione **Agregar**. Para **Un único equipo**, escriba `127.0.0.1` y seleccione **Aceptar**.  
  
     Al agregar 127.0.0.1, se permite que el servidor local envíe mensajes desde este servidor SMTP. Si quiere que otros equipos envíen mensajes desde este servidor SMTP, escriba sus direcciones IP.  
  
5.  En la pestaña **Entrega**, seleccione **Seguridad de salida**. Elija entre las opciones siguientes:  
  
     **Acceso anónimo**: no se requiere nombre de cuenta ni contraseña. Esta opción deshabilita la autenticación para el servidor SMTP.  
  
     **Autenticación básica**: el nombre de cuenta y la contraseña del servidor al que se va a conectar se envían sin cifrar. La cuenta que especifique transmite los mensajes de correo electrónico. Se puede elegir autenticación básica cuando se envía correo electrónico a una cuenta personal o a una cuenta de Exchange. Puesto que las credenciales se pasan como texto sin cifrar, se recomienda habilitar **Cifrado TLS**.  
  
     **Autenticación de Windows integrada**: se usan el nombre y la contraseña de la cuenta de Windows para la autenticación. La cuenta que especifique transmite los mensajes de correo electrónico.  
  
     **Cifrado TLS**: TLS protege la conexión de forma similar a SSL. Requiere un certificado de servidor SSL válido instalado en este servidor.  
  
    > [!TIP]
    >  Para probar la funcionalidad SMTP principal con una cuenta de correo electrónico personal, incluida una cuenta de Exchange, seleccione **Acceso anónimo**. Cuando se selecciona Autenticación básica, SMTP usa el comando AUTH. Algunos proveedores de correo electrónico pueden dar error debido al comando AUTH. Si AUTH da error, es probable que se registre un error en los registros de eventos de Windows en el servidor SMTP.  
  
6.  En la pestaña **Entrega**, seleccione **Conexiones salientes**. De forma predeterminada, el puerto TCP es el 25. Se puede especificar otro puerto si está abierto en el firewall. Seleccione **Aceptar**.  
  
7.  En la pestaña **Entrega**, seleccione **Avanzada**. De forma predeterminada, aparece el nombre del servidor local en **Nombre de dominio completo**. Según el proveedor de Internet, el cuadro de la propiedad **Host inteligente** puede estar vacío. Puede ser necesario ponerse en contacto con el proveedor de Internet para confirmar si es necesario un host inteligente. En caso contrario, quizá pueda especificar smtp.*ProveedorDeCorreo*.com.  
  
    > [!NOTE]
    >  Un **host inteligente** es un servidor dedicado que los servidores Exchange usan para enrutar todos los mensajes salientes. Cuando el **host inteligente** recibe los mensajes, los reenvía a un dominio remoto. El objetivo de un **host inteligente** es mejorar el rendimiento de un servidor Exchange. El servidor Exchange Server solo transmite al host inteligente, en lugar de contactar repetidamente al dominio remoto hasta que se establece una conexión.  
  
8.  Seleccione **Aceptar** para cerrar todas las ventanas.  
  
9. Reinicie el servidor SMTP. Para ello, haga clic con el botón derecho en **[Servidor virtual SMTP 1]**, seleccione **Detener** y, después, seleccione **Iniciar**. Es necesario reiniciar el equipo para aplicar la configuración del servidor SMTP. 

  
## <a name="windows-server-2008-r2-install-and-configure-smtp-server"></a>Windows Server 2008 R2: instalar y configurar el servidor SMTP  
  
### <a name="install-smtp-server"></a>Instalar el servidor SMTP  
 Siga estos pasos para instalar la característica Servidor SMTP:  
  
1.  En **Administrador del servidor**, seleccione **Características** y, después, seleccione **Agregar características**.  
  
3.  En **Agregar características**, seleccione **Servidor SMTP**. Si el sistema se lo pide, seleccione **Agregar servicios de rol requeridos** y, después, seleccione **Siguiente**.  
  
4.  Para continuar con la instalación, seleccione **Siguiente**.  
  
5.  En la ventana **Confirmar selecciones de instalación**, seleccione **Instalar**. Cuando haya finalizado, seleccione **Cerrar**.  
  
### <a name="configure-the-smtp-server"></a>Configurar el servidor SMTP  
 Siga estos pasos para configurar el servidor virtual SMTP con el Administrador de IIS 6.0:  
  
1.  Abra el Administrador de IIS 6.0. Para ello, en **Iniciar**, busque **IIS** y seleccione **Administrador de Internet Information Services (IIS) 6.0**.  
  
2.  Expanda el nombre del equipo. Haga clic con el botón derecho en **[Servidor virtual SMTP 1]** y seleccione **Propiedades**.  
  
3.  En la pestaña **Acceso**, haga clic en el botón **Retransmisión**.  
  
4.  Seleccione **Agregar**. Para **Un único equipo**, escriba `127.0.0.1` y seleccione **Aceptar**.  
  
     Al agregar 127.0.0.1, se permite que el servidor local envíe mensajes desde este servidor SMTP. Si quiere que otros equipos envíen mensajes desde este servidor SMTP, escriba sus direcciones IP.  
  
5.  En la pestaña **Entrega**, seleccione **Seguridad de salida**. Elija entre las opciones siguientes:  
  
     **Acceso anónimo**: no se requiere nombre de cuenta ni contraseña. Esta opción deshabilita la autenticación para el servidor SMTP.  
  
     **Autenticación básica**: el nombre de cuenta y la contraseña del servidor al que se va a conectar se envían sin cifrar. Se puede elegir autenticación básica cuando se envía correo electrónico a una cuenta personal o a una cuenta de Exchange. Puesto que las credenciales se pasan como texto sin cifrar, se recomienda habilitar **Cifrado TLS**.  
  
     **Autenticación de Windows integrada**: se usan el nombre y la contraseña de la cuenta de Windows para la autenticación. La cuenta que especifique transmite los mensajes de correo electrónico.  
  
     **Cifrado TLS**: TLS protege la conexión de forma similar a SSL. Requiere un certificado de servidor SSL válido instalado en este servidor.  
  
    > [!TIP]
    >  Para probar la funcionalidad SMTP principal con una cuenta de correo electrónico personal, incluida una cuenta de Exchange, seleccione **Acceso anónimo**. Cuando se selecciona Autenticación básica, SMTP usa el comando AUTH. Algunos proveedores de correo electrónico pueden dar error debido al comando AUTH. Si AUTH da error, es probable que se registre un error en los registros de eventos de Windows en el servidor SMTP.  
  
6.  En la pestaña **Entrega**, seleccione **Conexiones salientes**. De forma predeterminada, el puerto TCP es el 25. Se puede especificar otro puerto si está abierto en el firewall. Seleccione **Aceptar**.  
  
    > [!TIP]
    >  El puerto TCP se puede usar para conexiones entrantes y salientes.  
  
7.  En la pestaña **Entrega**, seleccione **Avanzada**. De forma predeterminada, aparece el nombre del servidor local en **Nombre de dominio completo**. Según el proveedor de Internet, el cuadro de la propiedad **Host inteligente** puede estar vacío. Puede ser necesario ponerse en contacto con el proveedor de Internet para confirmar si es necesario un host inteligente. En caso contrario, quizá pueda especificar smtp.*ProveedorDeCorreo*.com.  
  
    > [!NOTE]
    >  Un **host inteligente** es un servidor dedicado que los servidores Exchange usan para enrutar todos los mensajes salientes. Cuando el **host inteligente** recibe los mensajes, los reenvía a un dominio remoto. El objetivo de un **host inteligente** es mejorar el rendimiento de un servidor Exchange. El servidor Exchange Server solo transmite al host inteligente, en lugar de contactar repetidamente al dominio remoto hasta que se establece una conexión.  
  
8.  Seleccione **Aceptar** para cerrar todas las ventanas.  
  
9. Es necesario reiniciar el equipo para aplicar la configuración del servidor SMTP. Para reiniciar el servidor SMTP, haga clic con el botón derecho en **[Servidor virtual SMTP 1]**, seleccione **Detener** y, después, seleccione **Iniciar**.  
  
  
## <a name="test-the-smtp-server"></a>Probar el servidor SMTP  
 Para probar la configuración del servidor SMTP, se puede usar Telnet. En los pasos siguientes, se envía un mensaje mediante el servidor SMTP configurado a una dirección de correo electrónico. [http://support.microsoft.com/kb/153119](http://support.microsoft.com/kb/153119) se proporcionan descripciones de los comandos de telnet.  
  
1.  Abra una ventana de comandos como administrador.
  
2.  En el símbolo del sistema, escriba:  
  
     `telnet localhost 25`  
  
     Si Telnet no está instalado, escriba lo siguiente para instalarlo:  
  
     `pkgmgr /iu:"TelnetClient"`  
  
3.  Escriba lo siguiente para iniciar la comunicación:  
  
     `EHLO server`  
  
4.  Escriba la dirección del remitente:  
  
     `MAIL FROM: *YourEmailAddress*@*YourProvider*.com`  
  
     Por ejemplo, escriba:  
  
     `MAIL FROM: EmailAddress@outlook.com`  
  
5.  Escriba la dirección del destinatario:  
  
     `RCPT TO: *YourEmailAddress*@*YourProvider*.com`  
  
     Por ejemplo, escriba:  
  
     `RCPT TO: EmailAddress@outlook.com`  
  
6.  Escriba lo siguiente para indicarle al servidor SMTP que está listo para enviar datos:  
  
     `DATA`  
  
7.  Escriba el asunto:  
  
     `Subject: Test Message`  
  
8.  Presione Entrar dos veces.  
  
9. Escriba el cuerpo del mensaje:  
  
     `This is the message body of the test message.`  
  
10. Presione Entrar, escriba un punto (.) y presione Entrar.  
  
 Consulte la dirección RCPT TO para ver si ha llegado el mensaje de correo electrónico. Si no se ha entregado el mensaje (compruebe la bandeja de entrada y la de correo no deseado), significa que el mensaje no se envió correctamente y está en la carpeta de la cola SMTP (C:\inetpub\mailroot\Queue).  
  