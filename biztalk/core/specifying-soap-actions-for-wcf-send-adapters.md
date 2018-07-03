---
title: Especificar acciones SOAP para WCF adaptadores de envío | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send adapters, mapping
- send adapters, WCF services
- mapping, send adapters
- mapping, WCF send adapters
ms.assetid: fa9878eb-65b5-4ccc-b727-ff7e09ba6302
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47781b2b8add675207136248b38b0dadfe6b5610
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023498"
---
# <a name="specifying-soap-actions-for-wcf-send-adapters"></a>Especificar acciones SOAP para adaptadores de envío WCF
Puede establecer el **WCF. Acción** propiedad de contexto en el cuadro de diálogo de propiedades de transporte WCF envío adaptador o en la orquestación **expresión** formas. Si establece la **WCF. Acción** propiedad de contexto en la orquestación, debe dejar el **acción** campo en blanco en el cuadro de diálogo de propiedades WCF adaptador transporte para los puertos de envío estático. Si también especifica una acción en los puertos de envío estático, el **WCF. Acción** propiedad de contexto se establece en la orquestación que se va a reemplazar.  
  
 Además, hay dos maneras de especificar esta propiedad: el formato de acción única y el formato de asignación de acciones. Si establece esta propiedad en el formato de acción única, por ejemplo, http://MyService/IMyContract/MyAction1: cuadro de diálogo de propiedades de transporte de adaptador de envío de la acción SOAP de WCF para los mensajes salientes siempre se establece en el valor especificado en esta propiedad. Como alternativa, puede establecer el formato de acción única en la orquestación **expresión** forma. Por ejemplo,  
  
```  
OutboundMessage(WCF.Action)="http://MyService/IMyContract/MyAction1";  
```  
  
 Si establece esta propiedad en el formato de asignación de acción, la acción SOAP saliente viene determinada por la **BTS. Operación** propiedad de contexto. Por ejemplo, si esta propiedad se establece en el siguiente formato XML en WCF cuadro de diálogo de propiedades de transporte de adaptador de envío y la **BTS. Operación** propiedad está establecida en **Operation_1** en el puerto de envío en la orquestación, WCF adaptador de envío utiliza http://MyService/IMyContract/MyAction1 para la acción SOAP saliente.  
  
```  
BtsActionMapping xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
<Operation Name="Operation_1" Action="http://MyService/IMyContract/MyAction1" />  
<Operation Name="Operation_2" Action="http://MyService/IMyContract/MyAction2" />  
<Operation Name="Operation_3" Action="http://MyService/IMyContract/MyAction3" />  
</BtsActionMapping>  
```  
  
 Especificar asignación de acciones para **WCF. Acción** en un **expresión** no se admite la forma. Es necesario especificar la asignación de acciones en el cuadro de diálogo de propiedades de transporte WCF. A continuación, el adaptador de WCF buscará la acción SOAP mediante el uso de la **BTS. Operación** propiedad de contexto, lo que la orquestación establece el nombre de la operación en el puerto que se envía el mensaje.  
  
 Si los mensajes salientes se enrutan con enrutamiento por contenidos (CBR) donde el **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** no está establecida la propiedad, adaptadores de envío WCF establecerán la cadena de asignación de acción completa a la acción de los mensajes WCF salientes. Para solucionar este problema, puede realizar una de las siguientes acciones:  
  
- Establezca el campo de acción en el puerto de envío a http://MyService/IMyContract/MyAction1.  
  
- Establecer el **BTS. Operación** propiedad de contexto en una canalización. Por ejemplo, establezca el valor de **http://schemas.microsoft.com/BizTalk/2003/system-properties#Operation** como operation1.  
  
- Dejar en blanco el campo de acción y, en su lugar, usar la acción del mensaje entrante.  
  
  También puede usar el Asistente para consumición del Servicio WCF de BizTalk para consumir los servicios WCF con una única acción o con asignación de acciones. Para obtener más información, consulte [cómo usar el Asistente para consumición de servicio de BizTalk WCF para consumir un servicio WCF](../core/how-to-use-the-biztalk-wcf-service-consuming-wizard-to-consume-a-wcf-service.md).  
  
## <a name="see-also"></a>Vea también  
 [Configuración de puertos de envío dinámico mediante el uso de propiedades de contexto de adaptadores de WCF](../core/configuring-dynamic-send-ports-using-wcf-adapters-context-properties.md)