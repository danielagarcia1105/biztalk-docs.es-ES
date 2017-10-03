---
title: "Ampliar la solución para la captura y reparación de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- repairing messages, errors
- code samples, errors
- errors, code sample
- repairing messages, code sample
- ErrorCollection objects
ms.assetid: 93f463a0-ecff-4f3e-a145-7c506f42c767
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bb2f5fb1960a149c96a179ba596c67c9f402016
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="extending-the-solution-for-capture-and-message-repair"></a><span data-ttu-id="af644-102">Ampliar la solución para la captura y reparación de mensajes</span><span class="sxs-lookup"><span data-stu-id="af644-102">Extending the Solution for Capture and Message Repair</span></span>
<span data-ttu-id="af644-103">El Tutorial de extremo a extremo MT103 en esta Ayuda muestra cómo construir una orquestación de BizTalk que se suscribe a mensajes SWIFT con errores.</span><span class="sxs-lookup"><span data-stu-id="af644-103">The MT103 End-to-End Tutorial in this Help shows you how to construct a BizTalk orchestration that subscribes to failed SWIFT messages.</span></span>  
  
 <span data-ttu-id="af644-104">La orquestación en el Tutorial de extremo a extremo MT103 usa los métodos estáticos de una clase auxiliar, **ErrorExtractor**, para extraer la parte del error y el cuerpo del mensaje como cadenas.</span><span class="sxs-lookup"><span data-stu-id="af644-104">The orchestration in the MT103 End-to-End Tutorial uses the static methods of a helper class, **ErrorExtractor**, to extract the error part and body from the message as strings.</span></span> <span data-ttu-id="af644-105">La orquestación, a continuación, escribe los elementos para separar archivos.</span><span class="sxs-lookup"><span data-stu-id="af644-105">The orchestration then writes the parts to separate files.</span></span>  
  
 <span data-ttu-id="af644-106">Dado que el elemento de error del mensaje de error es una serialización de la **ErrorCollection** construido por el componente de canalización, puede deserializar la colección y utilizarlo para automatizar varios de los informes de errores y control.</span><span class="sxs-lookup"><span data-stu-id="af644-106">Because the error part of the failed message is a serialization of the **ErrorCollection** constructed by the pipeline component, you can deserialize the collection and use it to automate more of the error reporting and handling.</span></span> <span data-ttu-id="af644-107">El siguiente [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] fragmento de código muestra cómo deserializar la parte del mensaje de error de un mensaje error y recorrer en iteración los errores del análisis de la colección.</span><span class="sxs-lookup"><span data-stu-id="af644-107">The following [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] code fragment illustrates how to deserialize the error message part of a failed message and iterate over the parsing errors in the collection.</span></span> <span data-ttu-id="af644-108">El fragmento de código omite los requisitos de espacio de nombres para mejorar la legibilidad:</span><span class="sxs-lookup"><span data-stu-id="af644-108">The code fragment omits namespace qualifications for readability:</span></span>  
  
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
  
 <span data-ttu-id="af644-109">El **ErrorCollection** incluye métodos para iterar por los errores por tipo, así como para iterar por todos los errores de la colección.</span><span class="sxs-lookup"><span data-stu-id="af644-109">The **ErrorCollection** includes methods for iterating over errors by type as well as for iterating over all of the errors in the collection.</span></span> <span data-ttu-id="af644-110">Para obtener más información sobre la **ErrorCollection**, vea ErrorCollection (miembros).</span><span class="sxs-lookup"><span data-stu-id="af644-110">For more information about the **ErrorCollection**, see ErrorCollection Members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af644-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="af644-111">See Also</span></span>  
 [<span data-ttu-id="af644-112">Mensajes de error y ErrorCollection objetos</span><span class="sxs-lookup"><span data-stu-id="af644-112">Failed Messages and ErrorCollection Objects</span></span>](../../adapters-and-accelerators/accelerator-swift/failed-messages-and-errorcollection-objects.md)