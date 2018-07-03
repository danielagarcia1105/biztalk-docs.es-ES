---
title: Configurar la acción SOAP para la base de datos de Oracle en BizTalk | Microsoft Docs
description: Especifique una acción de SOAP en Visual Studio, o utilizar el adaptador WCF-Custom o WCF-OracleDB en el módulo de adaptador de BizTalk (BAP)
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d21cca-3907-4f99-af76-c1e7286e1bcf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe8b1b2c1043551b692530dcff4b8fdf49a44b54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994677"
---
# <a name="configure-the-soap-action-for-oracle-database"></a><span data-ttu-id="d9096-103">Configurar la acción SOAP para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="d9096-103">Configure the SOAP action for Oracle Database</span></span>
<span data-ttu-id="d9096-104">Para completar cualquier operación en la base de datos de Oracle con el basado en WCF [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], los usuarios de adaptador deben especificar una acción de SOAP.</span><span class="sxs-lookup"><span data-stu-id="d9096-104">To complete any operation on the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], adapter users must enter a SOAP action.</span></span> <span data-ttu-id="d9096-105">La acción SOAP comunica al adaptador qué acción debe completarse.</span><span class="sxs-lookup"><span data-stu-id="d9096-105">The SOAP action communicates to the adapter what action should be completed.</span></span> <span data-ttu-id="d9096-106">Puede especificar la acción de SOAP en tiempo de diseño o en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d9096-106">You can enter the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="d9096-107">Sin embargo, si especifica la acción de SOAP tanto en tiempo de diseño y tiempo de ejecución, se reemplaza la acción que escriba en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="d9096-107">However, if you enter the SOAP action both at design time and run time, the action you enter at design time is overridden.</span></span>  
  
 <span data-ttu-id="d9096-108">Para obtener más información acerca de cómo especificar la acción SOAP, vea [especificar acciones SOAP para adaptadores de envío WCF](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span><span class="sxs-lookup"><span data-stu-id="d9096-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>  
  
## <a name="enter-soap-action-from-visual-studio"></a><span data-ttu-id="d9096-109">Especifique la acción SOAP desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d9096-109">Enter SOAP Action from Visual Studio</span></span>  
 <span data-ttu-id="d9096-110">Desde Visual Studio, debe especificar la acción SOAP como parte de la orquestación mediante un **expresión** forma.</span><span class="sxs-lookup"><span data-stu-id="d9096-110">From Visual Studio, you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="d9096-111">En la orquestación de BizTalk, incluya una **expresión** forma arrastrándolo desde la **orquestación de BizTalk** cuadro de herramientas.</span><span class="sxs-lookup"><span data-stu-id="d9096-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="d9096-112">Haga doble clic en el **expresión** forma para abrir el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d9096-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="d9096-113">Especifica la acción en el Editor de expresiones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d9096-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="d9096-114">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d9096-114">For example:</span></span>  
  
    ```
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
    ```  
  
     <span data-ttu-id="d9096-115">Para obtener más información acerca de **expresión** forma y el Editor de expresiones de BizTalk, consulte [cómo crear expresiones](../../core/how-to-create-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="d9096-115">For more information about **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a><span data-ttu-id="d9096-116">Especifique la acción SOAP de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="d9096-116">Enter SOAP Action from BizTalk Server Administration</span></span>  
 <span data-ttu-id="d9096-117">Desde la consola de administración de BizTalk Server, debe especificar la acción SOAP como parte de la configuración del puerto WCF-Custom o WCF-OracleDB.</span><span class="sxs-lookup"><span data-stu-id="d9096-117">From the BizTalk Server Administration console, you must specify the SOAP action as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span> 

#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="d9096-118">Especifique una acción de SOAP para el puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="d9096-118">Enter a SOAP action for the WCF-Custom port</span></span>  
 
  
1. <span data-ttu-id="d9096-119">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="d9096-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="d9096-120">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="d9096-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="d9096-121">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="d9096-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3. <span data-ttu-id="d9096-122">En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="d9096-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="d9096-123">En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="d9096-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5. <span data-ttu-id="d9096-124">En el **acción** texto, especifique la acción SOAP para la operación.</span><span class="sxs-lookup"><span data-stu-id="d9096-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="d9096-125">Puede especificar la acción de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="d9096-125">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="d9096-126">**Con el formato de acción única**.</span><span class="sxs-lookup"><span data-stu-id="d9096-126">**By using the single action format**.</span></span> <span data-ttu-id="d9096-127">Utilice este formato si el WCF-Custom puerto envía y recibe mensajes de una sola operación.</span><span class="sxs-lookup"><span data-stu-id="d9096-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="d9096-128">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d9096-128">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   <span data-ttu-id="d9096-129">**Con el formato de asignación de acción**.</span><span class="sxs-lookup"><span data-stu-id="d9096-129">**By using the action mapping format**.</span></span> <span data-ttu-id="d9096-130">Utilice este formato si un puerto personalizado de WCF solo envía y recibe mensajes de más de una operación.</span><span class="sxs-lookup"><span data-stu-id="d9096-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="d9096-131">Por ejemplo, si un puerto personalizado de WCF solo envía y recibe mensajes para Op1 (para insertar registros en la tabla EMP) y Op2 (para actualizar registros en la tabla EMP), se puede especificar la acción SOAP de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d9096-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the EMP table) and Op2 (to update records in the EMP table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="d9096-132">Este enfoque proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluir a través del mismo puerto.</span><span class="sxs-lookup"><span data-stu-id="d9096-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="d9096-133">El formato de la acción SOAP es diferente para cada operación.</span><span class="sxs-lookup"><span data-stu-id="d9096-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="d9096-134">Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="d9096-134">For more information about action format for each operation, see [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-oracledb-port"></a><span data-ttu-id="d9096-135">Especifique una acción de SOAP para el puerto de WCF-OracleDB</span><span class="sxs-lookup"><span data-stu-id="d9096-135">Enter a SOAP action for the WCF-OracleDB port</span></span>  
  
1. <span data-ttu-id="d9096-136">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="d9096-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="d9096-137">Agregar el adaptador de WCF-OracleDB a la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d9096-137">Add the WCF-OracleDB adapter to the BizTalk Server Administration console.</span></span> <span data-ttu-id="d9096-138">Para obtener instrucciones, consulte [agregación del adaptador de base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="d9096-138">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="d9096-139">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="d9096-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="d9096-140">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="d9096-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4. <span data-ttu-id="d9096-141">En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el puerto de WCF-OracleDB que agregó anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="d9096-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleDB port you added earlier, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="d9096-142">En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **General** ficha.</span><span class="sxs-lookup"><span data-stu-id="d9096-142">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
6. <span data-ttu-id="d9096-143">En el **acción** texto, especifique la acción SOAP para la operación.</span><span class="sxs-lookup"><span data-stu-id="d9096-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="d9096-144">Puede especificar la acción de las maneras siguientes:</span><span class="sxs-lookup"><span data-stu-id="d9096-144">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="d9096-145">**Con el formato de acción única**.</span><span class="sxs-lookup"><span data-stu-id="d9096-145">**By using the single action format**.</span></span> <span data-ttu-id="d9096-146">Utilice este formato si el WCF-OracleDB puerto envía y recibe mensajes de una sola operación.</span><span class="sxs-lookup"><span data-stu-id="d9096-146">Use this format if the WCF-OracleDB port sends and receive messages for a single operation.</span></span> <span data-ttu-id="d9096-147">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d9096-147">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   <span data-ttu-id="d9096-148">**Con el formato de asignación de acción**.</span><span class="sxs-lookup"><span data-stu-id="d9096-148">**By using the action mapping format**.</span></span> <span data-ttu-id="d9096-149">Utilice este formato si un único puerto de WCF-OracleDB envía y recibe mensajes de más de una operación.</span><span class="sxs-lookup"><span data-stu-id="d9096-149">Use this format if a single WCF-OracleDB port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="d9096-150">Por ejemplo, si un único puerto de WCF-OracleDB envía y recibe los mensajes de Op1 (para insertar registros en la tabla EMP) y Op2 (para actualizar registros en la tabla EMP), se puede especificar la acción SOAP de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d9096-150">For example, if a single WCF-OracleDB port sends and receives messages for Op1 (to insert records in the EMP table) and Op2 (to update records in the EMP table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="d9096-151">Este enfoque proporciona mayor flexibilidad en términos de especificación de un conjunto de acciones y, por tanto, lo que permite los mensajes que pertenecen a tipos de acción diferentes fluir a través del mismo puerto.</span><span class="sxs-lookup"><span data-stu-id="d9096-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="d9096-152">El formato de la acción SOAP es diferente para cada operación.</span><span class="sxs-lookup"><span data-stu-id="d9096-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="d9096-153">Para obtener más información acerca del formato de acción para cada operación, vea [mensajes y esquemas de mensaje](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span><span class="sxs-lookup"><span data-stu-id="d9096-153">For more information about action format for each operation, see [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d9096-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9096-154">See Also</span></span>  
[<span data-ttu-id="d9096-155">Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="d9096-155">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)