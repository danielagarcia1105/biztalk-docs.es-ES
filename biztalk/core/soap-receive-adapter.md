---
title: Adaptador de recepción SOAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP adapters, receive adapters
- receive adapters, SOAP adapters
ms.assetid: bb968fa8-0515-4f3a-bb39-9effb83e960c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06fac19580d6083ed1b0d4be315d3285acf14fcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278396"
---
# <a name="soap-receive-adapter"></a><span data-ttu-id="5c1d2-102">Adaptador de recepción SOAP</span><span class="sxs-lookup"><span data-stu-id="5c1d2-102">SOAP Receive Adapter</span></span>
<span data-ttu-id="5c1d2-103">El adaptador de recepción SOAP se utiliza para recibir solicitudes de servicios Web.</span><span class="sxs-lookup"><span data-stu-id="5c1d2-103">You use the SOAP receive adapter to receive Web service requests.</span></span> <span data-ttu-id="5c1d2-104">El adaptador de recepción SOAP crea un objeto de mensaje de BizTalk y promociona las propiedades asociadas al contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5c1d2-104">The SOAP receive adapter creates a BizTalk Message object, and promotes the associated properties to the message context.</span></span>  
  
 <span data-ttu-id="5c1d2-105">Una recepción de SOAP adaptador URI debe correlacionarse con una o varias orquestaciones de BizTalk o esquemas que se han publicado como un servicio web con el **Asistente para publicación de BizTalk Web Services**.</span><span class="sxs-lookup"><span data-stu-id="5c1d2-105">A SOAP receive adapter URI must correlate to one or more BizTalk orchestrations or schemas that have been published as a web service with the **BizTalk Web Services Publishing Wizard**.</span></span> <span data-ttu-id="5c1d2-106">El servicio Web publicado expone uno o más métodos web que se correlacionan con uno o varios esquemas u orquestaciones de BizTalk Server en un ensamblado de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="5c1d2-106">The published web service exposes one or more web methods which correlate to one or more BizTalk Server orchestrations or schemas in a BizTalk assembly.</span></span> <span data-ttu-id="5c1d2-107">En esencia, el servicio Web publicado actúa como proxy del servidor para los esquemas o las orquestaciones de BizTalk y reenvía solicitudes y respuestas entre el cliente y éstos.</span><span class="sxs-lookup"><span data-stu-id="5c1d2-107">In effect, the published web service acts as a server proxy for the BizTalk orchestration(s) or schema(s) and forwards requests and responses between the client and the BizTalk orchestration(s) or schema(s).</span></span> <span data-ttu-id="5c1d2-108">Para obtener más información acerca de cómo publicar orquestaciones de BizTalk o esquemas como servicios web, consulte [publicar servicios Web](../core/publishing-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="5c1d2-108">For more information about publishing BizTalk orchestrations or schemas as web services see [Publishing Web Services](../core/publishing-web-services.md).</span></span>  
  
 <span data-ttu-id="5c1d2-109">Una ubicación de recepción que usa el adaptador de SOAP se puede configurar como unidireccional o como solicitud-respuesta (bidireccional).</span><span class="sxs-lookup"><span data-stu-id="5c1d2-109">A receive location that uses the SOAP adapter can be configured as one-way or request response (two way).</span></span> <span data-ttu-id="5c1d2-110">Cuando una ubicación de recepción unidireccional se configura para usar el adaptador de SOAP, el servicio Web asociado invoca el ensamblado enlazado al puerto de recepción y devuelve el estado de la solicitud al cliente.</span><span class="sxs-lookup"><span data-stu-id="5c1d2-110">When a one-way receive location is configured to use the SOAP adapter, the associated web service invokes the BizTalk assembly bound to the receive port, and returns the status of the request to the client.</span></span> <span data-ttu-id="5c1d2-111">Cuando una ubicación de recepción de solicitud-respuesta (bidireccional) se configura para usar el adaptador de SOAP, el servicio Web asociado invoca el ensamblado enlazado al puerto de recepción y devuelve un documento de respuesta al cliente.</span><span class="sxs-lookup"><span data-stu-id="5c1d2-111">When a request response (two way) receive location is configured to use the SOAP Adapter, the associated web service invokes the BizTalk assembly bound to the receive port, and returns a response document to the client.</span></span> <span data-ttu-id="5c1d2-112">Para obtener más información acerca de la mensajería de solicitud-respuesta vea [mensajería de solicitud-respuesta](../core/request-response-messaging.md).</span><span class="sxs-lookup"><span data-stu-id="5c1d2-112">For more information about request response messaging see [Request-Response Messaging](../core/request-response-messaging.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c1d2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c1d2-113">See Also</span></span>  
 <span data-ttu-id="5c1d2-114">[¿Qué es el adaptador de SOAP?](../core/what-is-the-soap-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="5c1d2-114">[What Is the SOAP Adapter?](../core/what-is-the-soap-adapter.md) </span></span>  
 [<span data-ttu-id="5c1d2-115">Recomendaciones de seguridad del adaptador SOAP</span><span class="sxs-lookup"><span data-stu-id="5c1d2-115">SOAP Adapter Security Recommendations</span></span>](../core/soap-adapter-security-recommendations.md)