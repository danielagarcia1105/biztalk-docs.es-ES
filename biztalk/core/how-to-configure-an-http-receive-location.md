---
title: "Cómo configurar ubicación de recepción HTTP | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive locations, HTTP adapters
- configuring [HTTP adapters], receive locations
- HTTP adapters, receive locations
ms.assetid: 901adfc8-0361-49d9-b992-c27089dfbd3b
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0ae5007816e606f15a74c54669be10c53fe530da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-http-receive-location"></a>Cómo configurar una ubicación de recepción de HTTP
Se pueden establecer variables de adaptador de ubicación de recepción HTTP mediante programación o con la consola de administración de BizTalk Server. Si no se definen las propiedades en la ubicación de recepción, se utilizarán los valores predeterminados del controlador de recepción definidos en la consola de administración de BizTalk Server.  
  
> [!NOTE]
>  Antes de completar este procedimiento, debe haber agregado un puerto de recepción. Para obtener más información, vea [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  
  
 **Cómo configurar un ubicación de recepción HTTP mediante programación**  
  
 El adaptador de HTTP almacena la información de configuración en la base de datos de administración de BizTalk (también conocida como la base de datos de configuración). La configuración se almacena en una bolsa de propiedades XML personalizada.  
  
 El modelo de objetos del explorador de BizTalk expone la **IReceiveLocation** interfaz de configuración, que tiene un **TransportTypeData** propiedad de lectura/escritura. Esta propiedad acepta la bolsa de propiedades de configuración de la ubicación de recepción HTTP en una cadena XML de par nombre-valor.  
  
 Establecer el **TransportTypeData** propiedad de la **IReceiveLocation** no es necesario. Si no se establece, se usan los valores predeterminados de la configuración de ubicación de recepción HTTP. La tabla siguiente enumera los valores predeterminados y las propiedades de configuración que puede establecer en el modelo de objetos del Explorador de BizTalk para la ubicación de recepción HTTP.  
  
|Nombre de la propiedad|Tipo|Description|Restricciones|Comentarios|  
|-------------------|----------|-----------------|------------------|--------------|  
|**ResponseContentType**|string|Tipo de contenido de los mensajes de respuesta HTTP que el adaptador de HTTP envía a los clientes desde esta ubicación de recepción. Esta propiedad es válida sólo para puertos de recepción de solicitud respuesta y se omite para puertos de recepción unidireccionales.|String<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|Valor predeterminado: Text/XML|  
|**Bucle invertido**|Boolean|Especifica que el mensaje de solicitud recibido en esta ubicación se enrutará a un puerto de envío o se devolverá a la ubicación de recepción para enviarlo como respuesta. Esta propiedad es válida únicamente para puertos de recepción de solicitud-respuesta. Se omite para puertos de recepción unidireccionales.|Ninguno|**Valor predeterminado:** False|  
|**ReturnCorrelationHandle**|Boolean|Especifica el token de correlación del mensaje que envía el adaptador de HTTP en la respuesta HTTP al cliente si el envío es correcto. Esta propiedad es válida sólo para puertos de recepción unidireccionales y se omite para puertos de recepción de solicitud-respuesta.|Ninguno|**Valor predeterminado:** True|  
|**SuspendFailedRequests**|Boolean|Especifica si se deben suspender las solicitudes HTTP con errores. Un valor de True indica que se suspenda la solicitud con errores y enviar un código de estado "Aceptado" (202) para el cliente para unidireccional recibe puertos o un código de estado de "Error" (500) al cliente para bidireccional puertos de recepción.|Ninguno|**Valor predeterminado:** False|  
|**UseSSO**|Boolean|Especifica si el adaptador HTTP emitirá el vale SSO para los mensajes que llegan a esta ubicación de recepción.|Ninguno|**Valor predeterminado:** False|  
  
 El formato de la cadena XML para establecer estas propiedades es el siguiente:  
  
```  
<CustomProps>  
   <UseSSO vt="11">-1</UseSSO>  
   <SuspendFailedRequests vt="11">-1</SuspendFailedRequests>  
   <ReturnCorrelationHandle vt="11">-1</ReturnCorrelationHandle>  
   <ResponseContentType vt="8">text/xml</ResponseContentType>  
   <LoopBack vt="11">-1</LoopBack>  
</CustomProps>  
  
```  
  
 **Cómo configurar HTTP ubicación de recepción con la consola de administración de BizTalk Server**  
  
 Para configurar la ubicación de recepción utilizando la consola de administración de BizTalk Server, siga el procedimiento que se detalla a continuación:  
  
### <a name="to-configure-variables-for-an-http-receive-location"></a>Para configurar variables para una ubicación de recepción HTTP  
  
1.  Configure los Servicios de Internet Information Server (IIS) para trabajar con ubicaciones de recepción HTTP. Para obtener instrucciones sobre cómo configurar IIS, consulte [cómo configurar IIS para una ubicación de recepción HTTP](../core/how-to-configure-iis-for-an-http-receive-location.md).  
  
2.  En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda el aplicación en el que desea crear una ubicación de recepción.  
  
3.  En el panel izquierdo, haga clic en el **puertos de recepción** nodo. A continuación, en el panel de la derecha, haga clic con el botón secundario en el puerto de recepción asociado con una ubicación de recepción existente o que desee asociar con una nueva ubicación de recepción. A continuación, haga clic en **Propiedades**.  
  
4.  En el **propiedades de puerto de recepción** cuadro de diálogo, en el panel izquierdo, seleccione **ubicaciones de recepción**y en el panel derecho, haga doble clic en otra ubicación de recepción o haga clic en **nuevo** Para crear una nueva ubicación de recepción.  
  
5.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en el **transporte** junto a la sección **tipo**, seleccione **HTTP** en la lista desplegable y, a continuación, haga clic en **configurar**.  
  
6.  En el **propiedades de transporte HTTP** diálogo cuadro, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Directorio virtual más extensión ISAPI**|Especificar el nombre del directorio virtual al que se envían los mensajes que recibe la ubicación de recepción HTTP/HTTPS. El directorio virtual incluye el nombre del archivo DLL de ubicación de recepción y una cadena de consulta opcional. Éstos son algunos ejemplos de nombres de directorio virtual:<br /><br /> /\<directorio virtual >/BTSHTTPReceive.dll<br /><br /> /\<¿directorio virtual > / BTSHTTPReceive.dll? Compra % 20Order<br /><br /> Esta ubicación no debe contener más de una extensión ISAPI BTSHTTPReceive.dll, incluidas todas las subcarpetas.<br /><br /> **Tipo:** cadena<br /><br /> **Longitud máxima:** 256 **Nota:** URI de un envío de puerto o recibir ubicación no puede superar los 256 caracteres.|  
    |**Dirección pública**|Especificar el URI completo de la ubicación de recepción. El valor de esta propiedad es una combinación del nombre del servidor y el directorio virtual. El motor de mensajería de BizTalk expone esta dirección a socios externos. El URI especificado debe designar la dirección URL del sitio Web público para que los socios comerciales se conecten cuando envíen mensajes a BizTalk Server.<br /><br /> Esta información es opcional y BizTalk Server no la utiliza. Este parámetro está disponible para permitir a los administradores documentar la dirección URL pública a la que está vinculada la ubicación de recepción.<br /><br /> **Tipo:** cadena<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|  
    |**Devolver el tipo de contenido**|Especificar el tipo de contenido de los mensajes de respuesta HTTP que la ubicación de recepción envía a los clientes. Esta propiedad sólo es válida para las ubicaciones de recepción de solicitud-respuesta.<br /><br /> **Valor predeterminado:** texto/xml<br /><br /> **Tipo:** cadena<br /><br /> **Longitud mínima:** 0<br /><br /> **Longitud máxima:** 256|  
    |**Bucle invertido**|Definir que el mensaje de solicitud recibido en esta ubicación se enrute a un puerto de envío o se devuelva a esta ubicación de recepción para enviarlo como respuesta. Esta propiedad sólo es válida para las ubicaciones de recepción de solicitud-respuesta.<br /><br /> **Valor predeterminado:** False<br /><br /> **Tipo:** booleano|  
    |**Devolver controlador de correlación en caso de éxito (sólo puerto unidireccional)**|Definir que, si la recepción es correcta, la ubicación de recepción envíe el token de correlación del mensaje enviado en la respuesta HTTP al cliente. Esta propiedad sólo es válida para las ubicaciones de recepción unidireccionales.<br /><br /> **Valor predeterminado:** True<br /><br /> **Tipo:** booleano|  
    |**Usar inicio de sesión único en**|Indicar que se utiliza el inicio de sesión único (SSO) empresarial.<br /><br /> **Valor predeterminado:** False<br /><br /> **Tipo:** booleano **Nota:** si esta opción está habilitada, también debe habilitar la opción de **permitir vales** en el **sistema SSO** nivel. El **permitir vales** opción es configurable en el **opciones** pestaña de la **propiedades del sistema SSO** disponibles en el cuadro de diálogo la **deadministracióndeSSO** Interfaz MMC. Si esta opción está habilitada y la **permitir vales** opción en el **sistema SSO** no está habilitada, a continuación, cualquier mensaje recibido en esta ubicación de recepción se suspenderán.|  
    |**Suspender solicitudes con error**|Indica si se deben suspender o no las solicitudes HTTP que dan error en el procesamiento de entrada.<br /><br /> El valor False indica que se descarte la solicitud con errores y se envíe un código de estado de error (401 o 500) al cliente.<br /><br /> El valor indica que se suspenda la solicitud con errores y se envíe un código de estado "Aceptado" (200) al cliente para puertos de recepción unidireccionales o un código de estado "Error" (500) al cliente para puertos de recepción bidireccionales.<br /><br /> **Valor predeterminado:** False<br /><br /> **Tipo:** booleano|  
  
7.  Haga clic en **Aceptar** para guardar la configuración.  
  
8.  Especifique los valores apropiados en el cuadro de diálogo **Propiedades de la ubicación de recepción** para completar la configuración de la ubicación de recepción y haga clic en **Aceptar** para guardar la configuración. Para obtener información sobre la **propiedades de ubicaciones de recepción** cuadro de diálogo, vea [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
 Si bien el cliente HTTP llama a la ubicación HTTP, el adaptador de HTTP autentica el cliente HTTP usando autenticación anónima, básica, implícita o integrada de Windows. Si se comprueba el usuario, se pasa el contexto del usuario al controlador de recepción.  
  
> [!NOTE]
>  No será válida ninguna configuración de IIS que haga que SOAP y HTTP compartan el mismo proceso. Sólo puede haber un receptor aislado por proceso.