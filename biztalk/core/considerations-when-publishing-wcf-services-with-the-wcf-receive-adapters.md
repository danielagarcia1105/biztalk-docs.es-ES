---
title: Consideraciones al publicar servicios WCF con WCF adaptadores de recepción | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- publishing, WCF services
- WCF adapters, best practices
- WCF adapters, receive adapters
- WCF services, publishing
- best practices, WCF adapters
ms.assetid: 797b7ffd-534c-4f09-9738-fb17b208bc96
caps.latest.revision: 34
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9c232f085647d3f69f576232ec9d9adb3b01a2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004085"
---
# <a name="considerations-when-publishing-wcf-services-with-the-wcf-receive-adapters"></a>Consideraciones al publicar servicios WCF con los adaptadores de recepción WCF
Este tema proporciona información que debe tenerse en cuenta a la hora de publicar servicios WCF con los adaptadores de recepción WCF.  Publicar un servicio mediante un adaptador WCF permite que un cliente WCF lo pueda llamar del mismo modo que si fuera un Servicio WCF convencional.  
  
## <a name="in-process-hosting"></a>Hosts de tipo En curso  
 Hospedar la ubicación de recepción en el espacio del proceso de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], btsntsvc.exe, permite disfrutar de las ventajas que ofrece el desarrollo y la implementación simplificados. Además, crea más instancias de host que hospedar en IIS para aprovechar las capacidades de elevada disponibilidad y equilibrio de carga de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  Para obtener información en el hospedaje fuera de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] proceso en IIS, consulte [configurar IIS para los adaptadores de recepción WCF aislados](../core/configuring-iis-for-the-isolated-wcf-receive-adapters.md).  
  
## <a name="set-the-isoneway-property-of-wcf-services-published-with-the-wcf-adapters-except-for-the-wcf-netmsmq-receive-adapter-to-false"></a>Establezca en false la propiedad IsOneWay de los Servicios WCF publicados con los adaptadores de WCF (excepto el adaptador de recepción WCF-NetMsmq).  
 El **System.ServiceModel.OperationContractAttribute.IsOneWay** propiedad de los servicios WCF publicados con los adaptadores WCF, excepto para servicios publicados con el WCF-NetMsmq: donde se establece en el adaptador de recepción **true**  : se establece en **false** incluso para las ubicaciones de recepción la unidireccional. Si el **IsOneWay** propiedad está establecida en **false**, incluso los métodos que devuelven un **void** dar lugar a un mensaje de respuesta. En este caso, la infraestructura crea y envía un mensaje vacío para indicar al usuario que llama que el método se ha devuelto. Esta aproximación permite habilitar la infraestructura para enviar excepciones iniciadas por la operación del servicio devuelta al cliente.  
  
 Para consumir servicios WCF publicados con los adaptadores de WCF (excepto el adaptador de recepción de WCF-NetMsmq) en el que **IsOneWay** es **false**, **IsOneWay** propiedad en el lado del cliente debe establecerse en **false** como sigue:  
  
```  
[ServiceContract(Namespace="Microsoft.WCF.Documentation")]  
  public interface ISampleService{  
    [OperationContract(IsOneWay=false, ReplyAction="*",Action="…"]  
    string SampleMethod(string msg);  
}  
```  
  
> [!NOTE]
>  Dado que el valor predeterminado de la **IsOneWay** propiedad es **false**, no es necesario especificar la propiedad en el código.  
  
## <a name="the-replyaction-property-of-the-operationcontractattribute-on-the-client-side-should-be-set-to--an-asterisk-when-consuming-wcf-services-published-with-one-way-receive-locations"></a>La propiedad ReplyAction de OperationContractAttribute del equipo cliente debe establecerse en "*" (un asterisco) al consumir servicios WCP publicados con ubicaciones de recepción unidireccionales.  
 El **System.ServiceModel.OperationContractAttribute.ReplyAction** propiedad de la **System.ServiceModel.OperationContractAttribute** puede usarse en el lado cliente para especificar el valor de la Acción SOAP para los mensajes de respuesta de los servicios de WCF.  
  
 Además de especificar un valor en particular para el encabezado de acción del mensaje de respuesta (para notificar al cliente que es una respuesta y la acción que debe seguirse), también puede especificar la cadena "*" (un asterisco). Especificar un asterisco en la aplicación cliente le ordena al cliente que no valide la acción de respuesta en los mensajes de respuesta que envía el servicio.  
  
 Para consumir un WCF servicio publicado por un unidireccional ubicación de recepción, el método de proxy para el servicio WCF debe devolver **void**, en cuyo caso el método proxy espera que el servicio de WCF enviará un mensaje vacío para indicar al autor de llamada que el método ha devuelto. El método proxy reciba este mensaje vacío, el **ReplyAction** propiedad de la **OperationContractAttribute** debe establecerse en "*" (asterisco) como sigue:  
  
```  
[ServiceContract(Namespace="Microsoft.WCF.Documentation")]  
  public interface ISampleService{  
    [OperationContract(IsOneWay=false, ReplyAction="*",Action="…"]  
    string SampleMethod(string msg);  
}  
```  
  
> [!NOTE]
>  No es necesario que establecer el **ReplyAction** propiedad en "\*" (asterisco) para el adaptador WCF-NetMsmq, porque el adaptador WCF-NetMsmq requiere que los clientes WCF establecer el **IsOneWay** propiedad **true**.  
  
## <a name="an-isolated-host-instance-can-run-only-one-adapter"></a>Una instancia de host aislado sólo puede ejecutar un adaptador  
 Una instancia de host aislado sólo puede ejecutar un adaptador. Si configura los controladores de recepción de varios adaptadores aislados como los adaptadores de HTTP, SOAP y WCF con un host aislado, debe crear varios grupos de aplicaciones, uno para cada adaptador. Para obtener más información acerca de los hosts aislados de BizTalk, consulte [habilitar los servicios Web](../core/enabling-web-services.md).  
  
## <a name="use-the-template----content-specified-by-template-option-when-sending-non-xml-content-as-response-messages"></a>Utilice la opción "Plantilla: contenido especificado por plantilla" al enviar contenido que no sea XML como mensajes de respuesta  
 Los adaptadores de WCF con **cuerpo--cuerpo de mensaje de respuesta de BizTalk** (el valor predeterminado) opción no permite el envío de mensajes que no son XML, como las imágenes de mapa de bits y datos de carácter. Puede usar el **plantilla--contenido especificado por plantilla** opción para los adaptadores de WCF enviar los mensajes que no sean XML. Para obtener más información sobre cómo usar la plantilla, consulte [especificando el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).  
  
## <a name="setting-up-the-permissions-for-a-wcf-service-published-with-the-wcf-service-publishing-wizard"></a>Configurar los permisos para un Servicio WCF publicado con el Asistente para publicación de Servicio WCF.  
 Al usar aplicaciones ASP.NET creadas mediante el Asistente para publicación de Servicio WCF en la plataforma [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] o [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], pueden aparecer problemas relacionados con el acceso a los DLL durante la invocación del Servicio WCF. Estos errores suelen estar relacionados a problemas con el valor predeterminado de seguridad de [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] y [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]. Para obtener más información acerca de estos errores, vea el artículo de Microsoft Help and Support denominado "Recibirá un"System.IO.FileNotFoundException"Error cuando la aplicación cliente llama a un servicio Web" en el sitio Web de ayuda y soporte técnico en [ http://go.microsoft.com/fwlink/?LinkId=43659 ](http://go.microsoft.com/fwlink/?LinkId=43659).  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] requiere que, al proceso que ejecuta el Servicio WCF, se le concedan los permisos apropiados si un host de tipo en curso o un host aislado ejecutan el servicio. En [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] y [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)], el grupo de Windows predeterminado para hosts aislados es el Grupo de usuarios de hosts aislados. Como consecuencia, si se agregan los permisos a este grupo, se debería solucionar el problema.  
  
#### <a name="to-add-the-permissions-to-the-isolated-host-users-group"></a>Para agregar los permisos al Grupo de usuarios de hosts aislados  
  
1.  En el Explorador de Microsoft Windows, localice el directorio %windir%\temp.  
  
2.  Haga clic en % windir%\temp y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades** cuadro de diálogo, haga clic en el **seguridad** ficha.  
  
4.  Haga clic en **agregar**, seleccione **el grupo de usuarios de hosts aislados**y, a continuación, haga clic en **Aceptar**.  
  
## <a name="setting-up-the-permissions-for-a-wcf-receive-location-with-the-wcf-netmsmq-adapter"></a>Configurar los permisos para una ubicación de recepción WCF con el adaptador de WCF-NetMsmq  
 Cuando un cliente de WCF que utiliza NetMsmqBinding envía un mensaje a un Servicio WCF publicado con el adaptador de WCF-NetMsmq, éste dirige el mensaje a la cola de destino, que es la cola administrada por el administrador de colas del servicio. El administrador de colas del cliente envía el mensaje a una cola de transmisión (o saliente). La cola de transmisión es una cola situada en el administrador de colas del cliente que almacena mensajes para transmitirlos a la cola de destino.  
  
 El administrador de colas del servicio acepta los mensajes dirigidos a las colas de destino que le pertenecen y, además, almacena los mensajes. A continuación, el servicio realiza solicitudes para leer de la cola de destino y el administrador de colas entrega los mensajes al servicio. Por este motivo, la cuenta del servicio de la instancia de host de BizTalk que aloja la ubicación de recepción debe disponer de los permisos necesarios para leer desde la cola de destino.  
  
## <a name="use-an-empty-body-path-expression-to-receive-a-soap-message-with-character-data-in-the-content-of-the-soap-body-element"></a>Utilizar una expresión de ruta de cuerpo vacía para recibir un mensaje SOAP con datos de caracteres en el contenido del elemento de cuerpo SOAP  
 Adaptador para crear un mensaje de BizTalk desde un mensaje de respuesta entrante con datos de caracteres en el contenido del mensaje SOAP de recepción WCF **cuerpo** elemento, como se muestra en el ejemplo siguiente, debe dejar el **ruta de cuerpo expresión** cuadro de texto vacío en el **mensaje** ficha en el cuadro de diálogo de propiedades de transporte WCF adaptador.  
  
```  
<s:Envelope xmlns:s="http://www.w3.org/2003/05/soap-envelope" xmlns:a="http://www.w3.org/2005/08/addressing">  
    <s:Header>  
      ...  
    </s:Header>  
    <s:Body>Contoso</s:Body>  
</s:Envelope>  
```  
  
 Si selecciona el **sobres** o **cuerpo** opción, el adaptador no puede crear el mensaje de BizTalk desde el mensaje entrante anterior. El mensaje no se suspende porque los mensajes que producen error en el procesamiento del cálculo de referencia de SOAP entrante no se suspenden. Para obtener más información sobre cómo usar la expresión de ruta de cuerpo en el **mensaje** pestaña, vea [especificando el cuerpo del mensaje para los adaptadores de WCF](../core/specifying-the-message-body-for-the-wcf-adapters.md).  
  
> [!NOTE]
>  Puede usar la herramienta TraceViewer (SvcTraceViewer.exe) de Windows SDK mediante la configuración de BTSNTSvc.exe.config.file. Para obtener más información sobre el SDK de Windows, vea "Novedades en el SDK de Windows" en [ http://go.microsoft.com/fwlink/?LinkId=75219 ](http://go.microsoft.com/fwlink/?LinkId=75219). Para obtener más información acerca de la herramienta TraceViewer, vea "TraceViewer Tool (SvcTraceViewer.exe)" en [ http://go.microsoft.com/fwlink/?LinkId=75218 ](http://go.microsoft.com/fwlink/?LinkId=75218).  
  
## <a name="using-schemas-that-reference-other-schemas"></a>Utilizar esquemas que hacen referencia a otros esquemas  
 Puede usar el **redefinir**, **incluyen**, y **importar** elementos cuando los esquemas se hacen grandes y complejas, o cuando los esquemas que representan los distintos tipos de los mensajes de instancia tienen algunas partes en común. Puede resultar útil combinar esquemas más pequeños en los esquemas que en última instancia definen la estructura de los mensajes de instancias que planea intercambiar con socios comerciales. Puede publicar estos esquemas como servicios WCF utilizando el Asistente para publicación de Servicio WCF de BizTalk.  
  
 Debe utilizar el Asistente para publicación de Servicio WCF de BizTalk para crear artefactos de BizTalk necesarios para consumir los servicios WCF desde un proyecto de BizTalk. Si desea consumir los servicios WCF desde una aplicación .NET, debe utilizar la herramienta de metadatos del modelo de servicio (Svcutil.exe) para crear la clase proxy para los servicios WCF. Para obtener más información acerca de cómo utilizar los esquemas que hacen referencia a otros esquemas, vea [esquemas que usar otros esquemas](../core/schemas-that-use-other-schemas.md) y [cómo crear esquemas que usar otros esquemas](../core/how-to-create-schemas-that-use-other-schemas.md). Para obtener más información acerca de Svcutil.exe, vea "Service Model Metadata utilidad Tool (Svcutil.exe)" en [ http://go.microsoft.com/fwlink/?LinkID=74696 ](http://go.microsoft.com/fwlink/?LinkID=74696).  
  
 La siguiente tabla muestra las limitaciones y consideraciones que necesita tener en cuenta a la hora de consumir servicios WCF publicados con esquemas que utilizan otros esquemas.  
  
|Elemento de esquema XML|Consumir servicios WCF publicados con el Asistente para publicación de Servicio WCF de BizTalk|Consumir servicios WCF alojados por aplicaciones .NET|  
|------------------------|-------------------------------------------------------------------------------------|--------------------------------------------------------|  
|\<Importación\>|Compatible con el Asistente para consumición del Servicio WCF de BizTalk y Svcutil.exe|Compatible con el Asistente para consumición del Servicio WCF de BizTalk y Svcutil.exe|  
|\<incluir\>|Compatible con el Asistente de consumición de servicio WCF de BizTalk y Svcutil.exe **Nota:** Svcutil.exe puede generar un mensaje de advertencia al crear la clase de proxy.|Compatible con el Asistente de consumición de servicio WCF de BizTalk y Svcutil.exe **Nota:** Svcutil.exe puede generar un mensaje de advertencia al crear la clase de proxy.|  
|\<redefine\>|-Compatible con el Asistente para consumición del servicio de WCF de BizTalk<br />-Compatibilidad svcutil.exe de limitada **Nota:** Svcutil.exe tiene la misma limitación para el **redefinir** elemento como XSD.exe tiene.|Compatible con el Asistente de consumición de servicio WCF de BizTalk y Svcutil.exe **Nota:** Svcutil.exe puede generar un mensaje de advertencia al crear la clase de proxy.|  
  
> [!NOTE]
>  Svcutil.exe puede generar un mensaje de advertencia al crear la clase de proxy con el servicio WCF de BizTalk publicado con los esquemas mediante la **incluyen** y **redefinir** elementos. Por ejemplo, para indicar que el elemento global ya ha sido declarado.  
  
## <a name="ensure-that-an-in-process-wcf-receive-location-is-not-disabled-after-you-change-the-computer-name-part-in-its-service-endpoint-address"></a>Garantizar que una ubicación de recepción WCF en curso no se encuentra deshabilitada después de cambiar la parte del nombre del equipo en la dirección de extremo de servicio  
 Si cambia la parte del nombre del equipo en el **dirección (URI)** ubicación de recepción del cuadro de texto de un WCF ejecutan en un proceso, se recomienda que utilice la consola de administración de BizTalk para comprobar si todavía se está ejecutando la ubicación de recepción. Por ejemplo, si cambia una dirección de punto de conexión de servicio mediante WCF-NetTcp adaptador de recepción, **net.tcp://\<**<em>del nombre del equipo</em>**\>/samplepath**a **net.tcp://localhost/samplepath**, la ubicación de recepción puede deshabilitarse con un **Service.InvalidOperationException**. Si sólo modifica la parte del nombre del equipo en la dirección de extremo de servicio sin modificar la parte de la ruta, asegúrese de que la ubicación de recepción no se encuentra deshabilitada y habilítela si es necesario.  
  
## <a name="set-the-appropriate-msdtc-security-configuration-options-on-client-computers-communicating-with-remote-wcf-receive-locations-through-a-transaction-protocol"></a>Establezca las opciones apropiadas de configuración de seguridad de MSDTC en los equipos clientes que se comunican con ubicaciones de recepción WCF remotas a través de un protocolo de transacción  
 Adaptadores de recepción WCF-NetTcp, WCF-WSHttp y WCF-NetNamedPipe pueden participar en procesos de coordinación transaccionales que los clientes de WCF administran con el **WS-AtomicTransaction** y **OleTransaction**protocolos de transacción. Los mensajes pueden transmitirse a las ubicaciones de recepción de destino y pueden eliminarse de la base de datos de cuadro de mensajes en un contexto transaccional usando el protocolo WS-AtomicTransaction.  
  
 Para comunicarse con el servidor remoto de ubicaciones de recepción WCF mediante el uso de los protocolos de transacción, debe configurar adecuadamente MSDTC **configuración de seguridad** opciones en los equipos cliente WCF. La tabla siguiente enumeran los valores necesarios para las opciones que están disponibles en el MSDTC **configuración de seguridad** cuadro de diálogo:  
  
|Opción de configuración|Valor predeterminado|Valor recomendado|  
|--------------------------|-------------------|-----------------------|  
|Acceso de DTC a la red|Deshabilitado|Habilitado|  
|Permitir salientes|Deshabilitado|Habilitado|  
|Se requiere autenticación mutua|Habilitado|Habilitada si recibe el correspondiente control remoto ubicaciones ejecutan Windows Server 2003 SP1 o SP2 y se configuran con **requiere autenticación mutua**.|  
|Se requiere autenticación de llamada entrante|Deshabilitado|Habilitada si se ejecuta MSDTC en un clúster.|  
  
 Después de aplicar estos cambios, deberá reiniciar el servicio MSDTC.  
  
 Para obtener acceso a MSDTC **configuración de seguridad** diálogo cuadro, siga estos pasos:  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**y el tipo **dcomcnfg** para iniciar el **servicios de componentes** consola de administración.  
  
2.  Expanda **servicios de componentes**, expanda **equipos**, haga clic en **Mi PC**y, a continuación, haga clic en **propiedades**.  
  
3.  En el **propiedades de Mi PC** cuadro de diálogo, haga clic en el **MSDTC** pestaña y, a continuación, haga clic en **configuración de seguridad** para mostrar el **configuración de seguridad**  cuadro de diálogo.  
  
## <a name="explanation-of-the-soap-wrapper-when-using-the-biztalk-wcf-service-publishing-wizard"></a>Explicación del contenedor SOAP cuando se usa al Asistente para publicación de Servicio WCF de BizTalk  
 Cuando se expone una orquestación como servicio de [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] mediante el Asistente para publicación de Servicio [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)], se genera un contenedor. Este contenedor usa el nombre del método del puerto en el mensaje XML al que se envía el mensaje. Este contenedor es el valor predeterminado para los sobres SOAP de Microsoft y permite a [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] envolver el mensaje SOAP de varias partes en un mensaje de WCF para que el adaptador pueda transmitirlo al extremo.  
  
 Se recomienda que el remitente use un contenedor y el destinatario lo espere, o bien que el remitente no use un contenedor y el destinatario espere el mensaje de [!INCLUDE[nextref_btsWinCommFoundation](../includes/nextref-btswincommfoundation-md.md)] sin procesar. Si no se acuerda previamente si se va a usar un contenedor o no, se pueden producir problemas de compatibilidad entre lo que se envía y lo que se recibe.