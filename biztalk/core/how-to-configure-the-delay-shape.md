---
title: "Cómo configurar la forma retraso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Delay shape [Orchestration Designer], configuring
- Delay shape [Orchestration Designer]
- Delay shape [Orchestration Designer], timeouts
- Delay shape [Orchestration Designer], about Delay shape
- configuring [Orchestration Designer], Delay shapes
ms.assetid: 727be28d-932a-41d5-af3f-3ee6f7129a17
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b76448398facd3af7f3b9712491f9895ffb406d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-delay-shape"></a><span data-ttu-id="4895e-102">Cómo configurar la forma Retraso</span><span class="sxs-lookup"><span data-stu-id="4895e-102">How to Configure the Delay Shape</span></span>
![](../core/media/ebiz-orch-delay.gif "ebiz_orch_delay")  
<span data-ttu-id="4895e-103">Forma Retraso</span><span class="sxs-lookup"><span data-stu-id="4895e-103">Delay shape</span></span>  
  
 <span data-ttu-id="4895e-104">Hay dos maneras de especificar el tiempo de espera para una **retraso**:</span><span class="sxs-lookup"><span data-stu-id="4895e-104">There are two ways to specify the timeout for a **Delay**:</span></span>  
  
-   <span data-ttu-id="4895e-105">Puede usar **System.DateTime**, lo que hace que la orquestación se pause hasta que la fecha especificada y se alcanza el tiempo.</span><span class="sxs-lookup"><span data-stu-id="4895e-105">You can use **System.DateTime**, which causes your orchestration to pause until the specified date and time is reached.</span></span>  
  
     <span data-ttu-id="4895e-106">System.DateTime.UtcNow.AddSeconds(60)</span><span class="sxs-lookup"><span data-stu-id="4895e-106">System.DateTime.UtcNow.AddSeconds(60)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4895e-107">Retrasos deben expresar en hora Universal coordinada (UTC) cuando se usa **DateTime**.</span><span class="sxs-lookup"><span data-stu-id="4895e-107">Delays must be expressed in Coordinated Universal Time (UTC) when using **DateTime**.</span></span>  
  
-   <span data-ttu-id="4895e-108">Puede usar **System.TimeSpan**, lo que hace que la orquestación durante el período de tiempo especificado.</span><span class="sxs-lookup"><span data-stu-id="4895e-108">You can use **System.TimeSpan**, which causes your orchestration to pause for the specified length of time.</span></span>  
  
     <span data-ttu-id="4895e-109">System.TimeSpan(0, 1, 0)</span><span class="sxs-lookup"><span data-stu-id="4895e-109">System.TimeSpan(0, 1, 0)</span></span>  
  
 <span data-ttu-id="4895e-110">Si su **retraso** forma está dentro de un **escuchar** forma, no es necesario agregar un punto y coma al final de la expresión.</span><span class="sxs-lookup"><span data-stu-id="4895e-110">If your **Delay** shape is inside a **Listen** shape, you do not need to add a semicolon at the end of the expression.</span></span>  
  
 <span data-ttu-id="4895e-111">Para obtener más información acerca de **System.DateTime** y **System.TimeSpan**, consulte "DateTime (estructura)" y "TimeSpan (estructura)" en la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] colección combinada.</span><span class="sxs-lookup"><span data-stu-id="4895e-111">For more information about **System.DateTime** and **System.TimeSpan**, see "DateTime Structure" and "TimeSpan Structure" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Combined Collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4895e-112">En un entorno de instalación de varios equipos donde [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y SQL Server están instalados en equipos separados, la **retraso** forma puede finalizar antes de lo esperado debido a las horas en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] y [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] máquinas no están sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="4895e-112">In a multiple machines installation environment where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and SQL Server are installed on separated machines, the **Delay** shape may end earlier than expected because of the times on [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] machines are unsynchronized.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4895e-113">En condiciones de sobrecarga, el tiempo de espera especificado en el **retraso** forma posible se prolongue más de lo especificado.</span><span class="sxs-lookup"><span data-stu-id="4895e-113">Under the stress condition, the timeout specified in the **Delay** shape may occur later than what you have specified.</span></span> <span data-ttu-id="4895e-114">Esto se debe a la falta de subprocesos en condiciones de sobrecarga.</span><span class="sxs-lookup"><span data-stu-id="4895e-114">This is because of the thread starvation under the stress condition.</span></span>  
  
### <a name="to-configure-a-delay-shape"></a><span data-ttu-id="4895e-115">Para configurar una forma Retraso</span><span class="sxs-lookup"><span data-stu-id="4895e-115">To configure a Delay shape</span></span>  
  
1.  <span data-ttu-id="4895e-116">Si el Editor de expresiones de BizTalk no está visible, haga clic en el **retraso** forma y haga clic en **editar retraso**, o en la ventana Propiedades, haga clic en el **puntos suspensivos** ( **...** ) botón la **expresión** propiedad.</span><span class="sxs-lookup"><span data-stu-id="4895e-116">If BizTalk Expression Editor is not visible, right-click the **Delay** shape and click **Edit Delay**, or in the Properties window, click the **Ellipsis** (**...**) button for the **Expression** property.</span></span>  
  
2.  <span data-ttu-id="4895e-117">En el Editor de expresiones de BizTalk, cree una expresión que devuelve un **System.DateTime** objeto o un **System.TimeSpan** objeto.</span><span class="sxs-lookup"><span data-stu-id="4895e-117">In BizTalk Expression Editor, create an expression that returns a **System.DateTime** object or a **System.TimeSpan** object.</span></span> <span data-ttu-id="4895e-118">Para obtener más información, consulte [requisitos y limitaciones para las expresiones](../core/requirements-and-limitations-for-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="4895e-118">For more information, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span>