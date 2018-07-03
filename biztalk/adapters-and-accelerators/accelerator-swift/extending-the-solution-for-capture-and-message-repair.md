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
# <a name="extending-the-solution-for-capture-and-message-repair"></a><span data-ttu-id="13285-102">Ampliación de la solución para la captura y reparación de mensajes</span><span class="sxs-lookup"><span data-stu-id="13285-102">Extending the Solution for Capture and Message Repair</span></span>
<span data-ttu-id="13285-103">El Tutorial de extremo a otro MT103 en esta Ayuda muestra cómo construir una orquestación de BizTalk que se suscribe a mensajes SWIFT con errores.</span><span class="sxs-lookup"><span data-stu-id="13285-103">The MT103 End-to-End Tutorial in this Help shows you how to construct a BizTalk orchestration that subscribes to failed SWIFT messages.</span></span>  
  
 <span data-ttu-id="13285-104">La orquestación en el Tutorial de extremo a otro MT103 usa los métodos estáticos de una clase auxiliar, **ErrorExtractor**, para extraer la parte del error y el cuerpo del mensaje como cadenas.</span><span class="sxs-lookup"><span data-stu-id="13285-104">The orchestration in the MT103 End-to-End Tutorial uses the static methods of a helper class, **ErrorExtractor**, to extract the error part and body from the message as strings.</span></span> <span data-ttu-id="13285-105">La orquestación, a continuación, escribe las partes para separar archivos.</span><span class="sxs-lookup"><span data-stu-id="13285-105">The orchestration then writes the parts to separate files.</span></span>  
  
 <span data-ttu-id="13285-106">Dado que la parte de error del mensaje de error es una serialización de la **ErrorCollection** construido por el componente de canalización, puede deserializar la colección y utilizarlo para automatizar varios de los informes de errores y control.</span><span class="sxs-lookup"><span data-stu-id="13285-106">Because the error part of the failed message is a serialization of the **ErrorCollection** constructed by the pipeline component, you can deserialize the collection and use it to automate more of the error reporting and handling.</span></span> <span data-ttu-id="13285-107">El siguiente Microsoft [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] fragmento de código muestra cómo deserializar la parte de mensaje de error de un mensaje con errores y recorrer en iteración los errores del análisis de la colección.</span><span class="sxs-lookup"><span data-stu-id="13285-107">The following Microsoft [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] code fragment illustrates how to deserialize the error message part of a failed message and iterate over the parsing errors in the collection.</span></span> <span data-ttu-id="13285-108">El fragmento de código omite las calificaciones del espacio de nombres de legibilidad:</span><span class="sxs-lookup"><span data-stu-id="13285-108">The code fragment omits namespace qualifications for readability:</span></span>  
  
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
  
 <span data-ttu-id="13285-109">El **ErrorCollection** incluye métodos para recorrer en iteración los errores por tipo, así como para recorrer en iteración todos los errores en la colección.</span><span class="sxs-lookup"><span data-stu-id="13285-109">The **ErrorCollection** includes methods for iterating over errors by type as well as for iterating over all of the errors in the collection.</span></span> <span data-ttu-id="13285-110">Para obtener más información sobre la **ErrorCollection**, vea ErrorCollection miembros.</span><span class="sxs-lookup"><span data-stu-id="13285-110">For more information about the **ErrorCollection**, see ErrorCollection Members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13285-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="13285-111">See Also</span></span>  
 [<span data-ttu-id="13285-112">Mensajes de error y objetos ErrorCollection</span><span class="sxs-lookup"><span data-stu-id="13285-112">Failed Messages and ErrorCollection Objects</span></span>](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)