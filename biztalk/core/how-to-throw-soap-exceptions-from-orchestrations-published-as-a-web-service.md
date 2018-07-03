---
title: Cómo iniciar excepciones SOAP desde orquestaciones publicado como un servicio Web | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, SOAP exceptions
- orchestrations, SOAP errors
- Web services, orchestrations
ms.assetid: e1c7cd74-d1c8-4b9d-a418-4601b1f040d7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 328f468485f729df03c28bca48a8b5ed4eaf59e5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015205"
---
# <a name="how-to-throw-soap-exceptions-from-orchestrations-published-as-a-web-service"></a><span data-ttu-id="9c5f7-102">Cómo iniciar excepciones SOAP desde orquestaciones publicadas como un servicio Web</span><span class="sxs-lookup"><span data-stu-id="9c5f7-102">How to Throw SOAP Exceptions from Orchestrations Published as a Web Service</span></span>
<span data-ttu-id="9c5f7-103">Puede devolver una excepción SOAP desde una orquestación que haya publicado como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="9c5f7-103">You can return a SOAP exception from an orchestration that you have published as a Web service.</span></span> <span data-ttu-id="9c5f7-104">Además, puede agregar un mensaje de error al puerto SOAP y enviarlo en lugar de la respuesta.</span><span class="sxs-lookup"><span data-stu-id="9c5f7-104">You add a fault message to your SOAP port and send the fault message instead of the response.</span></span>  
  
### <a name="to-throw-a-soap-exception-from-an-orchestration-published-as-a-web-service"></a><span data-ttu-id="9c5f7-105">Para iniciar una excepción SOAP desde una orquestación publicada como un servicio Web</span><span class="sxs-lookup"><span data-stu-id="9c5f7-105">To throw a SOAP exception from an orchestration published as a Web service</span></span>  
  
1. <span data-ttu-id="9c5f7-106">Agregar un mensaje de error al tipo de puerto SOAP.</span><span class="sxs-lookup"><span data-stu-id="9c5f7-106">Add a fault message to the SOAP port type.</span></span> <span data-ttu-id="9c5f7-107">El tipo de este mensaje puede ser cualquier esquema compatible con esquema XML (XSD) o un tipo simple.</span><span class="sxs-lookup"><span data-stu-id="9c5f7-107">The message type for the fault message can be any XML Schema (XSD) compliant schema or simple type.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="9c5f7-108">Para devolver una cadena como un **SoapException** con información de error, puede usar la cadena de tipo simple como el tipo de mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="9c5f7-108">To return a string as a **SoapException** with error information, you can use the simple type string as the fault message type.</span></span>  
  
2. <span data-ttu-id="9c5f7-109">En la orquestación, crear el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="9c5f7-109">In your orchestration, create the fault message.</span></span>  
  
3. <span data-ttu-id="9c5f7-110">Use la **enviar** forma para vincular a la operación errónea en el puerto SOAP que se corresponde con el mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="9c5f7-110">Use the **Send** shape to link to the fault operation in the SOAP port that corresponds to the fault message.</span></span> <span data-ttu-id="9c5f7-111">Una excepción SOAP ajusta el mensaje de error devuelto.</span><span class="sxs-lookup"><span data-stu-id="9c5f7-111">A SOAP exception wraps the returned fault message.</span></span>  
  
   <span data-ttu-id="9c5f7-112">Si la orquestación no devuelve un error, use otro **enviar** forma para enviar el mensaje de respuesta SOAP estándar mediante la operación de respuesta habitual.</span><span class="sxs-lookup"><span data-stu-id="9c5f7-112">If your orchestration does not return an error, use a different **Send** shape to send the standard SOAP response message using the usual response operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c5f7-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c5f7-113">See Also</span></span>  
 <span data-ttu-id="9c5f7-114">[Mensajes de error](../core/fault-messages.md) </span><span class="sxs-lookup"><span data-stu-id="9c5f7-114">[Fault Messages](../core/fault-messages.md) </span></span>  
 [<span data-ttu-id="9c5f7-115">Publicación de una orquestación como un servicio web</span><span class="sxs-lookup"><span data-stu-id="9c5f7-115">Publishing an Orchestration as a Web Service</span></span>](../core/publishing-an-orchestration-as-a-web-service.md)