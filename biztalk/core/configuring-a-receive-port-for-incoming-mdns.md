---
title: "Configurar un puerto de recepción para MDN entrantes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d156beae-e145-48de-9f02-37457073ef97
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8585ae946e15d2677e225d42f6c123d5dd5e8e49
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="configuring-a-receive-port-for-incoming-mdns"></a>Configurar un puerto de recepción para MDN entrantes
Para recibir un MDN de AS2, cree un puerto de recepción HTTP unidireccional para recibir el mensaje y devolver una respuesta a la entidad.  
  
 Los puertos de recepción bidireccionales de solicitud-respuesta que se utilizan para recibir mensajes AS2 no deben utilizarse para recibir mensajes MDN. El empleo de un puerto de recepción de solicitud-respuesta para un MDN evitaría que un mensaje 200OK se devolviese en respuesta al MDN entrante, lo que generaría reintentos innecesarios de la transmisión MDN.  
  
 Para procesar un MDN recibido, puede utilizarse la canalización AS2Receive o la AS2EdiReceive. Sin embargo, si utiliza AS2EdiReceive, no podrá enrutar el MDN en el cuadro de mensajes estableciendo la **procesar el MDN entrante en el cuadro de mensajes para opciones de enrutado y entrega** propiedad en el **confirmaciones** página de la pestaña del acuerdo unidireccional. Al tratar de hacerlo se producirá un error de EDI, ya que el MSN se pasará al descodificador EDI, que no puede procesar un MDN. Si el MDN no se envía al cuadro de mensajes, el descodificador AS2 consumirá el MDN, de modo que no se pasará al descodificador EDI.  
  
 Cree el puerto de recepción con la siguiente configuración:  
  
|Ubicación|Propiedad|Configuración|  
|--------------|--------------|-------------|  
|**Propiedades de puerto de recepción: General**|Tipo de puerto|Unidireccional|  
|**Propiedades de la ubicación de recepción: General**|Tipo de transporte|HTTP<br /><br /> **Tenga en cuenta** sólo el adaptador HTTP puede utilizarse para transportar MDN, que son mensajes con codificación EDIINT/AS2. Este transporte no funcionará con un adaptador que no sea el adaptador de HTTP.|  
|**Propiedades de la ubicación de recepción: General**|Controlador de recepción|BizTalkServerIsolatedHost|  
|**Propiedades de la ubicación de recepción: General**|Canalización de recepción|AS2Receive o AS2EdiReceive|  
|**Propiedades de transporte HTTP**|Directorio virtual más extensión ISAPI|/\<nombre del directorio virtual de \> /BTSHTTPReceive.dll|  
  
## <a name="see-also"></a>Vea también  
 [Configuración de puertos para una solución AS2](../core/configuring-ports-for-an-as2-solution.md)