---
title: "Resolución de punto a punto de puntos de conexión y los requisitos de transformación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4c570bf-8274-4779-ae83-2aef2bf57ded
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8899c5f713f1c9ebfe299d3e431754dd8b9794d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="point-to-point-resolution-of-endpoints-and-transformation-requirements"></a><span data-ttu-id="887db-102">Resolución de punto a punto de puntos de conexión y los requisitos de transformación</span><span class="sxs-lookup"><span data-stu-id="887db-102">Point-to-Point Resolution of Endpoints and Transformation Requirements</span></span>
<span data-ttu-id="887db-103">En este caso de uso, un cliente del servicio Web llama a un servicio Web sin tener que pasar a través de ESB.</span><span class="sxs-lookup"><span data-stu-id="887db-103">In this use case, a Web service client calls a Web service without going through the ESB.</span></span> <span data-ttu-id="887db-104">Los dos puntos se comunican directamente, pero antes de que el cliente realiza la llamada, que debe resolver el extremo del servicio Web.</span><span class="sxs-lookup"><span data-stu-id="887db-104">The two points communicate directly, but before the client makes the call, it must resolve the endpoint of the Web service.</span></span> <span data-ttu-id="887db-105">La llamada al servicio Web puede ser un unidireccional o solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="887db-105">The call to the Web service can be either a one-way or a request-response.</span></span> <span data-ttu-id="887db-106">Una manera de conseguirlo es usar las características de resolución dinámica de ESB, tal como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="887db-106">One way of achieving this is to use the dynamic resolution features of the ESB, as shown in Figure 1.</span></span>  
  
 <span data-ttu-id="887db-107">![Punto de &#45; a &#45; Punto de resolución de extremos](../esb-toolkit/media/ch3-pointtopoint.gif "Ch3-PointToPoint")</span><span class="sxs-lookup"><span data-stu-id="887db-107">![Point&#45;to&#45;Point Resolution of Endpoints](../esb-toolkit/media/ch3-pointtopoint.gif "Ch3-PointToPoint")</span></span>  
  
 <span data-ttu-id="887db-108">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="887db-108">**Figure 1**</span></span>  
  
 <span data-ttu-id="887db-109">**Resolver los extremos que usan UDDI**</span><span class="sxs-lookup"><span data-stu-id="887db-109">**Resolving endpoints using UDDI**</span></span>  
  
 <span data-ttu-id="887db-110">El ejemplo de servicio de la resolución que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="887db-110">The Resolver Service sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="887db-111">El ejemplo muestra cómo llamar al servicio de resolución de ESB para llevar a cabo la resolución, lo que permite probar la resolución mientras se desarrolla el contenido de los almacenes de back-end, como Universal Description, Discovery y Integration (UDDI), XML Path Language (XPath) Estáticos o directivas en el motor de reglas de negocio de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="887db-111">The sample shows how to call the ESB Resolver Service to perform resolution, which enables you to test resolution as you are developing the contents of the back-end stores, such as Universal Description, Discovery, and Integration (UDDI), XML Path Language (XPath), Static, or policies in the BizTalk Server Business Rules Engine.</span></span>  
  
 <span data-ttu-id="887db-112">Para obtener más información, consulte [instalar y ejecutar el ejemplo de servicio de resolución](../esb-toolkit/installing-and-running-the-resolver-service-sample.md).</span><span class="sxs-lookup"><span data-stu-id="887db-112">For more information, see [Installing and Running the Resolver Service Sample](../esb-toolkit/installing-and-running-the-resolver-service-sample.md).</span></span>