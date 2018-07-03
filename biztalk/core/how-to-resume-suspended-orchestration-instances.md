---
title: Cómo reanudar instancias de orquestación suspendidas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- instances, resuming [HAT]
- HAT, resuming orchestrations
- HAT, resuming pipelines
- orchestrations, resuming
- resuming, pipelines
- resuming, orchestrations
- HAT, debug mode
ms.assetid: da133183-68d9-48d1-9601-8f6d4d5b8898
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5f3243173f454d560515d1c3cbb9bef749fc17d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991173"
---
# <a name="how-to-resume-suspended-orchestration-instances"></a><span data-ttu-id="40011-102">Cómo reanudar instancias de orquestación suspendidas</span><span class="sxs-lookup"><span data-stu-id="40011-102">How to Resume Suspended Orchestration Instances</span></span>
<span data-ttu-id="40011-103">Si ha suspendido instancias de orquestación enumeradas como "suspendidas reanudables", puede intentar reanudarlas desde el panel de previsualización o de resultados de consulta.</span><span class="sxs-lookup"><span data-stu-id="40011-103">If you have suspended orchestration instances that are listed as "suspended resumable," you can attempt to resume the orchestration instance from the query results or preview pane.</span></span> <span data-ttu-id="40011-104">La reanudación de la instancia de orquestación sólo se realizará correctamente si el problema subyacente que ocasionó su suspensión se ha resuelto.</span><span class="sxs-lookup"><span data-stu-id="40011-104">Resuming the orchestration instance will only succeed if the underlying problem that caused the orchestration instance to become suspended has also been fixed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="40011-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="40011-105">Prerequisites</span></span>  
 <span data-ttu-id="40011-106">Debe ser iniciado sesión como miembro del grupo Operadores de BizTalk Server para llevar a cabo este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="40011-106">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-resume-suspended-orchestration-instances"></a><span data-ttu-id="40011-107">Para reanudar instancias de orquestación suspendidas</span><span class="sxs-lookup"><span data-stu-id="40011-107">To resume suspended orchestration instances</span></span>  
  
1. <span data-ttu-id="40011-108">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="40011-108">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="40011-109">En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="40011-109">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3. <span data-ttu-id="40011-110">En el panel de detalles, haga clic en el **nueva consulta** ficha.</span><span class="sxs-lookup"><span data-stu-id="40011-110">In the details pane, click the **New Query** tab.</span></span>  
  
4. <span data-ttu-id="40011-111">En el **expresión de consulta** grupo, en el **valor** columna, seleccione **instancias de servicio suspendidas** desde el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="40011-111">In the **Query Expression** group, in the **Value** column, select **Suspended Service Instances** from the drop-down list box.</span></span>  
  
5. <span data-ttu-id="40011-112">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="40011-112">Do one of the following:</span></span>  
  
   - <span data-ttu-id="40011-113">Para reanudar una única instancia, en el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (**\\**<em>), seleccione el \**denombredeservicio</em>*  filtro y, a continuación, en el **valor** columna, especifique el nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="40011-113">To resume a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\\**<em>), select the \**Service Name</em>* filter and then in the **Value** column, specify the service name.</span></span>  
  
   - <span data-ttu-id="40011-114">Para reanudar las instancias de forma masiva, en el **nombre de campo** columna, en el cuadro de lista desplegable vacío junto al asterisco (**\\**<em>), seleccione \**agrupar resultados por</em>*  y, a continuación, en el **valor** columna, especifique el nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="40011-114">To resume instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\\**<em>), select \**Group Results By</em>* and then in the **Value** column, specify the service name.</span></span>  
  
6. <span data-ttu-id="40011-115">Haga clic en **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="40011-115">Click **Run Query**.</span></span>  
  
7. <span data-ttu-id="40011-116">En la lista de resultados de consulta, haga clic en la instancia de orquestación que desea reanudar y, a continuación, haga clic en **reanudar instancia** o **Reanudar instancias**.</span><span class="sxs-lookup"><span data-stu-id="40011-116">In the query results list, right-click the orchestration instance you want to resume, and then click **Resume Instance** or **Resume Instances**.</span></span> <span data-ttu-id="40011-117">Esto permite seleccionar las instancias que desea reanudar.</span><span class="sxs-lookup"><span data-stu-id="40011-117">This allows you to select which instances to resume.</span></span>  
  
    <span data-ttu-id="40011-118">[Estados de instancia de servicio](../core/service-instance-states.md) proporciona más información sobre el en estado suspendido.</span><span class="sxs-lookup"><span data-stu-id="40011-118">[Service Instance States](../core/service-instance-states.md) provides more information on the on the suspended state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40011-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="40011-119">See Also</span></span>  
 [<span data-ttu-id="40011-120">Investigación de errores de mensaje, orquestación y puerto</span><span class="sxs-lookup"><span data-stu-id="40011-120">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)
