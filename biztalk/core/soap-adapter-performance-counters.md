---
title: Contadores de rendimiento del adaptador SOAP | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 40b54d4e-0a2e-483f-982a-97ab9fb59202
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 543c982a68d2a940b4800711d757f4fb159611de
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="soap-adapter-performance-counters"></a><span data-ttu-id="8fdb4-102">Contadores de rendimiento del adaptador de SOAP</span><span class="sxs-lookup"><span data-stu-id="8fdb4-102">SOAP Adapter Performance Counters</span></span>
<span data-ttu-id="8fdb4-103">Los contadores de rendimiento le permiten controlar aspectos específicos del trabajo realizado por el servicio en el sitio o sistema.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-103">Performance counters allow you to monitor specific aspects of work performed on the site or system by service.</span></span> <span data-ttu-id="8fdb4-104">Los contadores de rendimiento pueden ayudarle a identificar y solucionar problemas de rendimiento del servidor.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-104">Performance counters can help you identify and troubleshoot server performance issues.</span></span>  
  
 <span data-ttu-id="8fdb4-105">Los siguientes contadores de rendimiento son accesibles para cada instancia de host en el **BizTalk: adaptador de recepción** y **BizTalk: adaptador de envío** categorías de objetos de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="8fdb4-105">The following performance counters are accessible for each host instance under the **BizTalk:SOAP Receive Adapter** and the **BizTalk:SOAP Send Adapter** performance object categories:</span></span>  
  
|<span data-ttu-id="8fdb4-106">**Categoría**</span><span class="sxs-lookup"><span data-stu-id="8fdb4-106">**Category**</span></span>|<span data-ttu-id="8fdb4-107">**Contador**</span><span class="sxs-lookup"><span data-stu-id="8fdb4-107">**Counter**</span></span>|<span data-ttu-id="8fdb4-108">**Description**</span><span class="sxs-lookup"><span data-stu-id="8fdb4-108">**Description**</span></span>|  
|------------------|-----------------|---------------------|  
|<span data-ttu-id="8fdb4-109">BizTalk:Adaptador de recepción SOAP</span><span class="sxs-lookup"><span data-stu-id="8fdb4-109">BizTalk:SOAP Receive Adapter</span></span>|<span data-ttu-id="8fdb4-110">Mensajes recibidos</span><span class="sxs-lookup"><span data-stu-id="8fdb4-110">Messages received</span></span>|<span data-ttu-id="8fdb4-111">Número total de mensajes recibidos por el adaptador de recepción SOAP.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-111">Total number of messages received by the SOAP receive adapter.</span></span> <span data-ttu-id="8fdb4-112">El contador aumenta cuando el adaptador lee completamente un mensaje de solicitud desde el cliente SOAP.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-112">The counter is incremented after a request message is completely read by the adapter from the SOAP client.</span></span>|  
||<span data-ttu-id="8fdb4-113">Mensajes recibidos/s</span><span class="sxs-lookup"><span data-stu-id="8fdb4-113">Messages received/Sec</span></span>|<span data-ttu-id="8fdb4-114">Número de mensajes recibidos por el adaptador de recepción SOAP por segundo.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-114">Number of messages received by the SOAP receive adapter per second.</span></span> <span data-ttu-id="8fdb4-115">El contador sólo es aplicable a los mensajes de solicitud que el adaptador ha leído completamente desde el cliente SOAP.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-115">The counter applies only to request messages that have been completely read by the adapter from the SOAP client.</span></span>|  
|<span data-ttu-id="8fdb4-116">BizTalk:Adaptador de envío SOAP</span><span class="sxs-lookup"><span data-stu-id="8fdb4-116">BizTalk:SOAP Send Adapter</span></span>|<span data-ttu-id="8fdb4-117">Mensajes enviados</span><span class="sxs-lookup"><span data-stu-id="8fdb4-117">Messages sent</span></span>|<span data-ttu-id="8fdb4-118">Número total de mensajes enviados por el adaptador de envío SOAP.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-118">Total number of messages sent by the SOAP send adapter.</span></span> <span data-ttu-id="8fdb4-119">El contador sólo aumenta con mensajes que han alcanzado la dirección URL de destino.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-119">The counter is incremented only for messages that have reached the destination URL.</span></span>|  
||<span data-ttu-id="8fdb4-120">Mensajes enviados/s</span><span class="sxs-lookup"><span data-stu-id="8fdb4-120">Messages sent/Sec</span></span>|<span data-ttu-id="8fdb4-121">Número de mensajes enviados por el adaptador de envío SOAP por segundo.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-121">Number of messages sent by the SOAP send adapter per second.</span></span> <span data-ttu-id="8fdb4-122">El contador sólo es aplicable a mensajes que han alcanzado la dirección URL de destino.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-122">The counter applies only to messages that have reached the destination URL.</span></span>|  
  
## <a name="to-access-performance-counters"></a><span data-ttu-id="8fdb4-123">Para tener acceso a los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="8fdb4-123">To access performance counters</span></span>  
 <span data-ttu-id="8fdb4-124">Siga los pasos que se indican a continuación para obtener acceso a los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-124">Use the following steps to access the performance counters.</span></span>  
  
#### <a name="if-you-are-using-windows-server-2008"></a><span data-ttu-id="8fdb4-125">Si usa Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="8fdb4-125">If you are using Windows Server 2008</span></span>  
  
1.  <span data-ttu-id="8fdb4-126">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Monitor de rendimiento**.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-126">Click **Start**, point to **Administrative Tools**, and then click **Performance Monitor**.</span></span>  
  
2.  <span data-ttu-id="8fdb4-127">En el **Monitor de rendimiento** cuadro de diálogo, expanda **herramientas de supervisión**, seleccione **Monitor de rendimiento**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-127">In the **Performance Monitor** dialog box, expand **Monitoring Tools**, select **Performance Monitor**, and then click **Add**.</span></span>  
  
3.  <span data-ttu-id="8fdb4-128">En el **agregar contadores** cuadro de diálogo, desde el **contadores disponibles** lista, expanda la **BizTalk** objeto de contador de rendimiento y seleccione los contadores que desea supervisar</span><span class="sxs-lookup"><span data-stu-id="8fdb4-128">In the **Add Counters** dialog box, from the **Available Counters** list, expand the **BizTalk:SOAP** performance counter object and select the counters to be monitored</span></span>  
  
4.  <span data-ttu-id="8fdb4-129">En el **instancias del objeto seleccionado** , seleccione las instancias específicas que se deben supervisar en los contadores seleccionados y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-129">In the **Instances of Selected object** list, select the specific instances to be monitored for the selected counters and then click **Add**.</span></span> <span data-ttu-id="8fdb4-130">Para seleccionar todas las instancias de contador disponibles, seleccione \< **todas las instancias**\>.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-130">To select all available counter instances, select \<**All instances**\>.</span></span>  
  
5.  <span data-ttu-id="8fdb4-131">Después de agregar los contadores, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-131">After adding the counters, click **OK**.</span></span>  
  
     <span data-ttu-id="8fdb4-132">Los contadores de rendimiento seleccionados aparecen en la **Monitor de rendimiento** pantalla.</span><span class="sxs-lookup"><span data-stu-id="8fdb4-132">The selected performance counters appear on the **Performance Monitor** screen.</span></span>