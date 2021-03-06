---
title: Adaptador de mensajería de Service Bus | Microsoft Docs
description: Enviar y recibir mensajes mediante el adaptador Azure SB-Messaging en BizTalk Server
ms.custom: ''
ms.date: 11/21/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c06c4934-45b2-4f6f-9d19-3ebd937c32ae
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3ce37fbf72f07bc3610a88096098722e8be55d6b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015717"
---
# <a name="sb-messaging-adapter"></a>Adaptador SB-Messaging
Service Bus (**SB-Messaging**) se utiliza el adaptador para recibir y enviar de entidades de Service Bus como colas, temas y retransmisiones. Puede usar el **SB-Messaging** adaptador para conectarse a sus instalaciones [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en Azure.

**A partir de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] Feature Pack 2**, se admite Premium de Service Bus. Al configurar un puerto de envío con este adaptador, puede enviar mensajes a los temas y colas con particiones. 

## <a name="authenticating-with-service-bus"></a>Autenticar con Service Bus
Service Bus ofrece dos métodos de autenticación: 

- Access Control Service (ACS) 
- Firma de acceso compartido (SAS)

Se recomienda usar la firma de acceso compartido (SAS) para autenticar con Service Bus. El valor de clave de acceso compartido aparece en la [portal Azure](https://portal.azure.com).

Cuando se crea un espacio de nombres de Service Bus, no se crea automáticamente el espacio de nombres de Access Control (ACS). Para usar el Control de acceso, necesitará los valores de nombre del emisor y clave del emisor de este espacio de nombres. Estos valores están disponibles cuando se crea un nuevo espacio de nombres de ACS mediante Windows PowerShell. Estos valores no se muestran en el portal de Azure.

Para usar ACS para la autenticación y obtener los valores de nombre del emisor y clave del emisor, los pasos generales son:

1. Instalar el [cmdlets de Powershell de Azure](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).
2. Agregue su cuenta de Azure: `Add-AzureAccount`
3. Devolver el nombre de la suscripción: `get-azuresubscription`
4. Seleccione su suscripción: `select-azuresubscription <name of your subscription>` 
5. Crear un nuevo espacio de nombres: `new-azuresbnamespace <name for the service bus> "Location" -CreateACSNamespace $true -NamespaceType Messaging`

    Ejemplo:    `new-azuresbnamespace biztalksbnamespace "South Central US" -CreateACSNamespace $true -NamespaceType Messaging`

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

Consulte [New-AzureSBNamespace](https://docs.microsoft.com/powershell/module/Azure/New-AzureSBNamespace) para obtener instrucciones.

## <a name="receive-messages-from-service-bus"></a>Recibir mensajes de Service Bus

1. En la consola de administración de BizTalk Server, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda la aplicación. 

2. Haga clic en **puertos de recepción**, seleccione **New**y seleccione **unidireccional puerto de recepción**. 

3. Asígnele un nombre y seleccione **ubicaciones de recepción**. 

4. Seleccione **New**, asígnele una **nombre**. En el **transporte** sección, seleccione **SB-Messaging** desde el **tipo** lista desplegable y, a continuación, seleccione **configurar**.  

5. Configurar la **General** propiedades:  


   |           Use            |                                                                                                                                                                                                                                                                                                                                              Para                                                                                                                                                                                                                                                                                                                                               |
   |-------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Dirección URL de cola o suscripción** |                                                                                                                                                                                                                                                               Especifique la dirección URL en la que se implementa la cola de Service Bus. Normalmente, la dirección URL tiene el siguiente formato:<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`                                                                                                                                                                                                                                                               |
   |       **Tiempo de espera de abrir**        |                                                                                                                                                                                                                                                                                 Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de apertura del canal.<br /><br /> **Valor predeterminado:** 1 minuto                                                                                                                                                                                                                                                                                 |
   |       **Tiempo de espera de cierre**       |                                                                                                                                                                                                                                                                                Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de cierre del canal.<br /><br /> **Valor predeterminado:** 1 minuto                                                                                                                                                                                                                                                                                 |
   |      **Tiempo de espera de recepción**      |                                                                                                                                                                                                                                                                                  Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de recepción.<br /><br /> **Valor predeterminado:** 10 minutos                                                                                                                                                                                                                                                                                   |
   |      **Número de capturas previas**       | Especifica el número de mensajes que se reciben de forma simultánea de la cola o de un tema de Service Bus. La captura previa permite a la cola o al cliente de la suscripción cargar mensajes adicionales desde el servicio al realizar una operación de recepción. El cliente almacena estos mensajes en una caché local. El tamaño de la caché está determinado por el valor de la propiedad de recuento de captura previa que especifique aquí.<br /><br /> Para obtener más información, consulte la sección "Captura previa" en [https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements/)<br /><br /> **Valor predeterminado:** -1 |
   |        **Usar sesión**        |                                                                                                                                                                                                                                                                                                Active esta casilla para usar una sesión de Service Bus para recibir mensajes de una cola o una suscripción.                                                                                                                                                                                                                                                                                                 |


6. Configurar la **autenticación** propiedades:  


   |                                               Use                                                |                                                                                                                                                                                             Para                                                                                                                                                                                             |
   |-------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                      **Servicio de Control de acceso**                                       | Seleccione esta opción para usar ACS para la autenticación y proporcione los valores siguientes:<br /><br /> -Escriba el URI de STS de Access Control Service de Service Bus. Normalmente, el URI tiene el siguiente formato:<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> -Escriba el nombre del emisor del espacio de nombres de Service Bus.<br /><br /> -Escriba la clave del emisor del espacio de nombres de Service Bus. |
   | **Firma de acceso compartido** (nuevo a partir de [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]) |                                                                                                                                          Seleccione esta opción para usar la autenticación con Firma de acceso compartido (SAS) y proporcione el nombre y el valor de la clave SAS.                                                                                                                                          |


7. En el **propiedades** ficha la **Namespace para propiedades de mensajes desacoplados**, escriba el espacio de nombres que utiliza el adaptador para escribir las propiedades de mensaje negociado como propiedades de contexto de mensaje en el mensaje recibido por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Si desea promocionar las propiedades de mensaje negociado, seleccione el **promocionar propiedades de mensajes desacoplados** casilla de verificación.  

8. Seleccione **Aceptar**.  

9. Seleccione su **controlador de recepción**y el **canalización de recepción**. Seleccione **Aceptar** para guardar los cambios. [Crear una ubicación de recepción](../core/how-to-create-a-receive-location.md) proporciona alguna orientación.  

## <a name="send-messages-to-service-bus"></a>Enviar mensajes a Service Bus

1. En la consola de administración de BizTalk Server, haga clic en **puertos de envío**, seleccione **New**y seleccione **puerto de envío unidireccional estático**.

   [Crear un puerto de envío](../core/how-to-create-a-send-port2.md) proporciona alguna orientación.

2. Escriba un **nombre**. En **transporte**, establezca el **tipo** a **SB-Messaging**y seleccione **configurar**. 

3. Configurar la **General** propiedades:  


   |         Use         |                                                                                                                                                                                                                                             Para                                                                                                                                                                                                                                              |
   |--------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **Dirección URL de destino**    |                                                                                                                                                               Escriba la dirección URL donde se implementa la cola de Service Bus. Normalmente, la dirección URL tiene el siguiente formato:<br /><br /> `sb://<namespace>.servicebus.windows.net/<queue_name>`                                                                                                                                                               |
   | **Intervalo de vaciado de lote** | Especifica un valor de intervalo de tiempo que indica el intervalo en el que se vacían los lotes de mensajes que se envían a una cola o tema. El valor predeterminado es 20 milisegundos.<br /><br /> Para obtener más información sobre el procesamiento por lotes con respecto a los temas y colas de Service Bus, consulte el **procesamiento por lotes del lado cliente** sección en [ https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements ](https://azure.microsoft.com/documentation/articles/service-bus-performance-improvements). |
   |     **Tiempo de espera de abrir**     |                                                                                                                                                                                Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de apertura del canal.<br /><br /> **Valor predeterminado:** 1 minuto                                                                                                                                                                                |
   |     **Tiempo de espera de envío**     |                                                                                                                                                                                    Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de envío.<br /><br /> **Valor predeterminado:** 1 minuto                                                                                                                                                                                    |
   |    **Tiempo de espera de cierre**     |                                                                                                                                                                               Especifica un valor de marco temporal que indica el tiempo para que se complete una operación de cierre del canal.<br /><br /> **Valor predeterminado:** 1 minuto                                                                                                                                                                                |


4. Configurar la **autenticación** propiedades: 


   |                                               Use                                                |                                                                                                                                                                                             Para                                                                                                                                                                                             |
   |-------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                                      **Servicio de Control de acceso**                                       | Seleccione esta opción para usar ACS para la autenticación y proporcione los valores siguientes:<br /><br /> -Escriba el URI de STS de Access Control Service de Service Bus. Normalmente, el URI tiene el siguiente formato:<br /><br /> `https://<namespace>-sb.accesscontrol.windows.net/`<br /><br /> -Escriba el nombre del emisor del espacio de nombres de Service Bus.<br /><br /> -Escriba la clave del emisor del espacio de nombres de Service Bus. |
   | **Firma de acceso compartido** (nuevo a partir de [!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]) |                                                                                                                                          Seleccione esta opción para usar la autenticación con Firma de acceso compartido (SAS) y proporcione el nombre y el valor de la clave SAS.                                                                                                                                          |


5. En el **propiedades** , escriba el **Namespace para el usuario define propiedades de mensajes desacoplados** que contiene las propiedades de contexto de mensaje de BizTalk que se desean escribir en el mensaje saliente a Bus de servicio. Todas las propiedades de espacio de nombres se escriben en el mensaje como propiedades de mensajes desacoplados definidas por el usuario. El adaptador ignora el espacio de nombres al escribir las propiedades como propiedades de mensajes desacoplados. Usa el espacio de nombres solo para confirmar qué propiedades escribir.  

    También puede especificar los valores de las propiedades BrokeredMessage. Estas propiedades se describen en [propiedades BrokeredMessage](https://docs.microsoft.com/dotnet/api/microsoft.servicebus.messaging.brokeredmessage), incluido el **clave de partición**.

6. Seleccione **Aceptar** para guardar los cambios.  

## <a name="see-also"></a>Vea también
[Uso de adaptadores](../core/using-adapters.md)