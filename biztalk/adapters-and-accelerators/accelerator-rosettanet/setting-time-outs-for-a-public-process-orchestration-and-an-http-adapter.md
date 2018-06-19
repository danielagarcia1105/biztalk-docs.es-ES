---
title: Establecer los tiempos de espera para una orquestación de proceso público y un adaptador de HTTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- public processes, HTTP adapters
- public processes, orchestrations
- orchestrations, time-outs
- public processes, time-outs
- orchestrations, public-process orchestrations
- HTTP adapters, public processes
- HTTP adapters, time-outs
ms.assetid: 82fd64ac-6191-410c-94b3-8a3d1ff2611f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 339f4eb5fa11b23602d05f8cd75c30ca3aa16279
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963298"
---
# <a name="setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter"></a><span data-ttu-id="607ef-102">Establecer los tiempos de espera para una orquestación de proceso público y un adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="607ef-102">Setting Time-Outs for a Public-Process Orchestration and an HTTP Adapter</span></span>
<span data-ttu-id="607ef-103">Cuando se utiliza una orquestación de proceso público con un adaptador de HTTP en un escenario sincrónico, debe establecer los tiempos de espera para cada uno de ellos correctamente.</span><span class="sxs-lookup"><span data-stu-id="607ef-103">When you use a public-process orchestration with an HTTP adapter in a synchronous scenario, you must set the time-outs for each appropriately.</span></span> <span data-ttu-id="607ef-104">El valor de tiempo de espera para la orquestación (tiempo para realizar) debe ser menor que el tiempo de espera para el adaptador HTTP (tiempo de espera de solicitud).</span><span class="sxs-lookup"><span data-stu-id="607ef-104">The time-out setting for the orchestration (Time to Perform) must be smaller than the time-out for the HTTP adapter (Request Timeout).</span></span> <span data-ttu-id="607ef-105">Esto es porque si la configuración del adaptador de HTTP es menor, pudo instalar el adaptador de tiempo de espera antes de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="607ef-105">This is because if the setting for the HTTP adapter is smaller, the adapter could time out before the orchestration.</span></span> <span data-ttu-id="607ef-106">Esto proporciona al control de adaptador del proceso.</span><span class="sxs-lookup"><span data-stu-id="607ef-106">This gives the adapter control of the process.</span></span> <span data-ttu-id="607ef-107">La orquestación debe tener el control del proceso; por lo tanto, su valor de tiempo de espera debe ser menor.</span><span class="sxs-lookup"><span data-stu-id="607ef-107">The orchestration must be in control of the process; therefore, its time-out setting must be smaller.</span></span>  
  
### <a name="to-set-the-time-out-setting-for-the-http-adapter"></a><span data-ttu-id="607ef-108">Para establecer la configuración de tiempo de espera del adaptador de HTTP</span><span class="sxs-lookup"><span data-stu-id="607ef-108">To set the time-out setting for the HTTP adapter</span></span>  
  
1.  <span data-ttu-id="607ef-109">En el Explorador de BizTalk, expanda **puertos de envío**y, a continuación, haga doble clic en el puerto de envío HTTP con la orquestación de proceso público.</span><span class="sxs-lookup"><span data-stu-id="607ef-109">In BizTalk Explorer, expand **Send ports**, and then double-click the HTTP send port used with the public-process orchestration.</span></span>  
  
2.  <span data-ttu-id="607ef-110">En la ventana Propiedades de puerto de envío, haga clic en el botón de puntos suspensivos (**...** ) para **dirección (URI)**.</span><span class="sxs-lookup"><span data-stu-id="607ef-110">In the Send Port Properties window, click the ellipsis button (**...**) for **Address (URI)**.</span></span>  
  
3.  <span data-ttu-id="607ef-111">En la ventana de propiedades de transporte HTTP, en el panel General, en la **solicitar tiempo de espera (seg.)** , escriba un valor adecuado para el tiempo de espera. Este valor debe ser mayor que el **tiempo para realizar** establecer para el proceso de interfaz de socio (PIP) pertinentes.</span><span class="sxs-lookup"><span data-stu-id="607ef-111">In the HTTP Transport Properties window, in the General pane, in the **Request timeout (sec.)** box, type an appropriate value for the time-out. This value must be larger than the **Time to Perform** setting for the relevant Partner Interface Process (PIP).</span></span>  
  
4.  <span data-ttu-id="607ef-112">Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.</span><span class="sxs-lookup"><span data-stu-id="607ef-112">Click **OK**, and then click **OK** again.</span></span>  
  
### <a name="to-set-the-time-out-setting-for-the-public-process-orchestration"></a><span data-ttu-id="607ef-113">Para establecer la configuración de tiempo de espera para la orquestación de proceso público</span><span class="sxs-lookup"><span data-stu-id="607ef-113">To set the time-out setting for the public-process orchestration</span></span>  
  
1.  <span data-ttu-id="607ef-114">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en  **Acelerador de BizTalk para RosettaNet Management Console**.</span><span class="sxs-lookup"><span data-stu-id="607ef-114">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click  **BizTalk Accelerator for RosettaNet Management Console**.</span></span>  
  
2.  <span data-ttu-id="607ef-115">Expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en **configuración del proceso**.</span><span class="sxs-lookup"><span data-stu-id="607ef-115">Expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click **Process Configuration Settings**.</span></span>  
  
3.  <span data-ttu-id="607ef-116">Haga clic en el PIP que desea establecer el tiempo de espera de y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="607ef-116">Right-click the PIP that you want to set the time-out setting for, and then click **Properties**.</span></span>  
  
4.  <span data-ttu-id="607ef-117">En el cuadro de diálogo de theProperties, en la **actividad** ficha la **tiempo para realizar** , escriba un valor adecuado que es menor que el tiempo de espera del adaptador HTTP establecer y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="607ef-117">In theProperties dialog box, on the **Activity** tab, in the **Time to Perform** box, type an appropriate value that is smaller than the HTTP adapter time-out setting, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="607ef-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="607ef-118">See Also</span></span>  
 [<span data-ttu-id="607ef-119">Guía de programación</span><span class="sxs-lookup"><span data-stu-id="607ef-119">Programming Guide</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)