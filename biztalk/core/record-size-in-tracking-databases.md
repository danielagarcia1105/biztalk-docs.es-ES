---
title: Tamaño de registro para el seguimiento de las bases de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: be7a891b-2674-49a3-a8e0-6aa11a918bf2
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1f4d09d1af92ce4777f5036885d81ea7bf3e648
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268316"
---
# <a name="record-size-in-tracking-databases"></a><span data-ttu-id="d10e3-102">Tamaño de registros en las bases de datos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d10e3-102">Record Size in Tracking Databases</span></span>
<span data-ttu-id="d10e3-103">Para ayudarle a planear los requisitos de hardware de BizTalk, en la tabla siguiente se muestra el tamaño de registro esperado para varios registros de eventos en la base de datos de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d10e3-103">To help you plan your hardware requirements for BizTalk, the following table shows the expected record size for various event records in the Tracking database.</span></span>  
  
|<span data-ttu-id="d10e3-104">Tipo de acción</span><span class="sxs-lookup"><span data-stu-id="d10e3-104">Action Type</span></span>|<span data-ttu-id="d10e3-105">Tamaño</span><span class="sxs-lookup"><span data-stu-id="d10e3-105">Size</span></span>|<span data-ttu-id="d10e3-106">Notas</span><span class="sxs-lookup"><span data-stu-id="d10e3-106">Notes</span></span>|  
|-----------------|----------|-----------|  
|<span data-ttu-id="d10e3-107">Implementar un servicio</span><span class="sxs-lookup"><span data-stu-id="d10e3-107">Deploying a Service</span></span>|<span data-ttu-id="d10e3-108">1864 + información simbólica</span><span class="sxs-lookup"><span data-stu-id="d10e3-108">1864 + Symbolic Information Size</span></span>|<span data-ttu-id="d10e3-109">La información simbólica depende del tamaño de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="d10e3-109">Symbolic Information depends on the size of the orchestration.</span></span> <span data-ttu-id="d10e3-110">Por ejemplo, una orquestación que recibe un mensaje y que envía un mensaje con 2 formas ocupa aproximadamente 4.000 bytes.</span><span class="sxs-lookup"><span data-stu-id="d10e3-110">For example, an orchestration that receives one message and sends one message out with 2 shapes in it takes approximately 4000 bytes.</span></span>|  
|<span data-ttu-id="d10e3-111">Instancia de servicio iniciada y finalizada correctamente</span><span class="sxs-lookup"><span data-stu-id="d10e3-111">Started and Successfully Completed Service Instance</span></span>|<span data-ttu-id="d10e3-112">Normalmente, 252 bytes.</span><span class="sxs-lookup"><span data-stu-id="d10e3-112">Normally 252 bytes.</span></span><br /><br /> <span data-ttu-id="d10e3-113">En casos extremos, puede llegar a tener 735 bytes.</span><span class="sxs-lookup"><span data-stu-id="d10e3-113">Extreme cases, can reach 735 bytes.</span></span>||  
|<span data-ttu-id="d10e3-114">Instancia de servicio iniciada y con errores o una excepción</span><span class="sxs-lookup"><span data-stu-id="d10e3-114">Started and Failed/Exception Met Service Instance</span></span>|<span data-ttu-id="d10e3-115">Normalmente, 252 bytes + información del error.</span><span class="sxs-lookup"><span data-stu-id="d10e3-115">Normally 252 bytes + error information.</span></span><br /><br /> <span data-ttu-id="d10e3-116">En casos extremos, puede llegar a tener 735 bytes + información del error.</span><span class="sxs-lookup"><span data-stu-id="d10e3-116">Extreme cases can reach 735 bytes + error information.</span></span>|<span data-ttu-id="d10e3-117">La información del error hace referencia a los datos de texto devueltos por un componente de BizTalk o de usuario.</span><span class="sxs-lookup"><span data-stu-id="d10e3-117">Error information is the text data returned by a BizTalk or user component.</span></span> <span data-ttu-id="d10e3-118">Puede tener entre 100 bytes y 2 KB.</span><span class="sxs-lookup"><span data-stu-id="d10e3-118">Ranges from 100 bytes to 2 KB.</span></span>|  
|<span data-ttu-id="d10e3-119">Inicio o fin de una forma en una orquestación</span><span class="sxs-lookup"><span data-stu-id="d10e3-119">Start/End of a Shape In an Orchestration</span></span>|<span data-ttu-id="d10e3-120">120 bytes cada uno.</span><span class="sxs-lookup"><span data-stu-id="d10e3-120">120 bytes each.</span></span>||  
|<span data-ttu-id="d10e3-121">eventos de entrada y salida de mensajes</span><span class="sxs-lookup"><span data-stu-id="d10e3-121">Message In/Out Events</span></span>|<span data-ttu-id="d10e3-122">Mínimo 162 bytes.</span><span class="sxs-lookup"><span data-stu-id="d10e3-122">Minimum 162 bytes.</span></span><br /><br /> <span data-ttu-id="d10e3-123">Un mensaje que se ve por primera vez tiene 202 bytes + la propiedad del mensaje (si se realiza su seguimiento).</span><span class="sxs-lookup"><span data-stu-id="d10e3-123">First time message is seen it is 202 bytes + Message Property (if tracked)</span></span><br /><br /> <span data-ttu-id="d10e3-124">En casos extremos, puede llegar a tener 2.930 bytes.</span><span class="sxs-lookup"><span data-stu-id="d10e3-124">Extreme cases can reach 2930 bytes.</span></span>|<span data-ttu-id="d10e3-125">Considere un promedio de 182 bytes si no se realiza el seguimiento de ninguna propiedad del mensaje.</span><span class="sxs-lookup"><span data-stu-id="d10e3-125">You can safely assume that the average is 182 bytes if there is no message property tracking.</span></span>|  
|<span data-ttu-id="d10e3-126">Tamaño de propiedad de mensaje</span><span class="sxs-lookup"><span data-stu-id="d10e3-126">Message Property Size</span></span>|<span data-ttu-id="d10e3-127">De 40 a 288 bytes si DTA reconoce esta propiedad de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d10e3-127">40 to 288 bytes if DTA recognizes this tracking property.</span></span><br /><br /> <span data-ttu-id="d10e3-128">Considere 268 bytes adicionales para realizar un seguimiento de la propiedad la primera vez.</span><span class="sxs-lookup"><span data-stu-id="d10e3-128">Add up to 268 bytes for tracking the property the first time.</span></span>||  
  
## <a name="see-also"></a><span data-ttu-id="d10e3-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="d10e3-129">See Also</span></span>  
 <span data-ttu-id="d10e3-130">[¿Qué es el seguimiento de mensajes?](../core/what-is-message-tracking.md) </span><span class="sxs-lookup"><span data-stu-id="d10e3-130">[What is Message Tracking?](../core/what-is-message-tracking.md) </span></span>  
 [<span data-ttu-id="d10e3-131">Arquitectura de seguimiento y administración</span><span class="sxs-lookup"><span data-stu-id="d10e3-131">Management and Tracking Architecture</span></span>](../core/management-and-tracking-architecture.md)