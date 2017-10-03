---
title: "Cómo puertos de enlace directo de uso MessageBox | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1839184b-408e-4ac6-94a4-a0eb708183f6
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82fbe52d46847bdaa7caffbb4402ce8d380a73f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-messagebox-direct-bound-ports"></a>Cómo usar puertos de enlace directo de cuadro de mensajes
Los puertos de enlace directo de cuadro de mensajes permiten entregar mensajes directamente en la base de datos de cuadro de mensajes sin que exista un destinatario explícito, así como suscribirse a los mensajes que cumplan determinados criterios, en lugar de a los que procedan de un remitente concreto.  
  
 Envía un mensaje en un cuadro de mensajes el puerto de enlace directo es equivalente a publicar el mensaje en un bus de mensajes: en este caso, para la base de datos de cuadro de mensajes. Puede haber cualquier número de suscriptores para cualquier mensaje publicado. Además, si no hay suscriptores interesados en el mensaje en el momento de publicarlo, se produce una excepción de suscripción no encontrada. Si envía un mensaje a través de un puerto de enlace directo de cuadro de mensajes con un destinatario concreto, puede que desee establecer propiedades en determinados valores en el **asignación de mensajes** forma para el suscriptor específico buscar. Puede establecer las propiedades de acuerdo con las definiciones de propiedades predefinidas de BizTalk Server o con sus propias definiciones de propiedades. Por ejemplo:  
  
```  
myMessage(PropertyNamespace.PropertyName) = "My Property")  
```  
  
 Recibir un mensaje a través de un puerto de enlace directo de cuadro de mensajes equivale a suscribirse a un bus de mensajes con criterios de filtro. Los destinatarios del mensaje pueden ser cualquier tipo de servicio capaz de suscribirse a mensajes, lo que incluye las orquestaciones y los puertos de envío. Para una activación **recepción** forma la suscripción es el tipo de mensaje y la expresión de filtro y para no activar **recepción** forma la suscripción es el tipo de mensaje y la correlación establecido. Cada **recepción** forma siempre incluye el tipo de mensaje como parte de su suscripción.  
  
> [!NOTE]
>  Debe usar una expresión de filtro si tiene una activación **recepción** forma recibir un mensaje de tipo **System.Xml.XmlDocument** o **Microsoft.XLANGs.BaseTypes.Any** en un puerto de enlace directo con el enrutamiento definido por la suscripción.  
  
 Si no se especificó ningún criterio de filtro en la activación **recepción** forma conectada a un puerto de enlace directo de cuadro de mensajes, a continuación, la suscripción tendrá un aspecto similar al siguiente:  
  
```  
http://schemas.microsoft.com/BizTalk/2003/system-properties.ReceivePortID == {2F6A80E1-2518-4A69-9C28-401C2DB1CBF6} And  
http://schemas.microsoft.com/BizTalk/2003/system-properties.MessageType == http://MyMessageType  
```  
  
 En el ejemplo anterior, el puerto de recepción de enlace directo de cuadro de mensajes recibirá todos los mensajes que coincidan con el tipo de mensaje para el que se ha configurado la operación del puerto.  
  
> [!NOTE]
>  Cuando se usan puertos de recepción de enlace directo de cuadro de mensajes, los filtros deben ser lo más específicos que sea posible. Si el filtro no es lo bastante específico, la orquestación podría recibir mensajes no deseados.  
  
 Para configurar un puerto de enlace directo de cuadro de mensajes, seleccione **enrutamiento entre puertos lo definirán expresiones de filtro en los mensajes entrantes en la base de datos de cuadro de mensaje** en el Asistente para configuración de puertos.  
  
 Para obtener un ejemplo de cómo usar puertos de enlace directo de cuadro de mensajes, consulte el ejemplo SDK "Direct enlace a the MessageBox Database in Orchestrations" en [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).  
  
## <a name="see-also"></a>Vea también  
 [Puertos de enlace de uso directo de autocorrelación](../core/how-to-use-self-correlating-direct-bound-ports.md)   
 [Cómo utilizar la orquestación de socio directo puertos de enlace](../core/how-to-use-partner-orchestration-direct-bound-ports.md)