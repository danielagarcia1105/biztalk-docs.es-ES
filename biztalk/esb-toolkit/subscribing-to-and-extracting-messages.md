---
title: Suscribirse a y extraer mensajes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4e7fbc17-44d6-4cc5-a266-b54256e7b453
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22d5a7f6065e8040e390947d44510bb7414e8e10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="subscribing-to-and-extracting-messages"></a>Suscribirse a y extraer los mensajes
Orquestación puede contener código para suscribirse a y extraer los mensajes de un mensaje de error ESB. Por ejemplo, el siguiente código utiliza el **GetMessage** y **GetException** métodos para extraer dos fuertemente tipados mensajes y la **System.Exception** objeto desde un ESB mensaje de error.  
  
```csharp  
// Retrieve two messages from the fault message.  
requestMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetMessage(  
                                    faultMsg, "ApprovedRequest");  
deniedMsg = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetMessage(  
                                    faultMsg, "DeniedRequest");  
  
// Retrieve the System.Exception object.  
newExc = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetException(  
                                    faultMsg);  
```  
  
 Para extraer mensajes sin tipo, el código siguiente usa el **GetMessages** método para extraer todos los mensajes y, a continuación, recorrer en iteración.  
  
```csharp  
Microsoft.Practices.ESB.ExceptionHandling.MessageCollection msgs;  
msgs = Microsoft.Practices.ESB.ExceptionHandling.ExceptionMgmt.GetMessages(faultMsg);  
System.Xml.XmlDocument tmpMsg;  
while (msgs.MoveNext())  
{  
  tmpMsg = msgs.Current;  
}  
```