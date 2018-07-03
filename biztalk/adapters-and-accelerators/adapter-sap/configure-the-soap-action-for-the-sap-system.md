---
title: Configurar la acción SOAP para el sistema SAP en BizTalk | Microsoft Docs
description: Especifique una acción de SOAP en forma de expresión, o utilizar el adaptador WCF-Custom o WCF-SAP en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76084bc5-7a10-4c4c-be22-bee83779a011
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 963c4b3c8d8287b430774813487e924837880a01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004877"
---
# <a name="configure-the-soap-action-for-the-sap-system"></a><span data-ttu-id="32e64-103">Configurar la acción SOAP para el sistema SAP</span><span class="sxs-lookup"><span data-stu-id="32e64-103">Configure the SOAP action for the SAP system</span></span>
<span data-ttu-id="32e64-104">Para realizar cualquier operación en el sistema SAP mediante basada en WCF [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], los usuarios de adaptador deben especificar una acción de SOAP.</span><span class="sxs-lookup"><span data-stu-id="32e64-104">To perform any operation on the SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], adapter users must specify a SOAP action.</span></span> <span data-ttu-id="32e64-105">La acción SOAP comunica al adaptador qué acción debe realizarse.</span><span class="sxs-lookup"><span data-stu-id="32e64-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="32e64-106">Puede especificar la acción de SOAP en tiempo de diseño o en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="32e64-106">You can specify the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="32e64-107">Sin embargo, si se especifica la acción de SOAP tanto en tiempo de diseño y tiempo de ejecución, se invalidará la acción que ha especificado en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="32e64-107">However, if you specify the SOAP action both at design time and run time, the action you specified at design time will be overridden.</span></span>  
  
 <span data-ttu-id="32e64-108">Para obtener más información acerca de cómo especificar la acción SOAP, vea [especificar acciones SOAP para adaptadores de envío WCF](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="32e64-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>
  
## <a name="enter-soap-action-at-design-time"></a><span data-ttu-id="32e64-109">Especifique la acción de SOAP en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="32e64-109">Enter SOAP Action at Design Time</span></span>  
 <span data-ttu-id="32e64-110">Para el tiempo de diseño, debe especificar la acción SOAP como parte de la orquestación mediante la inclusión de una forma de expresión.</span><span class="sxs-lookup"><span data-stu-id="32e64-110">For design time, you must specify the SOAP action as part of orchestration by including an expression shape.</span></span>  
  
 
1.  <span data-ttu-id="32e64-111">En la orquestación de BizTalk, incluya una forma expresión arrastrándolo desde la **orquestación de BizTalk** cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="32e64-111">In the BizTalk orchestration, include an Expression shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="32e64-112">Haga doble clic en el **expresión** forma para abrir el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="32e64-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="32e64-113">Especifica la acción en el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="32e64-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="32e64-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32e64-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET"  
    ```  
  
     <span data-ttu-id="32e64-115">Para obtener más información sobre la **expresión** forma y el Editor de expresiones de BizTalk, consulte [cómo crear expresiones](../../core/how-to-create-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="32e64-115">For more information about the **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>
  
## <a name="enter-soap-action-at-run-time"></a><span data-ttu-id="32e64-116">Especifique la acción de SOAP en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="32e64-116">Enter SOAP Action at Run Time</span></span>  
 <span data-ttu-id="32e64-117">Para el tiempo de ejecución, puede especificar la acción SOAP como parte de la configuración del puerto WCF-Custom o WCF-SAP.</span><span class="sxs-lookup"><span data-stu-id="32e64-117">For run time, you can specify the SOAP action as part of the WCF-Custom or WCF-SAP port configuration.</span></span>  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="32e64-118">Especifique una acción de SOAP para el puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="32e64-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1. <span data-ttu-id="32e64-119">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="32e64-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="32e64-120">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="32e64-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="32e64-121">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="32e64-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3. <span data-ttu-id="32e64-122">En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="32e64-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="32e64-123">En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="32e64-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5. <span data-ttu-id="32e64-124">En el **acción** texto, especifique la acción SOAP para la operación.</span><span class="sxs-lookup"><span data-stu-id="32e64-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="32e64-125">Puede especificar la acción de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="32e64-125">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="32e64-126">**Con el formato de acción única**.</span><span class="sxs-lookup"><span data-stu-id="32e64-126">**By using the single action format**.</span></span> <span data-ttu-id="32e64-127">Utilice este formato si el WCF-Custom puerto envía y recibe mensajes de una sola operación.</span><span class="sxs-lookup"><span data-stu-id="32e64-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="32e64-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32e64-128">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   <span data-ttu-id="32e64-129">**Con el formato de asignación de acción**.</span><span class="sxs-lookup"><span data-stu-id="32e64-129">**By using the action mapping format**.</span></span> <span data-ttu-id="32e64-130">Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación.</span><span class="sxs-lookup"><span data-stu-id="32e64-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="32e64-131">Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para invocar RFC RFC_CUSTOMER_GET) y Op2 (para invocar BAPI BAPI_SALESORDER_CREATEFROMDAT2), se puede especificar la acción SOAP de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="32e64-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to invoke RFC_CUSTOMER_GET RFC) and Op2 (to invoke BAPI_SALESORDER_CREATEFROMDAT2 BAPI), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="32e64-132">Este enfoque proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluir a través del mismo puerto.</span><span class="sxs-lookup"><span data-stu-id="32e64-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="32e64-133">El formato de la acción SOAP es diferente para cada operación.</span><span class="sxs-lookup"><span data-stu-id="32e64-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="32e64-134">Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="32e64-134">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>
  
### <a name="enter-a-soap-action-for-the-wcf-sap-port"></a><span data-ttu-id="32e64-135">Especifique una acción de SOAP para el puerto de SAP de WCF</span><span class="sxs-lookup"><span data-stu-id="32e64-135">Enter a SOAP action for the WCF-SAP port</span></span>  
  
1. <span data-ttu-id="32e64-136">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="32e64-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="32e64-137">Agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="32e64-137">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="32e64-138">Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="32e64-138">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="32e64-139">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="32e64-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="32e64-140">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="32e64-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4. <span data-ttu-id="32e64-141">En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el adaptador SAP de WCF que agregó anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="32e64-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="32e64-142">En el cuadro de diálogo Propiedades de transporte, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="32e64-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6. <span data-ttu-id="32e64-143">En el **acción** texto, especifique la acción SOAP para la operación.</span><span class="sxs-lookup"><span data-stu-id="32e64-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="32e64-144">Puede especificar la acción de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="32e64-144">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="32e64-145">**Con el formato de acción única**.</span><span class="sxs-lookup"><span data-stu-id="32e64-145">**By using the single action format**.</span></span> <span data-ttu-id="32e64-146">Utilice este formato si el WCF-Custom puerto envía y recibe mensajes de una sola operación.</span><span class="sxs-lookup"><span data-stu-id="32e64-146">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="32e64-147">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32e64-147">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   <span data-ttu-id="32e64-148">**Con el formato de asignación de acción**.</span><span class="sxs-lookup"><span data-stu-id="32e64-148">**By using the action mapping format**.</span></span> <span data-ttu-id="32e64-149">Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación.</span><span class="sxs-lookup"><span data-stu-id="32e64-149">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="32e64-150">Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para invocar RFC RFC_CUSTOMER_GET) y Op2 (para invocar BAPI BAPI_SALESORDER_CREATEFROMDAT2), se puede especificar la acción SOAP de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="32e64-150">For example, if a single WCF-Custom port sends and receives messages for Op1 (to invoke RFC_CUSTOMER_GET RFC) and Op2 (to invoke BAPI_SALESORDER_CREATEFROMDAT2 BAPI), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="32e64-151">Este enfoque proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluir a través del mismo puerto.</span><span class="sxs-lookup"><span data-stu-id="32e64-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="32e64-152">El formato de la acción SOAP es diferente para cada operación.</span><span class="sxs-lookup"><span data-stu-id="32e64-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="32e64-153">Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="32e64-153">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="32e64-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="32e64-154">See Also</span></span>  
[<span data-ttu-id="32e64-155">Bloques de creación para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="32e64-155">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)