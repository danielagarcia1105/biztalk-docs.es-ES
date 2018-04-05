---
title: Diagrama físico | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, network configuration
ms.assetid: 4291727b-8687-496a-8f03-0da4b3201967
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fcd0558d8fe3d45063a53800b1f3c082a2ba056
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="physical-diagram"></a><span data-ttu-id="66ec2-102">Diagrama físico</span><span class="sxs-lookup"><span data-stu-id="66ec2-102">Physical Diagram</span></span>
<span data-ttu-id="66ec2-103">Una implementación típica agrupado equipos con BizTalk Server para la mensajería (enviar y recibir), equipos de BizTalk Server para ejecutar el proceso empresarial (orquestación), los equipos con BizTalk Server para tener acceso a las plantillas de InfoPath (sitio MRSR), y equipos con SQL Server en clúster.</span><span class="sxs-lookup"><span data-stu-id="66ec2-103">A typical deployment has clustered BizTalk Server computers for messaging (sending and receiving), BizTalk Server computers for executing the business process (orchestration), BizTalk Server computers for accessing the InfoPath templates (MRSR site), and clustered SQL Server computers.</span></span> <span data-ttu-id="66ec2-104">La siguiente implementación garantiza un entorno seguro desde la intranet y los usuarios de Internet.</span><span class="sxs-lookup"><span data-stu-id="66ec2-104">The following deployment ensures a secure environment from both the intranet and Internet users.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="66ec2-105">Esta implementación típica es la configuración recomendada.</span><span class="sxs-lookup"><span data-stu-id="66ec2-105">This typical deployment is the recommended configuration.</span></span> <span data-ttu-id="66ec2-106">Debe comprobar sus propias necesidades empresariales y las configuraciones de servidor para asegurarse de que la implementación funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="66ec2-106">You will need to verify your own business needs and server configurations to make certain your deployment works correctly.</span></span>  
  
 <span data-ttu-id="66ec2-107">Se puede ajustar esta implementación hacia arriba o hacia abajo, hacia fuera o hacia atrás, según el perfil de uso y sus crecientes necesidades empresariales.</span><span class="sxs-lookup"><span data-stu-id="66ec2-107">You can scale this deployment up or down, out or back, depending on the usage profile and your growing business needs.</span></span> <span data-ttu-id="66ec2-108">Los escenarios de escalabilidad típicos incluyen agregar uno o más servidores en cada clúster para garantizar la alta disponibilidad o un mejor rendimiento.</span><span class="sxs-lookup"><span data-stu-id="66ec2-108">Typical scalability scenarios include adding one or more servers in each cluster to ensure higher availability or better throughput.</span></span> <span data-ttu-id="66ec2-109">Las empresas más pequeñas podría ser preferible escalar su implementación para que los mismos servidores realice varias funciones, como tener una [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] equipo controlar de mensajería y orquestación.</span><span class="sxs-lookup"><span data-stu-id="66ec2-109">Smaller enterprises might prefer scaling back their deployment to have the same servers perform multiple functions, such as having one [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] computer handle both orchestration and messaging.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="66ec2-110">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]admite la implementación en un solo servidor.</span><span class="sxs-lookup"><span data-stu-id="66ec2-110">[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] supports deployment on a single server.</span></span> <span data-ttu-id="66ec2-111">En la siguiente ilustración muestra un ejemplo del entorno de implementación distribuida recomendada para una implementación completa de A4SWIFT.</span><span class="sxs-lookup"><span data-stu-id="66ec2-111">The following figure shows an example of the recommended distributed deployment environment for a full A4SWIFT deployment.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-deploy-full.gif "FSA_Deploy_Full")  
<span data-ttu-id="66ec2-112">Ejemplo de una implementación completa de A4SWIFT</span><span class="sxs-lookup"><span data-stu-id="66ec2-112">Example of a full A4SWIFT deployment</span></span>