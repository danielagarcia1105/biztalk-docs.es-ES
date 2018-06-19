---
title: Contadores de rendimiento de adaptador de SMTP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0c7aa7dd-1674-4bbb-b22f-92204d55c4b8
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3503b5a37a7b2ab48be2478879cc61187895029
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25973394"
---
# <a name="smtp-adapter-performance-counters"></a><span data-ttu-id="a55c5-102">Contadores de rendimiento del adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="a55c5-102">SMTP Adapter Performance Counters</span></span>
<span data-ttu-id="a55c5-103">Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema.</span><span class="sxs-lookup"><span data-stu-id="a55c5-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="a55c5-104">Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="a55c5-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="a55c5-105">Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **adaptador de envío SMTP** categoría de objeto de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="a55c5-105">The following performance counters are accessible for each host instance under the **BizTalk:SMTP Send Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="a55c5-106">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="a55c5-106">**Category**</span></span>|<span data-ttu-id="a55c5-107">**Contador**</span><span class="sxs-lookup"><span data-stu-id="a55c5-107">**Counter**</span></span>|<span data-ttu-id="a55c5-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="a55c5-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="a55c5-109">BizTalk:Adaptador de envío SMTP</span><span class="sxs-lookup"><span data-stu-id="a55c5-109">BizTalk:SMTP Send Adapter</span></span>|<span data-ttu-id="a55c5-110">Mensajes enviados</span><span class="sxs-lookup"><span data-stu-id="a55c5-110">Messages sent</span></span>|<span data-ttu-id="a55c5-111">Número total de mensajes enviados por el adaptador de SMTP</span><span class="sxs-lookup"><span data-stu-id="a55c5-111">Total number of messages sent by the SMTP adapter.</span></span> <span data-ttu-id="a55c5-112">El contador sólo aumenta con mensajes que se han transmitido al servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="a55c5-112">The counter is incremented only for messages that have been transmitted to the SMTP server.</span></span>|  
||<span data-ttu-id="a55c5-113">Mensajes enviados/s</span><span class="sxs-lookup"><span data-stu-id="a55c5-113">Messages sent/Sec</span></span>|<span data-ttu-id="a55c5-114">Número de mensajes enviados por el adaptador de SMTP por segundo.</span><span class="sxs-lookup"><span data-stu-id="a55c5-114">Number of messages sent by the SMTP adapter per second.</span></span> <span data-ttu-id="a55c5-115">El contador sólo se aplica a mensajes que se han transmitido al servidor SMTP.</span><span class="sxs-lookup"><span data-stu-id="a55c5-115">The counter applies only to messages that have been transmitted to the SMTP server.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="a55c5-116">Para tener acceso a los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="a55c5-116">To access performance counters</span></span>  
 <span data-ttu-id="a55c5-117">Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a55c5-117">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="a55c5-118">Si está usando Windows 2008</span><span class="sxs-lookup"><span data-stu-id="a55c5-118">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="a55c5-119">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="a55c5-119">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="a55c5-120">En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="a55c5-120">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="a55c5-121">En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **adaptador de envío SMTP**objeto de contador de rendimiento y seleccione los contadores que pueden supervisar</span><span class="sxs-lookup"><span data-stu-id="a55c5-121">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:SMTP Send Adapter**performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="a55c5-122">En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="a55c5-122">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="a55c5-123">Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**\>.</span><span class="sxs-lookup"><span data-stu-id="a55c5-123">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="a55c5-124">Después de agregar los contadores, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a55c5-124">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="a55c5-125">Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.</span><span class="sxs-lookup"><span data-stu-id="a55c5-125">The selected performance counters appear on the **Performance Monitor** screen.</span></span>