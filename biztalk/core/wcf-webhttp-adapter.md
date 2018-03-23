---
title: Adaptador de WCF-WebHttp | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67a353e7-1ba3-427a-8e99-c9b8d83061cb
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 891f636a5380eda7db676559194618915213dc37
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2018
---
# <a name="wcf-webhttp-adapter"></a>Adaptador WCF-WebHttp
[!INCLUDE[btsCoName](../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] usa el **WCF-WebHttp** adaptador para enviar mensajes a los servicios RESTful. El **WCF-WebHttp** de envío de adaptador envía mensajes HTTP a un servicio de un mensaje de BizTalk. La ubicación de recepción recibe los mensajes de un servicio de RESTful. Para la solicitud GET y DELETE, el adaptador no usa ninguna carga. Para las solicitudes POST y PUT, el adaptador usa la parte del cuerpo del mensaje de BizTalk para el contenido/carga de HTTP.  

En este tema se muestra cómo crear la ubicación de recepción y el puerto de envío mediante administración de BizTalk.

## <a name="create-a-receive-location"></a>Crear una ubicación de recepción
  
> [!NOTE]
>  Antes de completar el procedimiento siguiente, debe haber agregado un unidireccional puerto de recepción. Vea [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
  
1.  En la consola de administración de BizTalk, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **Grupo de BizTalk**, expanda **Aplicaciones**y, luego, expanda la aplicación en la que desea crear la ubicación de recepción.  
  
2.  En el panel izquierdo, haga clic en el nodo **Puertos de recepción** y, en el panel derecho, haga clic con el botón derecho en el puerto de recepción al que desea asociar la nueva ubicación de recepción y, a continuación, haga clic en **Propiedades**.  
  
3.  En el panel de la izquierda del cuadro de diálogo **Propiedades de puerto de recepción** , seleccione **Ubicaciones de recepción**y, en el panel de la derecha, haga clic en **Nueva** para crear una nueva ubicación de recepción.  
  
4.  En el cuadro de diálogo **Propiedades de la ubicación de recepción** , en la sección **Transporte** , seleccione **WCF-WebHttp** en la lista desplegable **Tipo** y, a continuación, haga clic en **Configurar** para configurar las propiedades de transporte de la ubicación de recepción.  
  
5.  En el **General** pestaña, configure la dirección del extremo de la interfaz REST desde donde se recibió el mensaje.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Dirección (URI)**|Requerido. Especifique el URI en el que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede recibir mensajes RESTful basados en HTTP.|  
    |**Identidad del extremo**|Opcional. Especifique la identidad del extremo. Esta configuración habilita al extremo para autenticar la ubicación de recepción. En el proceso de negociación entre el extremo y la ubicación de recepción, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad del servicio esperado coincide con los valores de este elemento.<br /><br /> El valor predeterminado es una cadena vacía.|  
    |**Método HTTP y asignación de dirección URL**|La asignación de operación BTS permite a los usuarios asignar solicitudes HTTP entrantes a operaciones BTS en el contexto del mensaje, en función del método HTTP entrante y la subdirección URL. El método HTTP entrante y la subruta de acceso a la dirección URL se comparan con un conjunto de métodos HTTP y la plantilla de URI. Si se encuentra alguna coincidencia, el adaptador promueve la propiedad **BTS.Operation** al contexto del mensaje de BizTalk con el valor especificado en el mensaje.<br /><br /> Es posible especificar el método HTTP para la asignación de URL con un formato único o un formato de múltiples asignaciones. El formato de asignaciones múltiples tiene el aspecto siguiente:<br /><br /> `<BtsHttpUrlMapping> <Operation Name = "DelCust" Method="DELETE" Url="/Customer/12345</BtsHttpUrlMapping>`<br /><br /> En el fragmento anterior, observe que el identificador de cliente se proporciona como un valor constante, que es *12345*. Sin embargo, podrían existir situaciones en las que el identificador de cliente, o cualquier otra variable de consulta, debe determinarse en el tiempo de ejecución. Para permitir este tipo de situaciones, deberá proporcionar el componente variable de la dirección URL entre llaves { }. Por ejemplo, en el fragmento anterior, si especifica el identificador de cliente como una variable, tendría el aspecto siguiente:<br /><br /> `<BtsHttpUrlMapping> <Operation Name = "DelCust" Method="DELETE" Url="/Customer/{ID}</BtsHttpUrlMapping>`<br /><br /> En dicho caso, también deberá especificar de dónde debe obtenerse el valor de la variable **ID** en el tiempo de ejecución. Para ello, se usa **Asignaciones de variables**.<br /><br />**Nota**<br /> En el campo de dirección URL, los caracteres XML especiales se deben "escape". Esto garantiza que los caracteres XML especiales se procesan y conserva el puerto. Por ejemplo, el `&` caracteres especiales deben ser de escape como `&amp;`. <br /><br />From:<br />`Url=”/Customer?{ID}& group=Location”`<br />Para: <br />`Url=”/Customer?{ID}&amp;group=Location”`|  
    |**Asignación de variable**|Si especificó variables para la asignación de direcciones URL del método HTTP, deberá especificar los elementos a los que se asignan las variables en el tiempo de ejecución. Haga clic en el botón **Editar** para iniciar el cuadro de diálogo **Asignaciones de variables** . En la columna **Variable** , el cuadro de diálogo indica las variables definidas para **Método HTTP y asignación de direcciones URL**. En el campo **Nombre de propiedad** , deberá especificar el nombre de la propiedad que proporciona el valor que debe asociarse a la variable. Debe haber definido o promocionado esta propiedad como parte de la solución. También debe proporcionar el espacio de nombres de la propiedad en el campo **Espacio de nombre de propiedad** .|  
  
6.  En el **enlace** pestaña, configure las propiedades relacionadas con la codificación y el tiempo de espera.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Abra el tiempo de espera (hh:mmss)**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de apertura del canal. Este valor debe ser mayor o igual que **System.TimeSpan.Zero**.<br /><br /> Valor predeterminado: 00:01:00<br /><br /> Valor máximo:  23:59:59|  
    |**Enviar tiempo de espera (hh:mmss)**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de envío. Este valor debe ser mayor o igual que **System.TimeSpan.Zero**. Si usa un puerto de recepción solicitud-respuesta, este valor especifica un marco temporal para que se complete la interacción, incluso cuando el cliente devuelva un mensaje grande.<br /><br /> Valor predeterminado: 00:01:00<br /><br /> Valor máximo:  23:59:59|  
    |**Tiempo de espera de cierre (hh:mmss)**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de cierre del canal. Este valor debe ser mayor o igual que **System.TimeSpan.Zero**.<br /><br /> Valor predeterminado: 00:01:00<br /><br /> Valor máximo:  23:59:59|  
    |**Tamaño máximo del mensaje recibido (bytes)**|Especificar el tamaño máximo, en bytes, para mensajes, con encabezados incluidos, que se pueden recibir a través de la red. El tamaño de los mensajes se limita mediante la cantidad de memoria asignada a cada mensaje. Puede usar esta propiedad para limitar la exposición a ataques por denegación de servicio (DoS).<br /><br /> El adaptador de WCF-WebHttp usa la clase [WebHttpBinding](http://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.aspx) en el modo de transferencia con búfer para comunicarse con un extremo. Para el modo de transferencia almacenado en búfer, la propiedad [WebHttpBinding.MaxBufferSize](http://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.maxbuffersize.aspx) siempre es igual al valor de esta propiedad.<br /><br /> Valor predeterminado: 65536<br /><br /> Valor máximo: 2147483647|  
    |**Número máximo de llamadas simultáneos**|Especificar el número de llamadas concurrentes en una instancia de servicio única. Las llamadas que superan el límite se ponen en cola. Establecer este valor como 0 es equivalente a establecerlo como **Int32.MaxValue**.<br /><br /> El valor predeterminado es 200.|  
  
7.  En el **seguridad** ficha, definir la seguridad de la ubicación de recepción de las capacidades de WCF-WebHttp.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Modo de seguridad**|Especificar el tipo de seguridad que se usa. Los valores válidos incluyen los siguientes:<br /><br /> -                          **Ninguno**: mensajes no están protegidos durante la transferencia.<br /><br /> - **Transporte**: se proporciona seguridad mediante el transporte HTTPS. Los mensajes SOAP están protegidos mediante HTTPS. Para usar este modo, debe configurar Capa de sockets seguros (SSL) en los Servicios de Microsoft Internet Information Server (IIS).<br /><br /> - **TransportWithMessageCredential**: el transporte HTTPS proporciona integridad, confidencialidad y autenticación del servicio. Para usar este modo, debe configurar Capa de sockets seguros (SSL) en los Servicios de Microsoft Internet Information Server (IIS).<br /><br /> El valor predeterminado es **Transporte**.|  
    |**Tipo de credencial de cliente de transporte**|Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación del cliente. Los valores válidos incluyen los siguientes:<br /><br /> - **Ninguno**: No se produce autenticación en el nivel de transporte.<br /><br /> - **Básico**: autenticación básica. En la autenticación básica, los nombres de usuario y las contraseñas se envían en texto sin formato por la red. Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales.<br /><br /> - **Síntesis**: la autenticación implícita. Este método de autenticación funciona de forma muy similar a la autenticación básica, excepto que las contraseñas se envían a través de la red como un valor hash para obtener más seguridad. La autenticación implícita está disponible sólo en dominios con controladores de dominio que ejecutan la autenticación de sistemas operativos de Windows Server. Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales del cliente.<br /><br /> -                          **NTLM**: la autenticación NTLM. Los clientes pueden enviar las credenciales sin enviar una contraseña a esta ubicación de recepción. Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales del cliente.<br /><br /> -                          **Windows**: autenticación integrada de Windows. Windows Communication Foundation negocia Kerberos o NTLM; prefiere Kerberos si hay un dominio presente. Si desea usar Kerberos, es importante que el cliente identifique el servicio con un nombre principal de servicio (SPN). Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales del cliente.<br /><br /> - **Certificado**: autenticación del cliente mediante el certificado de cliente. La cadena de certificados de CA de los certificados X.509 del cliente debe estar instalada en el almacén de certificados Entidades emisoras de certificados raíz de confianza del equipo de modo que se puedan autenticar los clientes en esta ubicación de recepción.<br /><br /> **Tenga en cuenta**el **tipo de credencial de cliente de transporte** propiedad debe coincidir con el esquema de autenticación de IIS virtual directory aloja esta ubicación de recepción. Por ejemplo, si la propiedad está establecida como **Windows**, necesita habilitar también **Autenticación de Windows integrada** para el directorio virtual que la aloja. De forma parecida, si la propiedad está establecida como **Ninguna**, debe permitir el acceso anónimo al directorio virtual que aloja esta ubicación de recepción.<br /><br /> El valor predeterminado es **Windows**.|  
    |**Servicio - huella digital**|Especificar la huella digital del certificado X.509 para esta ubicación de recepción que los clientes utilizan para autenticar el servicio. La huella digital puede seleccionarse desplazándose por **Mi** almacén, dentro de **Usuario actual** , con el botón **Examinar** .<br /><br /> **Tenga en cuenta** debe instalar el certificado de servicio en la **usuario actual** ubicación de la cuenta de usuario para el controlador de recepción que aloja esta ubicación de recepción.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 40<br /><br /> El valor predeterminado es una cadena vacía.|  

8. En el **comportamiento** ficha, especificar comportamientos diferentes en el nivel de servicio y el nivel del extremo. Estos comportamientos basados en clases de .NET Framework.  
  
    | Use|Para|  
    |--------------|----------------|  
    | ServiceBehavior | Ampliar la funcionalidad del servicio WCF en el nivel de servicio. Puede agregar extensiones que realizar diferentes operaciones, como definen la configuración de seguridad, habilitar la depuración, implementan la limitación y utilicen otras clases. NET.  <br/><br/> Seleccione derecha **ServiceBehavior**, y **Agregar extensión**. La lista muestra las clases de .NET que se pueden usar.|
    | EndpointBehavior | Ampliar la funcionalidad de cómo se reciben las solicitudes en el nivel de punto de conexión. Puede agregar extensiones que realizar diferentes operaciones, como reciban solicitudes HTTP de un cliente de AJAX de ASP.NET basado en explorador, especifican un intervalo de tiempo en las transacciones, optar por recibir mensajes de forma sincrónica o asincrónica y utilice otras clases. NET. <br/><br/> Seleccione derecha **EndpointBehavior**, y **Agregar extensión**. La lista muestra las clases de .NET que se pueden usar.|

    Esto es similar a la configuración de comportamiento de ubicación de recepción de un WCF-Custom. Consulte la **comportamiento del cuadro de diálogo de propiedades de transporte WCF-Custom, recepción,** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
    
9.  En el **mensajes** ficha, especifique la selección de datos de SOAP **cuerpo** elemento.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Encabezados HTTP salientes**|Especifica los encabezados HTTP con los que se marcará el mensaje de respuesta, si corresponde.|  
    |**Deshabilitar ubicación en caso de error**|Especificar si se va a deshabilitar la ubicación de recepción cuyo procesamiento de entrada no se puede realizar correctamente debido a un error de canalización de recepción o de enrutamiento.<br /><br /> El valor predeterminado es desactivada.|  
    |**Suspender mensaje de solicitud en caso de error**|Especificar si se va a suspender el mensaje de solicitud cuyo procesamiento de entrada no se puede realizar correctamente debido a un error de canalización de recepción o de enrutamiento.<br /><br /> Esta opción está desactivada de forma predeterminada.|  
    |**Incluir detalle de excepción en errores**|Especificar si se van a devolver errores de SOAP cuando se produce un error para una depuración sencilla.<br /><br /> Esta opción está desactivada de forma predeterminada.|  
  
9. Haga clic en **Aceptar**.  
  
10. Especifique los valores apropiados en el cuadro de diálogo **Propiedades de la ubicación de recepción** para completar la configuración de la ubicación de recepción y haga clic en **Aceptar** para guardar la configuración. Para obtener información sobre la **propiedades de ubicaciones de recepción** cuadro de diálogo, vea [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  

## <a name="create-the-send-port"></a>Crear el puerto de envío

1.  En la consola de administración de BizTalk, cree un nuevo puerto de envío o haga doble clic en un puerto de envío existente para modificarlo. Vea [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configure todas las opciones del puerto de envío y especifique **WCF-WebHttp** para el **tipo** opción en el **transporte** sección de la **General** pestaña.  
  
2.  En el **General** ficha la **transporte** sección, haga clic en el **configurar** botón.  
  
3.  En el **General** pestaña, configure la dirección del extremo de la interfaz REST donde se envía el mensaje.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Dirección (URI)**|Requerido. Especifique la URI de la interfaz REST donde se envía el mensaje.|  
    |**Identidad del extremo**|Opcional. Especifique la identidad del extremo. Esta configuración permite al extremo autenticar el puerto de envío. En el proceso de negociación entre el extremo y la ubicación de recepción, la infraestructura de Windows Communication Foundation (WCF) asegurará que la identidad del servicio esperado coincide con los valores de este elemento.<br /><br /> El valor predeterminado es una cadena vacía.|  
    |**Método HTTP y asignación de dirección URL**|La asignación de operación BTS permite a los usuarios asignar solicitudes HTTP entrantes a operaciones BTS en el contexto del mensaje, en función del método HTTP entrante y la subdirección URL. El método HTTP entrante y la subruta de acceso a la dirección URL se comparan con un conjunto de métodos HTTP y la plantilla de URI. Si se encuentra alguna coincidencia, el adaptador promueve la propiedad **BTS.Operation** al contexto del mensaje de BizTalk con el valor especificado en el mensaje.<br /><br /> Es posible especificar el método HTTP para la asignación de URL con un formato único o un formato de múltiples asignaciones. El formato de asignaciones múltiples tiene el aspecto siguiente:<br /><br /> `BtsHttpUrlMapping> <Operation Name = "DelCust" Method="DELETE" Url="/Customer/12345" /> </BtsHttpUrlMapping>`<br /><br /> En el fragmento anterior, observe que el identificador de cliente se proporciona como un valor constante, que es *12345*. Sin embargo, podrían existir situaciones en las que el identificador de cliente, o cualquier otra variable de consulta, debe determinarse en el tiempo de ejecución. Para permitir este tipo de situaciones, deberá proporcionar el componente variable de la dirección URL entre llaves { }. Por ejemplo, en el fragmento anterior, si especifica el identificador de cliente como una variable, tendría el aspecto siguiente:<br /><br /> `<BtsHttpUrlMapping> <Operation Name = "DelCust" Method="DELETE" Url="/Customer/{ID}" /> </BtsHttpUrlMapping>`<br /><br /> En dicho caso, también deberá especificar de dónde debe obtenerse el valor de la variable **ID** en el tiempo de ejecución. Para ello, se usa **Asignaciones de variables**. <br /><br />**Nota**<br /> En el campo de dirección URL, los caracteres XML especiales se deben "escape". Esto garantiza que los caracteres XML especiales se procesan y conserva el puerto. Por ejemplo, el `&` caracteres especiales deben ser de escape como `&amp;`. <br /><br />From:<br />`Url=”/Customer?{ID}& group=Location”`<br />Para: <br />`Url=”/Customer?{ID}&amp;group=Location”`|  
    |**Asignación de variable**|Si especificó variables para la asignación de direcciones URL del método HTTP, deberá especificar los elementos a los que se asignan las variables en el tiempo de ejecución. Haga clic en el botón **Editar** para iniciar el cuadro de diálogo **Asignaciones de variables** . En la columna **Variable** , el cuadro de diálogo indica las variables definidas para **Método HTTP y asignación de direcciones URL**. En el campo **Nombre de propiedad** , deberá especificar el nombre de la propiedad que proporciona el valor que debe asociarse a la variable. Debe haber definido o promocionado esta propiedad como parte de la solución. También debe proporcionar el espacio de nombres de la propiedad en el campo **Espacio de nombre de propiedad** .|  
  
4.  En el **enlace** pestaña, configure las propiedades relacionadas con la codificación y el tiempo de espera.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Abra el tiempo de espera (hh:mmss)**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de apertura del canal. Este valor debe ser mayor o igual que **System.TimeSpan.Zero**.<br /><br /> Valor predeterminado: 00:01:00<br /><br /> Valor máximo:  23:59:59|  
    |**Enviar tiempo de espera (hh:mmss)**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de envío. Este valor debe ser mayor o igual que **System.TimeSpan.Zero**. Si usa un puerto de recepción solicitud-respuesta, este valor especifica un marco temporal para que se complete la interacción, incluso cuando el cliente devuelva un mensaje grande.<br /><br /> Valor predeterminado: 00:01:00<br /><br /> Valor máximo:  23:59:59|  
    |**Tiempo de espera de cierre (hh:mmss)**|Especificar un valor de marco temporal que indica el intervalo de tiempo proporcionado para que se complete una operación de cierre del canal. Este valor debe ser mayor o igual que **System.TimeSpan.Zero**.<br /><br /> Valor predeterminado: 00:01:00<br /><br /> Valor máximo:  23:59:59|  
    |**Tamaño máximo del mensaje recibido (bytes)**|Especificar el tamaño máximo, en bytes, para mensajes, con encabezados incluidos, que se pueden recibir a través de la red. El tamaño de los mensajes se limita mediante la cantidad de memoria asignada a cada mensaje. Puede usar esta propiedad para limitar la exposición a ataques por denegación de servicio (DoS).<br /><br /> El adaptador de WCF-WebHttp usa la clase [WebHttpBinding](http://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.aspx) en el modo de transferencia con búfer para comunicarse con un extremo. Para el modo de transferencia almacenado en búfer, la propiedad [WebHttpBinding.MaxBufferSize](http://msdn.microsoft.com/library/system.servicemodel.webhttpbinding.maxbuffersize.aspx) siempre es igual al valor de esta propiedad.<br /><br /> Valor predeterminado: 65536<br /><br /> Valor máximo: 2147483647|  
  
5.  En el **seguridad** ficha, defina las capacidades de seguridad del puerto de envío WCF-WebHttp.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Modo de seguridad**|Especificar el tipo de seguridad que se usa. Los valores válidos incluyen los siguientes:<br /><br /> -   **Ninguno**: mensajes no están protegidos durante la transferencia.<br />-   **Transporte**: se proporciona seguridad mediante el transporte HTTPS. Los mensajes SOAP están protegidos mediante HTTPS. La cadena de certificados de CA del certificado X.509 del servicio debe estar instalada en el almacén de certificados Entidades emisoras de certificados raíz de confianza del equipo de modo que se pueda autenticar el servicio en el puerto de envío mediante el certificado del servicio.<br />-   **TransportWithMessageCredential**: el transporte HTTPS proporciona integridad, confidencialidad y autenticación del servicio. La cadena de certificados de CA del certificado X.509 del servicio debe estar instalada en el almacén de certificados Entidades emisoras de certificados raíz de confianza en este equipo de modo que se pueda autenticar el servicio en el puerto de envío mediante el certificado del servicio. La seguridad de mensajes de SOAP proporciona la autenticación del puerto de envío.<br /><br /> El valor predeterminado es **ninguno**.|  
    |**Tipo de credencial de cliente de transporte**|Especificar el tipo de credenciales que se va a usar a la hora de realizar la autenticación del cliente. Los valores válidos incluyen los siguientes:<br /><br /> -   **Ninguno**: No se produce autenticación en el nivel de transporte.<br />-   **Básico**: autenticación básica. En la autenticación básica, los nombres de usuario y las contraseñas se envían en texto sin formato por la red. Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales.<br />-   **Síntesis**: la autenticación implícita. Este método de autenticación funciona de forma muy similar a la autenticación básica, excepto que las contraseñas se envían a través de la red como un valor hash para obtener más seguridad. La autenticación implícita está disponible sólo en dominios con controladores de dominio que ejecutan la autenticación de sistemas operativos de Windows Server. Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales del cliente.<br />-   **NTLM**: la autenticación NTLM. Los clientes pueden enviar las credenciales sin enviar una contraseña a esta ubicación de recepción. Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales del cliente.<br />-   **Windows**: autenticación integrada de Windows. Windows Communication Foundation negocia Kerberos o NTLM; prefiere Kerberos si hay un dominio presente. Si desea usar Kerberos, es importante que el cliente identifique el servicio con un nombre principal de servicio (SPN). Debe crear las cuentas de dominio o de usuario local correspondientes a las credenciales del cliente.<br />-   **Certificado**: autenticación del cliente mediante el certificado de cliente. La cadena de certificados de CA de los certificados X.509 del cliente debe estar instalada en el almacén de certificados Entidades emisoras de certificados raíz de confianza del equipo de modo que se puedan autenticar los clientes en esta ubicación de recepción. **Nota:** el **tipo de credencial de cliente de transporte** propiedad debe coincidir con el esquema de autenticación de IIS virtual directory aloja esta ubicación de recepción. Por ejemplo, si la propiedad está establecida como **Windows**, necesita habilitar también **Autenticación de Windows integrada** para el directorio virtual que la aloja. De forma parecida, si la propiedad está establecida como **Ninguna**, debe permitir el acceso anónimo al directorio virtual que aloja esta ubicación de recepción. <br /><br /> El valor predeterminado es **Windows**.|  
    |**Huella digital de certificado de cliente**|Especifique la huella digital del certificado X.509 para autenticar este puerto de envío en el extremo. Puede seleccionar la huella digital desplazándose hasta la **mi** almacenar en la **usuario actual** ubicación con el **examinar** botón. **Nota:** debe instalar el certificado de cliente en el **usuario actual** ubicación de la cuenta de usuario para el controlador de envío que aloja este puerto de envío. <br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 40<br /><br /> El valor predeterminado es una cadena vacía.|  
    |**Huella digital de certificado de servicio**|Especifique la huella digital del certificado X.509 para autenticar el extremo al que este puerto de envío envía mensajes. Puede seleccionar la huella digital desplazándose por el **otras personas** almacenar en la **equipo Local** ubicación con el **examinar** botón.<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 40<br /><br /> El valor predeterminado es una cadena vacía.|  
    |**Credenciales de nombre de usuario**|Especificar las credenciales para enviar mensajes. Puede especificar la propiedad haciendo clic en el **editar** botón. Debe establecer las credenciales si seleccionó la **nombre de usuario** opción **tipo de credencial de cliente de mensaje**.<br /><br /> El valor predeterminado es **no use Single Sign-On**.|  
    |**Usar identidad de servicio de ACS**|Se aplica a [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)] y BizTalk Server 2013. <br /><br />Seleccione esta casilla de verificación y haga clic en **editar** y proporcione los valores siguientes para autenticar con el Bus de servicio. Esto es necesario sólo al invocar un resto interfaz Bus de servicio de las entidades relacionadas.<br /><br /> -   **Uri de STS del servicio de Control de acceso** : establezca esta propiedad en `https://<Namespace>-sb.accesscontrol.windows.net/`, donde \<espacio de nombres\> es el espacio de nombres de Bus de servicio.<br />-   **Nombre del emisor** : especifique el nombre del emisor. Normalmente, este valor está establecido en el propietario.<br />-   **Clave del emisor** : especifique la clave del emisor.|  
    |**Información de conexión de Bus de servicio** | Nuevo a partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)].<br/><br/>Elija esta opción utilizar la firma de acceso compartido (SAS) o el servicio de Control de acceso (ACS) del espacio de nombres de Bus de servicio. <br/><br/>Seleccione una opción y, a continuación, seleccione **editar** para escribir la información de clave:<br/><br/> - **Firma de acceso compartido** : escriba el nombre de la clave de acceso y la clave de acceso. Ambos valores se muestran en la [portal de Azure](https://portal.azure.com).<br/> - **Access Control Service** : escriba el URI de STS (`https://<yourNamespace>-sb.accesscontrol.windows.net/`), nombre del emisor y clave del emisor. Usar Windows PowerShell para recuperar estos valores, como se describe en [adaptador SB-Messaging](../core/sb-messaging-adapter.md). |
  
6.  En el **comportamiento** pestaña, configure el comportamiento del extremo para este puerto de envío. 

    |Use|Para|  
    |--------------|----------------|  
    | EndpointBehavior | Ampliar la funcionalidad de cómo se envían las solicitudes en el nivel de punto de conexión. Puede agregar extensiones que realicen diferentes operaciones, como definen el comportamiento del procesamiento de SOAP, especifican un intervalo de tiempo en las transacciones, control de la funcionalidad de detección y utilicen otras clases de .NET. <br/><br/>Seleccione derecha **EndpointBehavior**, y **Agregar extensión**. La lista muestra las clases de .NET que se pueden usar. |
    
    La configuración es similar a la del comportamiento del extremo para un puerto de envío WCF-Custom. Consulte la **comportamiento del cuadro de diálogo de propiedades de transporte WCF-Custom, envío,** ficha [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
7.  En el **Proxy** pestaña, configure la configuración de proxy para el puerto de envío WCF-WebHttp. 
  
    |Use|Para|  
    |--------------|----------------|  
    |**Utilice la configuración de proxy del controlador de envío**|Especificar si el puerto de envío usa la configuración de proxy en el controlador de envío que aloja este puerto de envío.<br /><br /> Esta es la configuración predeterminada.|  
    |**No utilice el proxy**|Indicar si el puerto de envío usa un servidor proxy.<br /><br /> Esta opción está desactivada de forma predeterminada.|  
    |**Utilizar proxy**|Indicar si este puerto de envío usa el servidor proxy especificado en el **dirección** propiedad.<br /><br /> Esta opción está desactivada de forma predeterminada.|  
    |**Dirección**|Especificar la dirección del servidor proxy. Use la **https** o **http** esquema según la configuración de seguridad. Esta dirección puede ir seguida de dos puntos y el número de puerto. Por ejemplo, http://127.0.0.1:8080.<br /><br /> Esta propiedad requiere un valor sólo si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud máxima: 256<br /><br /> El valor predeterminado es una cadena vacía.|  
    |**Nombre de usuario.**|Especificar el nombre de usuario que se utilizará para la autenticación. Si se usa la autenticación integrada, el nombre de usuario incluye el dominio, es decir, dominio\nombre de usuario. Si se usa la autenticación básica o implícita, el nombre de usuario no incluye el dominio\\. Esta propiedad requiere un valor sólo si **utilizar proxy** está seleccionada. **Nota:** WCF-WebHttp de envío de adaptador utiliza la autenticación básica para el proxy. <br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256<br /><br /> El valor predeterminado es una cadena vacía.|  
    |**Contraseña**|Especificar la contraseña que se utilizará para la autenticación.<br /><br /> Esta propiedad requiere un valor sólo si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256<br /><br /> El valor predeterminado es una cadena vacía.|  
  
8.  En el **mensajes** ficha, especifique cómo se envía el mensaje a la interfaz REST.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Encabezados HTTP salientes**|Especifica los encabezados HTTP con los que se marcará el mensaje de respuesta, si corresponde.|  
    |**Suprimir el cuerpo para verbos**|Según el verbo que use para invocar un extremo REST, es posible que necesite o no necesite una carga de mensaje. Por ejemplo, es posible que no necesite una carga de mensaje mientras usa los verbos GET o DELETE. Sin embargo, para activar una llamada al extremo REST mediante el puerto de envío, puede usar un mensaje ficticio que incluya una carga de mensaje. Antes de que el mensaje se envíe al extremo REST, se deberá quitar la carga de mensaje del mensaje ficticio. Puede especificar los verbos para el que la carga del mensaje debe quitarse mediante la **suprimir el cuerpo para verbos** propiedad.<br /><br /> Por ejemplo, si desea quitar la carga del mensaje cuando se usa un verbo GET, especifique el valor de esta propiedad como `GET`.|  
  
9. Haga clic en **Aceptar** y **Aceptar** nuevo para guardar la configuración.  

## <a name="import-wcf-extensions"></a>Extensiones de importación de WCF

Las extensiones WCF en el controlador de recepción o el controlador de envío de importación:

1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración, expanda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **adaptadores** .  

2.  Seleccione **WCF-WebHttp**y, a continuación, la recepción de selección doble o controlador de envío.  

3. En la ficha General, seleccione **propiedades**. 

4. En **extensiones de WCF**, seleccione **importación**y busque el archivo de configuración de extensión WCF. 

  
## <a name="add-a-proxy-to-the-send-handler"></a>Agregar a un proxy para el controlador de envío

Puede agregar a un servidor proxy para el puerto de envío o el controlador de envío. Si va a agregar a un servidor proxy en el puerto de envío, a continuación, omita esta sección.

1.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración, expanda **grupo de BizTalk**, expanda **configuración de plataforma**y, a continuación, expanda **adaptadores**.  
  
2.  Seleccione **WCF-WebHttp**y, a continuación, seleccione el controlador de envío.  
  
3.  En **propiedades de controlador de adaptador**, en la **General** ficha, seleccione **propiedades**.  
  
4.  En el **Proxy** ficha, realice lo siguiente.  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Utilizar proxy**|Indicar si este controlador de envío usa un servidor proxy.<br /><br /> Esta opción está desactivada de forma predeterminada.|  
    |**Dirección**|Especificar la dirección del servidor proxy. Use la **https** o **http** esquema según la configuración de seguridad. Esta dirección puede ir seguida de dos puntos y el número de puerto. Por ejemplo, http://127.0.0.1:8080.<br /><br /> Esta propiedad requiere un valor sólo si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud máxima: 256<br /><br /> El valor predeterminado es una cadena vacía.|  
    |**Nombre de usuario.**|Especificar el nombre de usuario que se utilizará para la autenticación. Si se usa la autenticación integrada o básica, el nombre de usuario incluye el dominio, es decir, dominio\nombre de usuario. Si se utiliza la autenticación implícita, el nombre de usuario no incluye el dominio\\.<br /><br /> Esta propiedad requiere un valor sólo si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256<br /><br /> El valor predeterminado es una cadena vacía.|  
    |**Contraseña**|Especificar la contraseña que se utilizará para la autenticación.<br /><br /> Esta propiedad requiere un valor sólo si **utilizar proxy** está seleccionada.<br /><br /> Tipo: cadena<br /><br /> Longitud mínima: 0<br /><br /> Longitud máxima: 256<br /><br /> El valor predeterminado es una cadena vacía.|  
  
5.  Haga clic en **Aceptar** hasta que salga de todos los cuadros de diálogo.  
   
## <a name="see-also"></a>Vea también  
[Adaptador SB-Messaging](../core/sb-messaging-adapter.md)

[Uso de adaptadores](../core/using-adapters.md)

[¿Qué son los adaptadores de WCF?](../core/what-are-the-wcf-adapters.md)
