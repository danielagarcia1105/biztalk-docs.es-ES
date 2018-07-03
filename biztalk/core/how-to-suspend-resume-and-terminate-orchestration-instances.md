---
title: Cómo suspender, reanudar y finalizar instancias de orquestación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [orchestrations], resuming
- orchestrations, terminating
- managing [orchestrations], suspending
- orchestrations, resuming
- orchestrations, suspending
- managing [orchestrations], terminating
ms.assetid: 7b373dad-57d5-4696-9b29-a6c351d44fa8
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88ad7a5b278f8f972a518af40d527ff312d0d237
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980397"
---
# <a name="how-to-suspend-resume-and-terminate-orchestration-instances"></a><span data-ttu-id="85711-102">Cómo suspender, reanudar y finalizar instancias de orquestación</span><span class="sxs-lookup"><span data-stu-id="85711-102">How to Suspend, Resume, and Terminate Orchestration Instances</span></span>
<span data-ttu-id="85711-103">En este tema se describe cómo suspender, reanudar y finalizar una o varias instancias de servicio en ejecución de una orquestación mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="85711-103">This topic describes how to suspend, resume, and terminate one or more running service instances of an orchestration by using the BizTalk Server Administration console.</span></span> <span data-ttu-id="85711-104">Una instancia de servicio es una instancia de una orquestación que BizTalk Server es un procesamiento o que se ha serializado en el cuadro de mensajes de seguimiento o procesamiento ulterior.</span><span class="sxs-lookup"><span data-stu-id="85711-104">A service instance is an instance of an orchestration that BizTalk Server is either processing or that has been serialized into the MessageBox for further processing or tracking.</span></span>  
  
 <span data-ttu-id="85711-105">Los efectos de estas tres operaciones se describen a continuación:</span><span class="sxs-lookup"><span data-stu-id="85711-105">The following describes the effects of these three operations:</span></span>  
  
-   <span data-ttu-id="85711-106">**Suspender.**</span><span class="sxs-lookup"><span data-stu-id="85711-106">**Suspend.**</span></span> <span data-ttu-id="85711-107">Esta opción detiene la instancia de servicio.</span><span class="sxs-lookup"><span data-stu-id="85711-107">This pauses the service instance.</span></span> <span data-ttu-id="85711-108">Los mensajes en curso se ejecutan hasta que finalizan.</span><span class="sxs-lookup"><span data-stu-id="85711-108">In-process messages run to completion.</span></span> <span data-ttu-id="85711-109">Los mensajes se seguirán enrutando a las instancias de servicio, pero no se procesarán.</span><span class="sxs-lookup"><span data-stu-id="85711-109">Messages are still routed to service instances, but are not processed.</span></span>  
  
-   <span data-ttu-id="85711-110">**Reanudar.**</span><span class="sxs-lookup"><span data-stu-id="85711-110">**Resume.**</span></span> <span data-ttu-id="85711-111">Esta opción reanuda el procesamiento de las instancias suspendidas.</span><span class="sxs-lookup"><span data-stu-id="85711-111">This resumes processing of suspended instances.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85711-112">No puede reanudar una instancia desde un estado de punto de interrupción.</span><span class="sxs-lookup"><span data-stu-id="85711-112">You cannot resume an instance from a breakpoint state.</span></span> <span data-ttu-id="85711-113">La reanudación de una instancia de este tipo puede mostrar el estado de "Pendiente" pero, finalmente, se producirá un error en la instancia.</span><span class="sxs-lookup"><span data-stu-id="85711-113">Resuming such an instance may show a status of "Pending," but the instance will eventually fail.</span></span>  
  
-   <span data-ttu-id="85711-114">**Finalizar.**</span><span class="sxs-lookup"><span data-stu-id="85711-114">**Terminate.**</span></span> <span data-ttu-id="85711-115">Esta opción finaliza el procesamiento de todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="85711-115">This terminates all message processing.</span></span> <span data-ttu-id="85711-116">La instancia de servicio se elimina de las bases de datos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="85711-116">The service instance is deleted from the BizTalk Server databases.</span></span> <span data-ttu-id="85711-117">También se eliminan los mensajes que esté procesando la instancia de servicio, excepto aquellos a los que haga referencia una instancia de servicio que no se esté finalizando.</span><span class="sxs-lookup"><span data-stu-id="85711-117">Messages that the service instance is processing are also deleted, except for any messages that are also referenced by a service instance that is not being terminated.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="85711-118">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="85711-118">Prerequisites</span></span>  
 <span data-ttu-id="85711-119">Para realizar el procedimiento detallado en este tema, debe haber iniciado sesión como miembro del grupo de operadores o de administradores de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="85711-119">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Operators group or the BizTalk Server Administrators group.</span></span> <span data-ttu-id="85711-120">Para obtener más información sobre los permisos, consulte [los permisos necesarios para implementar y administrar una aplicación de BizTalk](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="85711-120">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-view-start-stop-or-terminate-an-instance-of-an-orchestration"></a><span data-ttu-id="85711-121">Para ver iniciar, detener o finalizar instancias de orquestación</span><span class="sxs-lookup"><span data-stu-id="85711-121">To view start, stop, or terminate an instance of an orchestration</span></span>  
  
1. <span data-ttu-id="85711-122">Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="85711-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="85711-123">Seleccione el grupo de BizTalk para mostrar la página Concentrador de grupo.</span><span class="sxs-lookup"><span data-stu-id="85711-123">Select the BizTalk Group to display the Group Hub page.</span></span>  
  
3. <span data-ttu-id="85711-124">En **trabajo en curso**, haga clic en **ejecutando instancias de servicio**.</span><span class="sxs-lookup"><span data-stu-id="85711-124">Under **Work in Progress**, click **Running service instances**.</span></span>  
  
    <span data-ttu-id="85711-125">En el panel de resultados de consulta de la sección inferior de la página, se muestran todas las instancias de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="85711-125">The query results panel in the lower section of the page displays all instances of the orchestration.</span></span>  
  
4. <span data-ttu-id="85711-126">Para refinar la consulta y ver las distintas instancias de la orquestación, haga clic en el cuadro en **valor** para el **buscar** , seleccione el tipo de instancia para ver y, a continuación, haga clic en **Ejecutar consulta** .</span><span class="sxs-lookup"><span data-stu-id="85711-126">To refine the query and view different instances for the orchestration, click the box under **Value** for the **Search For** field, select the instance type to view, and then click **Run Query**.</span></span> <span data-ttu-id="85711-127">Para obtener más información acerca de la creación de consultas, vea los temas que aparecen en Vea también al ejecutar la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="85711-127">For more information about creating queries, see the topics on searching under See Also.</span></span>  
  
5. <span data-ttu-id="85711-128">Haga clic en la instancia que desee y haga clic en **Suspend**, **reanudar**, o **Terminate**.</span><span class="sxs-lookup"><span data-stu-id="85711-128">Right-click the instance you want and click **Suspend**, **Resume**, or **Terminate**.</span></span> <span data-ttu-id="85711-129">Esta funcionalidad permite seleccionar las instancias que desea reanudar.</span><span class="sxs-lookup"><span data-stu-id="85711-129">This functionality allows you to select which instances to resume.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="85711-130">Para realizar la operación en varias instancias, mantenga presionada la tecla CTRL y haga clic en las instancias que desee.</span><span class="sxs-lookup"><span data-stu-id="85711-130">To perform the operation on multiple instances, hold down the CTRL key and click the instances you want.</span></span> <span data-ttu-id="85711-131">A continuación, haga clic en una instancia y haga clic en **Suspend**, **reanudar**, o **Terminate**.</span><span class="sxs-lookup"><span data-stu-id="85711-131">Then right-click an instance and click **Suspend**, **Resume**, or **Terminate**.</span></span>  
  
    <span data-ttu-id="85711-132">[Estados de instancia de servicio](../core/service-instance-states.md) proporciona más información sobre el estado suspendido.</span><span class="sxs-lookup"><span data-stu-id="85711-132">[Service Instance States](../core/service-instance-states.md) provides more information on the suspended state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85711-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="85711-133">See Also</span></span>  
 <span data-ttu-id="85711-134">[Administración de orquestaciones](../core/managing-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="85711-134">[Managing Orchestrations](../core/managing-orchestrations.md) </span></span>  
 <span data-ttu-id="85711-135">[Cómo buscar instancias de servicio de ejecución](../core/how-to-search-for-running-service-instances.md) </span><span class="sxs-lookup"><span data-stu-id="85711-135">[How to Search for Running Service Instances](../core/how-to-search-for-running-service-instances.md) </span></span>  
 [<span data-ttu-id="85711-136">Cómo buscar instancias de servicio suspendidas</span><span class="sxs-lookup"><span data-stu-id="85711-136">How to Search for Suspended Service Instances</span></span>](../core/how-to-search-for-suspended-service-instances.md)