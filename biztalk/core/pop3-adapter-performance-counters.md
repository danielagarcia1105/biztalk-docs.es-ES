---
title: POP3 Contadores de rendimiento de adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f799175e-e9e7-4937-93bd-aaec1c43b75a
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b0f48879fcc00041ce0fa1cf842a066c6da59804
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="pop3-adapter-performance-counters"></a><span data-ttu-id="46388-102">Contadores de rendimiento del adaptador de POP3</span><span class="sxs-lookup"><span data-stu-id="46388-102">POP3 Adapter Performance Counters</span></span>
<span data-ttu-id="46388-103">Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema.</span><span class="sxs-lookup"><span data-stu-id="46388-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="46388-104">Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="46388-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="46388-105">Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **adaptador de recepción POP3** categoría de objeto de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="46388-105">The following performance counters are accessible for each host instance under the **BizTalk:POP3 Receive Adapter** performance object category:</span></span>  
  
|<span data-ttu-id="46388-106">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="46388-106">**Category**</span></span>|<span data-ttu-id="46388-107">**Contador**</span><span class="sxs-lookup"><span data-stu-id="46388-107">**Counter**</span></span>|<span data-ttu-id="46388-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="46388-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="46388-109">BizTalk:Adaptador de recepción POP3</span><span class="sxs-lookup"><span data-stu-id="46388-109">BizTalk:POP3 Receive Adapter</span></span>|<span data-ttu-id="46388-110">Sesiones activas</span><span class="sxs-lookup"><span data-stu-id="46388-110">Active sessions</span></span>|<span data-ttu-id="46388-111">Número de conexiones POP3 abiertas que el adaptador administra a la vez.</span><span class="sxs-lookup"><span data-stu-id="46388-111">Number of open POP3 connections the POP3 adapter is managing at a time.</span></span>|  
||<span data-ttu-id="46388-112">Bytes recibidos</span><span class="sxs-lookup"><span data-stu-id="46388-112">Bytes received</span></span>|<span data-ttu-id="46388-113">Número total de bytes descargados por el adaptador de POP3 desde el servidor de correo.</span><span class="sxs-lookup"><span data-stu-id="46388-113">Total number of bytes downloaded by the POP3 adapter from a mail server.</span></span>|  
||<span data-ttu-id="46388-114">Bytes recibidos/s</span><span class="sxs-lookup"><span data-stu-id="46388-114">Bytes receive/Sec</span></span>|<span data-ttu-id="46388-115">Número de bytes descargados por segundo por el adaptador de POP3 desde el servidor de correo.</span><span class="sxs-lookup"><span data-stu-id="46388-115">Number of bytes downloaded by the POP3 adapter from a mail server per second.</span></span>|  
||<span data-ttu-id="46388-116">Mensajes recibidos</span><span class="sxs-lookup"><span data-stu-id="46388-116">Messages received</span></span>|<span data-ttu-id="46388-117">Número total de mensajes de correo descargados por el adaptador de POP3 desde el servidor de correo.</span><span class="sxs-lookup"><span data-stu-id="46388-117">Total number of email messages downloaded by the POP3 adapter from a mail server.</span></span>|  
||<span data-ttu-id="46388-118">Mensajes recibidos/s</span><span class="sxs-lookup"><span data-stu-id="46388-118">Messages received/Sec</span></span>|<span data-ttu-id="46388-119">Número de mensajes de correo descargados por segundo por el adaptador de POP3 desde el servidor de correo.</span><span class="sxs-lookup"><span data-stu-id="46388-119">Number of email messages downloaded by the POP3 adapter from mail server per second.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="46388-120">Para tener acceso a los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="46388-120">To access performance counters</span></span>  
 <span data-ttu-id="46388-121">Realice estos pasos para obtener acceso a los contadores de rendimiento para el adaptador de POP3:</span><span class="sxs-lookup"><span data-stu-id="46388-121">Follow these steps to access performance counters for the POP3 adapter:</span></span>  
  
#### <a name="if-you-are-using-windows-2008"></a><span data-ttu-id="46388-122">Si está usando Windows 2008</span><span class="sxs-lookup"><span data-stu-id="46388-122">If you are using Windows 2008</span></span>  
  
1.  <span data-ttu-id="46388-123">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="46388-123">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="46388-124">En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="46388-124">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="46388-125">En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **adaptador de recepción POP3** objeto de contador de rendimiento y seleccione los contadores que pueden supervisar</span><span class="sxs-lookup"><span data-stu-id="46388-125">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:POP3 Receive Adapter** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="46388-126">En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="46388-126">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span>  <span data-ttu-id="46388-127">Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**>.</span><span class="sxs-lookup"><span data-stu-id="46388-127">To select all available counter instances, select \<**All instances**>.</span></span>  
  
5.  <span data-ttu-id="46388-128">Después de agregar los contadores, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46388-128">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="46388-129">Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.</span><span class="sxs-lookup"><span data-stu-id="46388-129">The selected performance counters appear on the **Performance Monitor** screen.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46388-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="46388-130">See Also</span></span>  
 [<span data-ttu-id="46388-131">Supervisión de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="46388-131">Monitoring BizTalk Server</span></span>](../core/monitoring-biztalk-server.md)  
 <span data-ttu-id="46388-132">[Procesar mensajes de varias partes con el adaptador de POP3](../core/processing-multi-part-messages-with-the-pop3-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="46388-132">[Processing Multi Part Messages with the POP3 Adapter](../core/processing-multi-part-messages-with-the-pop3-adapter.md) </span></span>  
 [<span data-ttu-id="46388-133">Consideraciones para ejecutar controladores del adaptador en un Host en clúster</span><span class="sxs-lookup"><span data-stu-id="46388-133">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)