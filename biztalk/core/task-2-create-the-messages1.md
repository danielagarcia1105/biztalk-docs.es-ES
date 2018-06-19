---
title: 'Tarea 2: Crear el Messages1 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df908ea0-b3be-47e6-99ba-4122cb1db561
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e326662737919e325f95d82b86aa8824e4e3a06
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278852"
---
# <a name="task-2-create-the-messages"></a><span data-ttu-id="9a641-102">Tarea 2: Crear los mensajes</span><span class="sxs-lookup"><span data-stu-id="9a641-102">Task 2: Create the Messages</span></span>
<span data-ttu-id="9a641-103">Crear los siguientes mensajes, se van a utilizar en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="9a641-103">Create the following Messages, they will be used in the orchestration.</span></span>  
  
### <a name="to-create-the-messages"></a><span data-ttu-id="9a641-104">Para crear mensajes</span><span class="sxs-lookup"><span data-stu-id="9a641-104">To create the messages</span></span>  
  
1.  <span data-ttu-id="9a641-105">Haga clic en **mensaje**y, a continuación, seleccione **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="9a641-105">Right-click **Message**, and then select **New Message**.</span></span>  
  
2.  <span data-ttu-id="9a641-106">Cumplimente lo siguiente para el identificador y el tipo de mensaje>esquema, y seleccione el tipo de la lista que aparece para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="9a641-106">Fill in the following for the Identifier and the Message Type>Schema and select the type from the displayed list for each message.</span></span>  
  
    |<span data-ttu-id="9a641-107">Identificador</span><span class="sxs-lookup"><span data-stu-id="9a641-107">Identifier</span></span>|<span data-ttu-id="9a641-108">Tipo de mensaje > esquema</span><span class="sxs-lookup"><span data-stu-id="9a641-108">Message Type>Schema</span></span>|  
    |----------------|--------------------------|  
    |<span data-ttu-id="9a641-109">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="9a641-109">BeginDocMsg</span></span>|<span data-ttu-id="9a641-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="9a641-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="9a641-111">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="9a641-111">BeginDocResponseMsg</span></span>|<span data-ttu-id="9a641-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="9a641-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span></span>|  
    |<span data-ttu-id="9a641-113">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="9a641-113">BeginDocSessionMsg</span></span>|<span data-ttu-id="9a641-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="9a641-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="9a641-115">EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="9a641-115">EditLineMsg</span></span>|<span data-ttu-id="9a641-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="9a641-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="9a641-117">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="9a641-117">EditLineResponseMsg</span></span>|<span data-ttu-id="9a641-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span><span class="sxs-lookup"><span data-stu-id="9a641-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span></span>|  
    |<span data-ttu-id="9a641-119">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="9a641-119">EditLineSessionMsg</span></span>|<span data-ttu-id="9a641-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="9a641-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="9a641-121">EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="9a641-121">EndDocMsg</span></span>|<span data-ttu-id="9a641-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="9a641-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
    |<span data-ttu-id="9a641-123">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="9a641-123">EndDocResponseMsg</span></span>|<span data-ttu-id="9a641-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="9a641-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span></span>|  
    |<span data-ttu-id="9a641-125">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="9a641-125">EndDocSessionMsg</span></span>|<span data-ttu-id="9a641-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="9a641-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9a641-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a641-127">See Also</span></span>  
 <span data-ttu-id="9a641-128">[Tarea 1: Crear los puertos](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="9a641-128">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="9a641-129">[Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="9a641-129">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 <span data-ttu-id="9a641-130">[Tarea 4: Configurar la forma construir mensaje](../core/task-4-configure-the-construct-message-shape2.md) </span><span class="sxs-lookup"><span data-stu-id="9a641-130">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape2.md) </span></span>  
 [<span data-ttu-id="9a641-131">Tarea 5: Configurar la forma transformación</span><span class="sxs-lookup"><span data-stu-id="9a641-131">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)