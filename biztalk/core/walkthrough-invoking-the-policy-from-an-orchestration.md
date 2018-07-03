---
title: 'Tutorial: Invocar la directiva desde una orquestación | Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb2d2974-8a36-4d36-905c-799e4236ef99
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33bef51b2c702e71fcf6ef0ea0c4fd63b28fbde8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976563"
---
# <a name="walkthrough-invoking-the-policy-from-an-orchestration"></a><span data-ttu-id="2524b-102">Tutorial: Invocar la directiva desde una orquestación</span><span class="sxs-lookup"><span data-stu-id="2524b-102">Walkthrough: Invoking the Policy from an Orchestration</span></span>
<span data-ttu-id="2524b-103">Puede invocar una directiva desde una orquestación de una de las formas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2524b-103">You can invoke a policy from an orchestration in one of the following ways:</span></span>  

- <span data-ttu-id="2524b-104">Mediante el uso de la **reglas de llamada** forma</span><span class="sxs-lookup"><span data-stu-id="2524b-104">By using the **Call Rules** shape</span></span>  

- <span data-ttu-id="2524b-105">Mediante el uso de la **expresión** dar forma a e invocando mediante programación el motor de reglas para ejecutar la directiva (**Policy.Execute** método)</span><span class="sxs-lookup"><span data-stu-id="2524b-105">By using the **Expression** shape, and programmatically invoking the rule engine to execute the policy (**Policy.Execute** method)</span></span>  

  <span data-ttu-id="2524b-106">Mediante el **reglas de llamada** forma es la manera más común y también el método recomendado para invocar una directiva desde una orquestación.</span><span class="sxs-lookup"><span data-stu-id="2524b-106">Using the **Call Rules** shape is the most common way and also the recommended way to invoke a policy from an orchestration.</span></span> <span data-ttu-id="2524b-107">Este tutorial proporciona procedimientos paso a paso para usar el **reglas de llamada** forma para invocar el **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="2524b-107">This walkthrough provides step-by-step procedures for using the **Call Rules** shape to invoke the **ProcessPurchaseOrder** policy.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="2524b-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2524b-108">Prerequisites</span></span>  
 <span data-ttu-id="2524b-109">Debe completar el [Tutorial: probar la directiva](../core/walkthrough-testing-the-policy.md) tutorial antes de realizar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="2524b-109">You must complete the [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) walkthrough before performing this walkthrough.</span></span>  

## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="2524b-110">Información general de este tutorial</span><span class="sxs-lookup"><span data-stu-id="2524b-110">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="2524b-111">Este tutorial contiene siete procedimientos, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="2524b-111">This walkthrough contains seven procedures, as described in the following table.</span></span>  

|<span data-ttu-id="2524b-112">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="2524b-112">Procedure title</span></span>|<span data-ttu-id="2524b-113">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="2524b-113">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="2524b-114">Para crear un proyecto de BizTalk con un esquema y una orquestación</span><span class="sxs-lookup"><span data-stu-id="2524b-114">To create a BizTalk project with a schema and an orchestration</span></span>|<span data-ttu-id="2524b-115">Proporciona instrucciones paso a paso para crear un esquema y una orquestación que invoca la **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="2524b-115">Provides step-by-step instructions for creating a schema and an orchestration that invokes the **ProcessPurchaseOrder** policy.</span></span>|  
|<span data-ttu-id="2524b-116">Procedimiento para crear variables de mensaje</span><span class="sxs-lookup"><span data-stu-id="2524b-116">To create message variables</span></span>|<span data-ttu-id="2524b-117">Proporciona instrucciones paso a paso para crear variables de mensaje que se usan en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2524b-117">Provides step-by-step instructions for creating message variables used in the orchestration.</span></span>|  
|<span data-ttu-id="2524b-118">Para configurar formas</span><span class="sxs-lookup"><span data-stu-id="2524b-118">To configure shapes</span></span>|<span data-ttu-id="2524b-119">Proporciona instrucciones paso a paso para configurar formas en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2524b-119">Provides step-by-step instructions for configuring shapes in the orchestration.</span></span>|  
|<span data-ttu-id="2524b-120">Para crear puertos</span><span class="sxs-lookup"><span data-stu-id="2524b-120">To create ports</span></span>|<span data-ttu-id="2524b-121">Proporciona instrucciones paso a paso para crear puertos en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2524b-121">Provides step-by-step instructions for creating ports in the orchestration.</span></span>|  
|<span data-ttu-id="2524b-122">Procedimiento para conectar puertos con las formas</span><span class="sxs-lookup"><span data-stu-id="2524b-122">To connect ports with the shapes</span></span>|<span data-ttu-id="2524b-123">Proporciona instrucciones paso a paso para conectar puertos con las formas.</span><span class="sxs-lookup"><span data-stu-id="2524b-123">Provides step-by-step instructions for connecting ports with the shapes.</span></span>|  
|<span data-ttu-id="2524b-124">Procedimiento para generar e implementar la solución</span><span class="sxs-lookup"><span data-stu-id="2524b-124">To build and deploy the solution</span></span>|<span data-ttu-id="2524b-125">Proporciona instrucciones paso a paso para generar e implementar la solución.</span><span class="sxs-lookup"><span data-stu-id="2524b-125">Provides step-by-step instructions for building and deploying the solution.</span></span>|  
|<span data-ttu-id="2524b-126">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="2524b-126">To test the solution</span></span>|<span data-ttu-id="2524b-127">Proporciona instrucciones paso a paso para probar la solución.</span><span class="sxs-lookup"><span data-stu-id="2524b-127">Provides step-by-step instructions for testing the solution.</span></span>|  

### <a name="to-create-a-biztalk-project-with-a-schema-and-an-orchestration"></a><span data-ttu-id="2524b-128">Para crear un proyecto de BizTalk con un esquema y una orquestación</span><span class="sxs-lookup"><span data-stu-id="2524b-128">To create a BizTalk project with a schema and an orchestration</span></span>  

1. <span data-ttu-id="2524b-129">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="2524b-129">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="2524b-130">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="2524b-130">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  

3. <span data-ttu-id="2524b-131">En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2524b-131">In the **New Project** dialog box, do the following:</span></span>  


   |             <span data-ttu-id="2524b-132">Use</span><span class="sxs-lookup"><span data-stu-id="2524b-132">Use this</span></span>              |                             <span data-ttu-id="2524b-133">Para</span><span class="sxs-lookup"><span data-stu-id="2524b-133">To do this</span></span>                              |
   |-----------------------------------|---------------------------------------------------------------------|
   |         <span data-ttu-id="2524b-134">**Tipos de proyecto**</span><span class="sxs-lookup"><span data-stu-id="2524b-134">**Project types**</span></span>         |                     <span data-ttu-id="2524b-135">Haga clic en **proyectos de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="2524b-135">Click **BizTalk Projects**.</span></span>                     |
   |           <span data-ttu-id="2524b-136">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="2524b-136">**Templates**</span></span>           |               <span data-ttu-id="2524b-137">Haga clic en **proyecto de BizTalk Server vacío**.</span><span class="sxs-lookup"><span data-stu-id="2524b-137">Click **Empty BizTalk Server Project**.</span></span>               |
   |             <span data-ttu-id="2524b-138">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2524b-138">**Name**</span></span>              |                         <span data-ttu-id="2524b-139">Tipo **RuleTest**.</span><span class="sxs-lookup"><span data-stu-id="2524b-139">Type **RuleTest**.</span></span>                          |
   |           <span data-ttu-id="2524b-140">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="2524b-140">**Location**</span></span>            |                  <span data-ttu-id="2524b-141">Especificar **C:\BRE-Walkthroughs**.</span><span class="sxs-lookup"><span data-stu-id="2524b-141">Specify **C:\BRE-Walkthroughs**.</span></span>                   |
   |         <span data-ttu-id="2524b-142">**Nombre de solución**</span><span class="sxs-lookup"><span data-stu-id="2524b-142">**Solution Name**</span></span>         |                        <span data-ttu-id="2524b-143">Tipo **RuleTestSol**.</span><span class="sxs-lookup"><span data-stu-id="2524b-143">Type **RuleTestSol**.</span></span>                        |
   | <span data-ttu-id="2524b-144">**Crear directorio para la solución**</span><span class="sxs-lookup"><span data-stu-id="2524b-144">**Create directory for solution**</span></span> | <span data-ttu-id="2524b-145">Seleccione esta casilla para crear un directorio para los archivos de la solución.</span><span class="sxs-lookup"><span data-stu-id="2524b-145">Select this check box to create a directory for the solution files.</span></span> |


4. <span data-ttu-id="2524b-146">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-146">Click **OK**.</span></span> <span data-ttu-id="2524b-147">El **RuleTest** proyecto debe aparecer en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="2524b-147">The **RuleTest** project should appear in Solution Explorer.</span></span> <span data-ttu-id="2524b-148">Si no ve el Explorador de soluciones, haga clic en **el Explorador de soluciones** en el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="2524b-148">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  

5. <span data-ttu-id="2524b-149">En el Explorador de soluciones, haga clic en **RuleTest**, apunte a **agregar**y, a continuación, haga clic en **elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="2524b-149">In Solution Explorer, right-click **RuleTest**, point to **Add**, and then click **Existing Item**.</span></span>  

6. <span data-ttu-id="2524b-150">Busque y agregue el **PO.xsd** que creó en el archivo de esquema el [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial.</span><span class="sxs-lookup"><span data-stu-id="2524b-150">Browse and add the **PO.xsd** schema file you created in the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough.</span></span> <span data-ttu-id="2524b-151">Visual Studio realiza una copia de la **PO.xsd** de archivo y lo agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="2524b-151">Visual Studio makes a copy of the **PO.xsd** file and adds it to the project.</span></span>  

7. <span data-ttu-id="2524b-152">En el Explorador de soluciones, haga clic en **RuleTest**, apunte a **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2524b-152">In Solution Explorer, right-click **RuleTest**, point to **Add**, and then click **New Item**.</span></span>  

8. <span data-ttu-id="2524b-153">En el **Agregar nuevo elemento** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2524b-153">In the **Add New Item** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="2524b-154">Use</span><span class="sxs-lookup"><span data-stu-id="2524b-154">Use this</span></span>    |            <span data-ttu-id="2524b-155">Para</span><span class="sxs-lookup"><span data-stu-id="2524b-155">To do this</span></span>            |
   |----------------|----------------------------------|
   | <span data-ttu-id="2524b-156">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="2524b-156">**Categories**</span></span> |  <span data-ttu-id="2524b-157">Haga clic en **archivos de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="2524b-157">Click **Orchestration Files**.</span></span>  |
   | <span data-ttu-id="2524b-158">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="2524b-158">**Templates**</span></span>  | <span data-ttu-id="2524b-159">Haga clic en **orquestación de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="2524b-159">Click **BizTalk Orchestration**.</span></span> |
   |    <span data-ttu-id="2524b-160">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="2524b-160">**Name**</span></span>    |      <span data-ttu-id="2524b-161">Tipo **RuleTest.odx**.</span><span class="sxs-lookup"><span data-stu-id="2524b-161">Type **RuleTest.odx**.</span></span>      |


9. <span data-ttu-id="2524b-162">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-162">Click **Add**.</span></span>  

10. <span data-ttu-id="2524b-163">Haga clic en **coloca una forma desde el cuadro de herramientas aquí**, apunte a **Insertar forma**y, a continuación, haga clic en **recepción**.</span><span class="sxs-lookup"><span data-stu-id="2524b-163">Right-click **Drop a shape from the toolbox here**, point to **Insert Shape**, and then click **Receive**.</span></span>  

11. <span data-ttu-id="2524b-164">En la ventana Propiedades, cambie el nombre de la **recepción** dar forma a **ReceivePO**y establezca el valor de la **activar** propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="2524b-164">In the Properties window, change the name of the **Receive** shape to **ReceivePO**, and set the value of the **Activate** property to `true`.</span></span>  

12. <span data-ttu-id="2524b-165">En el cuadro de herramientas, en el **orquestaciones de BizTalk** pestaña, arrastre el **reglas de llamada** forma en una línea de conexión debajo el **recepción** forma.</span><span class="sxs-lookup"><span data-stu-id="2524b-165">In the Toolbox, on the **BizTalk Orchestrations** tab, drag the **Call Rules** shape onto a connecting line below the **Receive** shape.</span></span>  

13. <span data-ttu-id="2524b-166">En la ventana Propiedades, cambie el nombre de la **reglas de llamada** dar forma a **CallProcessPOPolicy**.</span><span class="sxs-lookup"><span data-stu-id="2524b-166">In the Properties window, change the name of the **Call Rules** shape to **CallProcessPOPolicy**.</span></span>  

14. <span data-ttu-id="2524b-167">A continuación haga el **reglas de llamada** forma, elija **Insertar forma**y, a continuación, haga clic en **enviar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-167">Right-click below the **Call Rules** shape, point to **Insert Shape**, and then click **Send**.</span></span>  

15. <span data-ttu-id="2524b-168">En la ventana Propiedades, cambie el nombre de la **enviar** dar forma a **SendPO**.</span><span class="sxs-lookup"><span data-stu-id="2524b-168">In the Properties window, change the name of the **Send** shape to **SendPO**.</span></span> <span data-ttu-id="2524b-169">La orquestación tendrá aspecto de la ilustración siguiente:</span><span class="sxs-lookup"><span data-stu-id="2524b-169">The orchestration should look like the following figure.</span></span>  

     <span data-ttu-id="2524b-170">![BRE&#45;tutorial&#45;UnconfiguredOrch](../core/media/1f3502ac-82a9-40bf-ae31-6e8356a283e2.gif "1f3502ac-82a9-40bf-ae31-6e8356a283e2")</span><span class="sxs-lookup"><span data-stu-id="2524b-170">![BRE&#45;Walkthrough&#45;UnconfiguredOrch](../core/media/1f3502ac-82a9-40bf-ae31-6e8356a283e2.gif "1f3502ac-82a9-40bf-ae31-6e8356a283e2")</span></span>  

### <a name="to-create-message-variables"></a><span data-ttu-id="2524b-171">Procedimiento para crear variables de mensaje</span><span class="sxs-lookup"><span data-stu-id="2524b-171">To create message variables</span></span>  

1.  <span data-ttu-id="2524b-172">En la ventana Vista orquestación, haga clic en **mensajes**y, a continuación, haga clic en **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="2524b-172">In the Orchestration View window, right-click **Messages**, and then click **New Message**.</span></span> <span data-ttu-id="2524b-173">Si no ve la ventana Vista orquestación, haga clic en el **vista** menú, elija **Other Windows**y, a continuación, haga clic en **Vista orquestación**.</span><span class="sxs-lookup"><span data-stu-id="2524b-173">If you do not see the Orchestration View window, click the **View** menu, point to **Other Windows**, and then click **Orchestration View**.</span></span> <span data-ttu-id="2524b-174">Normalmente, la ventana Vista orquestación está en la ficha situada junto a la ficha Explorador de soluciones. De forma predeterminada, el nuevo mensaje se denomina **Message_1**.</span><span class="sxs-lookup"><span data-stu-id="2524b-174">Typically, the Orchestration View window is on the tab next to the Solution Explorer tab. By default, the new message is named **Message_1**.</span></span>  

     <span data-ttu-id="2524b-175">![BRE&#45;tutorial&#45;OrchViewNewMsg](../core/media/a0b7fee3-af90-4c01-9464-146f0ca449e5.gif "a0b7fee3-af90-4c01-9464-146f0ca449e5")</span><span class="sxs-lookup"><span data-stu-id="2524b-175">![BRE&#45;Walkthrough&#45;OrchViewNewMsg](../core/media/a0b7fee3-af90-4c01-9464-146f0ca449e5.gif "a0b7fee3-af90-4c01-9464-146f0ca449e5")</span></span>  

2.  <span data-ttu-id="2524b-176">En la ventana Vista orquestación, haga clic en **Message_1**.</span><span class="sxs-lookup"><span data-stu-id="2524b-176">In the Orchestration View window, click **Message_1**.</span></span>  

3.  <span data-ttu-id="2524b-177">En la ventana Propiedades, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2524b-177">In the Properties window, do the following:</span></span>  

    |<span data-ttu-id="2524b-178">Use</span><span class="sxs-lookup"><span data-stu-id="2524b-178">Use this</span></span>|<span data-ttu-id="2524b-179">Para</span><span class="sxs-lookup"><span data-stu-id="2524b-179">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="2524b-180">**Identificador**</span><span class="sxs-lookup"><span data-stu-id="2524b-180">**Identifier**</span></span>|<span data-ttu-id="2524b-181">Tipo **POInst**, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="2524b-181">Type **POInst**, and then press ENTER.</span></span>|  
    |<span data-ttu-id="2524b-182">**Tipo de mensaje**</span><span class="sxs-lookup"><span data-stu-id="2524b-182">**Message Type**</span></span>|<span data-ttu-id="2524b-183">En la lista desplegable, expanda **esquemas**y, a continuación, seleccione **RuleTest.PO**.</span><span class="sxs-lookup"><span data-stu-id="2524b-183">From the drop-down list, expand **Schemas**, and then select **RuleTest.PO**.</span></span>|  

     <span data-ttu-id="2524b-184">![BRE&#45;tutorial&#45;MsgProps](../core/media/c82cfb67-63f6-4133-95bf-daadac0e213a.gif "c82cfb67-63f6-4133-95bf-daadac0e213a")</span><span class="sxs-lookup"><span data-stu-id="2524b-184">![BRE&#45;Walkthrough&#45;MsgProps](../core/media/c82cfb67-63f6-4133-95bf-daadac0e213a.gif "c82cfb67-63f6-4133-95bf-daadac0e213a")</span></span>  

### <a name="to-configure-shapes"></a><span data-ttu-id="2524b-185">Para configurar formas</span><span class="sxs-lookup"><span data-stu-id="2524b-185">To configure shapes</span></span>  

1. <span data-ttu-id="2524b-186">Seleccione el **recepción** forma en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="2524b-186">Select the **Receive** shape in Orchestration Designer.</span></span>  

2. <span data-ttu-id="2524b-187">En la ventana Propiedades, seleccione **POInst** para el **mensaje** propiedad.</span><span class="sxs-lookup"><span data-stu-id="2524b-187">In the Properties window, select **POInst** for the **Message** property.</span></span>  

3. <span data-ttu-id="2524b-188">Haga doble clic en el **reglas de llamada** forma en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="2524b-188">Double-click the **Call Rules** shape in Orchestration Designer.</span></span>  

4. <span data-ttu-id="2524b-189">En el **configuración de directiva de reglas de llamada** cuadro de diálogo, seleccione **ProcessPurchaseOrder** para la directiva.</span><span class="sxs-lookup"><span data-stu-id="2524b-189">In the **Call Rules policy configuration** dialog box, select **ProcessPurchaseOrder** for the policy.</span></span>  

5. <span data-ttu-id="2524b-190">Haga clic en siguiente para **\\** <em>, a continuación \*\* nombre de parámetro</em><em>y seleccione \**POInst</em>*  como un parámetro a la directiva.</span><span class="sxs-lookup"><span data-stu-id="2524b-190">Click next to **\\**<em>, below \*\*Parameter Name</em><em>, and select \**POInst</em>* as a parameter to the policy.</span></span>  

    <span data-ttu-id="2524b-191">![BRE&#45;tutorial&#45;ConfigureCallRules](../core/media/0e7dab04-41db-433b-bbf5-b13901033b41.gif "0e7dab04-41db-433b-bbf5-b13901033b41")</span><span class="sxs-lookup"><span data-stu-id="2524b-191">![BRE&#45;Walkthrough&#45;ConfigureCallRules](../core/media/0e7dab04-41db-433b-bbf5-b13901033b41.gif "0e7dab04-41db-433b-bbf5-b13901033b41")</span></span>  

6. <span data-ttu-id="2524b-192">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-192">Click **OK**.</span></span>  

7. <span data-ttu-id="2524b-193">Seleccione el **enviar** forma en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2524b-193">Select the **Send** shape in the orchestration.</span></span>  

8. <span data-ttu-id="2524b-194">En la ventana Propiedades, establezca el valor de la **tipo de mensaje** propiedad **POInst**.</span><span class="sxs-lookup"><span data-stu-id="2524b-194">In the Properties window, set the value of the **Message Type** property to **POInst**.</span></span>  

### <a name="to-create-ports"></a><span data-ttu-id="2524b-195">Para crear puertos</span><span class="sxs-lookup"><span data-stu-id="2524b-195">To create ports</span></span>  

1.  <span data-ttu-id="2524b-196">Cree dos carpetas, **entrada** y **salida**, en la carpeta C:\BRE-Walkthroughs\RuleTestSol.</span><span class="sxs-lookup"><span data-stu-id="2524b-196">Create two folders, **Input** and **Output**, in the C:\BRE-Walkthroughs\RuleTestSol folder.</span></span>  

2.  <span data-ttu-id="2524b-197">Haga clic en la superficie de puerto de la izquierda de la orquestación y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="2524b-197">Right-click the left port surface of the orchestration, and then click **New Configured Port**.</span></span>  

3.  <span data-ttu-id="2524b-198">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2524b-198">Click **Next**.</span></span> <span data-ttu-id="2524b-199">Tipo **ReceivePOPrt** para el nombre del puerto.</span><span class="sxs-lookup"><span data-stu-id="2524b-199">Type **ReceivePOPrt** for the port name.</span></span>  

4.  <span data-ttu-id="2524b-200">Haga clic en **siguiente** dos veces.</span><span class="sxs-lookup"><span data-stu-id="2524b-200">Click **Next** twice.</span></span>  

5.  <span data-ttu-id="2524b-201">Seleccione **especificar ahora** para el **enlace de puerto**.</span><span class="sxs-lookup"><span data-stu-id="2524b-201">Select **Specify Now** for the **port binding**.</span></span>  

6.  <span data-ttu-id="2524b-202">Especificar **archivo** para el **transporte**y escriba el nombre del directorio de entrada como **C:\BRE-Walkthroughs\RuleTestSol\Input\\\*.xml** junto con la máscara de archivo (**\*.xml**) para el URI.</span><span class="sxs-lookup"><span data-stu-id="2524b-202">Specify **FILE** for the **transport**, and type the name of the input directory as **C:\BRE-Walkthroughs\RuleTestSol\Input\\\*.xml** along with the file mask (**\*.xml**) for the URI.</span></span>  

7.  <span data-ttu-id="2524b-203">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-203">Click **Next**, and then click **Finish**.</span></span>  

8.  <span data-ttu-id="2524b-204">Haga clic en la superficie para puerto derecha de la orquestación y, a continuación, haga clic en **nuevo puerto configurado**.</span><span class="sxs-lookup"><span data-stu-id="2524b-204">Right-click the right port surface of the orchestration, and then click **New Configuration Port**.</span></span>  

9. <span data-ttu-id="2524b-205">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2524b-205">Click **Next**.</span></span> <span data-ttu-id="2524b-206">Tipo **sendpoport como** para el nombre del puerto.</span><span class="sxs-lookup"><span data-stu-id="2524b-206">Type **SendPOPort** for the port name.</span></span>  

10. <span data-ttu-id="2524b-207">Haga clic en **siguiente** dos veces.</span><span class="sxs-lookup"><span data-stu-id="2524b-207">Click **Next** twice.</span></span>  

11. <span data-ttu-id="2524b-208">Cambiar el **dirección de puerto de comunicación** a **siempre enviaré los mensajes en este puerto**.</span><span class="sxs-lookup"><span data-stu-id="2524b-208">Change the **Port direction of communication** to **I'll always be sending messages on this port**.</span></span>  

12. <span data-ttu-id="2524b-209">Seleccione **especificar ahora** para el **enlace de puerto**.</span><span class="sxs-lookup"><span data-stu-id="2524b-209">Select **Specify Now** for the **port binding**.</span></span>  

13. <span data-ttu-id="2524b-210">Especificar **archivo** para el **transporte**y escriba el nombre del directorio de salida como **C:\BRE-Walkthroughs\RuleTestSol\Output**y %MessageID%.xml como el archivo de salida nombre.</span><span class="sxs-lookup"><span data-stu-id="2524b-210">Specify **FILE** for the **transport**, and type the name of the output directory as **C:\BRE-Walkthroughs\RuleTestSol\Output**,and %MessageID%.xml as the output file name.</span></span>  

14. <span data-ttu-id="2524b-211">Haga clic en **Siguiente**y, a continuación, en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-211">Click **Next**, and then click **Finish**.</span></span>  

### <a name="to-connect-ports-with-the-shapes"></a><span data-ttu-id="2524b-212">Procedimiento para conectar puertos con las formas</span><span class="sxs-lookup"><span data-stu-id="2524b-212">To connect ports with the shapes</span></span>  

1.  <span data-ttu-id="2524b-213">Conectar el **ReceivePOPrt** puerto a la **ReceivePO** forma.</span><span class="sxs-lookup"><span data-stu-id="2524b-213">Connect the **ReceivePOPrt** port to the **ReceivePO** shape.</span></span> <span data-ttu-id="2524b-214">(Arrastre la flecha situada a la derecha del puerto ReceivePOPrt sobre la superficie de puerto hasta el cuadro sobre la forma ReceivePO.)</span><span class="sxs-lookup"><span data-stu-id="2524b-214">(Drag the arrow to the right of ReceivePOPrt port on the port surface to the box on the ReceivePO shape.)</span></span>  

     <span data-ttu-id="2524b-215">![BRE&#45;tutorial&#45;ConnectRP](../core/media/75bdf79e-ca98-43bb-8ff6-5f46005a6490.gif "75bdf79e-ca98-43bb-8ff6-5f46005a6490")</span><span class="sxs-lookup"><span data-stu-id="2524b-215">![BRE&#45;Walkthrough&#45;ConnectRP](../core/media/75bdf79e-ca98-43bb-8ff6-5f46005a6490.gif "75bdf79e-ca98-43bb-8ff6-5f46005a6490")</span></span>  

2.  <span data-ttu-id="2524b-216">Conectar el **SendPO** dar forma a la **SendPOPrt** puerto.</span><span class="sxs-lookup"><span data-stu-id="2524b-216">Connect the **SendPO** shape to the **SendPOPrt** port.</span></span>  

     <span data-ttu-id="2524b-217">![BRE&#45;tutorial&#45;ConnectSP](../core/media/7513f52b-2782-4357-b8eb-1874dec33869.gif "7513f52b-2782-4357-b8eb-1874dec33869")</span><span class="sxs-lookup"><span data-stu-id="2524b-217">![BRE&#45;Walkthrough&#45;ConnectSP](../core/media/7513f52b-2782-4357-b8eb-1874dec33869.gif "7513f52b-2782-4357-b8eb-1874dec33869")</span></span>  

### <a name="to-build-and-deploy-the-solution"></a><span data-ttu-id="2524b-218">Procedimiento para generar e implementar la solución</span><span class="sxs-lookup"><span data-stu-id="2524b-218">To build and deploy the solution</span></span>  

1. <span data-ttu-id="2524b-219">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="2524b-219">Start **Microsoft Visual Studio**.</span></span>  

2. <span data-ttu-id="2524b-220">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en el **RuleTest** del proyecto y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="2524b-220">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click the **RuleTest** project, and then click **Properties**.</span></span>  

3. <span data-ttu-id="2524b-221">En el Diseñador de proyectos (en el panel central), haga clic en **firma**.</span><span class="sxs-lookup"><span data-stu-id="2524b-221">In Project Designer (in the center pane), click **Signing**.</span></span>  

4. <span data-ttu-id="2524b-222">En la ficha firma, marque **firmar el ensamblado** casilla de verificación; En la lista desplegable **elegir un archivo de clave de nombre seguro**, haga clic en **New**; En el **nombre de archivo de clave** , introduzca la prueba de la regla; En el **contraseña** campo (opcional), establezca la contraseña y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-222">In Signing tab, Check **Sign the assembly** checkbox; In the dropdown list **Choose a strong name key file**, click **New**; In the **Key File name** field, enter Rule Test; In the **Password** field (Optional),  set Password, and then click **OK**.</span></span>  

5. <span data-ttu-id="2524b-223">En el Diseñador de proyectos, haga clic en **implementación** para cambiar a la pestaña implementación.</span><span class="sxs-lookup"><span data-stu-id="2524b-223">In Project Designer, click **Deployment** to switch to the Deployment tab.</span></span>  

6. <span data-ttu-id="2524b-224">Especificar **RuleTestApp** como el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2524b-224">Specify **RuleTestApp** as the application name.</span></span>  

    <span data-ttu-id="2524b-225">![BRE&#45;tutorial&#45;RuleTestApp](../core/media/b153e5b0-ca46-4d27-bfa1-9ad4e58e9787.gif "b153e5b0-ca46-4d27-bfa1-9ad4e58e9787")</span><span class="sxs-lookup"><span data-stu-id="2524b-225">![BRE&#45;Walkthrough&#45;RuleTestApp](../core/media/b153e5b0-ca46-4d27-bfa1-9ad4e58e9787.gif "b153e5b0-ca46-4d27-bfa1-9ad4e58e9787")</span></span>  

7. <span data-ttu-id="2524b-226">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-226">Click **OK**.</span></span>  

8. <span data-ttu-id="2524b-227">Haga clic en el **RuleTest** del proyecto y, a continuación, haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-227">Right-click the **RuleTest** project, and then click **Build**.</span></span>  

9. <span data-ttu-id="2524b-228">Haga clic en el **RuleTest** del proyecto y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-228">Right-click the **RuleTest** project, and then click **Deploy**.</span></span>  

### <a name="to-test-the-solution"></a><span data-ttu-id="2524b-229">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="2524b-229">To test the solution</span></span>  

1. <span data-ttu-id="2524b-230">En el Compositor de reglas de negocio, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.0**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-230">In Business Rule Composer, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Publish**.</span></span>  

2. <span data-ttu-id="2524b-231">Haga clic en **versión 1.0 - publicada**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-231">Right-click **Version 1.0 - Published**, and then click **Deploy**.</span></span>  

3. <span data-ttu-id="2524b-232">En el **iniciar** menú Abrir **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2524b-232">In the **Start** menu, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="2524b-233">Si la consola de administración de BizTalk Server ya está abierta, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="2524b-233">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  

4. <span data-ttu-id="2524b-234">Expanda **raíz de consola**, expanda [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expanda **grupo de BizTalk**y, a continuación, expanda **aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="2524b-234">Expand **Console Root**, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and then expand **Applications**.</span></span>  

5. <span data-ttu-id="2524b-235">Haga clic en **RuleTestApp**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-235">Right-click **RuleTestApp**, and then click **Configure**.</span></span>  

6. <span data-ttu-id="2524b-236">Haga clic en **Orchestration_1**y especifique **BizTalkServerApplication** como el host.</span><span class="sxs-lookup"><span data-stu-id="2524b-236">Click **Orchestration_1**, and specify **BizTalkServerApplication** as the host.</span></span>  

    <span data-ttu-id="2524b-237">![BRE&#45;tutorial&#45;AppHost](../core/media/ba348a98-661f-4e71-8b9b-b8c5fadf035a.gif "ba348a98-661f-4e71-8b9b-b8c5fadf035a")</span><span class="sxs-lookup"><span data-stu-id="2524b-237">![BRE&#45;Walkthrough&#45;AppHost](../core/media/ba348a98-661f-4e71-8b9b-b8c5fadf035a.gif "ba348a98-661f-4e71-8b9b-b8c5fadf035a")</span></span>  

7. <span data-ttu-id="2524b-238">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-238">Click **OK**.</span></span>  

8. <span data-ttu-id="2524b-239">Haga clic en **RuleTestApp**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="2524b-239">Right-click **RuleTestApp**, and then click **Start**.</span></span>  

9. <span data-ttu-id="2524b-240">En el **inicio de aplicación 'RuleTestApp'** cuadro de diálogo, haga clic en **iniciar**y, a continuación, espere hasta que la aplicación se ha iniciado correctamente.</span><span class="sxs-lookup"><span data-stu-id="2524b-240">In the **Start 'RuleTestApp' Application** dialog box, click **Start**, and then wait until the application is started successfully.</span></span>  

10. <span data-ttu-id="2524b-241">Abra **SamplePO.xml** y **SamplePO2.xml** en el Bloc de notas y cambie el valor de la **estado** campo **XYZ**.</span><span class="sxs-lookup"><span data-stu-id="2524b-241">Open **SamplePO.xml** and **SamplePO2.xml** in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  

11. <span data-ttu-id="2524b-242">Copia el **SamplePO.xml** archivo desde el directorio C:\BRE-Walkthroughs al directorio C:\BRE-Walkthroughs\RuleTestSol\Input para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2524b-242">Copy the **SamplePO.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  

12. <span data-ttu-id="2524b-243">Debería ver un archivo de salida en el directorio C:\BRE-Walkthroughs\RuleTestSol\Output para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2524b-243">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory for the orchestration.</span></span> <span data-ttu-id="2524b-244">Abra el archivo XML de salida y observe que el valor de la **estado** campo se establece en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="2524b-244">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  

13. <span data-ttu-id="2524b-245">Repita los pasos 11 y 12 con **SamplePO2.xml**y tenga en cuenta que el valor de la **estado** campo en el documento de salida es igual que en el documento de entrada (**xyz**).</span><span class="sxs-lookup"><span data-stu-id="2524b-245">Repeat steps 11 and 12 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**xyz**).</span></span>  

## <a name="comments"></a><span data-ttu-id="2524b-246">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2524b-246">Comments</span></span>  

-   <span data-ttu-id="2524b-247">En este tutorial no se han utilizado las formas del Cuadro de herramientas para agregarlas a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2524b-247">In this walkthrough, to add the shapes to the orchestration, you did not use the shapes from the Toolbox.</span></span> <span data-ttu-id="2524b-248">En lugar de ello, ha hecho clic con el botón secundario del mouse y ha seleccionado la forma que quería insertar.</span><span class="sxs-lookup"><span data-stu-id="2524b-248">Instead, you clicked the right mouse button and selected the shape that you wanted to insert.</span></span>  

-   <span data-ttu-id="2524b-249">La configuración de la **reglas de llamada** forma examina la última versión guardada al determinar los tipos utilizados.</span><span class="sxs-lookup"><span data-stu-id="2524b-249">The configuration for the **Call Rules** shape looks at the latest saved version when determining the types used.</span></span> <span data-ttu-id="2524b-250">En tiempo de ejecución, se utilizará la última versión implementada.</span><span class="sxs-lookup"><span data-stu-id="2524b-250">At run time, the latest deployed version will be used.</span></span>  

-   <span data-ttu-id="2524b-251">Si tiene previsto utilizar una versión de directiva que no sea la última versión implementada, debe usar un **expresión** forma e invocar el motor de reglas mediante programación para ejecutar la directiva de esa versión específica.</span><span class="sxs-lookup"><span data-stu-id="2524b-251">If you plan to use a policy version other than the latest deployed version, you should use an **Expression** shape, and invoke the rule engine programmatically to execute the policy of that specific version.</span></span> <span data-ttu-id="2524b-252">Para obtener más información, consulte [cómo ejecutar directivas](../core/how-to-execute-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2524b-252">For more information, see [How to Execute Policies](../core/how-to-execute-policies.md).</span></span>  

-   <span data-ttu-id="2524b-253">El **reglas de llamada** forma reconstruye el mensaje, como si utilizara un **construir mensaje** shape, que a su vez puede provocar que las propiedades de contexto del mensaje que se pierdan.</span><span class="sxs-lookup"><span data-stu-id="2524b-253">The **Call Rules** shape reconstructs the message, as if using a **Construct Message** shape, which in turn may cause context properties of the message to be lost.</span></span>  

-   <span data-ttu-id="2524b-254">Una directiva no se puede modificar tras su publicación.</span><span class="sxs-lookup"><span data-stu-id="2524b-254">A policy cannot be modified after it is published.</span></span>  

-   <span data-ttu-id="2524b-255">Las aplicaciones cliente pueden obtener acceso sólo a las directivas implementadas.</span><span class="sxs-lookup"><span data-stu-id="2524b-255">The client applications can access only the deployed policies.</span></span> <span data-ttu-id="2524b-256">Si una aplicación cliente invoca una directiva que no se ha implementado, el motor de reglas genera una **RuleEngineDeploymentNotDeployedException** excepción.</span><span class="sxs-lookup"><span data-stu-id="2524b-256">If a client application invokes a policy that is not deployed, the rule engine generates a **RuleEngineDeploymentNotDeployedException** exception.</span></span> <span data-ttu-id="2524b-257">Puede ver el mensaje de error detallado en el registro de eventos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2524b-257">You can see the detailed error message in the application event log.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="2524b-258">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2524b-258">Next Steps</span></span>  
 <span data-ttu-id="2524b-259">Ahora que ha realizado este tutorial, realice el [Tutorial: crear y usar un vocabulario en la directiva](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) tutorial, que encontrará instrucciones paso a paso para crear un vocabulario y usarlo en el **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="2524b-259">Now that you have completed this walkthrough, perform the [Walkthrough: Creating and Using a Vocabulary in the Policy](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) walkthrough, which gives you step-by-step instructions for creating a vocabulary and using the vocabulary in the **ProcessPurchaseOrder** policy.</span></span>  

## <a name="see-also"></a><span data-ttu-id="2524b-260">Vea también</span><span class="sxs-lookup"><span data-stu-id="2524b-260">See Also</span></span>  
 <span data-ttu-id="2524b-261">[Evaluación de condiciones y ejecución de acciones](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="2524b-261">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 <span data-ttu-id="2524b-262">[Agenda y prioridad](../core/agenda-and-priority.md) </span><span class="sxs-lookup"><span data-stu-id="2524b-262">[Agenda and Priority](../core/agenda-and-priority.md) </span></span>  
 [<span data-ttu-id="2524b-263">Invocación de reglas de negocio en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="2524b-263">Invoking Business Rules in Orchestrations</span></span>](../core/invoking-business-rules-in-orchestrations.md)