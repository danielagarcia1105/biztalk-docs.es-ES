---
title: "Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Tracking database, database size
ms.assetid: db1126c7-0b86-4635-bfdc-3b69a82cc64b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 327953843b2d9b70f500796f43302320924a330c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-4-sizing-the-tracking-database-for-all-messages"></a><span data-ttu-id="a73ac-102">Escenario 4: Ajustar el tamaño de la base de datos de seguimiento para todos los mensajes</span><span class="sxs-lookup"><span data-stu-id="a73ac-102">Scenario 4: Sizing the Tracking Database for all Messages</span></span>
<span data-ttu-id="a73ac-103">Si tuviera los tres escenarios de mensajes presentes en una implementación de Microsoft® BizTalk Server® 2004, tendría que sumar los resultados de los tres escenarios para determinar el tamaño de la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a73ac-103">If you had all three message scenarios present in a Microsoft® BizTalk Server® 2004 implementation, you would need to add together all of the scenario results to determine the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="a73ac-104">En los ejemplos anteriores:</span><span class="sxs-lookup"><span data-stu-id="a73ac-104">From the examples shown above:</span></span>  
  
|<span data-ttu-id="a73ac-105">Escenario</span><span class="sxs-lookup"><span data-stu-id="a73ac-105">Scenario</span></span>|<span data-ttu-id="a73ac-106">Espacio requerido por año en GB</span><span class="sxs-lookup"><span data-stu-id="a73ac-106">Space required, per year, in GB</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="a73ac-107">Mensajes sencillos</span><span class="sxs-lookup"><span data-stu-id="a73ac-107">Simple messages</span></span>|<span data-ttu-id="a73ac-108">4.78</span><span class="sxs-lookup"><span data-stu-id="a73ac-108">4.78</span></span>|  
|<span data-ttu-id="a73ac-109">Mensajes de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="a73ac-109">Messages in orchestrations</span></span>|<span data-ttu-id="a73ac-110">7.18</span><span class="sxs-lookup"><span data-stu-id="a73ac-110">7.18</span></span>|  
|<span data-ttu-id="a73ac-111">Mensajes de orquestaciones enviados a listas de distribución</span><span class="sxs-lookup"><span data-stu-id="a73ac-111">Messages in orchestrations sent out to distribution lists</span></span>|<span data-ttu-id="a73ac-112">10.8</span><span class="sxs-lookup"><span data-stu-id="a73ac-112">10.8</span></span>|  
|<span data-ttu-id="a73ac-113">**Total**</span><span class="sxs-lookup"><span data-stu-id="a73ac-113">**Total**</span></span>|<span data-ttu-id="a73ac-114">22.04</span><span class="sxs-lookup"><span data-stu-id="a73ac-114">22.04</span></span>|  
  
 <span data-ttu-id="a73ac-115">Además, si activamos el seguimiento del cuerpo de los mensajes para los tres escenarios, tendríamos los siguientes resultados:</span><span class="sxs-lookup"><span data-stu-id="a73ac-115">In addition, if we turn on message body tracking for all three scenarios, we would get the following results:</span></span>  
  
|<span data-ttu-id="a73ac-116">Escenario</span><span class="sxs-lookup"><span data-stu-id="a73ac-116">Scenario</span></span>|<span data-ttu-id="a73ac-117">Espacio requerido por año en GB</span><span class="sxs-lookup"><span data-stu-id="a73ac-117">Space required, per year, in GB</span></span>|  
|--------------|-------------------------------------|  
|<span data-ttu-id="a73ac-118">Mensajes sencillos</span><span class="sxs-lookup"><span data-stu-id="a73ac-118">Simple messages</span></span>|<span data-ttu-id="a73ac-119">50.1</span><span class="sxs-lookup"><span data-stu-id="a73ac-119">50.1</span></span>|  
|<span data-ttu-id="a73ac-120">Mensajes de orquestaciones</span><span class="sxs-lookup"><span data-stu-id="a73ac-120">Messages in orchestrations</span></span>|<span data-ttu-id="a73ac-121">50.1</span><span class="sxs-lookup"><span data-stu-id="a73ac-121">50.1</span></span>|  
|<span data-ttu-id="a73ac-122">Mensajes de orquestaciones enviados a listas de distribución</span><span class="sxs-lookup"><span data-stu-id="a73ac-122">Messages in orchestrations sent out to distribution lists</span></span>|<span data-ttu-id="a73ac-123">83.45</span><span class="sxs-lookup"><span data-stu-id="a73ac-123">83.45</span></span>|  
|<span data-ttu-id="a73ac-124">**Total**</span><span class="sxs-lookup"><span data-stu-id="a73ac-124">**Total**</span></span>|<span data-ttu-id="a73ac-125">183.65</span><span class="sxs-lookup"><span data-stu-id="a73ac-125">183.65</span></span>|  
  
 <span data-ttu-id="a73ac-126">Esto supondría un aumento total de la base de datos de seguimiento de BizTalk de 205,69 GB al año.</span><span class="sxs-lookup"><span data-stu-id="a73ac-126">This would give you a grand total of 205.69 GB per year growth on the BizTalk Tracking database.</span></span> <span data-ttu-id="a73ac-127">Esta cifra no incluye ninguna contingencia.</span><span class="sxs-lookup"><span data-stu-id="a73ac-127">This figure does not include any contingency.</span></span> <span data-ttu-id="a73ac-128">Si decidiera agregar una contingencia del 10% a este total, como se recomienda, debería planear un crecimiento de la base de datos de seguimiento de BizTalk de 227,94 GB por año.</span><span class="sxs-lookup"><span data-stu-id="a73ac-128">If you decided to add a contingency of 10 percent to this total, as is recommended, then you should plan on the BizTalk Tracking database growing 227.94 GB per year.</span></span> <span data-ttu-id="a73ac-129">Además, debe considerar la sobrecarga producida por los índices de SQL, almacenamiento, etcetera. Se debe basar el factor de multiplicación después de ejecutar los escenarios de prueba en pruebas si es posible.</span><span class="sxs-lookup"><span data-stu-id="a73ac-129">On top of this, you should consider the overhead due to SQL indices, storage, etc. You should base your multiplying factor after running the test scenarios in test if possible.</span></span>  
  
## <a name="other-factors-affecting-biztalk-tracking-database-size"></a><span data-ttu-id="a73ac-130">Otros factores que inciden en el tamaño de la base de datos de seguimiento de BizTalk</span><span class="sxs-lookup"><span data-stu-id="a73ac-130">Other factors affecting BizTalk Tracking database size</span></span>  
 <span data-ttu-id="a73ac-131">Hay otros elementos, como las formas utilizadas en una orquestación, que también afectan al tamaño de la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a73ac-131">There are other items, such as the shapes used within an orchestration that also affect the size of the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="a73ac-132">Si la opción del depurador de orquestaciones está activada, que es la configuración predeterminada, el estado de cada forma de la orquestación se guarda en la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a73ac-132">If the orchestration debugger option is turned on, which it is by default, the status of each shape in the orchestration is saved to the BizTalk Tracking database.</span></span>  
  
 <span data-ttu-id="a73ac-133">La fórmula para determinar el tamaño necesario para mantener un seguimiento del estado de las formas es:</span><span class="sxs-lookup"><span data-stu-id="a73ac-133">The formula to determine the size needed to track shape status is:</span></span>  
  
```  
[(# of object shapes ] * 76 bytes  
```  
  
 <span data-ttu-id="a73ac-134">Por ejemplo, en la siguiente ilustración se utiliza la siguiente fórmula para determinar el tamaño del seguimiento de BizTalk:</span><span class="sxs-lookup"><span data-stu-id="a73ac-134">For example, in the following figure, you would use the following formula to determine the BizTalk Tracking size:</span></span>  
  
```  
((4) * 76 bytes = 304 bytes  
```  
  
 <span data-ttu-id="a73ac-135">![Ejemplo de orquestación](../core/media/sample-orchestration.gif "Sample_orchestration")</span><span class="sxs-lookup"><span data-stu-id="a73ac-135">![Orchestration Example](../core/media/sample-orchestration.gif "Sample_orchestration")</span></span>  
  
 <span data-ttu-id="a73ac-136">Si asumimos que esta orquestación procesa 3,5 millones de mensajes, el espacio adicional necesario para mantener un seguimiento de esta orquestación sería:</span><span class="sxs-lookup"><span data-stu-id="a73ac-136">If we assume that this orchestration processes 3.5 million messages, the additional space needed to track this orchestration would be:</span></span>  
  
```  
304 bytes * 3,500,000/1024/1024 = 1015 MB ~ 0.99 GB.  
```  
  
 <span data-ttu-id="a73ac-137">Deberá tener en cuenta cada orquestación que tenga "activado" el depurador de orquestaciones para obtener un tamaño aproximado de la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a73ac-137">You will need to account for each orchestration that has the orchestration debugger set to "on" to get an approximate size for the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a73ac-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="a73ac-138">See Also</span></span>  
 <span data-ttu-id="a73ac-139">[Usar Variables de mensaje para cambiar el tamaño de la base de datos de seguimiento](../core/using-message-variables-to-size-the-tracking-database.md) </span><span class="sxs-lookup"><span data-stu-id="a73ac-139">[Using Message Variables to Size the Tracking Database](../core/using-message-variables-to-size-the-tracking-database.md) </span></span>  
 <span data-ttu-id="a73ac-140">[Ajustar el tamaño de la base de datos de seguimiento para realizar el seguimiento de cuerpos de mensaje](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span><span class="sxs-lookup"><span data-stu-id="a73ac-140">[Sizing the Tracking Database to Track Message Bodies](../core/sizing-the-tracking-database-to-track-message-bodies.md) </span></span>  
 <span data-ttu-id="a73ac-141">[Escenario 1: Ajustar el tamaño de la base de datos de seguimiento para mensajes sencillos de BizTalk](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span><span class="sxs-lookup"><span data-stu-id="a73ac-141">[Scenario 1: Sizing the Tracking Database  for Simple BizTalk Messages](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md) </span></span>  
 <span data-ttu-id="a73ac-142">[Escenario 2: Ajustar el tamaño de la base de datos de seguimiento para mensajes de orquestaciones](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="a73ac-142">[Scenario 2: Sizing the Tracking Database  for Messages in Orchestrations](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="a73ac-143">Escenario 3: Ajustar el tamaño de la base de datos de seguimiento para los mensajes enviados a listas de distribución</span><span class="sxs-lookup"><span data-stu-id="a73ac-143">Scenario 3: Sizing the Tracking Database  for Messages Sent Out to Distribution Lists</span></span>](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)