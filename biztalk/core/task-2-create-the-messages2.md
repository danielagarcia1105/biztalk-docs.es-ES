---
title: 'Tarea 2: Crear el Messages2 | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2db67595-bcb6-455b-ad81-07b4426b7ea4
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3f970e692f72af21c8b1c3c76dfdebae15350f5f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279084"
---
# <a name="task-2-create-the-messages"></a><span data-ttu-id="55017-102">Tarea 2: Crear los mensajes</span><span class="sxs-lookup"><span data-stu-id="55017-102">Task 2: Create the Messages</span></span>
<span data-ttu-id="55017-103">Cree los siguientes mensajes, que se usarán en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="55017-103">Create the following Messages, which will be used in the orchestration.</span></span>  
  
### <a name="to-create-the-messages"></a><span data-ttu-id="55017-104">Para crear mensajes</span><span class="sxs-lookup"><span data-stu-id="55017-104">To create the messages</span></span>  
  
1.  <span data-ttu-id="55017-105">Haga clic en **mensaje**y, a continuación, seleccione **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="55017-105">Right-click **Message**, and then select **New Message**.</span></span>  
  
2.  <span data-ttu-id="55017-106">Cumplimente lo siguiente para el identificador y el tipo de mensaje>esquema, y seleccione el tipo de la lista que aparece para cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="55017-106">Fill in the following for the Identifier and the Message Type>Schema and select the type from the displayed list for each message.</span></span>  
  
    |<span data-ttu-id="55017-107">Identificador</span><span class="sxs-lookup"><span data-stu-id="55017-107">Identifier</span></span>|<span data-ttu-id="55017-108">Tipo de mensaje > Esquema</span><span class="sxs-lookup"><span data-stu-id="55017-108">Message Type > Schema</span></span>|  
    |----------------|----------------------------|  
    |<span data-ttu-id="55017-109">BeginDocMsg</span><span class="sxs-lookup"><span data-stu-id="55017-109">BeginDocMsg</span></span>|<span data-ttu-id="55017-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="55017-110">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="55017-111">BeginDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="55017-111">BeginDocResponseMsg</span></span>|<span data-ttu-id="55017-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span><span class="sxs-lookup"><span data-stu-id="55017-112">BeginDocTest.B4200310Service_1.F4211FSBeginDocResponse</span></span>|  
    |<span data-ttu-id="55017-113">BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="55017-113">BeginDocSessionMsg</span></span>|<span data-ttu-id="55017-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span><span class="sxs-lookup"><span data-stu-id="55017-114">BeginDocTest.B4200310Service_1.F4211FSBeginDoc</span></span>|  
    |<span data-ttu-id="55017-115">EditLineMsg</span><span class="sxs-lookup"><span data-stu-id="55017-115">EditLineMsg</span></span>|<span data-ttu-id="55017-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="55017-116">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="55017-117">EditLineResponseMsg</span><span class="sxs-lookup"><span data-stu-id="55017-117">EditLineResponseMsg</span></span>|<span data-ttu-id="55017-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span><span class="sxs-lookup"><span data-stu-id="55017-118">BeginDocTest.B4200310Service_1.F4211FSEditLineResponse</span></span>|  
    |<span data-ttu-id="55017-119">EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="55017-119">EditLineSessionMsg</span></span>|<span data-ttu-id="55017-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span><span class="sxs-lookup"><span data-stu-id="55017-120">BeginDocTest.B4200310Service_1.F4211FSEditLine</span></span>|  
    |<span data-ttu-id="55017-121">EndDocMsg</span><span class="sxs-lookup"><span data-stu-id="55017-121">EndDocMsg</span></span>|<span data-ttu-id="55017-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="55017-122">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
    |<span data-ttu-id="55017-123">EndDocResponseMsg</span><span class="sxs-lookup"><span data-stu-id="55017-123">EndDocResponseMsg</span></span>|<span data-ttu-id="55017-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span><span class="sxs-lookup"><span data-stu-id="55017-124">BeginDocTest.B4200310Service_1.F4211FSEndDocResponse</span></span>|  
    |<span data-ttu-id="55017-125">EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="55017-125">EndDocSessionMsg</span></span>|<span data-ttu-id="55017-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span><span class="sxs-lookup"><span data-stu-id="55017-126">BeginDocTest.B4200310Service_1.F4211FSEndDoc</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="55017-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="55017-127">See Also</span></span>  
 <span data-ttu-id="55017-128">[Tarea 1: Crear los puertos](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="55017-128">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="55017-129">[Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes2.md) </span><span class="sxs-lookup"><span data-stu-id="55017-129">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes2.md) </span></span>  
 <span data-ttu-id="55017-130">[Tarea 4: Configurar la forma construir mensaje](../core/task-4-configure-the-construct-message-shape1.md) </span><span class="sxs-lookup"><span data-stu-id="55017-130">[Task 4: Configure the Construct Message Shape](../core/task-4-configure-the-construct-message-shape1.md) </span></span>  
 [<span data-ttu-id="55017-131">Tarea 5: Configurar la forma transformación</span><span class="sxs-lookup"><span data-stu-id="55017-131">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)