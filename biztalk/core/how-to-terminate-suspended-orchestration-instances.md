---
title: "Cómo finalizar instancias de orquestación suspendidas | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, terminating [HAT]
- messages, saving [HAT]
- HAT, saving messages
- HAT, terminating pipelines
- HAT, terminiating orchestrations
- orchestrations, terminating [HAT]
ms.assetid: b5d44cce-b05c-47f9-9015-5b10c2312bf1
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dc0160be5aeeef43b9595953893b4ea1af82c62
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-terminate-suspended-orchestration-instances"></a><span data-ttu-id="20ba7-102">Cómo finalizar instancias de orquestación suspendidas</span><span class="sxs-lookup"><span data-stu-id="20ba7-102">How to Terminate Suspended Orchestration Instances</span></span>
<span data-ttu-id="20ba7-103">Puede finalizar cualquier puerto o instancia de orquestación suspendida desde el panel Resultados de la consulta o el panel de previsualización de la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="20ba7-103">You can terminate any suspended orchestration instances or ports from the Query results or preview pane in the BizTalk Server Administration Console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="20ba7-104">Cada instancia de un puerto de envío de entrega ordenada puede tener varios mensajes asociados a él.</span><span class="sxs-lookup"><span data-stu-id="20ba7-104">Each instance of an ordered delivery a send port may have several messages associated with it.</span></span> <span data-ttu-id="20ba7-105">Para evitar pérdida de datos o finalización accidental, compruebe que ha revisado todas las asociaciones de este tipo antes de finalizar la instancia.</span><span class="sxs-lookup"><span data-stu-id="20ba7-105">To prevent accidental termination or data loss, be sure you have reviewed all such associations before terminating an instance.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="20ba7-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="20ba7-106">Prerequisites</span></span>  
 <span data-ttu-id="20ba7-107">Debe ser iniciado sesión como miembro del grupo de operadores de BizTalk Server para llevar a cabo este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="20ba7-107">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-terminate-suspended-orchestration-instances"></a><span data-ttu-id="20ba7-108">Para finalizar instancias de orquestación suspendidas</span><span class="sxs-lookup"><span data-stu-id="20ba7-108">To terminate suspended orchestration instances</span></span>  
  
1.  <span data-ttu-id="20ba7-109">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="20ba7-109">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="20ba7-110">En el árbol de consola, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)] y, a continuación, haga clic en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="20ba7-110">In the console tree, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="20ba7-111">En el panel de detalles, haga clic en el **nueva consulta** ficha.</span><span class="sxs-lookup"><span data-stu-id="20ba7-111">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="20ba7-112">En el **expresión de consulta** grupo, en la **valor** columna, seleccione **instancias de servicio suspendidas** en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="20ba7-112">In the **Query Expression** group, in the **Value** column, select **Suspended Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="20ba7-113">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="20ba7-113">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="20ba7-114">Para finalizar una única instancia, en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione la **nombre del servicio** filtro y, a continuación, en la **valor** columna, especifique el nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="20ba7-114">To terminate a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select the **Service Name** filter and then in the **Value** column, specify the service name.</span></span>  
  
    -   <span data-ttu-id="20ba7-115">Para finalizar instancias de forma masiva en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione **agrupar resultados por** y, a continuación, en el **valor** columna, especifique el nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="20ba7-115">To terminate instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select **Group Results By** and then in the **Value** column, specify the service name.</span></span>  
  
6.  <span data-ttu-id="20ba7-116">Haga clic en **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="20ba7-116">Click **Run Query**.</span></span>  
  
7.  <span data-ttu-id="20ba7-117">En la lista de resultados de la consulta, haga clic en la instancia de orquestación o un grupo de instancias que desea finalizar y, a continuación, haga clic en **finalizar instancia** o **finalizar instancias**.</span><span class="sxs-lookup"><span data-stu-id="20ba7-117">In the query results list, right-click the orchestration instance or group of instances you want to terminate, and then click **Terminate Instance** or **Terminate Instances**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20ba7-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="20ba7-118">See Also</span></span>  
 [<span data-ttu-id="20ba7-119">Investigación de orquestación, puerto y errores de mensaje</span><span class="sxs-lookup"><span data-stu-id="20ba7-119">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)