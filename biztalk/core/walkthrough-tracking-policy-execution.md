---
title: "Tutorial: Seguimiento de ejecución de la directiva en BizTalk Server | Documentos de Microsoft"
description: Tutorial para habilitar el seguimiento y ver los detalles de seguimiento de la directiva en el servidor BizTalk Server
ms.custom: 
ms.date: 04/05/2016
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef88eae7-f0f8-4f3f-85d0-3961a47395b6
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f20b35aca2c4fb35419153ccfb149aa34501b21a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="walkthrough-tracking-policy-execution"></a><span data-ttu-id="2d64e-103">Tutorial: Ejecución de la directiva de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2d64e-103">Walkthrough: Tracking Policy Execution</span></span>
<span data-ttu-id="2d64e-104">Procedimientos paso a paso para habilitar el seguimiento de la **ProcessPurchaseOrder** Directiva así como para ver la información de seguimiento después de ejecutar la directiva.</span><span class="sxs-lookup"><span data-stu-id="2d64e-104">Step-by-step procedures for enabling tracking for the **ProcessPurchaseOrder** policy, and for viewing the tracking information after the policy is executed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2d64e-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="2d64e-105">Prerequisites</span></span>  
<span data-ttu-id="2d64e-106">Completar la [Tutorial: modificar la directiva](../core/walkthrough-modifying-the-policy.md) tutorial antes de llevar a cabo este tutorial.</span><span class="sxs-lookup"><span data-stu-id="2d64e-106">Complete the [Walkthrough: Modifying the Policy](../core/walkthrough-modifying-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="enable-tracking-for-the-processpurchaseorder-policy"></a><span data-ttu-id="2d64e-107">Habilitar el seguimiento de la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="2d64e-107">Enable tracking for the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="2d64e-108">Abra **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-108">Open **BizTalk Server Administration**.</span></span> <span data-ttu-id="2d64e-109">Si ya está abierto, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="2d64e-109">If it's already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="2d64e-110">Expanda **raíz de consola**, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **RuleTestApp**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-110">Expand **Console Root**, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **RuleTestApp**.</span></span>  
  
3.  <span data-ttu-id="2d64e-111">Haga clic en **directivas**, seleccione **agregar**y, a continuación, seleccione **directiva**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-111">Right-click **Policies**, select **Add**, and then select **Policy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2d64e-112">Para habilitar el seguimiento de una directiva, debe agregarla a una aplicación de BizTalk mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="2d64e-112">To enable tracking for a policy, you must add the policy to a BizTalk application by using the BizTalk Server Administration console.</span></span>  
  
4.  <span data-ttu-id="2d64e-113">En el **agregar directivas** cuadro de diálogo, expanda **ProcessPurchaseOrder**y seleccione versión **1.3**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-113">In the **Add Policies** dialog box, expand **ProcessPurchaseOrder**, and select Version **1.3**.</span></span>  
  
5.  <span data-ttu-id="2d64e-114">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-114">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="2d64e-115">Si no ve **ProcessPurchaseOrder** en la lista, seleccione F5 para actualizar la vista.</span><span class="sxs-lookup"><span data-stu-id="2d64e-115">If you don't see **ProcessPurchaseOrder** in the list, select F5 to refresh the view.</span></span>
  
7.  <span data-ttu-id="2d64e-116">Haga clic en **ProcessPurchaseOrder**y, a continuación, seleccione **de seguimiento.**</span><span class="sxs-lookup"><span data-stu-id="2d64e-116">Right-click **ProcessPurchaseOrder**, and then select **Tracking.**</span></span>  
  
8.  <span data-ttu-id="2d64e-117">En el **opciones de seguimiento de la directiva** cuadro de diálogo, seleccione todas las casillas de verificación para **actividad de hechos**, **evaluación de condición**, **regla activaciones**, y **actualizaciones de Agenda**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-117">In the **Policy Tracking Options** dialog box, select all the check boxes for **Fact activity**, **Condition evaluation**, **Rule firings**, and **Agenda updates**.</span></span>  
  
9. <span data-ttu-id="2d64e-118">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-118">Click **OK**.</span></span>  
  
## <a name="test-the-solution-and-view-the-tracking-information"></a><span data-ttu-id="2d64e-119">Probar la solución y ver la información de seguimiento</span><span class="sxs-lookup"><span data-stu-id="2d64e-119">Test the solution and view the tracking information</span></span>  
  
1.  <span data-ttu-id="2d64e-120">Abra **SamplePO.xml** y **SamplePO2.xml** en el Bloc de notas y cambie el valor de la **estado** campo **XYZ**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-120">Open **SamplePO.xml** and **SamplePO2.xml** in notepad, and change the value of the **Status** field to **XYZ**.</span></span>  
  
2.  <span data-ttu-id="2d64e-121">Copia **SamplePO.xml** que creó en [Tutorial: probar la directiva](../core/walkthrough-testing-the-policy.md) al directorio de entrada para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2d64e-121">Copy **SamplePO.xml** that you created in [Walkthrough: Testing the Policy](../core/walkthrough-testing-the-policy.md) to the input directory for the orchestration.</span></span>  
  
3.  <span data-ttu-id="2d64e-122">Debería ver un archivo de salida en el directorio de salida de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="2d64e-122">You should see an output file in the output directory for the orchestration.</span></span> <span data-ttu-id="2d64e-123">Abra el archivo XML de salida y observe que el valor de la **estado** campo está establecido en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-123">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
4.  <span data-ttu-id="2d64e-124">En **administración de BizTalk Server**, vaya a la **información general del grupo** página, haga clic en el **concentrador de grupo** ficha y, a continuación, haga clic en **instancias de servicio controladas**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-124">In **BizTalk Server Administration**, go to the **Group Overview** page, click on the **Group Hub** tab, and then click on **Tracked Service Instances**.</span></span>  
  
5.  <span data-ttu-id="2d64e-125">Haga clic en el nombre de la orquestación (RuleTest.Orchestration_1) y, a continuación, haga clic en **flujo de mensajes**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-125">Right-click the name of the Orchestration (RuleTest.Orchestration_1), and then click **Message Flow**.</span></span>  
  
6.  <span data-ttu-id="2d64e-126">Haga clic en **siga este vínculo para ver los detalles de ejecución de directiva para esta instancia de orquestación**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-126">Click **Follow this link to view the Policy execution details for this orchestration instance**.</span></span> <span data-ttu-id="2d64e-127">Asegúrese de que ve una ventana similar a la siguiente ilustración:</span><span class="sxs-lookup"><span data-stu-id="2d64e-127">Make sure you see the window that looks like the following figure:</span></span>  
  
     <span data-ttu-id="2d64e-128">![BRE &#45; Tutorial &#45; FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")</span><span class="sxs-lookup"><span data-stu-id="2d64e-128">![BRE&#45;Walkthrough&#45;FirstScreen](../core/media/1e59fe9e-cf2d-407a-81cd-102b57a515d2.gif "1e59fe9e-cf2d-407a-81cd-102b57a515d2")</span></span>  
  
7. <span data-ttu-id="2d64e-129">Haga clic en el tiempo o **ProcessPurchaseOrder1.3** para ver la siguiente pantalla.</span><span class="sxs-lookup"><span data-stu-id="2d64e-129">Click the time or **ProcessPurchaseOrder1.3** to see the following screen.</span></span> <span data-ttu-id="2d64e-130">En esta pantalla, puede ver el servicio (orquestación) que solicitó la ejecución de la directiva, el Id. de la orquestación, la fecha y hora de ejecución de la directiva y el Id. de la directiva.</span><span class="sxs-lookup"><span data-stu-id="2d64e-130">In this screen, you can see the service (orchestration) that requested the policy execution, the ID of the orchestration, the time at which the policy was executed, and the ID of the policy.</span></span>  
  
     <span data-ttu-id="2d64e-131">![BRE &#45; Tutorial &#45; PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")</span><span class="sxs-lookup"><span data-stu-id="2d64e-131">![BRE&#45;Walkthrough&#45;PolicyExecDetails](../core/media/a65fd48f-2a54-4cc5-9b45-4cd3c211da33.gif "a65fd48f-2a54-4cc5-9b45-4cd3c211da33")</span></span>  
  
8. <span data-ttu-id="2d64e-132">Haga clic en **actividad de hechos** para ver los hechos (datos) que se impusieron en la regla de trabajo del motor de memoria así como los hechos que se retiraron de memoria de trabajo del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="2d64e-132">Click **Fact Activity** to see the facts (data) that were asserted into the rule engine's working memory and the facts that were retracted from the rule engine's working memory.</span></span>  
  
     <span data-ttu-id="2d64e-133">![BRE &#45; Tutorial &#45; FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")</span><span class="sxs-lookup"><span data-stu-id="2d64e-133">![BRE&#45;Walkthrough&#45;FactActivity](../core/media/27bc0d84-f202-4f5a-87a1-8b53006b3cee.gif "27bc0d84-f202-4f5a-87a1-8b53006b3cee")</span></span>  
  
9. <span data-ttu-id="2d64e-134">En el **archivo** menú, haga clic en **Navigate back**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-134">On the **File** menu, click **Navigate back**.</span></span>  
  
10. <span data-ttu-id="2d64e-135">Haga clic en **condiciones que evalúan**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-135">Click **Conditions that Evaluated**.</span></span> <span data-ttu-id="2d64e-136">Consulte los detalles acerca de las condiciones que se han evaluado.</span><span class="sxs-lookup"><span data-stu-id="2d64e-136">You see the details about the conditions that were evaluated.</span></span> <span data-ttu-id="2d64e-137">En este caso, hay dos reglas en la directiva, y cada directiva tiene una condición.</span><span class="sxs-lookup"><span data-stu-id="2d64e-137">In this case, there are two rules in the policy, and each policy has a condition.</span></span> <span data-ttu-id="2d64e-138">Puede ver que se han evaluado dos condiciones; como `true`, y el otro se evalúa a `false`.</span><span class="sxs-lookup"><span data-stu-id="2d64e-138">You can see that two conditions were evaluated; one evaluated to `true`, and the other one evaluated to `false`.</span></span>  
  
     <span data-ttu-id="2d64e-139">![BRE &#45; Tutorial &#45; ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")</span><span class="sxs-lookup"><span data-stu-id="2d64e-139">![BRE&#45;Walkthrough&#45;ConditionEvaluation](../core/media/ac772d01-919f-4b22-995b-409501a96848.gif "ac772d01-919f-4b22-995b-409501a96848")</span></span>  
  
11. <span data-ttu-id="2d64e-140">En el **archivo** menú, haga clic en **Navigate back**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-140">On the **File** menu, click **Navigate back**.</span></span>  
  
12. <span data-ttu-id="2d64e-141">Haga clic en **actualizaciones de Agenda**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-141">Click **Agenda Updates**.</span></span> <span data-ttu-id="2d64e-142">Como puede ver, sólo ApprovalRule se agrega a la agenda.</span><span class="sxs-lookup"><span data-stu-id="2d64e-142">You can see that only the ApprovalRule is added to the agenda.</span></span> <span data-ttu-id="2d64e-143">DeniedRule no se agrega a la agenda porque su condición se evalúa como `false`.</span><span class="sxs-lookup"><span data-stu-id="2d64e-143">The DeniedRule is not added to the agenda because its condition evaluates to `false`.</span></span>  
  
     <span data-ttu-id="2d64e-144">![BRE &#45; Tutorial &#45; Agenda](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")</span><span class="sxs-lookup"><span data-stu-id="2d64e-144">![BRE&#45;Walkthrough&#45;Agenda](../core/media/bc85d9ea-fc76-44de-aa75-134f47a5ec20.gif "bc85d9ea-fc76-44de-aa75-134f47a5ec20")</span></span>  
  
13. <span data-ttu-id="2d64e-145">Haga clic en **ApprovalRule** para ver la definición correspondiente.</span><span class="sxs-lookup"><span data-stu-id="2d64e-145">Click **ApprovalRule** to see the definition of the ApprovalRule.</span></span>  
  
14. <span data-ttu-id="2d64e-146">En el **archivo** menú, haga clic en **Navigate back**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-146">On the **File** menu, click **Navigate back**.</span></span>  
  
15. <span data-ttu-id="2d64e-147">En **archivo** menú, haga clic en **Navigate back** nuevo.</span><span class="sxs-lookup"><span data-stu-id="2d64e-147">On **File** menu, click **Navigate back** again.</span></span>  
  
16. <span data-ttu-id="2d64e-148">Haga clic en **reglas que ha activado**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-148">Click **Rules that fired**.</span></span> <span data-ttu-id="2d64e-149">Puede ver que sólo ApprovalRule se activó (se ejecutaron acciones para ApprovalRule).</span><span class="sxs-lookup"><span data-stu-id="2d64e-149">You can see that only ApprovalRule was fired (actions for the ApprovalRule were executed).</span></span>  
  
17. <span data-ttu-id="2d64e-150">En el **archivo** menú, haga clic en **Navigate back**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-150">On the **File** menu, click **Navigate back**.</span></span>  
  
18. <span data-ttu-id="2d64e-151">Haga clic en **reglas que no se han activado**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-151">Click **Rules that did not fire**.</span></span> <span data-ttu-id="2d64e-152">Puede ver que DeniedRule no se activó porque no estaba en la agenda.</span><span class="sxs-lookup"><span data-stu-id="2d64e-152">You can see that DeniedRule was not fired because it was not in the agenda.</span></span>  
  
19. <span data-ttu-id="2d64e-153">Repita los pasos 1-18 con **SamplePO2.xml**.</span><span class="sxs-lookup"><span data-stu-id="2d64e-153">Repeat steps 1-18 with **SamplePO2.xml**.</span></span>  
  
## <a name="key-details"></a><span data-ttu-id="2d64e-154">Detalles de la clave</span><span class="sxs-lookup"><span data-stu-id="2d64e-154">Key details</span></span>  
  
-   <span data-ttu-id="2d64e-155">La información de seguimiento de directiva es muy similar a la información de seguimiento que se ve en el Compositor de reglas de negocio cuando se prueba una directiva.</span><span class="sxs-lookup"><span data-stu-id="2d64e-155">The policy tracking information is very similar to the tracking information you see in Business Rule Composer when you test a policy.</span></span>  
  
-   <span data-ttu-id="2d64e-156">Aunque el nombre de la orquestación es RuleTest.odx, el nombre que se ve es Orchestration_1, porque Nombre de tipo está establecido como Orchestration_1 para la orquestación a pesar de que se cambie su nombre.</span><span class="sxs-lookup"><span data-stu-id="2d64e-156">Although the orchestration name is RuleTest.odx, you see the name of the orchestration as Orchestration_1, because the Type Name for the orchestration is set to Orchestration_1 even though the Name is changed.</span></span> <span data-ttu-id="2d64e-157">Seguimiento muestra el nombre de la orquestación con el formato \<Namespace\>.\< Escriba el nombre\>.</span><span class="sxs-lookup"><span data-stu-id="2d64e-157">Tracking is showing you the orchestration name in the format \<Namespace\>.\<Type Name\>.</span></span>  
  
-   <span data-ttu-id="2d64e-158">Al eliminar una directiva de una aplicación de BizTalk con la consola de administración de BizTalk Server, ésta se elimina tanto de la aplicación como de la base de datos del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="2d64e-158">If you delete a policy from a BizTalk application by using the BizTalk Server Administration console, the tool deletes the policy not only from the application, but also from the rule engine database.</span></span> <span data-ttu-id="2d64e-159">La directiva ya no aparecerá en el Compositor de reglas de negocio (presione F5 para actualizar la vista).</span><span class="sxs-lookup"><span data-stu-id="2d64e-159">You will no longer see the policy in Business Rule Composer (press F5 to refresh).</span></span> <span data-ttu-id="2d64e-160">Por tanto, se debe tener cuidado al eliminar una directiva de una aplicación.</span><span class="sxs-lookup"><span data-stu-id="2d64e-160">Therefore, you should be careful when deleting a policy from an application.</span></span>  
  
-   <span data-ttu-id="2d64e-161">Cuando se detiene RuleTestApp y se selecciona el **detención completa** opción, la directiva ProcessPurchaseOrder (versión 1.3) se anula automáticamente la implementación.</span><span class="sxs-lookup"><span data-stu-id="2d64e-161">When you stop the RuleTestApp and select the **Full Stop** option, the ProcessPurchaseOrder policy (version 1.3) is automatically undeployed.</span></span>  
  
-   <span data-ttu-id="2d64e-162">Si varias aplicaciones usan una directiva, cree una aplicación diferente para la directiva y, a continuación, establezca referencias a ella desde las aplicaciones cliente.</span><span class="sxs-lookup"><span data-stu-id="2d64e-162">If a policy is used by multiple applications, create a separate application for the policy and then create references to it from the client applications.</span></span> <span data-ttu-id="2d64e-163">Si agrega la directiva a todas las aplicaciones cliente, cuando detenga una de ellas, la implementación de la directiva se anulará y las demás aplicaciones clientes no podrán usar la directiva.</span><span class="sxs-lookup"><span data-stu-id="2d64e-163">If you add the policy to all the client applications, when you stop one of the client applications, the policy is undeployed, and the other client applications can no longer use the policy.</span></span> <span data-ttu-id="2d64e-164">Por lo tanto, se recomienda crear una aplicación diferente para las directivas que se compartan entre dos o más aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2d64e-164">Therefore it is a good practice to create a separate application for a policy that is shared across two or more applications.</span></span>  
  
-   <span data-ttu-id="2d64e-165">Al iniciar RuleTestApp, se implementa automáticamente la directiva ProcessPurchaseOrder (versión 1.3).</span><span class="sxs-lookup"><span data-stu-id="2d64e-165">When you start the RuleTestApp, the ProcessPurchaseOrder policy (version 1.3) is automatically deployed.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2d64e-166">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2d64e-166">Next Steps</span></span>  
 <span data-ttu-id="2d64e-167">Ahora que ha completado este tutorial, vaya a la [Tutorial: implementar la directiva](../core/walkthrough-deploying-the-policy.md) tutorial, que encontrará instrucciones paso a paso para implementar las directivas.</span><span class="sxs-lookup"><span data-stu-id="2d64e-167">Now that you have completed this walkthrough, go to the [Walkthrough: Deploying the Policy](../core/walkthrough-deploying-the-policy.md) walkthrough, which gives you step-by-step instructions for deploying policies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d64e-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d64e-168">See Also</span></span>  
 <span data-ttu-id="2d64e-169">[Cómo configurar el seguimiento de una directiva](../core/how-to-configure-tracking-for-a-policy.md) </span><span class="sxs-lookup"><span data-stu-id="2d64e-169">[How to Configure Tracking for a Policy](../core/how-to-configure-tracking-for-a-policy.md) </span></span>  
 [<span data-ttu-id="2d64e-170">Administración de directivas</span><span class="sxs-lookup"><span data-stu-id="2d64e-170">Managing Policies</span></span>](../core/managing-policies.md)