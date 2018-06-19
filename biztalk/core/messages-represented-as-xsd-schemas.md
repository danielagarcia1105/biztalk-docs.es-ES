---
title: Mensajes representan como esquemas XSD | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Message Assignment shape [Orchestration Designer], maps
- maps, transforms
- Expression Editor, assigning maps
ms.assetid: 646e84d4-1dcc-4f92-9205-84cb6c7df297
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 47242dc01ed05ca2ab3c2cb71daffc5a81f9462c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262972"
---
# <a name="messages-represented-as-xsd-schemas"></a>Mensajes representados como esquemas XSD
Una instancia XML de plantilla del tipo de mensaje XSD se define en el momento del diseño y luego se guarda en el disco. En tiempo de ejecución, un componente .NET toma el XML del disco y lo devuelve como XmlDocument. El código de orquestación puede asignar este resultado XmlDocument a la instancia del mensaje declarado en la orquestación.  
  
 El **asignación de mensajes** forma tiene una sola línea de código:  
  
```  
MsgOut = CreateMsgHelper.Helper.GetXmlDocumentTemplate();  
```  
  
 El componente Aplicación auxiliar que crea el XmlDocument tiene un solo método estático:  
  
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
  
## <a name="see-also"></a>Vea también  
 [Mensajes representados como clases .NET](../core/messages-represented-as-net-classes.md)   
 [Mensajes representados como XLANGMessage](../core/messages-represented-as-xlangmessage.md)   
 [Construir mensajes en el código de usuario](../core/constructing-messages-in-user-code.md)