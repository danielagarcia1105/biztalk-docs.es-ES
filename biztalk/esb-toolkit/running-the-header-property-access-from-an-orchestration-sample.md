---
title: Ejecuta el acceso a la propiedad de encabezado de un ejemplo de orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2059eb2c-50a3-4618-a6ec-faa1a9e5d368
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2ddbb2ea7ef978c0e5eae07835d5a9c1320bbc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294780"
---
# <a name="running-the-header-property-access-from-an-orchestration-sample"></a>Ejecuta el acceso a la propiedad de encabezado de un ejemplo de orquestación
Esta parte del ejemplo muestra cómo ESB promociona metadatos de encabezado JMS en Propiedades de contexto de mensaje, que pueden tener acceso código y los componentes en orquestaciones en Microsoft BizTalk. El ejemplo incluye una canalización de recepción que contiene una instancia del componente ESB JMS que promociona metadatos de encabezado JMS en Propiedades de contexto de mensaje.  
  
 El puerto de recepción pasa el mensaje a una orquestación JMSRouter con nombre que recupera el nombre de cola asignado por la utilidad RfhUtil (y enviado en los metadatos de encabezado) de las propiedades de contexto del mensaje. La orquestación asigna este nombre de cola a un puerto de envío dinámico y envía el mensaje a ese puerto.  
  
 Una canalización de envío para el puerto contiene una instancia del componente ESB JMS que degrada las propiedades de contexto de mensaje en los metadatos de encabezado JMS.  
  
 **Para ejecutar el ejemplo de acceso a la propiedad de encabezado**  
  
1.  Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.  
  
2.  Ejecute la utilidad IBM RfhUtil; Seleccione el Administrador de cola denominado ESB. JMS. Sample.QueueManager en la primera lista desplegable para conectarse a este administrador de cola, como en la parte 1 de este ejemplo.  
  
3.  En la segunda lista desplegable, seleccione la cola de salida de destino denominada ESB. JMS. EJEMPLO. SENDTOBIZTALK.  
  
4.  Haga clic en el **ReadFile** situado en la utilidad RfhUtil y, a continuación, navegue hasta el archivo de mensaje de prueba denominado 000128 de prueba. JMS ubicado en la subcarpeta denominada \Source\Samples\JMS\Test\Data\Load\\. Este archivo contiene un lote de mensajes de prueba 128, pero la utilidad carga solo la primera de ellas.  
  
5.  Haga clic en el **RFH** ficha y, a continuación, asegúrese de que sólo el **JMS** casilla está activada.  
  
6.  Haga clic en el **jms** ficha y, a continuación, asegúrese de que el seleccionado **responder a** cola es ESB. JMS. EJEMPLO. RESPUESTA y que el seleccionado **cola de destino** es ESB. JMS. EJEMPLO. DYNAMICQ2.  
  
7.  Haga clic en el **Main** ficha y, a continuación, haga clic en el **escribir preguntas** botón para escribir el mensaje en la cola.  
  
8.  Después de un retraso mientras se ejecuta la aplicación, aparece el mensaje de salida ESB en ESB. JMS. EJEMPLO. Cola de DYNAMICQ2. Abra el Explorador de la cola de WebSphere y examinar las colas para confirmarlo.  
  
## <a name="how-the-sample-works"></a>Cómo funciona el ejemplo  
 Dentro de la orquestación, código puede tener acceso a los valores que se encontraban en los encabezados JMS cargando el mensaje en una **XmlDocument** instancia, tal como se muestra en el código siguiente.  
  
```csharp  
if (null != InboundMsg(  
    Microsoft.Practices.ESB.JMS.Schemas.Property.MQRFH2_NameValueData))  
{     
  jmsInfo.LoadXml(InboundMsg(  
     Microsoft.Practices.ESB.JMS.Schemas.Property.MQRFH2_NameValueData));  
  if (null != jmsInfo)  
  {  
    if (null != jmsInfo.SelectSingleNode("//Dst"))  
    {  
      xElement = jmsInfo.SelectSingleNode("//Dst");  
      destinationQueue = xElement.InnerText.ToUpper(  
                         System.Globalization.CultureInfo.CurrentCulture);  
    }  
    if (null != jmsInfo.SelectSingleNode("//Rto"))  
    {  
      xElement = jmsInfo.SelectSingleNode("//Rto");  
      replyToQueue = xElement.InnerText.ToUpper(  
                     System.Globalization.CultureInfo.CurrentCulture);  
    }  
  }  
}  
```  
  
 Además, el código puede tener acceso a todas las propiedades de contexto MQMD del mensaje.