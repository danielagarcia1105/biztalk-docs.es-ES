---
title: "Configurar la acción SOAP para Oracle E-Business Suite en BizTalk Server | Documentos de Microsoft"
description: "Especifique una acción de SOAP en Visual Studio, o usar el adaptador de WCF-Custom o WCF-OracleEBS en el módulo de adaptador de BizTalk (BAP)"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ca799d96-66e4-4d4e-a632-cb5505e999b4
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c29cb5ce17f0a80e42ceae908639bed48e99e3a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-soap-action-for-oracle-e-business-suite"></a><span data-ttu-id="d7ffc-103">Configurar la acción SOAP para Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="d7ffc-103">Configure the SOAP action for Oracle E-Business Suite</span></span>
<span data-ttu-id="d7ffc-104">Para realizar cualquier operación en Oracle E-Business Suite con basadas en WCF [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], debe especificar una acción de SOAP.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-104">To perform any operation on Oracle E-Business Suite using the WCF-based [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must specify a SOAP action.</span></span> <span data-ttu-id="d7ffc-105">La acción SOAP comunica con el adaptador de la acción que debe realizarse.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="d7ffc-106">Puede especificar la acción SOAP de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] o desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-106">You can specify the SOAP action either from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="d7ffc-107">Sin embargo, si especifica la acción de SOAP en ambas ubicaciones, la acción especificado de [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] se invalida.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-107">However, if you specify the SOAP action from both locations, the action you specified from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] is overridden.</span></span>  
  
 <span data-ttu-id="d7ffc-108">Para obtener más información acerca de cómo especificar la acción SOAP, vea [especificar acciones SOAP para adaptadores de envío de WCF](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="d7ffc-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>  
  
## <a name="enter-soap-action-from-visual-studio"></a><span data-ttu-id="d7ffc-109">Especifique la acción de SOAP desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d7ffc-109">Enter SOAP Action from Visual Studio</span></span>  
 <span data-ttu-id="d7ffc-110">De [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], debe especificar la acción SOAP como parte de la orquestación mediante un **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-110">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="d7ffc-111">En la orquestación de BizTalk, incluya una **expresión** forma arrastrándolo desde el **orquestación de BizTalk** cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="d7ffc-112">Haga doble clic en el **expresión** forma para abrir el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-112">Double-click the **Expression** shape to open BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="d7ffc-113">Especifica la acción en el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-113">Specify the action in BizTalk Expression Editor.</span></span> <span data-ttu-id="d7ffc-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7ffc-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY"  
    ```  
  
     <span data-ttu-id="d7ffc-115">Para obtener más información sobre la **expresión** forma y el Editor de expresiones de BizTalk, consulte [cómo crear expresiones](../../core/how-to-create-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d7ffc-115">For more information about the **Expression** shape and BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a><span data-ttu-id="d7ffc-116">Especifique la acción de SOAP de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d7ffc-116">Enter SOAP Action from BizTalk Server Administration</span></span>  
 <span data-ttu-id="d7ffc-117">Desde el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración, debe especificar la acción SOAP como parte de la configuración del puerto WCF-Custom o WCF-OracleEBS.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-117">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the SOAP action as part of the WCF-Custom or WCF-OracleEBS port configuration.</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="d7ffc-118">Especifique una acción de SOAP para el puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="d7ffc-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="d7ffc-119">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="d7ffc-120">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="d7ffc-121">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="d7ffc-122">En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="d7ffc-123">En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="d7ffc-124">En el **acción** texto, especifique la acción SOAP para la operación.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="d7ffc-125">Puede especificar la acción de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="d7ffc-125">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="d7ffc-126">**Con el formato de acción única**.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-126">**By using the single action format**.</span></span> <span data-ttu-id="d7ffc-127">Utilice este formato si WCF-Custom puerto envía y recibe mensajes de una sola operación.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="d7ffc-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7ffc-128">For example:</span></span>  
  
        ```  
        InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
        ```  
  
    -   <span data-ttu-id="d7ffc-129">**Con el formato de asignación de acción**.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-129">**By using the action mapping format**.</span></span> <span data-ttu-id="d7ffc-130">Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="d7ffc-131">Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para insertar registros en la tabla GL_ALLOC_HISTORY) y Op2 (para actualizar registros en la tabla GL_ALLOC_HISTORY), la acción SOAP puede especificarse de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d7ffc-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the GL_ALLOC_HISTORY table) and Op2 (to update records in the GL_ALLOC_HISTORY table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
          <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="d7ffc-132">El método de asignación de acción proporciona mayor flexibilidad en cuanto a especificar un conjunto de acciones y, por lo tanto, lo que permite los mensajes que pertenecen a los tipos de acción diferentes atraviese el mismo puerto.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-132">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="d7ffc-133">El formato de la acción SOAP es diferente para cada operación.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="d7ffc-134">Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje para el adaptador de Oracle EBS](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="d7ffc-134">For more information about the action format for each operation, see [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>
  
#### <a name="enter-a-soap-action-for-the-wcf-oracleebs-port"></a><span data-ttu-id="d7ffc-135">Especifique una acción de SOAP para el puerto de WCF-OracleEBS</span><span class="sxs-lookup"><span data-stu-id="d7ffc-135">Enter a SOAP action for the WCF-OracleEBS port</span></span>  
  
1.  <span data-ttu-id="d7ffc-136">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="d7ffc-137">Agregar el adaptador de WCF-OracleEBS a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-137">Add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="d7ffc-138">Para obtener instrucciones, consulte [agregar el adaptador de Oracle E-Business Suite a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="d7ffc-138">For instructions, see [Adding the Oracle E-Business Suite Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="d7ffc-139">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="d7ffc-140">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="d7ffc-141">En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione el WCF-OracleEBS adaptador agrega anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleEBS adapter you add earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="d7ffc-142">En el cuadro de diálogo Propiedades de transporte, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="d7ffc-143">En el **acción** texto, especifique la acción SOAP para la operación.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="d7ffc-144">Puede especificar la acción de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="d7ffc-144">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="d7ffc-145">**Con el formato de acción única**.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-145">**By using the single action format**.</span></span> <span data-ttu-id="d7ffc-146">Utilice este formato si WCF-OracleEBS puerto envía y recibe mensajes de una sola operación.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-146">Use this format if the WCF-OracleEBS port sends and receive messages for a single operation.</span></span> <span data-ttu-id="d7ffc-147">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d7ffc-147">For example:</span></span>  
  
        ```  
        InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
        ```  
  
    -   <span data-ttu-id="d7ffc-148">**Con el formato de asignación de acción**.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-148">**By using the action mapping format**.</span></span> <span data-ttu-id="d7ffc-149">Utilice este formato si un único puerto de WCF-OracleEBS envía y recibe mensajes de más de una operación.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-149">Use this format if a single WCF-OracleEBS port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="d7ffc-150">Por ejemplo, si un único puerto de WCF-OracleEBS envía y recibe mensajes de Op1 (para insertar registros en la tabla GL_ALLOC_HISTORY) y Op2 (para actualizar registros en la tabla GL_ALLOC_HISTORY), la acción SOAP puede especificarse de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d7ffc-150">For example, if a single WCF-OracleEBS port sends and receives messages for Op1 (to insert records in the GL_ALLOC_HISTORY table) and Op2 (to update records in the GL_ALLOC_HISTORY table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
          <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="d7ffc-151">El método de asignación de acción proporciona mayor flexibilidad en cuanto a especificar un conjunto de acciones y, por lo tanto, lo que permite los mensajes que pertenecen a los tipos de acción diferentes atraviese el mismo puerto.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-151">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="d7ffc-152">El formato de la acción SOAP es diferente para cada operación.</span><span class="sxs-lookup"><span data-stu-id="d7ffc-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="d7ffc-153">Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje para el adaptador de Oracle EBS](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="d7ffc-153">For more information about the action format for each operation, see [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d7ffc-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="d7ffc-154">See Also</span></span>  
 [<span data-ttu-id="d7ffc-155">Bloques de creación para crear aplicaciones de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="d7ffc-155">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)