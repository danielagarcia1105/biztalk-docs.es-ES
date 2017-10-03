---
title: "Patrones de la administración del servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fea915c-0074-472e-909b-fbbd88d7359c
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a48639fb2a540b5b2597b34ad95ee390b4382c34
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="service-management-patterns"></a><span data-ttu-id="28885-102">Patrones de la administración de servicio</span><span class="sxs-lookup"><span data-stu-id="28885-102">Service Management Patterns</span></span>
## <a name="repair-and-resubmit"></a><span data-ttu-id="28885-103">Reparación y vuelva a intentarlo</span><span class="sxs-lookup"><span data-stu-id="28885-103">Repair and Resubmit</span></span>  
 <span data-ttu-id="28885-104">El patrón de reparación y vuelva a intentarlo define una solución en la que un servicio no puede procesar un mensaje y debe correctamente externalizar su estado en el formulario del mensaje con errores, habilitar el contenido del mensaje que esté disponible para reparar y, a continuación, volver a enviarla a un servicio Para continuar procesando el mensaje.</span><span class="sxs-lookup"><span data-stu-id="28885-104">The Repair and Resubmit pattern defines a solution in which a service is unable to process a message and needs to gracefully externalize its state in the form of the failed message, enabling the message content to be available for repair and then resubmit it to a service to continue processing the message.</span></span>  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]<span data-ttu-id="28885-105">incluye mecanismos por qué Microsoft BizTalk excepciones de mensajería y orquestación pueden normalizar y se expone para ninguna acción adicional.</span><span class="sxs-lookup"><span data-stu-id="28885-105"> includes mechanisms by which Microsoft BizTalk messaging and orchestration exceptions can be normalized and exposed for additional action.</span></span> <span data-ttu-id="28885-106">Al diseñar una solución ESB, es importante para la cuenta para el tratamiento de excepciones.</span><span class="sxs-lookup"><span data-stu-id="28885-106">When designing an ESB solution, it is important to account for how exceptions will be handled.</span></span> <span data-ttu-id="28885-107">El [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] incluye una aplicación de Portal de administración de ESB de ejemplo que muestra cómo se pueden ver y administrar las excepciones.</span><span class="sxs-lookup"><span data-stu-id="28885-107">The [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] includes a sample ESB Management Portal application that demonstrates how exceptions can be viewed and managed.</span></span> <span data-ttu-id="28885-108">Para obtener información detallada acerca de cómo reparar y volver a enviar excepciones mediante la aplicación de ejemplo de Portal de administración de ESB, consulte [reparando y volver a enviar mensajes](../esb-toolkit/repairing-and-resubmitting-messages.md).</span><span class="sxs-lookup"><span data-stu-id="28885-108">For detailed information about repairing and resubmitting exceptions using the ESB Management Portal sample application, see [Repairing and Resubmitting Messages](../esb-toolkit/repairing-and-resubmitting-messages.md).</span></span>