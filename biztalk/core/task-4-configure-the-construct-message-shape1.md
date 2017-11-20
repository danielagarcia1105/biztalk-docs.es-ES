---
title: "Tarea 4: Configurar el forma1 de mensaje de construcción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3e66a9d-c549-42d0-849b-9e1744056429
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f781e03f83223f7d82628ee9c01728a0754b149f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="task-4-configure-the-construct-message-shape"></a><span data-ttu-id="e9bf9-102">Tarea 4: Configurar la forma construir mensaje</span><span class="sxs-lookup"><span data-stu-id="e9bf9-102">Task 4: Configure the Construct Message Shape</span></span>
<span data-ttu-id="e9bf9-103">Las formas Construir mensaje contienen asignaciones de mensajes con las instrucciones para el código Begin, Edit y End Doc.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-103">The Construct Messages hold messages assignments with the instructions for the Begin, Edit, and End Doc code.</span></span>  
  
 <span data-ttu-id="e9bf9-104">Utilice este procedimiento para configurar la forma Construir mensaje.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-104">Use the following procedure to configure the Construct Message shape.</span></span>  
  
### <a name="to-configure-the-construct-message-shape"></a><span data-ttu-id="e9bf9-105">Para configurar la forma Construir mensaje</span><span class="sxs-lookup"><span data-stu-id="e9bf9-105">To configure the Construct Message shape</span></span>  
  
1.  <span data-ttu-id="e9bf9-106">Arrastre una forma Construir mensaje entre ReceiveBeginDoc y SendBeginDoc.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-106">Drag a Construct Message shape inbetween ReceiveBeginDoc and SendBeginDoc.</span></span>  
  
    -   <span data-ttu-id="e9bf9-107">**Mensajes construidos:** BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="e9bf9-107">**Messages Constructed:** BeginDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="e9bf9-108">**Nombre:** ConstructBeginDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="e9bf9-108">**Name:** ConstructBeginDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="e9bf9-109">Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-109">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="e9bf9-110">Haga doble clic en la forma MessageAssignment_1 interna.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-110">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="e9bf9-111">Aparecerá el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-111">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="e9bf9-112">Escriba su código, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e9bf9-112">Type in your code, for example:</span></span>  
  
        ```  
        BeginDocSessionMsg = BeginDocMsg;  
        BeginDocSessionMsg(JDE.ReserveSession) = true;  
        BeginDocSessionMsg(JDE.SessionID) = 0;  
        ```  
  
         <span data-ttu-id="e9bf9-113">Esto indica al adaptador que desea iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-113">This tells the adapter you want to start a session.</span></span> <span data-ttu-id="e9bf9-114">El valor de SessionID se inicializa como 0 pero cuando vuelve la respuesta se le asignará el Id. de forma el J.D.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-114">The SessionID is initialized as 0 but when the response comes back the ID will be assigned by the J.D.</span></span> <span data-ttu-id="e9bf9-115">Servidor de Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-115">Edwards EnterpriseOne Server.</span></span>  
  
     <span data-ttu-id="e9bf9-116">![Editor de expresiones de mensaje](../core/media/message-expression-editor.gif "message_expression_editor")</span><span class="sxs-lookup"><span data-stu-id="e9bf9-116">![Message Expression Editor](../core/media/message-expression-editor.gif "message_expression_editor")</span></span>  
  
2.  <span data-ttu-id="e9bf9-117">Arrastre una forma Construir mensaje delante de SendEditLine.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-117">Drag a Construct Message before SendEditLine.</span></span>  
  
    -   <span data-ttu-id="e9bf9-118">**Mensajes construidos:** EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="e9bf9-118">**Messages Constructed:** EditLineSessionMsg</span></span>  
  
    -   <span data-ttu-id="e9bf9-119">**Nombre:** ConstructEditLineMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="e9bf9-119">**Name:** ConstructEditLineMessageWithSession</span></span>  
  
     <span data-ttu-id="e9bf9-120">![Enviar Editar línea](../core/media/constructoreditlinemessagewithsession.gif "constructoreditlinemessagewithsession")</span><span class="sxs-lookup"><span data-stu-id="e9bf9-120">![Send Edit Line](../core/media/constructoreditlinemessagewithsession.gif "constructoreditlinemessagewithsession")</span></span>  
  
    1.  <span data-ttu-id="e9bf9-121">Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-121">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="e9bf9-122">Haga doble clic en la forma MessageAssignment_1 interna.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-122">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="e9bf9-123">Aparecerá el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-123">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="e9bf9-124">Escriba su código, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e9bf9-124">Type in your code, for example:</span></span>  
  
        ```  
        EditLineSessionMsg = EditLineMsg;  
        EditLineSessionMsg(JDE.ReserveSession) = true;  
        EditLineSessionMsg(JDE.SessionID) =  
        BeginDocResponseMsg(JDE.SessionID);  
        ```  
  
     <span data-ttu-id="e9bf9-125">![Editar línea Editor](../core/media/editline-editor.gif "editline_editor")</span><span class="sxs-lookup"><span data-stu-id="e9bf9-125">![Edit Line Editor](../core/media/editline-editor.gif "editline_editor")</span></span>  
  
3.  <span data-ttu-id="e9bf9-126">Arrastre una forma construir mensaje delante de SendEndDoc.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-126">Drag a Construct Message shape before SendEndDoc.</span></span>  
  
    -   <span data-ttu-id="e9bf9-127">**Mensajes construidos:** EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="e9bf9-127">**Messages Constructed:** EndDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="e9bf9-128">**Nombre:** ConstructEndDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="e9bf9-128">**Name:** ConstructEndDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="e9bf9-129">Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-129">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="e9bf9-130">Haga doble clic en la forma MessageAssignment_1 interna.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-130">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="e9bf9-131">Aparecerá el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e9bf9-131">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="e9bf9-132">Escriba su código, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="e9bf9-132">Type in your code, for example:</span></span>  
  
        ```  
        EndDocSessionMsg = EndDocMsg;  
        EndDocSessionMsg(JDE.ReserveSession) = false;  
        EndDocSessionMsg(JDE.SessionID) =  
           BeginDocResponseMsg(JDE.SessionID);  
        ```  
  
## <a name="see-also"></a><span data-ttu-id="e9bf9-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9bf9-133">See Also</span></span>  
 <span data-ttu-id="e9bf9-134">[Tarea 1: Crear los puertos](../core/task-1-create-the-ports1.md) </span><span class="sxs-lookup"><span data-stu-id="e9bf9-134">[Task 1: Create the Ports](../core/task-1-create-the-ports1.md) </span></span>  
 <span data-ttu-id="e9bf9-135">[Tarea 2: Crear los mensajes](../core/task-2-create-the-messages2.md) </span><span class="sxs-lookup"><span data-stu-id="e9bf9-135">[Task 2: Create the Messages](../core/task-2-create-the-messages2.md) </span></span>  
 <span data-ttu-id="e9bf9-136">[Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes2.md) </span><span class="sxs-lookup"><span data-stu-id="e9bf9-136">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes2.md) </span></span>  
 [<span data-ttu-id="e9bf9-137">Tarea 5: Configurar la forma transformación</span><span class="sxs-lookup"><span data-stu-id="e9bf9-137">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape2.md)