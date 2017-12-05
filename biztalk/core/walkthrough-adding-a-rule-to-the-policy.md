---
title: 'Tutorial: Agregar una regla a la directiva | Documentos de Microsoft'
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b2a682c0-a5d7-4550-924d-be9fa29b84d2
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b08fc197c16f04f3eb738468421db340060b9613
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="walkthrough-adding-a-rule-to-the-policy"></a><span data-ttu-id="be0bb-102">Tutorial: Agregar una regla a la directiva</span><span class="sxs-lookup"><span data-stu-id="be0bb-102">Walkthrough: Adding a Rule to the Policy</span></span>
<span data-ttu-id="be0bb-103">Este tutorial proporciona procedimientos paso a paso para agregar una regla denominada **DeniedRule** a la **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="be0bb-103">This walkthrough provides step-by-step procedures for adding a rule named **DeniedRule** to the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="be0bb-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="be0bb-104">Prerequisites</span></span>  
 <span data-ttu-id="be0bb-105">Debe completar la [Tutorial: crear y usar un vocabulario en la directiva](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) tutorial antes de llevar a cabo este tutorial.</span><span class="sxs-lookup"><span data-stu-id="be0bb-105">You must complete the [Walkthrough: Creating and Using a Vocabulary in the Policy](../core/walkthrough-creating-and-using-a-vocabulary-in-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="be0bb-106">Información general de este tutorial</span><span class="sxs-lookup"><span data-stu-id="be0bb-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="be0bb-107">Este tutorial contiene tres procedimientos, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="be0bb-107">This walkthrough contains three procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="be0bb-108">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="be0bb-108">Procedure title</span></span>|<span data-ttu-id="be0bb-109">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="be0bb-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="be0bb-110">Para agregar DeniedRule a la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="be0bb-110">To add DeniedRule to the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="be0bb-111">Proporciona instrucciones paso a paso para agregar una regla nueva denominada **DeniedRule** a la **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="be0bb-111">Provides step-by-step instructions for adding a new rule named **DeniedRule** to the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="be0bb-112">El **DeniedRule** regla establece el valor de la **estado** campo **denegado** si el valor de la **cantidad** es mayor que 500.</span><span class="sxs-lookup"><span data-stu-id="be0bb-112">The **DeniedRule** rule sets the value of the **Status** field to **Denied** if the value of the **Quantity** is greater than 500.</span></span>|  
|<span data-ttu-id="be0bb-113">Para realizar pruebas con el Compositor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="be0bb-113">To test with Business Rule Composer</span></span>|<span data-ttu-id="be0bb-114">Proporciona instrucciones paso a paso para probar el **ProcessPurchaseOrder** directiva usando el Compositor de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="be0bb-114">Provides step-by-step instructions for testing the **ProcessPurchaseOrder** policy by using Business Rule Composer.</span></span>|  
|<span data-ttu-id="be0bb-115">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="be0bb-115">To test the solution</span></span>|<span data-ttu-id="be0bb-116">Proporciona instrucciones paso a paso para probar la solución.</span><span class="sxs-lookup"><span data-stu-id="be0bb-116">Provides step-by-step instructions for testing the solution.</span></span>|  
  
### <a name="to-add-deniedrule-to-the-processpurchaseorder-policy"></a><span data-ttu-id="be0bb-117">Para agregar DeniedRule a la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="be0bb-117">To add DeniedRule to the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="be0bb-118">En el **iniciar** menú Abrir **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-118">On the **Start** menu, open **Business Rule Composer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="be0bb-119">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="be0bb-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="be0bb-120">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-120">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="be0bb-121">En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.1**y, a continuación, haga clic en **copiar**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-121">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.1**, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="be0bb-122">Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **Pegar versión de directiva**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-122">Right-click **ProcessPurchaseOrder**, and then click **Paste Policy Version**.</span></span>  
  
4.  <span data-ttu-id="be0bb-123">Haga clic en **versión 1.2 (sin guardar)**, haga clic en **agregar nueva regla**y, a continuación, cambie el nombre de la regla a **DeniedRule**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-123">Right-click **Version 1.2(not saved)**, click **Add New Rule**, and then change the name of the rule to **DeniedRule**.</span></span>  
  
5.  <span data-ttu-id="be0bb-124">Si olvidó cambiar el nombre de la regla a **DeniedRule** en el paso 4, haga clic en **Rule1**y cambie el nombre a **DeniedRule** en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="be0bb-124">If you forgot to change the name of the rule to **DeniedRule** in step 4, click **Rule1**, and change the name to **DeniedRule** in the Properties window.</span></span>  
  
6.  <span data-ttu-id="be0bb-125">En el panel si, haga clic en **condiciones**, seleccione **predicados**y, a continuación, haga clic en **mayor que**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-125">In the IF pane, right-click **Conditions**, point to **Predicates**, and then click **Greater Than**.</span></span>  
  
7.  <span data-ttu-id="be0bb-126">En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha.</span><span class="sxs-lookup"><span data-stu-id="be0bb-126">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
8.  <span data-ttu-id="be0bb-127">Expanda **vocabularios**, expanda **POVocabulary**, expanda **versión 1.0 - publicada**y, a continuación, arrastre **cantidad de solicitud** para **argumento1** en el panel si.</span><span class="sxs-lookup"><span data-stu-id="be0bb-127">Expand **Vocabularies**, expand **POVocabulary**, expand **Version 1.0 - Published**, and then drag **Request Quantity** to **argument1** in the IF pane.</span></span>  
  
9. <span data-ttu-id="be0bb-128">Arrastre **número máximo de elementos permitidos** a **argumento2** en el panel si.</span><span class="sxs-lookup"><span data-stu-id="be0bb-128">Drag **Maximum number of items allowed** to **argument2** in the IF pane.</span></span>  
  
10. <span data-ttu-id="be0bb-129">Arrastre **estado de la solicitud** al panel entonces.</span><span class="sxs-lookup"><span data-stu-id="be0bb-129">Drag **Request Status** to the THEN pane.</span></span>  
  
11. <span data-ttu-id="be0bb-130">Haga clic en  **\<una cadena vacía\>**  y, a continuación, escriba **denegado**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-130">Click **\<empty string\>** and then type **Denied**.</span></span>  
  
12. <span data-ttu-id="be0bb-131">Haga clic en **versión 1.2 (sin guardar)**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-131">Right-click **Version 1.2 (not saved)**, and then click **Save**.</span></span>  
  
13. <span data-ttu-id="be0bb-132">Haga clic en **versión 1.2**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-132">Right-click **Version 1.2**, and then click **Publish**.</span></span>  
  
14. <span data-ttu-id="be0bb-133">Haga clic en **versión 1.2**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-133">Right-click **Version 1.2**, and then click **Deploy**.</span></span>  
  
### <a name="to-test-with-business-rule-composer"></a><span data-ttu-id="be0bb-134">Para realizar pruebas con el Compositor de reglas de negocios</span><span class="sxs-lookup"><span data-stu-id="be0bb-134">To test with Business Rule Composer</span></span>  
  
1.  <span data-ttu-id="be0bb-135">Abra los archivos SamplePO.xml y SamplePO2.xml en el Bloc de notas y cambie el valor de la **estado** campo **XYZ**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-135">Open the SamplePO.xml and SamplePO2.xml files in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="be0bb-136">En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.2**y, a continuación, haga clic en **probar directiva**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-136">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.2**, and then click **Test Policy**.</span></span>  
  
3.  <span data-ttu-id="be0bb-137">En el **XMLDocuments** nodo, seleccione **RuleTest.PO**y, a continuación, haga clic en **Agregar instancia**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-137">Under the **XMLDocuments** node, select **RuleTest.PO**, and then click **Add Instance**.</span></span>  
  
4.  <span data-ttu-id="be0bb-138">Seleccione **SamplePO.xml**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-138">Select **SamplePO.xml**, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="be0bb-139">Haga clic en **prueba**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-139">Click **Test**.</span></span>  
  
6.  <span data-ttu-id="be0bb-140">Mire el **actualización de Agenda** sección en la salida y observe que sólo **ApprovalRule** se agrega a la agenda.</span><span class="sxs-lookup"><span data-stu-id="be0bb-140">Look at the **Agenda Update** section in the output, and notice that only **ApprovalRule** is added to the agenda.</span></span> <span data-ttu-id="be0bb-141">Por tanto, es la única regla que se activa (se ejecutan las acciones asociadas a la regla).</span><span class="sxs-lookup"><span data-stu-id="be0bb-141">Therefore it is the only rule that fires (actions associated with the rule are executed).</span></span>  
  
7.  <span data-ttu-id="be0bb-142">Abra **SamplePO.xml** en el Bloc de notas y observe que el valor de la **estado** campo está establecido en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-142">Open **SamplePO.xml** in Notepad and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
8.  <span data-ttu-id="be0bb-143">En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.2**y, a continuación, haga clic en **probar directiva.**</span><span class="sxs-lookup"><span data-stu-id="be0bb-143">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.2**, and then click **Test Policy.**</span></span>  
  
9. <span data-ttu-id="be0bb-144">Seleccione **SamplePO.xml**, haga clic en **quitar instancia**y, a continuación, haga clic en **Agregar instancia**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-144">Select **SamplePO.xml**, click **Remove instance**, and then click **Add Instance**.</span></span>  
  
10. <span data-ttu-id="be0bb-145">Seleccione **SamplePO2.xml**y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-145">Select **SamplePO2.xml**, and then click **Open**.</span></span>  
  
11. <span data-ttu-id="be0bb-146">Haga clic en **prueba**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-146">Click **Test**.</span></span>  
  
12. <span data-ttu-id="be0bb-147">Mire el **actualización de Agenda** sección en la salida y observe que sólo **DeniedRule** se agrega a la agenda.</span><span class="sxs-lookup"><span data-stu-id="be0bb-147">Look at the **Agenda Update** section in the output, and notice that only **DeniedRule** is added to the agenda.</span></span> <span data-ttu-id="be0bb-148">Por tanto, es la única regla que se activa.</span><span class="sxs-lookup"><span data-stu-id="be0bb-148">Therefore it is the only rule that fires.</span></span>  
  
13. <span data-ttu-id="be0bb-149">Abra **SamplePO2.xml** en el Bloc de notas y observe que el valor de la **estado** campo es **denegado**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-149">Open **SamplePO2.xml** in Notepad and notice that the value of the **Status** field is **Denied**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="be0bb-150">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="be0bb-150">To test the solution</span></span>  
  
1.  <span data-ttu-id="be0bb-151">Abra **SamplePO.xml** y **SamplePO2.xml** en el Bloc de notas y cambie el valor de la **estado** campo **XYZ**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-151">Open **SamplePO.xml** and **SamplePO2.xml** in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="be0bb-152">Copia la **SamplePO.xml** archivo desde el directorio C:\BRE-Walkthroughs al directorio C:\BRE-Walkthroughs\RuleTestSol\Input para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="be0bb-152">Copy the **SamplePO.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
3.  <span data-ttu-id="be0bb-153">Debería ver un archivo de salida en el directorio C:\BRE-Walkthroughs\RuleTestSol\Output para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="be0bb-153">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory for the orchestration.</span></span> <span data-ttu-id="be0bb-154">Abra el archivo XML de salida y observe que el valor de la **estado** campo está establecido en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-154">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
4.  <span data-ttu-id="be0bb-155">Repita los pasos 2 y 3 con **SamplePO2.xml**y observe que el valor de la **estado** campo está establecido en **denegado** en el documento de salida.</span><span class="sxs-lookup"><span data-stu-id="be0bb-155">Repeat steps 2 and 3 with **SamplePO2.xml**, and notice that the value of the **Status** field is set to **Denied** in the output document.</span></span> <span data-ttu-id="be0bb-156">Esto demuestra que la orquestación está usando la versión 1.2 de la **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="be0bb-156">This proves that the orchestration is using version 1.2 of the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="be0bb-157">La orquestación utiliza la última versión implementada de la **ProcessPurchaseOrder** directiva, que es **1.2**.</span><span class="sxs-lookup"><span data-stu-id="be0bb-157">The orchestration uses the latest deployed version of the **ProcessPurchaseOrder** policy, which is **1.2**.</span></span> <span data-ttu-id="be0bb-158">No es necesario anular la implementación de la versión 1.1 de la directiva para usar la versión 1.2 de la directiva.</span><span class="sxs-lookup"><span data-stu-id="be0bb-158">You do not need to undeploy version 1.1 of the policy to use version 1.2 of the policy.</span></span> <span data-ttu-id="be0bb-159">Sin embargo, es necesario esperar aproximadamente 60 segundos antes de probar la solución.</span><span class="sxs-lookup"><span data-stu-id="be0bb-159">However, you need to wait for approximately 60 seconds before testing the solution.</span></span> <span data-ttu-id="be0bb-160">Para obtener más información, vea la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="be0bb-160">For more information, see the Comments section.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="be0bb-161">Comentarios</span><span class="sxs-lookup"><span data-stu-id="be0bb-161">Comments</span></span>  
  
-   <span data-ttu-id="be0bb-162">Una directiva puede tener una o varias reglas.</span><span class="sxs-lookup"><span data-stu-id="be0bb-162">A policy can have one or more rules.</span></span> <span data-ttu-id="be0bb-163">No hay un límite lógico en el número de reglas de una directiva.</span><span class="sxs-lookup"><span data-stu-id="be0bb-163">There is no logical limit on the number of rules in a policy.</span></span>  
  
-   <span data-ttu-id="be0bb-164">El motor de reglas usa un algoritmo de Evaluación de condición – Resolución de conflictos – Ejecución de acciones.</span><span class="sxs-lookup"><span data-stu-id="be0bb-164">The rule engine uses a Condition Evaluation - Conflict Resolution - Action Execution algorithm.</span></span> <span data-ttu-id="be0bb-165">En el **evaluación de condición** fase, el motor de reglas evalúa condiciones en todas las reglas.</span><span class="sxs-lookup"><span data-stu-id="be0bb-165">In the **Condition Evaluation** stage, the rule engine evaluates conditions in all the rules.</span></span> <span data-ttu-id="be0bb-166">Las reglas cuyas condiciones se evalúen como true, se convierten en reglas candidatas para la ejecución.</span><span class="sxs-lookup"><span data-stu-id="be0bb-166">The rules whose conditions evaluate to true become candidate rules for execution.</span></span> <span data-ttu-id="be0bb-167">En el **la resolución de conflictos** fase, las reglas candidatas se agregan a la agenda en el orden de prioridad de la regla.</span><span class="sxs-lookup"><span data-stu-id="be0bb-167">In the **Conflict Resolution** stage, the candidate rules are added to the agenda in the order of the priority of the rule.</span></span> <span data-ttu-id="be0bb-168">En el **ejecución de acciones** fase, las acciones en el candidato que se ejecutan las reglas.</span><span class="sxs-lookup"><span data-stu-id="be0bb-168">In the **Action Execution** stage, the actions in the candidate rules are executed.</span></span> <span data-ttu-id="be0bb-169">Si las reglas candidatas tienen la misma prioridad, no hay un orden determinista en el que ejecutar las acciones para dichas reglas.</span><span class="sxs-lookup"><span data-stu-id="be0bb-169">If candidate rules have the same priority, there is no deterministic order in which the actions for those rules are executed.</span></span> <span data-ttu-id="be0bb-170">Debe asumir que se ejecutan en paralelo.</span><span class="sxs-lookup"><span data-stu-id="be0bb-170">You should assume that they are executed in parallel.</span></span>  
  
-   <span data-ttu-id="be0bb-171">En este escenario, sólo se activa una de las reglas para cualquier archivo de ejemplo dado.</span><span class="sxs-lookup"><span data-stu-id="be0bb-171">In this scenario, for any given sample file, only one of the rules is fired.</span></span> <span data-ttu-id="be0bb-172">Asegúrese de que cambia el valor de la **estado** campo antes de ejecutar una prueba.</span><span class="sxs-lookup"><span data-stu-id="be0bb-172">Make sure that you change the value of the **Status** field before running a test.</span></span>  
  
-   <span data-ttu-id="be0bb-173">Cuando se implementa una nueva versión de la directiva, debe esperar aproximadamente 60 segundos antes de realizar la prueba.</span><span class="sxs-lookup"><span data-stu-id="be0bb-173">When a new version of the policy is deployed, you should wait approximately 60 seconds before testing.</span></span> <span data-ttu-id="be0bb-174">El servicio de actualización del motor de reglas efectúa un sondeo en la base de datos del motor de reglas de forma periódica (cada 60 segundos de forma predeterminada) para buscar las directivas implementadas recientemente.</span><span class="sxs-lookup"><span data-stu-id="be0bb-174">The rule engine update service polls the rule engine database on a periodic basis (every 60 seconds by default) to look for newly deployed policies.</span></span> <span data-ttu-id="be0bb-175">El servicio de actualización del motor de reglas actualiza el objeto de directiva en la memoria con la información acerca de la versión de la última directiva implementada en la base de datos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="be0bb-175">The rule engine update service updates the policy object in memory with the information about the latest deployed version of the policy from the rule engine database.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="be0bb-176">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="be0bb-176">Next Steps</span></span>  
 <span data-ttu-id="be0bb-177">Ahora que ha completado este tutorial, realice la [Tutorial: modificar la directiva](../core/walkthrough-modifying-the-policy.md) tutorial, que encontrará instrucciones paso a paso para modificar la directiva para aprobar los pedidos de compra con el valor de **cantidad** menor o igual que 1000 (en lugar de 500).</span><span class="sxs-lookup"><span data-stu-id="be0bb-177">Now that you have completed this walkthrough, perform the [Walkthrough: Modifying the Policy](../core/walkthrough-modifying-the-policy.md) walkthrough, which gives you step-by-step instructions for modifying the policy to approve purchase orders with the value of **quantity** less than or equal to 1000 (instead of 500).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be0bb-178">Vea también</span><span class="sxs-lookup"><span data-stu-id="be0bb-178">See Also</span></span>  
 <span data-ttu-id="be0bb-179">[Evaluación de condiciones y ejecución de acciones](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="be0bb-179">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 [<span data-ttu-id="be0bb-180">Agenda y prioridad</span><span class="sxs-lookup"><span data-stu-id="be0bb-180">Agenda and Priority</span></span>](../core/agenda-and-priority.md)