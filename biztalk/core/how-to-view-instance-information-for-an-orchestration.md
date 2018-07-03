---
title: Cómo ver información de instancia de una orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, viewing
- managing [orchestrations], viewing
ms.assetid: 860ac2b2-c556-4e1f-8b7f-18ab8be52db4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 761f29d6f341410fec544fb0d6fdc032f671775c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983997"
---
# <a name="how-to-view-instance-information-for-an-orchestration"></a><span data-ttu-id="589eb-102">Cómo ver información de instancia para una orquestación</span><span class="sxs-lookup"><span data-stu-id="589eb-102">How to View Instance Information for an Orchestration</span></span>
<span data-ttu-id="589eb-103">En este tema se describe cómo ver información de instancia para una orquestación mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="589eb-103">This topic describes how to view instance information for an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="589eb-104">Una instancia de servicio es una instancia de una orquestación que BizTalk Server está procesando o ha serializado en el cuadro de mensajes para su seguimiento o procesamiento ulterior.</span><span class="sxs-lookup"><span data-stu-id="589eb-104">A service instance is an instance of an orchestration that BizTalk Server is either processing or has serialized into the MessageBox for further processing or tracking.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="589eb-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="589eb-105">Prerequisites</span></span>  
 <span data-ttu-id="589eb-106">Para realizar el procedimiento que se detalla en este tema, debe haber iniciado sesión como miembro del grupo de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="589eb-106">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="589eb-107">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="589eb-107">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-instance-information-for-an-orchestration"></a><span data-ttu-id="589eb-108">Para ver información de instancia para una orquestación</span><span class="sxs-lookup"><span data-stu-id="589eb-108">To view instance information for an orchestration</span></span>  
  
1. <span data-ttu-id="589eb-109">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="589eb-109">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="589eb-110">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda el grupo de BizTalk, expanda **aplicaciones**y, a continuación, expanda la aplicación que contiene la orquestación para la que desea ver información de instancia.</span><span class="sxs-lookup"><span data-stu-id="589eb-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand the BizTalk group, expand **Applications**, and then expand the application containing the orchestration for which you want to view instance information.</span></span>  
  
3. <span data-ttu-id="589eb-111">Haga clic en **orquestaciones**, seleccione la orquestación que desea ver información de instancia, haga clic en **vista**y, a continuación, seleccione **información de la instancia**.</span><span class="sxs-lookup"><span data-stu-id="589eb-111">Click **Orchestrations**, select the orchestration for which you want to view instance information, click **View**, and then select **Instance Information**.</span></span>  
  
    <span data-ttu-id="589eb-112">En el panel de resultados de consulta de la sección inferior de la página, se muestran todas las instancias de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="589eb-112">The query results panel in the lower section of the page displays all instances of the orchestration.</span></span>  
  
    <span data-ttu-id="589eb-113">Para refinar la consulta y ver información de instancia diferente para la orquestación, haga clic en el cuadro en **valor** para el campo Buscar y seleccionar el tipo de instancia para ver y, a continuación, haga clic en **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="589eb-113">To refine the query and view different instance information for the orchestration, click the box under **Value** for the Search For field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="589eb-114">Para obtener más información acerca de la creación de consultas, vea los temas que aparecen en Vea también al ejecutar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="589eb-114">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="589eb-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="589eb-115">See Also</span></span>  
 <span data-ttu-id="589eb-116">[Administración de orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="589eb-116">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="589eb-117">[Cómo buscar instancias de servicio de ejecución](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="589eb-117">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 <span data-ttu-id="589eb-118">[Cómo buscar instancias de servicio suspendidas](../core/how-to-search-for-suspended-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="589eb-118">[How to Search for Suspended Service Instances](../core/how-to-search-for-suspended-service-instances.md) </span></span>  
 <span data-ttu-id="589eb-119">[Cómo buscar mensajes](../core/how-to-search-for-messages.md) </span><span class="sxs-lookup"><span data-stu-id="589eb-119">[How to Search for Messages](../core/how-to-search-for-messages.md) </span></span>  
 [<span data-ttu-id="589eb-120">Cómo buscar suscripciones</span><span class="sxs-lookup"><span data-stu-id="589eb-120">How to Search for Subscriptions</span></span>](../core/how-to-search-for-subscriptions.md)