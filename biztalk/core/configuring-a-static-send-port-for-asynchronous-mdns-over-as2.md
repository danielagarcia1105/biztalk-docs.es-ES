---
title: "Configurar un puerto de envío estático para MDN asíncronos a través de AS2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cc43e767-d9d7-4b02-b3fc-0cfdfd6e61c4
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ccae5741ada6db57538289911a97e2ad3d9dfce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-static-send-port-for-asynchronous-mdns-over-as2"></a>Configuración de un puerto de envío estático para MDN asíncronos a través de AS2
Este tema describe cómo configurar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para que envíe un mensaje MDN codificado en EDIINT/AS2 mediante un puerto de envío estático. Esta configuración incluye la creación del puerto de envío estático y, si es necesario, la configuración de un certificado de cifrado que el puerto de envío vaya a usar.  
  
> [!NOTE]
>  En lugar de un puerto de envío estático, puede configurar un puerto de envío dinámico para enviar mensajes MDN. Para obtener más información, consulte [configurar un puerto de envío dinámico para MDN asíncronos a través de AS2](../core/configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2.md).  
  
 Para enviar un mensaje MDN, cree un puerto de envío HTTP unidireccional con la configuración siguiente:  
  
|Ubicación|Propiedad|Configuración|  
|--------------|--------------|-------------|  
|**Propiedades de puerto de envío: General**|Tipo de puerto|Puerto de envío unidireccional estático|  
|**Propiedades de puerto de envío: General**|Tipo de transporte|HTTP **Nota:** sólo el adaptador HTTP puede utilizarse para transportar mensajes con codificación EDIINT/AS2. Este transporte no funcionará con un adaptador que no sea el adaptador de HTTP.|  
|**Propiedades de puerto de envío: General**|Controlador de envío|BizTalkServerApplication|  
|**Propiedades de puerto de envío: General**|Canalización de envío|AS2Send|  
|**Propiedades de transporte HTTP**|Dirección URL de destino|\<Cadena de dirección URL de destino >|  
|**Propiedades de transporte HTTP**|Habilitar codificación fragmentada|Desactivado|  
|**Propiedades de puerto de envío: filtros**|Propiedad|EdiIntAS.IsAS2AsynchronousMdn **Nota:** también debe especificar expresiones de filtro adicional para asegurarse de que sólo los mensajes MDN destinados a la dirección especificada en este puerto de envío recoge este filtro de suscripción.|  
|**Propiedades de puerto de envío: filtros**|Operador|==|  
|**Propiedades de puerto de envío: filtros**|Valor|True|  
|**Propiedades de puerto de envío: certificados**|Nombre común y huella digital|Escriba el nombre de certificado y la huella digital si usa un certificado de cifrado para el mensaje MDN saliente.|  
  
 Un MDN asíncrono se enviarán a la dirección especificada en el **Receipt-Delivery-Option** encabezado del mensaje AS2 recibido. Un puerto de envío dinámico lo hará automáticamente, mientras que un puerto de envío estático enviará el mensaje a la **dirección URL de destino** en las propiedades de puerto de envío. Al enviar un MDN asincrónico con un puerto de envío estático, asegúrese de que la URL a la que envía sea correcta.  
  
## <a name="functionality"></a>Funcionalidad  
 El puerto de envío y la canalización deben realizar lo siguiente para enviar un MDN:  
  
-   Capture el MDN filtrando la propiedad `EdiIntAS.IsAS2AsynchronousMdn==True`.  
  
-   Genere un mensaje AS2. Para obtener más información acerca de este proceso, consulte [generar un mensaje AS2 saliente](../core/generating-an-outgoing-as2-message.md).  
  
-   Enrute el MDN a la dirección definida en el puerto de envío.  
  
## <a name="see-also"></a>Vea también  
 [Configurar puertos para una solución AS2](../core/configuring-ports-for-an-as2-solution.md)