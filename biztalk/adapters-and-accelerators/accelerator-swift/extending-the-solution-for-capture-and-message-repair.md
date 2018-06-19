---
title: Ampliar la solución para la captura y reparación de mensajes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- repairing messages, errors
- code samples, errors
- errors, code sample
- repairing messages, code sample
- ErrorCollection objects
ms.assetid: 93f463a0-ecff-4f3e-a145-7c506f42c767
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb2f5fb1960a149c96a179ba596c67c9f402016
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209092"
---
# <a name="extending-the-solution-for-capture-and-message-repair"></a>Ampliar la solución para la captura y reparación de mensajes
El Tutorial de extremo a extremo MT103 en esta Ayuda muestra cómo construir una orquestación de BizTalk que se suscribe a mensajes SWIFT con errores.  
  
 La orquestación en el Tutorial de extremo a extremo MT103 usa los métodos estáticos de una clase auxiliar, **ErrorExtractor**, para extraer la parte del error y el cuerpo del mensaje como cadenas. La orquestación, a continuación, escribe los elementos para separar archivos.  
  
 Dado que el elemento de error del mensaje de error es una serialización de la **ErrorCollection** construido por el componente de canalización, puede deserializar la colección y utilizarlo para automatizar varios de los informes de errores y control. El siguiente [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] fragmento de código muestra cómo deserializar la parte del mensaje de error de un mensaje error y recorrer en iteración los errores del análisis de la colección. El fragmento de código omite los requisitos de espacio de nombres para mejorar la legibilidad:  
  
```  
// instantiate an appropriate XmlTextReader  
// xm contains the message  
string sError = ErrorExtractor.GetErrorPartAsString(xm);  
StringReader sRdr = new StringReader(sError);  
XmlTextReader xRdr = new XmlTextReader(sRdr);  
  
// deserialize the collection  
ErrorCollection eC = ErrorCollection.GetErrorCollection(xRdr);  
  
// loop over the parsing errors in the collection  
IEnumerator pEnum = eC.GetParseErrorEnumerator();  
while(pEnum.MoveNext())   
{  
  // pEnum.Current() returns a ParseError object for processing  
}  
  
```  
  
 El **ErrorCollection** incluye métodos para iterar por los errores por tipo, así como para iterar por todos los errores de la colección. Para obtener más información sobre la **ErrorCollection**, vea ErrorCollection (miembros).  
  
## <a name="see-also"></a>Vea también  
 [Mensajes de error y ErrorCollection objetos](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)