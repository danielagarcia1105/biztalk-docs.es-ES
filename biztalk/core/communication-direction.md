---
title: "Dirección de comunicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- port types, communication direction
- communication direction [port types]
ms.assetid: b278325e-a1da-49a6-8332-80a5f640cc22
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d6c664643629971366805d08600677d22d7c419
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="communication-direction"></a><span data-ttu-id="0284f-102">Dirección de comunicación</span><span class="sxs-lookup"><span data-stu-id="0284f-102">Communication Direction</span></span>
<span data-ttu-id="0284f-103">Cada *puerto* tiene su propia dirección de comunicación.</span><span class="sxs-lookup"><span data-stu-id="0284f-103">Each *port* has its own communication direction.</span></span> <span data-ttu-id="0284f-104">La dirección de comunicación se utiliza junto con el patrón de comunicación del tipo de puerto para completar la definición de cómo se puede usar un puerto.</span><span class="sxs-lookup"><span data-stu-id="0284f-104">The communication direction is used in combination with the communication pattern of the port's type to complete the definition of how a port can be used.</span></span> <span data-ttu-id="0284f-105">La dirección de comunicación o polaridad determina la dirección en la que se transmiten los mensajes a través de ese puerto.</span><span class="sxs-lookup"><span data-stu-id="0284f-105">The communication direction, or polarity, determines in which direction messages will be transmitted over that port.</span></span>  
  
 <span data-ttu-id="0284f-106">Si el tipo de puerto tiene un patrón de comunicación unidireccional, la dirección de comunicación puede ser de envío o recepción.</span><span class="sxs-lookup"><span data-stu-id="0284f-106">If the port's type has a one-way communication pattern, its communication direction can be either Send or Receive.</span></span> <span data-ttu-id="0284f-107">Si el tipo de puerto tiene un patrón de comunicación bidireccional (Solicitud-respuesta), la dirección de comunicación puede ser de Envío-Recepción (se envía una solicitud y se recibe una respuesta) o de Recepción-Envío (se recibe una solicitud y se envía una respuesta).</span><span class="sxs-lookup"><span data-stu-id="0284f-107">If the port's type has a two-way (request-response) communication pattern, its communication direction can be Send-Receive, in which a request is sent and a response is received, or Receive-Send, in which a request is received and a response is sent.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0284f-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="0284f-108">See Also</span></span>  
 [<span data-ttu-id="0284f-109">Patrón de comunicación</span><span class="sxs-lookup"><span data-stu-id="0284f-109">Communication Pattern</span></span>](../core/communication-pattern.md)  
 <span data-ttu-id="0284f-110">[Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md) </span><span class="sxs-lookup"><span data-stu-id="0284f-110">[How to Run the Port Configuration Wizard](../core/how-to-run-the-port-configuration-wizard.md) </span></span>  
 [<span data-ttu-id="0284f-111">Uso de puertos en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="0284f-111">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)