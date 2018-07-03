---
title: Conservación de encabezados JMS al enrutar a través de una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d9a59ff3-0cbf-499f-92b2-cf5b808d8b3f
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 142bd0d2e5ff86362fe3c3ffa7ef8ec256202708
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979717"
---
# <a name="preserving-jms-headers-when-routing-through-an-orchestration"></a><span data-ttu-id="ccdb4-102">Conservación de encabezados JMS al enrutar a través de una orquestación</span><span class="sxs-lookup"><span data-stu-id="ccdb4-102">Preserving JMS Headers When Routing Through an Orchestration</span></span>
<span data-ttu-id="ccdb4-103">En este caso de uso, los componentes proporcionados con [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extraer los encabezados de Java Message Service (JMS) de un mensaje entrante y, a continuación, los reconstruye en el mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="ccdb4-103">In this use case, components provided with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] extract Java Message Service (JMS) headers from an incoming message and then reconstructs them in the outgoing message.</span></span> <span data-ttu-id="ccdb4-104">Esto demuestra la conservación de encabezado de mensaje JMS y acceso al contexto de encabezado desde dentro de una orquestación, tal como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="ccdb4-104">This demonstrates JMS message header preservation and access to header context from inside an orchestration, as illustrated in Figure 1.</span></span>  
  
 <span data-ttu-id="ccdb4-105">![Conservación de JMS](../esb-toolkit/media/ch3-preservingjms.gif "Ch3-PreservingJMS")</span><span class="sxs-lookup"><span data-stu-id="ccdb4-105">![Preserving JMS](../esb-toolkit/media/ch3-preservingjms.gif "Ch3-PreservingJMS")</span></span>  
  
 <span data-ttu-id="ccdb4-106">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="ccdb4-106">**Figure 1**</span></span>  
  
 <span data-ttu-id="ccdb4-107">**Conservación de la información de encabezado JMS a lo largo de una orquestación de ESB y procesamiento**</span><span class="sxs-lookup"><span data-stu-id="ccdb4-107">**Preserving JMS header information throughout an ESB orchestration and processing**</span></span>  
  
 <span data-ttu-id="ccdb4-108">El ejemplo de componente MQRFH2 de JMS incluido con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] muestra este caso de uso y consta de las siguientes tres partes:</span><span class="sxs-lookup"><span data-stu-id="ccdb4-108">The JMS MQRFH2 Component sample included with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] demonstrates this use case and consists of the following three parts:</span></span>  
  
- <span data-ttu-id="ccdb4-109">Parte 1 muestra cómo conservar el encabezado de fidelidad total tránsito de un mensaje de IBM WebSphere MQ, a través de ESB y BizTalk Server y de vuelta a IBM WebSphere MQ.</span><span class="sxs-lookup"><span data-stu-id="ccdb4-109">Part 1 demonstrates full-fidelity header preservation as a message travels from IBM WebSphere MQ, through ESB and BizTalk Server, and back to IBM WebSphere MQ.</span></span>  
  
- <span data-ttu-id="ccdb4-110">Parte 2 muestra cómo puede tener acceso a las propiedades de encabezado MQRFH2 código en una orquestación de ESB.</span><span class="sxs-lookup"><span data-stu-id="ccdb4-110">Part 2 demonstrates how code in an ESB orchestration can access MQRFH2 header properties.</span></span> <span data-ttu-id="ccdb4-111">En este caso, el código modifica una propiedad de encabezado JMS para especificar el nombre de la cola de destino.</span><span class="sxs-lookup"><span data-stu-id="ccdb4-111">In this case, the code modifies a JMS header property to specify the destination queue name.</span></span>  
  
- <span data-ttu-id="ccdb4-112">Parte 3 muestra una cola con mensajes de carga masiva y muestra cómo la aplicación enruta los mensajes a las colas de destino especificadas como parte del contenido del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ccdb4-112">Part 3 demonstrates bulk loading a queue with messages and shows how the application routes messages to the destination queues specified as part of the message content.</span></span>  
  
  <span data-ttu-id="ccdb4-113">Para obtener más información, consulte [instalar y ejecutar el ejemplo de componente MQRFH2 de JMS](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ccdb4-113">For more information, see [Installing and Running the JMS MQRFH2 Component Sample](../esb-toolkit/installing-and-running-the-jms-mqrfh2-component-sample.md).</span></span>