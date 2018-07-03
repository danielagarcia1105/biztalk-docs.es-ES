---
title: Administrar puertos de envío y grupos de puertos de envío | Microsoft Docs
description: Vínculos para crear, configurar, dar de alta, dar de baja e iniciar y detener puertos de envío de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db45f9f9-b32a-4b9c-a3bf-8c271d0f0cf9
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b3fe64a46ec4dd80d278e36f91406db0c431972
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015757"
---
# <a name="manage-send-ports-and-send-port-groups"></a><span data-ttu-id="6f06f-103">Administrar puertos de envío y grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="6f06f-103">Manage Send Ports and Send Port Groups</span></span>

## <a name="overview"></a><span data-ttu-id="6f06f-104">Información general</span><span class="sxs-lookup"><span data-stu-id="6f06f-104">Overview</span></span>
<span data-ttu-id="6f06f-105">En esta sección se proporcionan instrucciones acerca del uso de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para crear, configurar y administrar puertos de envío y grupos de puertos de envío en una aplicación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="6f06f-105">This section provides instructions on using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console to create, configure, and manage send ports and send port groups in a BizTalk application.</span></span> <span data-ttu-id="6f06f-106">Un puerto de envío especifica la ubicación a la que se envían los mensajes y, de forma opcional, confirma su recepción.</span><span class="sxs-lookup"><span data-stu-id="6f06f-106">A send port specifies the location to which messages are sent and optionally responses are received.</span></span> <span data-ttu-id="6f06f-107">Siempre que se envía un mensaje a un puerto de envío, se crea una nueva instancia de servicio de puerto de envío, que se denomina un *instancia del servicio*.</span><span class="sxs-lookup"><span data-stu-id="6f06f-107">Any time a message is sent to a send port, a new instance of the send port service is created, which is called a *service instance*.</span></span>  
  
 <span data-ttu-id="6f06f-108">Un grupo de puertos de envío es una agrupación lógica de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="6f06f-108">A send port group is a logical grouping of send ports.</span></span> <span data-ttu-id="6f06f-109">Cuando un mensaje se envía a un grupo de puertos de envío, se dirige a todos los puertos de envío asociados.</span><span class="sxs-lookup"><span data-stu-id="6f06f-109">When a message is sent to a send port group, it is routed to all of the associated send ports.</span></span>  <span data-ttu-id="6f06f-110">Para obtener información general sobre los puertos de envío y grupos de puertos de envío, consulte [puertos de envío y grupos de puertos de envío](../core/send-ports-and-send-port-groups.md).</span><span class="sxs-lookup"><span data-stu-id="6f06f-110">For background information about send ports and send port groups, see [Send Ports and Send Port Groups](../core/send-ports-and-send-port-groups.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f06f-111">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="6f06f-111">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="6f06f-112">Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="6f06f-112">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
> 
> [!NOTE]
>  <span data-ttu-id="6f06f-113">Al desarrollar una aplicación de BizTalk, el programador puede utilizar herramientas de diseño de BizTalk en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], por ejemplo, el Diseñador de orquestaciones, para crear y configurar puertos de envío y grupos de puertos de envío.</span><span class="sxs-lookup"><span data-stu-id="6f06f-113">While developing a BizTalk application, the developer can use BizTalk design tools in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], such as Orchestration Designer, to create and configure send ports and send port groups.</span></span> <span data-ttu-id="6f06f-114">Para obtener más información, consulte [mediante puertos en orquestaciones](../core/using-ports-in-orchestrations.md).</span><span class="sxs-lookup"><span data-stu-id="6f06f-114">For more information, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="6f06f-115">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6f06f-115">Next steps</span></span>
  
-   [<span data-ttu-id="6f06f-116">Creación y configuración de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="6f06f-116">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)  
  
-   [<span data-ttu-id="6f06f-117">Creación y configuración de grupos de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="6f06f-117">Creating and Configuring Send Port Groups</span></span>](../core/creating-and-configuring-send-port-groups.md)  
  
-   [<span data-ttu-id="6f06f-118">Dar de alta un puerto de envío o grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="6f06f-118">Enlist a Send Port or Send Port Group</span></span>](../core/how-to-enlist-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="6f06f-119">Dar de baja un puerto de envío o grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="6f06f-119">Unenlist a Send Port or Send Port Group</span></span>](../core/how-to-unenlist-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="6f06f-120">Iniciar un puerto de envío o un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="6f06f-120">Start a Send Port or Send Port Group</span></span>](../core/how-to-start-a-send-port-or-send-port-group.md)  
  
-   [<span data-ttu-id="6f06f-121">Detener un puerto de envío o un grupo de puertos de envío</span><span class="sxs-lookup"><span data-stu-id="6f06f-121">Stop a Send Port or Send Port Group</span></span>](../core/how-to-stop-a-send-port-or-send-port-group.md)