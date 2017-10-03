---
title: "Transformación sin almacenar en la base de datos de cuadro de mensaje de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f5b4caf-88e9-41dd-a644-e229e411a4a7
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 407725509121948619e4eb05b583f6c8c1362f9f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="transformation-without-persisting-to-the-biztalk-message-box-database"></a><span data-ttu-id="4d53e-102">Transformación sin almacenar en la base de datos de cuadro de mensaje de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4d53e-102">Transformation Without Persisting to the BizTalk Message Box Database</span></span>
<span data-ttu-id="4d53e-103">En este caso de uso, una llamada a un servicio Web realiza la transformación en tiempo real de un mensaje, basado en la resolución de tiempo de ejecución de la asignación correspondiente para aplicar y devuelve el resultado transformado.</span><span class="sxs-lookup"><span data-stu-id="4d53e-103">In this use case, a call to a Web service performs real-time transformation of a message, based on run-time resolution of the appropriate map to apply, and returns the transformed result.</span></span> <span data-ttu-id="4d53e-104">Figura 1 muestra una vista esquemática del proceso.</span><span class="sxs-lookup"><span data-stu-id="4d53e-104">Figure 1 illustrates a schematic view of the process.</span></span>  
  
 <span data-ttu-id="4d53e-105">![Transformación sin almacenar](../esb-toolkit/media/ch3-transformationwithout.gif "Ch3-TransformationWithout")</span><span class="sxs-lookup"><span data-stu-id="4d53e-105">![Transformation Without Persisting](../esb-toolkit/media/ch3-transformationwithout.gif "Ch3-TransformationWithout")</span></span>  
  
 <span data-ttu-id="4d53e-106">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="4d53e-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="4d53e-107">**Transformación de un mensaje sin almacenar en la base de datos de cuadro de mensaje de Microsoft BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="4d53e-107">**Transforming a message without persisting to the Microsoft BizTalk Server Message Box database**</span></span>  
  
 <span data-ttu-id="4d53e-108">El ejemplo de servicios de transformación que se incluye con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso.</span><span class="sxs-lookup"><span data-stu-id="4d53e-108">The Transformation Service sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case.</span></span> <span data-ttu-id="4d53e-109">Si la usa, puede llamar al servicio de transformación de ESB; Esto le permite probar las transformaciones y asignaciones, tal y como se va a programar componentes y las directivas en el motor de reglas de negocio de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4d53e-109">By using it, you can call the ESB Transformation Service; this enables you to test transformations and mappings as you are developing components and policies in the BizTalk Server Business Rules Engine.</span></span>  
  
 <span data-ttu-id="4d53e-110">Para obtener más información, consulte [instalar y ejecutar el ejemplo de servicio de transformación](../esb-toolkit/installing-and-running-the-transformation-service-sample.md).</span><span class="sxs-lookup"><span data-stu-id="4d53e-110">For more information, see [Installing and Running the Transformation Service Sample](../esb-toolkit/installing-and-running-the-transformation-service-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d53e-111">No confunda el servicio de transformación que se hace referencia aquí con las operaciones de transformación dinámica realizadas por el agente de transformación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="4d53e-111">Do not confuse the Transformation Service referred to here with the dynamic transformation operations performed by the BizTalk Server Transformation Agent.</span></span> <span data-ttu-id="4d53e-112">El servicio de transformación es un servicio Web de alto rendimiento que reduce significativamente la latencia llamando directamente al servidor BizTalk Server sin tener que pasar a través de la base de datos de cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="4d53e-112">The Transformation Service is a high-performance Web service that significantly reduces latency by calling directly into BizTalk Server without going through the Message Box database.</span></span>