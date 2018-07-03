---
title: Ampliación de la solución para la captura y reparación de mensajes | Microsoft Docs
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
ms.openlocfilehash: bc2b4436906b1df913deec8b525143773dd43e4e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979645"
---
# <a name="extending-the-solution-for-capture-and-message-repair"></a>Ampliación de la solución para la captura y reparación de mensajes
El Tutorial de extremo a otro MT103 en esta Ayuda muestra cómo construir una orquestación de BizTalk que se suscribe a mensajes SWIFT con errores.  
  
 La orquestación en el Tutorial de extremo a otro MT103 usa los métodos estáticos de una clase auxiliar, **ErrorExtractor**, para extraer la parte del error y el cuerpo del mensaje como cadenas. La orquestación, a continuación, escribe las partes para separar archivos.  
  
 Dado que la parte de error del mensaje de error es una serialización de la **ErrorCollection** construido por el componente de canalización, puede deserializar la colección y utilizarlo para automatizar varios de los informes de errores y control. El siguiente Microsoft [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] fragmento de código muestra cómo deserializar la parte de mensaje de error de un mensaje con errores y recorrer en iteración los errores del análisis de la colección. El fragmento de código omite las calificaciones del espacio de nombres de legibilidad:  
  
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
  
 El **ErrorCollection** incluye métodos para recorrer en iteración los errores por tipo, así como para recorrer en iteración todos los errores en la colección. Para obtener más información sobre la **ErrorCollection**, vea ErrorCollection miembros.  
  
## <a name="see-also"></a>Vea también  
 [Mensajes de error y objetos ErrorCollection](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)