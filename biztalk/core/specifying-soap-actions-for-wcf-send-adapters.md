---
title: "Especificar acciones SOAP para WCF adaptadores de envío | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send adapters, mapping
- send adapters, WCF services
- mapping, send adapters
- mapping, WCF send adapters
ms.assetid: fa9878eb-65b5-4ccc-b727-ff7e09ba6302
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 385e92f7801dc2512fbd038bd0b005d95c503e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="specifying-soap-actions-for-wcf-send-adapters"></a>Especificar acciones SOAP para adaptadores de envío WCF
Puede establecer el **WCF. Acción** propiedad de contexto en el cuadro de diálogo de propiedades de transporte WCF envío adaptador o en la orquestación **expresión** formas. Si establece la **WCF. Acción** propiedad de contexto en la orquestación, debe dejar el **acción** campo en blanco en el cuadro de diálogo de propiedades WCF adaptador transporte para los puertos de envío estático. Si también especifica una acción en los puertos de envío estáticos, el **WCF. Acción** se invalidará la propiedad de contexto se establece en la orquestación.  
  
 Además, hay dos maneras de especificar esta propiedad: el formato de acción única y el formato de asignación de acciones. Si establece esta propiedad en el formato de acción única: por ejemplo, http://MyService/IMyContract/MyAction1: cuadro de diálogo de propiedades de transporte de adaptador de envío de la acción de SOAP de WCF para los mensajes salientes siempre se establece en el valor especificado en esta propiedad. Como alternativa, puede establecer el formato de acción única en la orquestación **expresión** forma. Por ejemplo,  
  
```  
OutboundMessage(WCF.Action)="http://MyService/IMyContract/MyAction1";  
```  
  
 Si establece esta propiedad en el formato de asignación de acciones, la acción de SOAP saliente viene determinada por la **BTS. Operación** propiedad de contexto. Por ejemplo, si esta propiedad se establece en el siguiente formato XML en WCF cuadro de diálogo de propiedades de transporte de adaptador de envío y la **BTS. Operación** propiedad está establecida en **Operation_1** en el puerto de envío en la orquestación, el adaptador de envío WCF usa http://MyService/IMyContract/MyAction1 para la acción SOAP saliente.  
  
```  
BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<Operation Name="Operation_1" Action="http://MyService/IMyContract/MyAction1" />  
<Operation Name="Operation_2" Action="http://MyService/IMyContract/MyAction2" />  
<Operation Name="Operation_3" Action="http://MyService/IMyContract/MyAction3" />  
</BtsActionMapping>  
```  
  
 Especificar asignación de acción de **WCF. Acción** en un **expresión** no se admite la forma. Es necesario especificar la asignación de acciones en el cuadro de diálogo de propiedades de transporte WCF. A continuación, el adaptador de WCF buscará la acción SOAP mediante el uso de la **BTS. Operación** propiedad de contexto, que la orquestación establece el nombre de la operación en el puerto que se envía el mensaje.  
  
 Si los mensajes salientes se enrutan con enrutamiento por contenidos (CBR) donde el **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** propiedad no está establecida, adaptadores de envío WCF establecerá la asignación de acción completa cadena a la acción de los mensajes salientes de WCF. Para resolver este problema, siga uno de los siguientes:  
  
-   Establecer el campo de acción en el puerto de envío como http://MyService/IMyContract/MyAction1.  
  
-   Establecer el **BTS. Operación** propiedad de contexto en una canalización. Por ejemplo, establezca el valor de **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** como Operation1.  
  
-   Dejar en blanco el campo de acción y, en su lugar, usar la acción del mensaje entrante.  
  
 También puede usar el Asistente para consumición del Servicio WCF de BizTalk para consumir los servicios WCF con una única acción o con asignación de acciones. Para obtener más información, consulte [cómo utilizar el Asistente de consumición de servicio WCF de BizTalk para consumir un servicio WCF](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md).  
  
## <a name="see-also"></a>Vea también  
 [Configuración de puertos de envío dinámicos mediante propiedades de contexto de adaptadores de WCF](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)