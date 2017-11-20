---
title: "Tarea 4: Configurar el Shape2 de mensaje de construcción | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 43a7b912-0293-41be-b992-309eca550801
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6616fec48eb0915527a95f94992e4bda838e9d37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="task-4-configure-the-construct-message-shape"></a><span data-ttu-id="20163-102">Tarea 4: Configurar la forma construir mensaje</span><span class="sxs-lookup"><span data-stu-id="20163-102">Task 4: Configure the Construct Message Shape</span></span>
<span data-ttu-id="20163-103">Las formas Construir mensaje contienen asignaciones de mensajes con las instrucciones para el código Begin, Edit y End Doc.</span><span class="sxs-lookup"><span data-stu-id="20163-103">The Construct Messages hold messages assignments with the instructions for the Begin, Edit, and End Doc code.</span></span>  
  
 <span data-ttu-id="20163-104">Utilice este procedimiento para configurar la forma Construir mensaje.</span><span class="sxs-lookup"><span data-stu-id="20163-104">Use the following procedure to configure the Construct Message shape.</span></span>  
  
### <a name="to-configure-the-construct-message-shape"></a><span data-ttu-id="20163-105">Para configurar la forma Construir mensaje</span><span class="sxs-lookup"><span data-stu-id="20163-105">To configure the Construct Message shape</span></span>  
  
1.  <span data-ttu-id="20163-106">Arrastre una forma Construir mensaje entre ReceiveBeginDoc y SendBeginDoc.</span><span class="sxs-lookup"><span data-stu-id="20163-106">Drag a Construct Message shape inbetween ReceiveBeginDoc and SendBeginDoc.</span></span>  
  
    -   <span data-ttu-id="20163-107">**Mensajes construidos:** BeginDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="20163-107">**Messages Constructed:** BeginDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="20163-108">**Nombre:** ConstructBeginDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="20163-108">**Name:** ConstructBeginDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="20163-109">Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="20163-109">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="20163-110">Haga doble clic en la forma MessageAssignment_1 interna.</span><span class="sxs-lookup"><span data-stu-id="20163-110">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="20163-111">Aparecerá el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="20163-111">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="20163-112">Escriba su código, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="20163-112">Type in your code, for example:</span></span>  
  
    ```  
    BeginDocSessionMsg = BeginDocMsg;  
    BeginDocSessionMsg(JDE.ReserveSession) = true;  
    BeginDocSessionMsg(JDE.SessionID) = 0;  
    ```  
  
     <span data-ttu-id="20163-113">Esto indica al adaptador que desea iniciar una sesión.</span><span class="sxs-lookup"><span data-stu-id="20163-113">This tells the adapter you want to start a session.</span></span> <span data-ttu-id="20163-114">El valor de SessionID se inicializa como 0 pero cuando vuelve la respuesta se le asignará el Id. de forma el J.D.</span><span class="sxs-lookup"><span data-stu-id="20163-114">The SessionID is initialized as 0 but when the response comes back the ID will be assigned by the J.D.</span></span> <span data-ttu-id="20163-115">Servidor de Edwards OneWorld.</span><span class="sxs-lookup"><span data-stu-id="20163-115">Edwards OneWorld Server.</span></span>  
  
     ![](../core/media/jde-message-expression-editor.gif "JDE_message_expression_editor")  
  
2.  <span data-ttu-id="20163-116">Arrastre una forma Construir mensaje delante de SendEditLine.</span><span class="sxs-lookup"><span data-stu-id="20163-116">Drag a Construct Message before SendEditLine.</span></span>  
  
    -   <span data-ttu-id="20163-117">**Mensajes construidos:** EditLineSessionMsg</span><span class="sxs-lookup"><span data-stu-id="20163-117">**Messages Constructed:** EditLineSessionMsg</span></span>  
  
    -   <span data-ttu-id="20163-118">**Nombre:** ConstructEditLineMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="20163-118">**Name:** ConstructEditLineMessageWithSession</span></span>  
  
     ![](../core/media/jde-constructoreditlinemessagewithsession.gif "JDE_constructoreditlinemessagewithsession")  
  
    1.  <span data-ttu-id="20163-119">Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="20163-119">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="20163-120">Haga doble clic en la forma MessageAssignment_1 interna.</span><span class="sxs-lookup"><span data-stu-id="20163-120">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="20163-121">Aparecerá el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="20163-121">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="20163-122">Escriba su código, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="20163-122">Type in your code, for example:</span></span>  
  
    ```  
    EditLineSessionMsg = EditLineMsg;  
    EditLineSessionMsg(JDE.ReserveSession) = true;  
    EditLineSessionMsg(JDE.SessionID) =  
       BeginDocResponseMsg(JDE.SessionID);  
    ```  
  
     ![](../core/media/jde-editline-editor.gif "JDE_editline_editor")  
  
3.  <span data-ttu-id="20163-123">Arrastre una forma Construir mensaje delante de SendEndDoc.</span><span class="sxs-lookup"><span data-stu-id="20163-123">Drag a Construct Message before SendEndDoc.</span></span>  
  
    -   <span data-ttu-id="20163-124">**Mensajes construidos:** EndDocSessionMsg</span><span class="sxs-lookup"><span data-stu-id="20163-124">**Messages Constructed:** EndDocSessionMsg</span></span>  
  
    -   <span data-ttu-id="20163-125">**Nombre:** ConstructEndDocMessageWithSession</span><span class="sxs-lookup"><span data-stu-id="20163-125">**Name:** ConstructEndDocMessageWithSession</span></span>  
  
    1.  <span data-ttu-id="20163-126">Arrastre una forma Asignación de mensajes a la orquestación donde desea crear un mensaje nuevo.</span><span class="sxs-lookup"><span data-stu-id="20163-126">Drag a Message Assignment shape into your orchestration where you want to create a new message.</span></span>  
  
    2.  <span data-ttu-id="20163-127">Haga doble clic en la forma MessageAssignment_1 interna.</span><span class="sxs-lookup"><span data-stu-id="20163-127">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
         <span data-ttu-id="20163-128">Aparecerá el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="20163-128">The BizTalk Expression Editor appears.</span></span>  
  
    3.  <span data-ttu-id="20163-129">Escriba su código, por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="20163-129">Type in your code, for example:</span></span>  
  
    ```  
    EndDocSessionMsg = EndDocMsg;  
    EndDocSessionMsg(JDE.ReserveSession) = false;  
    EndDocSessionMsg(JDE.SessionID) =  
       BeginDocResponseMsg(JDE.SessionID);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="20163-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="20163-130">See Also</span></span>  
 <span data-ttu-id="20163-131">[Tarea 1: Crear los puertos](../core/task-1-create-the-ports2.md) </span><span class="sxs-lookup"><span data-stu-id="20163-131">[Task 1: Create the Ports](../core/task-1-create-the-ports2.md) </span></span>  
 <span data-ttu-id="20163-132">[Tarea 2: Crear los mensajes](../core/task-2-create-the-messages1.md) </span><span class="sxs-lookup"><span data-stu-id="20163-132">[Task 2: Create the Messages](../core/task-2-create-the-messages1.md) </span></span>  
 <span data-ttu-id="20163-133">[Tarea 3: Configurar el envío y recepción formas](../core/task-3-configure-the-send-and-receive-shapes1.md) </span><span class="sxs-lookup"><span data-stu-id="20163-133">[Task 3: Configure the Send and Receive Shapes](../core/task-3-configure-the-send-and-receive-shapes1.md) </span></span>  
 [<span data-ttu-id="20163-134">Tarea 5: Configurar la forma transformación</span><span class="sxs-lookup"><span data-stu-id="20163-134">Task 5: Configure the Transform Shape</span></span>](../core/task-5-configure-the-transform-shape1.md)