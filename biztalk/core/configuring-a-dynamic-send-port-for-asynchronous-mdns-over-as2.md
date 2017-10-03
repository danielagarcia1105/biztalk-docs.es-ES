---
title: "Configurar un puerto de envío dinámico para MDN asíncronos a través de AS2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 72646c90-89db-4884-824b-6921bb824f8d
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 754917ed1a089e3182c8543e8a132a9eff73615e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-dynamic-send-port-for-asynchronous-mdns-over-as2"></a>Configurar un puerto de envío dinámico para MDN asíncronos a través de AS2
Para enviar un mensaje MDN codificado con EDIINT/AS2 asíncrono a través de HTTP/HTTPS, cree un puerto de envío HTTP dinámico con la siguiente configuración:  
  
|Ubicación|Propiedad|Configuración|  
|--------------|--------------|-------------|  
|**Propiedades de puerto de envío: General**|Tipo de puerto|Unidireccional dinámico|  
|**Propiedades de puerto de envío: General**|Canalización de envío|AS2Send|  
|**Propiedades de puerto de envío: filtros**|Propiedad|EdiIntAS.IsAS2AsynchronousMdn|  
|**Propiedades de puerto de envío: filtros**|Operador|==|  
|**Propiedades de puerto de envío: filtros**|Valor|True|  
  
 Un MDN asíncrono se enviarán a la dirección contenida en el **Receipt-Delivery-Option** encabezado del mensaje AS2 recibido. Un puerto de envío dinámico lo hará, mientras que un puerto de envío estático enviará el mensaje a la **dirección URL de destino** en la definición de puerto de envío. La excepción a esto es si la **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad se establece en **validación** página de la ficha de acuerdo unidireccional el **acuerdo Propiedades** cuadro de diálogo. En ese caso, el puerto de envío enviará el mensaje MDN a la URL especificada en el **Receipt-Delivery-Option** propiedad del acuerdo. Sin embargo, el puerto de envío usado para ello debe ser un puerto de envío dinámico, no un puerto de envío estático.  
  
 Puede configurar este puerto de envío para devolver los MDN y las confirmaciones EDI. Por ejemplo, si se transporta un mensaje con codificación AS2/EDIINT a través de HTTP/HTTPS correctamente, pero se produce un error en el procesamiento de la carga con codificación EDI, el remitente del mensaje original recibirá un MDN que indica un procesamiento AS2 correcto y una confirmación EDI que indica un error en el procesamiento de EDI. Se suspenderá la carga con codificación EDI y expone un error.  
  
## <a name="functionality"></a>Funcionalidad  
 El puerto de envío y la canalización deben realizar lo siguiente para enviar un MDN:  
  
-   Capture el MDN filtrando la propiedad `EdiIntAS.IsAS2AsynchronousMdn==True`.  
  
-   Genere un mensaje AS2. Para obtener más información acerca de este proceso, consulte [generar un mensaje AS2 saliente](../core/generating-an-outgoing-as2-message.md).  
  
-   Enrute el MDN a la dirección en la **Receipt-Delivery-Option** línea en el encabezado del mensaje.  
  
    > [!NOTE]
    >  Si el **usar la configuración de acuerdo para validación y MDN en lugar del encabezado de mensaje** propiedad se establece en **validación** página de la ficha de acuerdo unidireccional el **propiedades del acuerdo de**cuadro de diálogo, el puerto de envío enviará el mensaje MDN a la URL especificada en el **Receipt-Delivery-Option** propiedad del acuerdo, no a la dirección mencionada en **Receipt-Delivery-Option**encabezado del mensaje AS2 recibido.  
  
## <a name="see-also"></a>Vea también  
 [Configurar puertos para una solución AS2](../core/configuring-ports-for-an-as2-solution.md)