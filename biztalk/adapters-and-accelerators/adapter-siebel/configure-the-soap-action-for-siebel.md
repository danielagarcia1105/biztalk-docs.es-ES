---
title: Configurar la acción SOAP para el adaptador Siebel en BizTalk | Documentos de Microsoft
description: Especifique una acción de SOAP en Visual Studio, o usar el adaptador de WCF-Custom o WCF-Siebel en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f22a4691-0355-4f08-a14e-e90a3c987ac0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b851aa0b26d80a43f5a839232298ace5507f471b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222564"
---
# <a name="configure-the-soap-action-for-siebel"></a><span data-ttu-id="a98b1-103">Configurar la acción SOAP para Siebel</span><span class="sxs-lookup"><span data-stu-id="a98b1-103">Configure the SOAP action for Siebel</span></span>
<span data-ttu-id="a98b1-104">Para realizar cualquier operación en el sistema de Siebel mediante basadas en WCF [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], los usuarios de adaptador deben especificar una acción de SOAP.</span><span class="sxs-lookup"><span data-stu-id="a98b1-104">To perform any operation on the Siebel system using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], adapter users must specify a SOAP action.</span></span> <span data-ttu-id="a98b1-105">La acción SOAP comunica con el adaptador de la acción que debe realizarse.</span><span class="sxs-lookup"><span data-stu-id="a98b1-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="a98b1-106">Puede especificar la acción de SOAP en tiempo de diseño o en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a98b1-106">You can specify the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="a98b1-107">Sin embargo, si especifica la acción de SOAP tanto en tiempo de diseño y tiempo de ejecución, se invalidará la acción especificada en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="a98b1-107">However, if you specify the SOAP action both at design time and run time, the action you specified at design time will be overridden.</span></span>  
  
 <span data-ttu-id="a98b1-108">Para obtener más información acerca de cómo especificar la acción SOAP, vea [especificar acciones SOAP para adaptadores de envío de WCF](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="a98b1-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>
  
## <a name="enter-soap-action-at-design-time"></a><span data-ttu-id="a98b1-109">Especifique la acción de SOAP en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="a98b1-109">Enter SOAP Action at Design Time</span></span>  
 <span data-ttu-id="a98b1-110">Para tiempo de diseño, debe especificar la acción SOAP como parte de la orquestación mediante la inclusión de una forma expresión.</span><span class="sxs-lookup"><span data-stu-id="a98b1-110">For design time, you must specify the SOAP action as part of orchestration by including an expression shape.</span></span>  
  
1.  <span data-ttu-id="a98b1-111">En BizTalk orquestación incluyen una forma expresión arrastrándolo desde el **orquestación de BizTalk** cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="a98b1-111">In the BizTalk orchestration include an Expression shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="a98b1-112">Haga doble clic en el **expresión** forma para abrir el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a98b1-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="a98b1-113">Especifica la acción en el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a98b1-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="a98b1-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a98b1-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"  
    ```  
  
     <span data-ttu-id="a98b1-115">Para obtener más información acerca de **expresión** forma y el Editor de expresiones de BizTalk, consulte [cómo crear expresiones](../../core/how-to-create-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="a98b1-115">For more information about **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-at-run-time"></a><span data-ttu-id="a98b1-116">Especifique la acción de SOAP en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a98b1-116">Enter SOAP Action at run time</span></span>  
 <span data-ttu-id="a98b1-117">Para el tiempo de ejecución, debe especificar la acción SOAP junto con el cuadro de diálogo de propiedades de puerto WCF-Custom o WCF-Siebel.</span><span class="sxs-lookup"><span data-stu-id="a98b1-117">For run time, you must specify the SOAP action as part of the WCF-Custom or WCF-Siebel port properties dialog box.</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="a98b1-118">Especifique una acción de SOAP para el puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="a98b1-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="a98b1-119">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a98b1-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a98b1-120">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="a98b1-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="a98b1-121">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="a98b1-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="a98b1-122">En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="a98b1-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="a98b1-123">En el **propiedades de transporte de WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="a98b1-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="a98b1-124">En el **acción** texto, especifique la acción SOAP para la operación.</span><span class="sxs-lookup"><span data-stu-id="a98b1-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="a98b1-125">Puede especificar la acción de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="a98b1-125">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="a98b1-126">**Con el formato de acción única**.</span><span class="sxs-lookup"><span data-stu-id="a98b1-126">**By using the single action format**.</span></span> <span data-ttu-id="a98b1-127">Utilice este formato si WCF-Custom puerto envía y recibe mensajes de una sola operación.</span><span class="sxs-lookup"><span data-stu-id="a98b1-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="a98b1-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a98b1-128">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    -   <span data-ttu-id="a98b1-129">**Con el formato de asignación de acción**.</span><span class="sxs-lookup"><span data-stu-id="a98b1-129">**By using the action mapping format**.</span></span> <span data-ttu-id="a98b1-130">Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación.</span><span class="sxs-lookup"><span data-stu-id="a98b1-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="a98b1-131">Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para realizar una operación de inserción en el componente de negocio de cuenta) y Op2 (para realizar una operación de actualización en el componente de negocio de cuenta), la acción SOAP puede especificarse en el siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="a98b1-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to perform an Insert operation on Account business component) and Op2 (to perform an Update operation on Account business component), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="a98b1-132">Este enfoque proporciona mayor flexibilidad en cuanto a especificar un conjunto de acciones y, por tanto, habilitar mensajes que pertenecen a tipos de acción diferentes fluyan a través del mismo puerto.</span><span class="sxs-lookup"><span data-stu-id="a98b1-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="a98b1-133">El formato de la acción SOAP es diferente para cada operación.</span><span class="sxs-lookup"><span data-stu-id="a98b1-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="a98b1-134">Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span><span class="sxs-lookup"><span data-stu-id="a98b1-134">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span></span>
  
#### <a name="enter-a-soap-action-for-the-wcf-siebel-port"></a><span data-ttu-id="a98b1-135">Especifique una acción de SOAP para el puerto de WCF-Siebel</span><span class="sxs-lookup"><span data-stu-id="a98b1-135">Enter a SOAP action for the WCF-Siebel port</span></span>  
  
1.  <span data-ttu-id="a98b1-136">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a98b1-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="a98b1-137">Agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="a98b1-137">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a98b1-138">Para obtener instrucciones, consulte [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="a98b1-138">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="a98b1-139">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="a98b1-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="a98b1-140">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="a98b1-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="a98b1-141">En el cuadro de diálogo de propiedades de puerto de la **tipo** lista desplegable, seleccione el WCF-Siebel adaptador agrega anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="a98b1-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-Siebel adapter you add earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="a98b1-142">En el cuadro de diálogo Propiedades de puerto, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="a98b1-142">In the port properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="a98b1-143">En el **acción** texto, especifique la acción SOAP para la operación.</span><span class="sxs-lookup"><span data-stu-id="a98b1-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="a98b1-144">Puede especificar la acción de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="a98b1-144">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="a98b1-145">**Con el formato de acción única**.</span><span class="sxs-lookup"><span data-stu-id="a98b1-145">**By using the single action format**.</span></span> <span data-ttu-id="a98b1-146">Utilice este formato si WCF-Custom puerto envía y recibe mensajes de una sola operación.</span><span class="sxs-lookup"><span data-stu-id="a98b1-146">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="a98b1-147">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a98b1-147">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    -   <span data-ttu-id="a98b1-148">**Con el formato de asignación de acción**.</span><span class="sxs-lookup"><span data-stu-id="a98b1-148">**By using the action mapping format**.</span></span> <span data-ttu-id="a98b1-149">Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación.</span><span class="sxs-lookup"><span data-stu-id="a98b1-149">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="a98b1-150">Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para realizar una operación de inserción en el componente de negocio de cuenta) y Op2 (para realizar una operación de actualización en el componente de negocio de cuenta), la acción SOAP puede especificarse en el siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="a98b1-150">For example, if a single WCF-Custom port sends and receives messages for Op1 (to perform an Insert operation on Account business component) and Op2 (to perform an Update operation on Account business component), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="a98b1-151">Este enfoque proporciona mayor flexibilidad en cuanto a especificar un conjunto de acciones y, por tanto, habilitar mensajes que pertenecen a tipos de acción diferentes fluyan a través del mismo puerto.</span><span class="sxs-lookup"><span data-stu-id="a98b1-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="a98b1-152">El formato de la acción SOAP es diferente para cada operación.</span><span class="sxs-lookup"><span data-stu-id="a98b1-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="a98b1-153">Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span><span class="sxs-lookup"><span data-stu-id="a98b1-153">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a98b1-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="a98b1-154">See Also</span></span>  
[<span data-ttu-id="a98b1-155">Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="a98b1-155">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)