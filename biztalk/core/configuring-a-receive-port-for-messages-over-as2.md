---
title: "Configurar un puerto de recepción de mensajes a través de AS2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 01d4d897-d12b-4de4-a86b-e6d2718470c2
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6f1a024769b0728873d6cf217e3028d2c5532055
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-receive-port-for-messages-over-as2"></a>Configurar un puerto de recepción para mensajes a través de AS2
Para recibir un mensaje AS2 con una carga EDI o que no sea EDI, cree un puerto de recepción HTTP para recibir el mensaje y devolver una respuesta a la entidad.  
  
 Si el MDN se va a devolver de forma sincrónica, el puerto de recepción debe ser un puerto de recepción de solicitud-respuesta bidireccional. Una ubicación de recepción en el puerto de recepción recibirá el mensaje AS2, mientras que el puerto de envío asociado con el puerto de recepción bidireccional enviará el MDN sincrónico.  
  
 Si se devuelve el MDN de forma asíncrona, el puerto de recepción puede ser un puerto de recepción unidireccional debido a que el MDN debe devolverse mediante un puerto de envío dinámico distinto. El puerto de recepción devolverá una respuesta HTTP si se trata de un puerto unidireccional o bidireccional. Si establece un puerto de recepción bidireccional para recibir un mensaje AS2, mientras se devuelve un MDN asíncrono, se devolverá la respuesta HTTP a través del puerto de envío de la ubicación de recepción bidireccional.  
  
> [!NOTE]
>  El puerto de recepción bidireccional que se va a utilizar para recibir mensajes AS2 no debe utilizarse para recibir mensajes MDN. Los mensajes MDN deben recibirse en un puerto de recepción unidireccional. Un puerto de recepción de solicitud o respuesta para un MDN evitaría que un mensaje 200OK se devolviese en repuesta al MDN entrante y, por lo tanto, se producen reintentos innecesarios de la transmisión MDN.  
  
 Cree el puerto de recepción con la siguiente configuración:  
  
|Ubicación|Propiedad|Configuración|  
|--------------|--------------|-------------|  
|**Propiedades de puerto de recepción: General**|Tipo de puerto|Solicitudes y respuestas|  
|**Propiedades de la ubicación de recepción: General**|Tipo de transporte|HTTP **Nota:** sólo el adaptador HTTP puede utilizarse para transportar mensajes con codificación EDIINT/AS2. Este transporte no funcionará con un adaptador que no sea el adaptador de HTTP.|  
|**Propiedades de la ubicación de recepción: General**|Controlador de recepción|BizTalkServerIsolatedHost|  
|**Propiedades de la ubicación de recepción: General**|Canalización de recepción|-AS2EdiReceive (si la carga es con codificación EDI)<br />-AS2Receive (si la carga no es de codificación EDI) **Nota:** cuando se utiliza la canalización AS2EdiReceive, debe agregar la cuenta de usuario que se ejecuta el proceso de instancia de Host aislado de BizTalk al grupo de usuarios de la aplicación de BizTalk. La canalización AS2EdiReceive se ejecuta en el proceso de instancia de host aislado de BizTalk. La canalización AS2EdiReceive obtiene acceso al almacén de SSO, que requiere que el usuario se encuentre en el grupo de usuarios de la aplicación [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].|  
|**Propiedades de la ubicación de recepción: General**|Canalización de envío|AS2Send|  
|**Propiedades de transporte HTTP**|Directorio virtual más extensión ISAPI|/\<nombre del directorio virtual >/BTSHTTPReceive.dll|  
|**Propiedades de transporte HTTP**|Tipo de contenido de devolución de solicitud-respuesta|text/xml|  
  
## <a name="functionality-of-the-receive-location-in-synchronous-and-asynchronous-modes"></a>Funcionalidad de la ubicación de recepción en los modos sincrónico y asíncrono  
 El puerto de recepción bidireccional realiza lo siguiente para recibir y procesar un mensaje EDI o AS2 y devolver una respuesta:  
  
-   Reciba el mensaje AS2 a través de HTTP.  
  
-   Procese el mensaje AS2 mediante la canalización de recepción AS2EDIReceive (para mensajes con codificación EDI) o la canalización de recepción AS2Receive (para mensajes que no se encuentren codificados en EDI). Para obtener más información acerca de este proceso, consulte [procesar un mensaje AS2 entrante](../core/processing-an-incoming-as2-message.md).  
  
-   Establezca las siguientes propiedades de contexto en el mensaje recibido:  
  
    -   `IsAS2PayloadMessage == True` (debido a que es un mensaje de carga)  
  
    -   `IsEmptyMDNResponse == False` (debido a que no es un MDN vacío)  
  
-   Si el mensaje es decodificación EDI, desensamble el archivo EDI, genere los archivos XML y colóquelos en el cuadro de mensajes. Establezca la propiedad de contexto de `BTS.MessageType` para cada archivo XML en el nombre de esquema con un espacio de nombres.  
  
-   Si el mensaje no es de codificación EDI, coloque el mensaje en su formato original en el cuadro de mensajes.  
  
-   Genere el archivo MDN, si está habilitado, mediante la canalización de recepción AS2EdiReceive. Para obtener más información acerca de este proceso, consulte [generar un MDN saliente](../core/generating-an-outgoing-mdn.md). Establezca las siguientes propiedades de contexto en el mensaje:  
  
    -   `EdiIntAS.IsAS2AsynchronousMdn == False` (si está en modo sincrónico)  
  
    -   `EdiIntAS.IsAS2AsynchronousMdn== True` (si está en modo asincrónico)  
  
-   Si se encuentra en el modo sincrónico, envíe el archivo MDN, si está habilitado, mediante la canalización de envío AS2Send. Para obtener más información acerca de este proceso, consulte [enviar un MDN saliente](../core/sending-an-outgoing-mdn.md).  
  
-   Si se encuentra en el modo asíncrono, enrute el archivo MDN, si está habilitado, en el cuadro de mensajes (para un puerto de envío dinámico distinto para recogerlo y enviarlo).  
  
-   Si se encuentra en un modo asíncrono, genere un MDN vacío junto con el MDN completo que éste devuelve de forma asíncrona. Establezca las siguientes propiedades de contexto en el mensaje:  
  
    -   `IsAS2PayloadMessage == False`  
  
    -   `IsEmptyMDNResponse == True`  
  
-   Si se encuentra en modo asíncrono, devuelva la respuesta HTTP al remitente original a través de la conexión HTTP entre el puerto de recepción y la entidad remitente, que cierra la conexión. Esto es necesario ya que el MDN completo no cierra la conexión sincrónica.  
  
-   Genere un mensaje de confirmación, si está habilitado, y colóquelo en el cuadro de mensajes. Establezca la propiedad de contexto de `BTS.MessageType` en el esquema de control de confirmación.  
  
## <a name="see-also"></a>Vea también  
 [Configurar puertos para una solución AS2](../core/configuring-ports-for-an-as2-solution.md)   
 [Procesar un mensaje AS2 entrante](../core/processing-an-incoming-as2-message.md)   
 [Generar un MDN saliente](../core/generating-an-outgoing-mdn.md)   
 [Enviar un MDN saliente](../core/sending-an-outgoing-mdn.md)