---
title: Consideraciones de seguridad para el desarrollo de orquestaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, orchestrations
- messages, subscriptions
- orchestrations, security
- messages, security
ms.assetid: a29b2018-4a8f-49ad-a817-6f279db3f801
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e020759a8d389461978a4de4138bcc139d527539
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269324"
---
# <a name="security-considerations-for-developing-orchestrations"></a><span data-ttu-id="ade42-102">Consideraciones de seguridad para el desarrollo de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="ade42-102">Security Considerations for Developing Orchestrations</span></span>
<span data-ttu-id="ade42-103">Cuando diseñe orquestaciones, debe tener en cuenta una serie de problemas de seguridad potenciales.</span><span class="sxs-lookup"><span data-stu-id="ade42-103">When designing your orchestrations, you should consider potential security issues.</span></span>  
  
## <a name="avoid-subscriptions-based-on-content-from-untrusted-messages"></a><span data-ttu-id="ade42-104">Evite el uso de suscripciones basadas en contenido de mensajes que no sean de confianza</span><span class="sxs-lookup"><span data-stu-id="ade42-104">Avoid subscriptions based on content from untrusted messages</span></span>  
 <span data-ttu-id="ade42-105">Para garantizar que un mensaje con pocos privilegios no inicie una instancia de orquestación que potencialmente pueda crear suscripciones basadas en el contenido o el contexto del mensaje, se recomienda que las orquestaciones no creen las suscripciones de mensajes según el contenido o el contexto de un mensaje que no sea de confianza.</span><span class="sxs-lookup"><span data-stu-id="ade42-105">To ensure that a low-privilege message does not initiate an orchestration instance that could potentially create subscriptions based on the message content or context, it is highly recommended that your orchestrations do not create their message subscriptions based on the content or context of a message that is not trusted.</span></span>  
  
 <span data-ttu-id="ade42-106">Para obtener información acerca de la seguridad en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], consulte [proteger BizTalk Server](../core/securing-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="ade42-106">For information about security in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Securing BizTalk Server](../core/securing-biztalk-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ade42-107">Vea también</span><span class="sxs-lookup"><span data-stu-id="ade42-107">See Also</span></span>  
 <span data-ttu-id="ade42-108">[Crear orquestaciones](../core/creating-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="ade42-108">[Creating Orchestrations](../core/creating-orchestrations.md) </span></span>  
 [<span data-ttu-id="ade42-109">Acerca de las orquestaciones</span><span class="sxs-lookup"><span data-stu-id="ade42-109">About Orchestrations</span></span>](../core/about-orchestrations.md)