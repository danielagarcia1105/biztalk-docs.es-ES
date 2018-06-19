---
title: Ejecutar el ejemplo de componente JMS MQRFH2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44f4b48c-398a-4ec1-a033-1fc4a76a305c
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fcea4bca324f73ee37b63e78673140eae250692
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294268"
---
# <a name="running-the-jms-mqrfh2-component-sample"></a><span data-ttu-id="5f04c-102">Ejecutar el ejemplo de componente JMS MQRFH2</span><span class="sxs-lookup"><span data-stu-id="5f04c-102">Running the JMS MQRFH2 Component Sample</span></span>
<span data-ttu-id="5f04c-103">El ejemplo de componente de JMS MQRFH2 consta de tres partes:</span><span class="sxs-lookup"><span data-stu-id="5f04c-103">The JMS MQRFH2 Component sample consists of three parts:</span></span>  
  
-   <span data-ttu-id="5f04c-104">[Ejecutar el ejemplo de conservación de JMS MQRFH2 encabezado](../esb-toolkit/running-the-jms-mqrfh2-header-preservation-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5f04c-104">[Running the JMS MQRFH2 Header Preservation Sample](../esb-toolkit/running-the-jms-mqrfh2-header-preservation-sample.md).</span></span> <span data-ttu-id="5f04c-105">Esta parte muestra conservar el encabezado totalmente exactos de tránsito de un mensaje de IBM WebSphere MQ, a través de ESB y Microsoft BizTalk Server y de vuelta a IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="5f04c-105">This part demonstrates full-fidelity header preservation as a message travels from IBM WebSphere MQ, through ESB and Microsoft BizTalk Server, and back to IBM WebSphere MQ.</span></span>  
  
-   <span data-ttu-id="5f04c-106">[Ejecuta el acceso a la propiedad de encabezado de un ejemplo de orquestación](../esb-toolkit/running-the-header-property-access-from-an-orchestration-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5f04c-106">[Running the Header Property Access from an Orchestration Sample](../esb-toolkit/running-the-header-property-access-from-an-orchestration-sample.md).</span></span> <span data-ttu-id="5f04c-107">Esta parte explica cómo el código dentro de una orquestación de ESB puede tener acceso a propiedades de encabezado de MQRFH2.</span><span class="sxs-lookup"><span data-stu-id="5f04c-107">This part demonstrates how code within an ESB orchestration can access MQRFH2 header properties.</span></span> <span data-ttu-id="5f04c-108">En este caso, el código utiliza una propiedad de encabezado para especificar el nombre de la cola de destino.</span><span class="sxs-lookup"><span data-stu-id="5f04c-108">In this case, the code uses a header property to specify the destination queue name.</span></span>  
  
-   <span data-ttu-id="5f04c-109">[Ejecuta la mayor parte cargar muestra de enrutamiento basado en contenido](../esb-toolkit/running-the-bulk-load-content-based-routing-sample.md).</span><span class="sxs-lookup"><span data-stu-id="5f04c-109">[Running the Bulk Load Content-Based Routing Sample](../esb-toolkit/running-the-bulk-load-content-based-routing-sample.md).</span></span> <span data-ttu-id="5f04c-110">Esta parte muestra una cola con los mensajes de carga masiva, y se muestra cómo la aplicación enruta los mensajes a las colas de destino especificadas como parte del contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="5f04c-110">This part demonstrates bulk loading a queue with messages, and it shows how the application routes messages to the destination queues specified as part of the message content.</span></span>