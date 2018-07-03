---
title: 'Tarea 4: Configurar el Shape2 mensaje construcción | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 43a7b912-0293-41be-b992-309eca550801
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 67c9e667248150a705841d0947bfb0cb3799a516
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012701"
---
# <a name="task-4-configure-the-construct-message-shape"></a><span data-ttu-id="b9be1-102">Tarea 4: Configurar la forma construir mensaje</span><span class="sxs-lookup"><span data-stu-id="b9be1-102">Task 4: Configure the Construct Message Shape</span></span>
<span data-ttu-id="b9be1-103">Las formas Construir mensaje contienen asignaciones de mensajes con las instrucciones para el código Begin, Edit y End Doc.</span><span class="sxs-lookup"><span data-stu-id="b9be1-103">The Construct Messages hold messages assignments with the instructions for the Begin, Edit, and End Doc code.</span></span>  
  
 <span data-ttu-id="b9be1-104">Utilice este procedimiento para configurar la forma Construir mensaje.</span><span class="sxs-lookup"><span data-stu-id="b9be1-104">Use the following procedure to configure the Construct Message shape.</span></span>  
  
### <a name="to-configure-the-construct-message-shape"></a><span data-ttu-id="b9be1-105">Para configurar la forma Construir mensaje</span><span class="sxs-lookup"><span data-stu-id="b9be1-105">To configure the Construct Message shape</span></span>  
  
1. <span data-ttu-id="b9be1-106">Arrastre una forma Construir mensaje entre ReceiveBeginDoc y SendBeginDoc.</span><span class="sxs-lookup"><span data-stu-id="b9be1-106">Drag a Construct Message shape inbetween ReceiveBeginDoc and SendBeginDoc.</span></span>  
  
   -   <span data-ttu-id="b9be1-107">**Mensajes construidos:** BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="b9be1-107">**Messages Constructed:** BeginDocSessionMsg</span></span>  
  
   -   <span data-ttu-id="b9be1-108">**Nombre:** ConstructBeginDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="b9be1-108">**Name:** ConstructBeginDocMessageWithSession</span></span>  
  
   1.  <span data-ttu-id="b9be1-109">Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="b9be1-109">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="b9be1-110">Haga doble clic en la forma MessageAssignment_1 interna.</span><span class="sxs-lookup"><span data-stu-id="b9be1-110">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="b9be1-111">Aparecerá el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b9be1-111">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="b9be1-112">Escriba su código, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b9be1-112">Type in your code, for example:</span></span>  
  
   ```  
   BeginDocSessionMsg = BeginDocMsg;  
   BeginDocSessionMsg(JDE.ReserveSession) = true;  
   BeginDocSessionMsg(JDE.SessionID) = 0;  
   ```  
  
    <span data-ttu-id="b9be1-113">Esto indica al adaptador que desea iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="b9be1-113">This tells the adapter you want to start a session.</span></span> <span data-ttu-id="b9be1-114">SessionID se inicializa como 0 pero cuando vuelve la respuesta el J.D. asignará el Id.</span><span class="sxs-lookup"><span data-stu-id="b9be1-114">The SessionID is initialized as 0 but when the response comes back the ID will be assigned by the J.D.</span></span> <span data-ttu-id="b9be1-115">Servidor de Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="b9be1-115">Edwards OneWorld Server.</span></span>  
  
    <span data-ttu-id="b9be1-116">![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")</span><span class="sxs-lookup"><span data-stu-id="b9be1-116">![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")</span></span>  
  
2. <span data-ttu-id="b9be1-117">Arrastre una forma Construir mensaje delante de SendEditLine.</span><span class="sxs-lookup"><span data-stu-id="b9be1-117">Drag a Construct Message before SendEditLine.</span></span>  
  
   - <span data-ttu-id="b9be1-118">**Mensajes construidos:** EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="b9be1-118">**Messages Constructed:** EditLineSessionMsg</span></span>  
  
   - <span data-ttu-id="b9be1-119">**Nombre:** ConstructEditLineMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="b9be1-119">**Name:** ConstructEditLineMessageWithSession</span></span>  
  
     <span data-ttu-id="b9be1-120">![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")</span><span class="sxs-lookup"><span data-stu-id="b9be1-120">![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")</span></span>  
  
   1.  <span data-ttu-id="b9be1-121">Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="b9be1-121">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="b9be1-122">Haga doble clic en la forma MessageAssignment_1 interna.</span><span class="sxs-lookup"><span data-stu-id="b9be1-122">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="b9be1-123">Aparecerá el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b9be1-123">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="b9be1-124">Escriba su código, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b9be1-124">Type in your code, for example:</span></span>  
  
   ```  
   EditLineSessionMsg = EditLineMsg;  
   EditLineSessionMsg(JDE.ReserveSession) = true;  
   EditLineSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
    <span data-ttu-id="b9be1-125">![](../core/media/jde-editline-editor.gif "JDE_editline_editor")</span><span class="sxs-lookup"><span data-stu-id="b9be1-125">![](../core/media/jde-editline-editor.gif "JDE_editline_editor")</span></span>  
  
3. <span data-ttu-id="b9be1-126">Arrastre una forma Construir mensaje delante de SendEndDoc.</span><span class="sxs-lookup"><span data-stu-id="b9be1-126">Drag a Construct Message before SendEndDoc.</span></span>  
  
   -   <span data-ttu-id="b9be1-127">**Mensajes construidos:** EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="b9be1-127">**Messages Constructed:** EndDocSessionMsg</span></span>  
  
   -   <span data-ttu-id="b9be1-128">**Nombre:** ConstructEndDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="b9be1-128">**Name:** ConstructEndDocMessageWithSession</span></span>  
  
   1.  <span data-ttu-id="b9be1-129">Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="b9be1-129">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
   2.  <span data-ttu-id="b9be1-130">Haga doble clic en la forma MessageAssignment_1 interna.</span><span class="sxs-lookup"><span data-stu-id="b9be1-130">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
        <span data-ttu-id="b9be1-131">Aparecerá el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="b9be1-131">The BizTalk Expression Editor appears.</span></span>  
  
   3.  <span data-ttu-id="b9be1-132">Escriba su código, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="b9be1-132">Type in your code, for example:</span></span>  
  
   ```  
   EndDocSessionMsg = EndDocMsg;  
   EndDocSessionMsg(JDE.ReserveSession) = false;  
   EndDocSessionMsg(JDE.SessionID) =  
      BeginDocResponseMsg(JDE.SessionID);  
   ```  
  
## <a name="see-also"></a><span data-ttu-id="b9be1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="b9be1-133">See Also</span></span>  
 <span data-ttu-id="b9be1-134">[Tarea 1: Creación de los puertos](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="b9be1-134">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="b9be1-135">[Tarea 2: Creación de los mensajes](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="b9be1-135">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="b9be1-136">[Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="b9be1-136">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="b9be1-137">Tarea 5: Configurar la forma Transformación</span><span class="sxs-lookup"><span data-stu-id="b9be1-137">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)