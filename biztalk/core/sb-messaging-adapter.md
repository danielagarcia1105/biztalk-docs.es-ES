---
title: Adaptador SB-Messaging | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c06c4934-45b2-4f6f-9d19-3ebd937c32ae
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2fb2eb8f532d72708dfca199f0eef794afdf77df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sb-messaging-adapter"></a>Adaptador SB-Messaging
El Bus de servicio (**SB-Messaging**) se utiliza el adaptador para recibir y enviar de entidades de Service Bus como colas, temas y retransmisiones. Puede usar el **SB-Messaging** adaptadores para unir la conectividad entre [!INCLUDE[winazure](../includes/winazure-md.md)] locales y en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], lo que permite a los usuarios crear una aplicación híbrida típica. Los temas de esta sección proporcionan instrucciones sobre cómo configurar un **SB-Messaging** ubicación de recepción y un puerto de envío para enviar y recibir mensajes de las entidades de Bus de servicio.  

## <a name="before-you-get-started"></a>Antes de comenzar
Bus de servicio proporciona dos métodos para autenticar: servicio de Control de acceso (ACS) y la firma de acceso compartido (SAS). Nuestra recomendación es usar la firma de acceso compartido (SAS) para autenticar con Bus de servicio. El valor de clave de acceso compartida aparece en la [portal de Azure](https://portal.azure.com).

Cuando se crea un espacio de nombres de Bus de servicio, no se crea automáticamente el espacio de nombres de Control de acceso (ACS). Para usar el Control de acceso, necesita los valores de nombre del emisor y clave del emisor de este espacio de nombres. Estos valores están disponibles cuando se crea un nuevo espacio de nombres de ACS mediante Windows PowerShell. Estos valores no se muestran en el portal de Azure.

Para usar ACS para la autenticación y obtener los valores de nombre del emisor y clave del emisor, los pasos generales son:

1. Instalar el [cmdlets de Powershell de Azure](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).
2. Agregue su cuenta de Azure:`Add-AzureAccount`
3. Devolver el nombre de la suscripción:`get-azuresubscription`
4. Seleccione su suscripción:`select-azuresubscription <name of your subscription>` 
5. Crear un nuevo espacio de nombres:`new-azuresbnamespace <name for the service bus> "Location" -CreateACSNamespace $true -NamespaceType Messaging`

    Ejemplo:`new-azuresbnamespace biztalksbnamespace "South Central US" -CreateACSNamespace $true -NamespaceType Messaging`
      
5. Cuando se crea el nuevo espacio de nombres de ACS (que puede tardar varios minutos), se muestran los valores IssuerName y IssuerKey en la cadena de conexión: 

    ```
    Name                  : biztalksbnamespace
    Region                : South Central US
    DefaultKey            : abcdefghijklmnopqrstuvwxyz
    Status                : Active
    CreatedAt             : 10/18/2016 9:36:30 PM
    AcsManagementEndpoint : https://biztalksbnamespace-sb.accesscontrol.windows.net/
    ServiceBusEndpoint    : https://biztalksbnamespace.servicebus.windows.net/
    ConnectionString      : Endpoint=sb://biztalksbnamespace.servicebus.windows.net/;SharedSecretIssuer=owner;SharedSecretValue=abcdefghijklmnopqrstuvwxyz
    NamespaceType         : Messaging
    ```
[Nueva AzureSBNamespace](https://msdn.microsoft.com/library/dn495165.aspx)

## <a name="receive-messages-from-service-bus"></a>Recibir mensajes de Bus de servicio
  
Esta sección proporciona información sobre cómo configurar un **SB-Messaging** ubicación de recepción utilizando la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
> [!NOTE]
>  Antes de completar el procedimiento siguiente, debe haber agregado un unidireccional puerto de recepción. Vea [cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md).  

 
1.  En la consola de administración de BizTalk Server, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear una ubicación de recepción.  
  
2.  En el panel izquierdo, haga clic en el nodo **Puertos de recepción** y, en el panel derecho, haga clic con el botón derecho en el puerto de recepción al que desea asociar la nueva ubicación de recepción y, a continuación, haga clic en **Propiedades**.  
  
3.  En el panel de la izquierda del cuadro de diálogo **Propiedades de puerto de recepción** , seleccione **Ubicaciones de recepción**y, en el panel de la derecha, haga clic en **Nueva** para crear una nueva ubicación de recepción.  
  
4.  En el **propiedades de la ubicación de recepción** cuadro de diálogo, en el **transporte** sección, seleccione **SB-Messaging** desde el **tipo** lista desplegable y, a continuación, haga clic en **configurar** para configurar las propiedades de transporte para la ubicación de recepción.  
  
5.  En el **propiedades de transporte SB-Messaging** cuadro de diálogo, en la **General** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Dirección URL de cola o suscripción**|Especifique la dirección URL en la que se implementa la cola de Service Bus. Normalmente, la dirección URL tiene el siguiente formato:<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`|  
    |**Open Timeout**|Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de apertura del canal.<br /><br /> **Valor predeterminado:** 1 minuto|  
    |**Tiempo de espera de cierre**|Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de cierre del canal.<br /><br /> **Valor predeterminado:** 1 minuto|  
    |**Tiempo de espera de recepción**|Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de recepción.<br /><br /> **Valor predeterminado:** 10 minutos|  
    |**Número de capturas previas**|Especifica el número de mensajes que se reciben de forma simultánea de la cola o de un tema de Service Bus. La captura previa permite a la cola o al cliente de la suscripción cargar mensajes adicionales desde el servicio al realizar una operación de recepción. El cliente almacena estos mensajes en una caché local. El tamaño de la caché está determinado por el valor de la propiedad de recuento de captura previa que especifique aquí.<br /><br /> Para obtener más información, consulte la sección "Captura previa" en [https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/)<br /><br /> **Valor predeterminado:** -1|  
    |**Usar sesión**|Active esta casilla para usar una sesión de Service Bus para recibir mensajes de una cola o una suscripción.|  
  
6.  En el **autenticación** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Servicio de Control de acceso**|Seleccione esta opción para usar ACS para la autenticación y proporcione los valores siguientes:<br /><br /> : Especifique el URI STS de servicio de Control de acceso de Service Bus. Normalmente, el URI tiene el siguiente formato:<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> : Especifique el nombre del emisor del espacio de nombres de Bus de servicio.<br /><br /> : Especifique la clave del emisor del espacio de nombres de Bus de servicio.|  
    |**Firma de acceso compartido** (nuevo a partir de [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])|Seleccione esta opción para usar la autenticación con Firma de acceso compartido (SAS) y proporcione el nombre y el valor de la clave SAS.|  
  
7.  En el **propiedades** ficha la **Namespace para propiedades de mensajes desacoplados** , especifique el espacio de nombres que utiliza el adaptador para escribir las propiedades de mensaje negociado como propiedades de contexto de mensaje en el mensaje recibido por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Además, si desea promocionar las propiedades de mensaje asíncrono, seleccione la **promocionar propiedades de mensajes desacoplados** casilla de verificación.  
  
8.  Haga clic en **Aceptar**.  
  
9. Especifique los valores apropiados en el cuadro de diálogo **Propiedades de la ubicación de recepción** para completar la configuración de la ubicación de recepción y haga clic en **Aceptar** para guardar la configuración. Para obtener información sobre la **propiedades de ubicaciones de recepción** cuadro de diálogo, vea [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
## <a name="send-messages-to-service-bus"></a>Enviar mensajes al Bus de servicio
Esta sección proporciona información sobre cómo configurar un **SB-Messaging** puerto de envío mediante el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración.  
  
1.  En la consola de administración de BizTalk Server, cree un nuevo puerto de envío o haga doble clic en un puerto de envío existente para modificarlo. Para obtener más información, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Configure todas las opciones del puerto de envío y especifique **SB-Messaging** para el **tipo** opción en el **transporte** sección de la **General** pestaña.  
  
2.  En el **General** ficha la **transporte** sección, haga clic en el **configurar** botón.  
  
3.  En el **propiedades de transporte SB-Messaging** cuadro de diálogo, en la **General** ficha, especifique lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Dirección URL de destino**|Escriba la dirección URL donde se implementa la cola de Bus de servicio. Normalmente, la dirección URL tiene el siguiente formato:<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`|  
    |**Intervalo de vaciado de lote**|Especifica un valor de intervalo de tiempo que indica el intervalo en el que se vacían los lotes de mensajes que se envían a una cola o tema. El valor predeterminado es 20 milisegundos.<br /><br /> Para obtener más información sobre el procesamiento por lotes con respecto a los temas y colas de Bus de servicio, consulte la **procesamiento por lotes de cliente** sección en [https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements).|  
    |**Open Timeout**|Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de apertura del canal.<br /><br /> **Valor predeterminado:** 1 minuto|  
    |**Tiempo de espera de envío**|Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de envío.<br /><br /> **Valor predeterminado:** 1 minuto|  
    |**Tiempo de espera de cierre**|Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de cierre del canal.<br /><br /> **Valor predeterminado:** 1 minuto|  
  
4.  En el **autenticación** ficha, realice lo siguiente:  
  
    |Use|Para|  
    |--------------|----------------|  
    |**Servicio de Control de acceso**|Seleccione esta opción para usar ACS para la autenticación y proporcione los valores siguientes:<br /><br /> : Especifique el URI STS de servicio de Control de acceso de Service Bus. Normalmente, el URI tiene el siguiente formato:<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> : Especifique el nombre del emisor del espacio de nombres de Bus de servicio.<br /><br /> : Especifique la clave del emisor del espacio de nombres de Bus de servicio.|  
    |**Firma de acceso compartido** (nuevo a partir de [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)])|Seleccione esta opción para usar la autenticación con Firma de acceso compartido (SAS) y proporcione el nombre y el valor de la clave SAS.|  
  
5.  En el **propiedades** ficha la **Namespace para el usuario define propiedades de mensajes desacoplados** , especifique el espacio de nombres que contiene las propiedades de contexto de mensaje de BizTalk que desee escribir como propiedades de mensajes desacoplados definidas por el usuario en el mensaje saliente enviado a la cola de Bus de servicio. Todas las propiedades que pertenezcan al espacio de nombres se escriben en el mensaje como propiedades de mensajes desacoplados definidas por el usuario. El adaptador ignora el espacio de nombres al escribir las propiedades como propiedades de mensajes desacoplados. Usa el espacio de nombres solo para confirmar qué propiedades escribir.  
  
     También puede especificar los valores de las propiedades BrokeredMessage. Para obtener más información acerca de las propiedades, vea [propiedades BrokeredMessage](https://msdn.microsoft.com/library/azure/microsoft.servicebus.messaging.brokeredmessage_properties.aspx).  
  
6.  Haga clic en **Aceptar** y **Aceptar** nuevo para guardar la configuración.  
  
## <a name="see-also"></a>Vea también
[Uso de adaptadores](../core/using-adapters.md)