---
title: Mensajes representan como esquemas XSD | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Message Assignment shape [Orchestration Designer], maps
- maps, transforms
- Expression Editor, assigning maps
ms.assetid: 646e84d4-1dcc-4f92-9205-84cb6c7df297
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47242dc01ed05ca2ab3c2cb71daffc5a81f9462c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="messages-represented-as-xsd-schemas"></a><span data-ttu-id="ad5c4-102">Mensajes representados como esquemas XSD</span><span class="sxs-lookup"><span data-stu-id="ad5c4-102">Messages Represented as XSD Schemas</span></span>
<span data-ttu-id="ad5c4-103">Una instancia XML de plantilla del tipo de mensaje XSD se define en el momento del diseño y luego se guarda en el disco.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-103">A template XML instance of the XSD message type is defined at design time and then stored on disk.</span></span> <span data-ttu-id="ad5c4-104">En tiempo de ejecución, un componente .NET toma el XML del disco y lo devuelve como XmlDocument.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-104">At run time, a .NET component picks up the XML from disk and returns it as an XmlDocument.</span></span> <span data-ttu-id="ad5c4-105">El código de orquestación puede asignar este resultado XmlDocument a la instancia del mensaje declarado en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="ad5c4-105">The orchestration code can assign this XmlDocument result to the message instance declared in the orchestration.</span></span>  
  
 <span data-ttu-id="ad5c4-106">El **asignación de mensajes** forma tiene una sola línea de código:</span><span class="sxs-lookup"><span data-stu-id="ad5c4-106">The **Message Assignment** shape has a single line of code:</span></span>  
  
```  
MsgOut = CreateMsgHelper.Helper.GetXmlDocumentTemplate();  
```  
  
 <span data-ttu-id="ad5c4-107">El componente Aplicación auxiliar que crea el XmlDocument tiene un solo método estático:</span><span class="sxs-lookup"><span data-stu-id="ad5c4-107">The Helper Component that creates the XmlDocument has a single static method:</span></span>  
  
```  
private static XmlDocument _template = null;  
private static object _sync = new object();  
private static String LOCATION = @"C:\MyTemplateLocation\MyMsgTemplate.xml";  
  
public static XmlDocument GetXmlDocumentTemplate()  
{  
   XmlDocument doc = _template;  
   if (doc == null)  
   {  
      // Load the doc template from disk.  
      doc = new XmlDocument();  
      XmlTextReader reader = new XmlTextReader(LOCATION);  
      doc.Load(reader);  
  
      // Synchronize assignment to _template.  
      lock (_sync)  
      {  
         XmlDocument doc2 = _template;  
         if (doc2 == null)  
         {  
            _template = doc;  
         }  
         else  
         {  
            // Another thread beat us to it.  
            doc = doc2;  
         }  
      }  
   }  
  
   // Need to explicitly create a clone so that we are not  
   // referencing the same object statically held by this class.  
   doc = (XmlDocument) doc.CloneNode(true);  
   return doc;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="ad5c4-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad5c4-108">See Also</span></span>  
 <span data-ttu-id="ad5c4-109">[Mensajes representados como clases .NET](../core/messages-represented-as-net-classes.md) </span><span class="sxs-lookup"><span data-stu-id="ad5c4-109">[Messages Represented as .NET Classes](../core/messages-represented-as-net-classes.md) </span></span>  
 <span data-ttu-id="ad5c4-110">[Mensajes representados como XLANGMessage](../core/messages-represented-as-xlangmessage.md) </span><span class="sxs-lookup"><span data-stu-id="ad5c4-110">[Messages Represented as XLANGMessage](../core/messages-represented-as-xlangmessage.md) </span></span>  
 [<span data-ttu-id="ad5c4-111">Construir mensajes en el código de usuario</span><span class="sxs-lookup"><span data-stu-id="ad5c4-111">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)