---
title: Cómo suspender puertos o instancias de orquestación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, suspending
- instances, suspending
- suspending
- HAT, suspending orchestrations
- HAT, suspending pipelines
- suspending, ports
- suspending, orchestrations
- orchestrations, suspending
- HAT, suspending ports
- suspending, instances
- ports, suspending
ms.assetid: cacc7e58-7d3e-4d6b-adb0-618fdc4f0d89
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62d91c8d1e02b7283a430f7c82c572b6a989d108
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "22256700"
---
# <a name="how-to-suspend-orchestration-instances-or-ports"></a><span data-ttu-id="c8d1c-102">Cómo suspender puertos o instancias de orquestación</span><span class="sxs-lookup"><span data-stu-id="c8d1c-102">How to Suspend Orchestration Instances or Ports</span></span>
<span data-ttu-id="c8d1c-103">Puede suspender puertos o instancias de orquestación desde una lista de resultados de consulta de la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c8d1c-103">You can suspend orchestration instances or ports from a query results list in the BizTalk Server Administration Console.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c8d1c-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c8d1c-104">Prerequisites</span></span>  
 <span data-ttu-id="c8d1c-105">Debe ser iniciado sesión como miembro del grupo de operadores de BizTalk Server para llevar a cabo este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="c8d1c-105">You must be logged on as a member of the BizTalk Server Operators group to perform this procedure.</span></span>  
  
### <a name="to-suspend-orchestration-instances-or-ports"></a><span data-ttu-id="c8d1c-106">Para suspender puertos o instancias de orquestación</span><span class="sxs-lookup"><span data-stu-id="c8d1c-106">To suspend orchestration instances or ports</span></span>  
  
1.  <span data-ttu-id="c8d1c-107">Haga clic en **iniciar**, haga clic en **programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="c8d1c-107">Click **Start**, click **Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="c8d1c-108">En el árbol de consola, expanda **administración de BizTalk Server**y, a continuación, haga clic en el grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c8d1c-108">In the console tree, expand **BizTalk Server Administration**, and then click the BizTalk group.</span></span>  
  
3.  <span data-ttu-id="c8d1c-109">En el panel de detalles, haga clic en el **nueva consulta** ficha.</span><span class="sxs-lookup"><span data-stu-id="c8d1c-109">In the details pane, click the **New Query** tab.</span></span>  
  
4.  <span data-ttu-id="c8d1c-110">En el **expresión de consulta** grupo, en la **valor** columna, seleccione **instancias de servicio en ejecución** en el cuadro de lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="c8d1c-110">In the **Query Expression** group, in the **Value** column, select **Running Service Instances** from the drop-down list box.</span></span>  
  
5.  <span data-ttu-id="c8d1c-111">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="c8d1c-111">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="c8d1c-112">Para suspender una única instancia, en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione la **nombre del servicio** filtro y a continuación, en la **valor** columna, especifique el nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="c8d1c-112">To suspend a single instance, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select the **Service Name** filter and then in the **Value** column, specify the service name.</span></span>  
  
    -   <span data-ttu-id="c8d1c-113">Para suspender las instancias de forma masiva en la **nombre de campo** columna, en el cuadro de lista desplegable vacía situada junto al asterisco (**\***), seleccione **agrupar resultados por** y, a continuación, en el **valor** columna, especifique el nombre del servicio.</span><span class="sxs-lookup"><span data-stu-id="c8d1c-113">To suspend instances in bulk, in the **Field Name** column, in the empty drop-down list box next to the asterisk (**\***), select **Group Results By** and then in the **Value** column, specify the service name.</span></span>  
  
6.  <span data-ttu-id="c8d1c-114">Haga clic en **Ejecutar consulta**.</span><span class="sxs-lookup"><span data-stu-id="c8d1c-114">Click **Run Query**.</span></span>  
  
7.  <span data-ttu-id="c8d1c-115">En la lista de resultados de la consulta, haga clic en la orquestación activa o el puerto que desea suspender y, a continuación, haga clic en **Suspender instancia** o **suspender instancias**.</span><span class="sxs-lookup"><span data-stu-id="c8d1c-115">In the query results list, right-click the active orchestration or port you want to suspend, and then click **Suspend Instance** or **Suspend Instances**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8d1c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8d1c-116">See Also</span></span>  
 [<span data-ttu-id="c8d1c-117">Investigación de errores de mensaje, orquestación y puerto</span><span class="sxs-lookup"><span data-stu-id="c8d1c-117">Investigating Orchestration, Port, and Message Failures</span></span>](../core/investigating-orchestration-port-and-message-failures.md)