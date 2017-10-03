---
title: "Cómo iniciar excepciones SOAP desde orquestaciones publicado como un servicio Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, SOAP exceptions
- orchestrations, SOAP errors
- Web services, orchestrations
ms.assetid: e1c7cd74-d1c8-4b9d-a418-4601b1f040d7
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4ef3d975632b6230cf1e3df299d0d9455f39da0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service"></a><span data-ttu-id="ec42a-102">Cómo iniciar excepciones SOAP desde orquestaciones publicadas como un servicio Web</span><span class="sxs-lookup"><span data-stu-id="ec42a-102">How to Throw SOAP Exceptions from Orchestrations Published as a Web Service</span></span>
<span data-ttu-id="ec42a-103">Puede devolver una excepción SOAP desde una orquestación que haya publicado como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="ec42a-103">You can return a SOAP exception from an orchestration that you have published as a Web service.</span></span> <span data-ttu-id="ec42a-104">Además, puede agregar un mensaje de error al puerto SOAP y enviarlo en lugar de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="ec42a-104">You add a fault message to your SOAP port and send the fault message instead of the response.</span></span>  
  
### <a name="to-throw-a-soap-exception-from-an-orchestration-published-as-a-web-service"></a><span data-ttu-id="ec42a-105">Para iniciar una excepción SOAP desde una orquestación publicada como un servicio Web</span><span class="sxs-lookup"><span data-stu-id="ec42a-105">To throw a SOAP exception from an orchestration published as a Web service</span></span>  
  
1.  <span data-ttu-id="ec42a-106">Agregar un mensaje de error al tipo de puerto SOAP.</span><span class="sxs-lookup"><span data-stu-id="ec42a-106">Add a fault message to the SOAP port type.</span></span> <span data-ttu-id="ec42a-107">El tipo de este mensaje puede ser cualquier esquema compatible con esquema XML (XSD) o un tipo simple.</span><span class="sxs-lookup"><span data-stu-id="ec42a-107">The message type for the fault message can be any XML Schema (XSD) compliant schema or simple type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ec42a-108">Para devolver una cadena como un **SoapException** con información de error, puede utilizar la cadena de tipo simple como el tipo de mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ec42a-108">To return a string as a **SoapException** with error information, you can use the simple type string as the fault message type.</span></span>  
  
2.  <span data-ttu-id="ec42a-109">En la orquestación, crear el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ec42a-109">In your orchestration, create the fault message.</span></span>  
  
3.  <span data-ttu-id="ec42a-110">Use la **enviar** forma que se va a vincular a la operación del error en el puerto SOAP que se corresponde con el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="ec42a-110">Use the **Send** shape to link to the fault operation in the SOAP port that corresponds to the fault message.</span></span> <span data-ttu-id="ec42a-111">Una excepción SOAP ajusta el mensaje de error devuelto.</span><span class="sxs-lookup"><span data-stu-id="ec42a-111">A SOAP exception wraps the returned fault message.</span></span>  
  
 <span data-ttu-id="ec42a-112">Si la orquestación no devuelve un error, utilice otro **enviar** forma para enviar el mensaje de respuesta SOAP estándar mediante la operación de respuesta habitual.</span><span class="sxs-lookup"><span data-stu-id="ec42a-112">If your orchestration does not return an error, use a different **Send** shape to send the standard SOAP response message using the usual response operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec42a-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec42a-113">See Also</span></span>  
 <span data-ttu-id="ec42a-114">[Mensajes de error](../core/fault-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ec42a-114">[Fault Messages](../core/fault-messages.md) </span></span>  
 [<span data-ttu-id="ec42a-115">Publicar una orquestación como servicio Web</span><span class="sxs-lookup"><span data-stu-id="ec42a-115">Publishing an Orchestration as a Web Service</span></span>](../core/publishing-an-orchestration-as-a-web-service.md)