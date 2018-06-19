---
title: Cómo reanudar instancias de orquestación suspendidas | Documentos de Microsoft
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
ms.openlocfilehash: 6696547ce3e918dc8d84b7cfcb4f24e31c8b70a0
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22316896"
---
# <a name="how-to-resume-suspended-orchestration-instances"></a><span data-ttu-id="a4944-102">Cómo reanudar instancias de orquestación suspendidas</span><span class="sxs-lookup"><span data-stu-id="a4944-102">How to Resume Suspended Orchestration Instances</span></span>
<span data-ttu-id="a4944-103">Si ha suspendido instancias de orquestación enumeradas como "suspendidas reanudables", puede intentar reanudarlas desde el panel de previsualización o de resultados de consulta.</span><span class="sxs-lookup"><span data-stu-id="a4944-103">If you have suspended orchestration instances that are listed as "suspended resumable," you can attempt to resume the orchestration instance from the query results or preview pane.</span></span> <span data-ttu-id="a4944-104">La reanudación de la instancia de orquestación sólo se realizará correctamente si el problema subyacente que ocasionó su suspensión se ha resuelto.</span><span class="sxs-lookup"><span data-stu-id="a4944-104">Resuming the orchestration instance will only succeed if the underlying problem that caused the orchestration instance to become suspended has also been fixed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a4944-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a4944-105">Prerequisites</span></span>  
 <span data-ttu-id="a4944-106">Debe ser iniciado sesión como miembro del grupo de operadores de BizTalk Server para llevar a cabo este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="a4944-106">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-resume-suspended-orchestration-instances"></a><span data-ttu-id="a4944-107">Para reanudar instancias de orquestación suspendidas</span><span class="sxs-lookup"><span data-stu-id="a4944-107">To resume suspended orchestration instances</span></span>  
  
1.  <span data-ttu-id="a4944-108">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="a4944-108">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a4944-109">En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a4944-109">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="a4944-110">En el panel de detalles, haga clic en el **nueva consulta** ficha.</span><span class="sxs-lookup"><span data-stu-id="a4944-110">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="a4944-111">En el **expresión de consulta** grupo, en la **valor** columna, seleccione **instancias de servicio suspendidas** en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="a4944-111">In the **Query Expression** group, in the **Value** column, select **Suspended Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="a4944-112">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="a4944-112">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="a4944-113">Para reanudar una única instancia, en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione la **nombre del servicio** filtro y a continuación, en la **valor** columna, especifique el nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="a4944-113">To resume a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select the **Service Name** filter and then in the **Value** column, specify the service name.</span></span>  
  
    -   <span data-ttu-id="a4944-114">Para reanudar las instancias de forma masiva en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione **agrupar resultados por** y, a continuación, en el **valor** columna, especifique el nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="a4944-114">To resume instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select **Group Results By** and then in the **Value** column, specify the service name.</span></span>  
  
6.  <span data-ttu-id="a4944-115">Haga clic en **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="a4944-115">Click **Run Query**.</span></span>  
  
7.  <span data-ttu-id="a4944-116">En la lista de resultados de la consulta, haga clic en la instancia de orquestación que desea reanudar y, a continuación, haga clic en **reanudar instancia** o **Reanudar instancias**.</span><span class="sxs-lookup"><span data-stu-id="a4944-116">In the query results list, right-click the orchestration instance you want to resume, and then click **Resume Instance** or **Resume Instances**.</span></span> <span data-ttu-id="a4944-117">Esto permite seleccionar las instancias que desea reanudar.</span><span class="sxs-lookup"><span data-stu-id="a4944-117">This allows you to select which instances to resume.</span></span>  
  
     <span data-ttu-id="a4944-118">[Estados de la instancia de servicio](../core/service-instance-states.md) proporciona más información sobre el en estado suspendido.</span><span class="sxs-lookup"><span data-stu-id="a4944-118">[Service Instance States](../core/service-instance-states.md) provides more information on the on the suspended state.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4944-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4944-119">See Also</span></span>  
 [<span data-ttu-id="a4944-120">Investigación de errores de mensaje, orquestación y puerto</span><span class="sxs-lookup"><span data-stu-id="a4944-120">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)
