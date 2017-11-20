---
title: 'Tutorial: Usar propiedades de contexto del mensaje TIBCO EMS | Documentos de Microsoft'
description: "Guía paso a paso para usar los campos de descriptor de mensajes de TIBCO Enterprise Message Service en la orquestación de BizTalk Server"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6e52593b-5001-4740-89fb-e003e12d8e69
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f17b45afb28a497c0443f788a44d05307103c547
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
---
# <a name="tutorial-use-tibco-ems-message-descriptors"></a><span data-ttu-id="9f3fb-103">Tutorial: Descriptores de mensaje uso TIBCO EMS</span><span class="sxs-lookup"><span data-stu-id="9f3fb-103">Tutorial: Use TIBCO EMS message descriptors</span></span>

## <a name="overview"></a><span data-ttu-id="9f3fb-104">Información general</span><span class="sxs-lookup"><span data-stu-id="9f3fb-104">Overview</span></span>
<span data-ttu-id="9f3fb-105">En este tutorial se muestra cómo usar las propiedades de contexto de BizTalk Server para establecer los campos de descriptor de mensajes de TIBCO Enterprise Message Service (EMS) en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-105">This tutorial demonstrates how to use BizTalk Server context properties to set TIBCO Enterprise Message Service (EMS) message descriptor fields in your orchestration.</span></span> <span data-ttu-id="9f3fb-106">El tutorial supone que dispone de una orquestación que recibe un mensaje de un puerto de recepción y lo envía a un puerto de envío enlazado al adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-106">The tutorial assumes that you have an orchestration that receives a message from a receive port and sends the message to a send port bound to Microsoft BizTalk Adapter for TIBCO Enterprise Message Service.</span></span>  
  
 <span data-ttu-id="9f3fb-107">En el siguiente procedimiento se muestra cómo cambiar la prioridad del mensaje de TIBCO EMS mediante el cambio del valor de la propiedad de contexto TibcoEMS.Priority.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-107">The following procedure demonstrates how to change the priority of the TIBCO EMS message by changing the value of the TibcoEMS.Priority context property.</span></span> <span data-ttu-id="9f3fb-108">En BizTalk Server, los mensajes son inmutables.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-108">In BizTalk Server, messages are immutable.</span></span> <span data-ttu-id="9f3fb-109">Por lo tanto, para cambiar un valor de propiedad, debe crear y modificar un nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-109">Therefore, to change a property value, you must create and modify a new message.</span></span> <span data-ttu-id="9f3fb-110">Puede crear y modificar el nuevo mensaje mediante la inserción de una forma de asignación del mensaje entre las formas de envío y recepción.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-110">You create and modify the new message by inserting a message assignment shape between the Receive and Send shapes.</span></span> <span data-ttu-id="9f3fb-111">No obstante, debe hacer referencia, en primer lugar, al esquema DLL para obtener acceso a las propiedades TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-111">First, however, you must reference the schema DLL to gain access to the TIBCO EMS properties.</span></span>  
  
## <a name="reference-the-schema-dll"></a><span data-ttu-id="9f3fb-112">Hacer referencia al esquema DLL</span><span class="sxs-lookup"><span data-stu-id="9f3fb-112">Reference the schema DLL</span></span>  
  
1.  <span data-ttu-id="9f3fb-113">En Visual Studio, abra el proyecto de BizTalk Server y abra **el Explorador de soluciones** .</span><span class="sxs-lookup"><span data-stu-id="9f3fb-113">In Visual Studio, open your BizTalk Server project, and open **Solution Explorer** .</span></span>  
  
2.  <span data-ttu-id="9f3fb-114">Haga clic en **referencias**y seleccione **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-114">Right-click **References**, and select **Add Reference**.</span></span>  
  
     <span data-ttu-id="9f3fb-115">Aparecerá el cuadro de diálogo **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-115">The **Add Reference** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="9f3fb-116">Haga clic en el **examinar** ficha.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-116">Click the **Browse** tab.</span></span>  
  
     <span data-ttu-id="9f3fb-117">El **Seleccionar componente** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-117">The **Select Component** dialog box appears.</span></span>  
  
4.  <span data-ttu-id="9f3fb-118">Busque  **\<EMS_Adapter_installation_directory TIBCO > \bin**y, a continuación, seleccione **Microsoft.Adapters.TibcoEMSProperties.dll**.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-118">Locate **\<TIBCO EMS_Adapter_installation_directory>\bin**, and then select **Microsoft.Adapters.TibcoEMSProperties.dll**.</span></span>  
  
5.  <span data-ttu-id="9f3fb-119">Haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-119">Click **Open**.</span></span>  
  
     <span data-ttu-id="9f3fb-120">El archivo DLL aparece en la **componentes seleccionados** en el **Agregar referencia** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-120">The DLL appears in the **Selected Components** in the **Add Reference** dialog box.</span></span>  
  
6.  <span data-ttu-id="9f3fb-121">Haga clic en **Aceptar** y, a continuación, haga doble clic en la orquestación para obtener acceso al diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-121">Click **OK** and then double-click your orchestration to access the Orchestration Designer.</span></span>  
  
7.  <span data-ttu-id="9f3fb-122">En el **vista** menú, elija **otras ventanas**y, a continuación, haga clic en **Vista orquestación**.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-122">On the **View** menu, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
8.  <span data-ttu-id="9f3fb-123">En la Vista orquestación, haga clic en **mensajes** y seleccione **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-123">In the Orchestration view, right-click **Messages** and select **New Message**.</span></span>  
  
9. <span data-ttu-id="9f3fb-124">Editar las propiedades de mensaje nuevo y asignar un **tipo de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-124">Edit your new message properties and assign a **Message Type**.</span></span>  
  
     <span data-ttu-id="9f3fb-125">Asignará Message_1 a Message_2.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-125">You will assign Message_1 to Message_2.</span></span> <span data-ttu-id="9f3fb-126">Por lo tanto, se debe asignar el mismo tipo de mensaje a ambos mensajes.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-126">Therefore, you must assign the same message type to both messages.</span></span>  
  
10. <span data-ttu-id="9f3fb-127">En el menú **Ver** , haga clic en **Cuadro de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-127">On the **View** menu, click **Toolbox**.</span></span>  
  
11. <span data-ttu-id="9f3fb-128">Arrastre un **asignación de mensajes** forma en la orquestación donde desea crear un nuevo mensaje.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-128">Drag a **Message Assignment** shape onto your orchestration where you want to create a new message.</span></span>  
  
12. <span data-ttu-id="9f3fb-129">Modifique la forma ConstructMessage_1 externa y seleccione el nuevo mensaje, Message_2, en la **mensajes construidos** propiedad.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-129">Edit the outer ConstructMessage_1 shape and select your new message, Message_2, in the **Constructed Messages** property.</span></span>  
  
13. <span data-ttu-id="9f3fb-130">Haga doble clic en la forma MessageAssignment_1 interna.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-130">Double-click the inner MessageAssignment_1 shape.</span></span>  
  
     <span data-ttu-id="9f3fb-131">Aparecerá el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-131">The BizTalk Expression Editor appears.</span></span>  
  
14. <span data-ttu-id="9f3fb-132">En el Editor de expresiones de BizTalk, escriba el código.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-132">In the BizTalk Expression Editor, type your code.</span></span>  
  
15. <span data-ttu-id="9f3fb-133">En primer lugar, copie un mensaje existente y asigne los valores a las propiedades de contexto de mensaje.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-133">First copy an existing message and then assign values to message context properties.</span></span>  
  
     <span data-ttu-id="9f3fb-134">La sintaxis es `Message(property) = value;`.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-134">The syntax is `Message(property) = value;`.</span></span> <span data-ttu-id="9f3fb-135">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="9f3fb-135">For example:</span></span>  
  
    ```  
    Message_2 = Message_1;  
    Message_2( TibcoEMS.Priority) = 6;  
    ```  
  
     <span data-ttu-id="9f3fb-136">Vea TIBCO EMS para obtener una lista de propiedades admitidas que puede usar en el mensaje personalizado.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-136">See TIBCO EMS for a list of supported properties that you can use in your custom message.</span></span>  
  
16. <span data-ttu-id="9f3fb-137">Haga clic en **Aceptar** para cerrar el Editor de expresiones de BizTalk y guarde el código.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-137">Click **OK** to close the BizTalk Expression Editor and save your code.</span></span>  
  
17. <span data-ttu-id="9f3fb-138">Haga clic en la forma envío y asignar el **mensaje** como **Message_2**.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-138">Click the Send shape and assign the **Message** to be **Message_2**.</span></span>  
  
18. <span data-ttu-id="9f3fb-139">Compruebe que las formas del flujo de mensajes restantes funcionan en el mensaje correspondiente.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-139">Verify that the shapes in the rest of the message flow operate on the appropriate message.</span></span>  
  
19. <span data-ttu-id="9f3fb-140">Haga clic en el proyecto en el Explorador de soluciones y seleccione **generar**.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-140">Right-click your project in Solution Explorer, and select **Build**.</span></span>  
  
20. <span data-ttu-id="9f3fb-141">Haga clic en el proyecto y seleccione **implementar**.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-141">Right-click your project and select **Deploy**.</span></span>  
  
21. <span data-ttu-id="9f3fb-142">Seleccione **enlazar**, **dar de alta**, y **iniciar** en el Explorador de BizTalk para probar su orquestación.</span><span class="sxs-lookup"><span data-stu-id="9f3fb-142">Select **Bind**, **Enlist**, and **Start** in the BizTalk Explorer to test your orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f3fb-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="9f3fb-143">See Also</span></span>  
[<span data-ttu-id="9f3fb-144">Propiedades de contexto del mensaje de TIBCO EMS</span><span class="sxs-lookup"><span data-stu-id="9f3fb-144">TIBCO EMS message context properties</span></span>](../core/message-context-properties-in-biztalk-server.md)