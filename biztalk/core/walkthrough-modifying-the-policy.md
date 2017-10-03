---
title: 'Tutorial: Modificar la directiva | Documentos de Microsoft'
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9dd74440-2a45-4a1a-8e36-98796e1e1392
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7292d541adaf0ae2242d1c504f1a845dde66f5dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-modifying-the-policy"></a><span data-ttu-id="f199b-102">Tutorial: Modificar la directiva</span><span class="sxs-lookup"><span data-stu-id="f199b-102">Walkthrough: Modifying the Policy</span></span>
<span data-ttu-id="f199b-103">Este tutorial proporciona instrucciones paso a paso para crear una nueva versión de la **POVocabulary**, crear una nueva versión de la **ProcessPurchaseOrder** directiva y utilizar la versión más reciente de la **POVocabulary** en la nueva versión de la **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="f199b-103">This walkthrough provides step-by-step instructions for creating a new version of the **POVocabulary**, creating a new version of the **ProcessPurchaseOrder** policy, and using the latest version of the **POVocabulary** in the new version of the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f199b-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="f199b-104">Prerequisites</span></span>  
 <span data-ttu-id="f199b-105">Debe completar la [Tutorial: agregar una regla a la directiva](../core/walkthrough-adding-a-rule-to-the-policy.md) tutorial antes de llevar a cabo este tutorial.</span><span class="sxs-lookup"><span data-stu-id="f199b-105">You must complete the [Walkthrough: Adding a Rule to the Policy](../core/walkthrough-adding-a-rule-to-the-policy.md) walkthrough before performing this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="f199b-106">Información general de este tutorial</span><span class="sxs-lookup"><span data-stu-id="f199b-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="f199b-107">Este tutorial contiene tres procedimientos, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="f199b-107">This walkthrough contains three procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="f199b-108">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="f199b-108">Procedure title</span></span>|<span data-ttu-id="f199b-109">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="f199b-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="f199b-110">Para modificar el vocabulario POVocabulary</span><span class="sxs-lookup"><span data-stu-id="f199b-110">To modify the POVocabulary vocabulary</span></span>|<span data-ttu-id="f199b-111">Proporciona instrucciones paso a paso para crear una nueva versión de vocabulario para modificar el valor de **número máximo de elementos permitidos** de **500** a **1000**.</span><span class="sxs-lookup"><span data-stu-id="f199b-111">Provides step-by-step instructions for creating a new vocabulary version to modify the value of **Maximum number of items allowed** from **500** to **1000**.</span></span>|  
|<span data-ttu-id="f199b-112">Para modificar la directiva ProcessPurchaseOrder con objeto de usar el vocabulario actualizado</span><span class="sxs-lookup"><span data-stu-id="f199b-112">To modify the ProcessPurchaseOrder policy to use the updated vocabulary</span></span>|<span data-ttu-id="f199b-113">Proporciona instrucciones paso a paso para crear una nueva versión de la **ProcessPurchaseOrder** directiva que se utilizará la nueva versión de **POVocabulary**.</span><span class="sxs-lookup"><span data-stu-id="f199b-113">Provides step-by-step instructions for creating a new version of the **ProcessPurchaseOrder** policy to use the new version of **POVocabulary**.</span></span>|  
|<span data-ttu-id="f199b-114">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="f199b-114">To test the solution</span></span>|<span data-ttu-id="f199b-115">Proporciona instrucciones detalladas para probar la solución y comprobar que la nueva directiva está activa.</span><span class="sxs-lookup"><span data-stu-id="f199b-115">Provides step-by-step instructions for testing the solution and verifying that the new policy is in effect.</span></span>|  
  
### <a name="to-modify-the-povocabulary-vocabulary"></a><span data-ttu-id="f199b-116">Para modificar el vocabulario POVocabulary</span><span class="sxs-lookup"><span data-stu-id="f199b-116">To modify the POVocabulary vocabulary</span></span>  
  
1.  <span data-ttu-id="f199b-117">En el **iniciar** menú Abrir **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="f199b-117">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="f199b-118">Si tiene el Compositor de reglas de negocio ya abrir, presione F5 o haga clic en **recarga** en el **archivo** menú para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="f199b-118">If you have Business Rule Composer already open, press F5 or click **Reload** on the **File** menu to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f199b-119">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="f199b-119">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="f199b-120">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="f199b-120">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="f199b-121">En la ventana Explorador de hechos, expanda **vocabularios**y, a continuación, expanda **POVocabulary**.</span><span class="sxs-lookup"><span data-stu-id="f199b-121">In the Facts Explorer window, expand **Vocabularies**, and then expand **POVocabulary**.</span></span>  
  
3.  <span data-ttu-id="f199b-122">Haga clic en **versión 1.0 - publicada**y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="f199b-122">Right-click **Version 1.0 - Published**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="f199b-123">Haga clic en **POVocabulary**y, a continuación, haga clic en **Pegar versión de vocabulario**.</span><span class="sxs-lookup"><span data-stu-id="f199b-123">Right-click **POVocabulary**, and then click **Paste Vocabulary Version**.</span></span>  
  
5.  <span data-ttu-id="f199b-124">Haga doble clic en **máximo número de elementos permitidos** en **versión 1.1 (sin guardar)** para iniciar el Asistente para definición de vocabulario.</span><span class="sxs-lookup"><span data-stu-id="f199b-124">Double-click **Maximum Number of Items Allowed** in **Version 1.1 (not saved)** to start the Vocabulary Definition Wizard.</span></span>  
  
6.  <span data-ttu-id="f199b-125">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f199b-125">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="f199b-126">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f199b-126">Click **Next**.</span></span>  
  
8.  <span data-ttu-id="f199b-127">Cambie el valor de **500** a **1000**.</span><span class="sxs-lookup"><span data-stu-id="f199b-127">Change the value from **500** to **1000**.</span></span>  
  
9. <span data-ttu-id="f199b-128">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="f199b-128">Click **Finish**.</span></span>  
  
10. <span data-ttu-id="f199b-129">Haga clic en **versión 1.1 (sin guardar)**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="f199b-129">Right-click **Version 1.1 (not saved)**, and then click **Save**.</span></span>  
  
11. <span data-ttu-id="f199b-130">Haga clic en **versión 1.1**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="f199b-130">Right-click **Version 1.1**, and then click **Publish**.</span></span>  
  
### <a name="to-modify-the-processpurchaseorder-policy-to-use-the-updated-vocabulary"></a><span data-ttu-id="f199b-131">Para modificar la directiva ProcessPurchaseOrder con objeto de usar el vocabulario actualizado</span><span class="sxs-lookup"><span data-stu-id="f199b-131">To modify the ProcessPurchaseOrder policy to use the updated vocabulary</span></span>  
  
1.  <span data-ttu-id="f199b-132">En el Explorador de directivas, expanda **directivas**y, a continuación, expanda **ProcessPurchaseOrder**.</span><span class="sxs-lookup"><span data-stu-id="f199b-132">In Policy Explorer, expand **Policies**, and then expand **ProcessPurchaseOrder**.</span></span>  
  
2.  <span data-ttu-id="f199b-133">Haga clic en **versión 1.2**y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="f199b-133">Right-click **Version 1.2**, and then click **Copy**.</span></span>  
  
3.  <span data-ttu-id="f199b-134">Haga clic en **ProcessPurchaseOrder**y, a continuación, haga clic en **PastePolicyVersion**.</span><span class="sxs-lookup"><span data-stu-id="f199b-134">Right-click **ProcessPurchaseOrder**, and then click **PastePolicyVersion**.</span></span>  
  
4.  <span data-ttu-id="f199b-135">Haga clic en **ApprovalRule** en **versión 1.3 (sin guardar)**.</span><span class="sxs-lookup"><span data-stu-id="f199b-135">Click **ApprovalRule** in **Version 1.3 (not saved)**.</span></span>  
  
5.  <span data-ttu-id="f199b-136">En el Explorador de hechos, expanda **vocabularios**, expanda **POVocabulary**y, a continuación, expanda **versión 1.1 - publicados**.</span><span class="sxs-lookup"><span data-stu-id="f199b-136">In Facts Explorer, expand **Vocabularies**, expand **POVocabulary**, and then expand **Version 1.1 - Published**.</span></span>  
  
6.  <span data-ttu-id="f199b-137">Arrastre **máximo número de elementos permitidos** en **versión 1.1 - publicados** para reemplazar **máximo número de elementos permitidos** de la versión 1.0 en el panel si.</span><span class="sxs-lookup"><span data-stu-id="f199b-137">Drag **Maximum Number of Items Allowed** in **Version 1.1 - Published** to replace **Maximum Number of Items Allowed** of version 1.0 in the IF pane.</span></span>  
  
7.  <span data-ttu-id="f199b-138">Repita los pasos del 4 al 6 con **DeniedRule**.</span><span class="sxs-lookup"><span data-stu-id="f199b-138">Repeat steps 4-6 with **DeniedRule**.</span></span>  
  
8.  <span data-ttu-id="f199b-139">Haga clic en **versión 1.3 (sin guardar)**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="f199b-139">Right-click **Version 1.3 (not saved)**, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="f199b-140">Haga clic en **versión 1.3**y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="f199b-140">Right-click **Version 1.3**, and then click **Publish**.</span></span>  
  
10. <span data-ttu-id="f199b-141">Haga clic en **versión 1.3**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="f199b-141">Right-click **Version 1.3**, and then click **Deploy**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="f199b-142">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="f199b-142">To test the solution</span></span>  
  
1.  <span data-ttu-id="f199b-143">Haga clic en **iniciar**, abra **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="f199b-143">Click **Start**, open **BizTalk Server Administration**.</span></span> <span data-ttu-id="f199b-144">Si la consola de administración de BizTalk Server ya está abierta, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="f199b-144">If you have the BizTalk Server Administration console already open, press F5 to refresh it.</span></span>  
  
2.  <span data-ttu-id="f199b-145">Haga clic en **RuleTestApp**y, a continuación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="f199b-145">Right-click **RuleTestApp**, and then click **Start**.</span></span> <span data-ttu-id="f199b-146">Si **iniciar** está deshabilitado, la aplicación ya se está ejecutando y puede omitir el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="f199b-146">If **Start** is disabled, the application is already running and you can ignore the next step.</span></span>  
  
3.  <span data-ttu-id="f199b-147">Haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="f199b-147">Click **Start**.</span></span>  
  
4.  <span data-ttu-id="f199b-148">Copia la **SamplePO2.xml** archivo desde el directorio C:\BRE-Walkthroughs al directorio C:\BRE-Walkthroughs\RuleTestSol\Input para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f199b-148">Copy the **SamplePO2.xml** file from the C:\BRE-Walkthroughs directory to the C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
5.  <span data-ttu-id="f199b-149">Debería ver un archivo de salida en el directorio C:\BRE-Walkthroughs\RuleTestSol\Output.</span><span class="sxs-lookup"><span data-stu-id="f199b-149">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory.</span></span> <span data-ttu-id="f199b-150">Abra el archivo XML de salida y observe que el valor de la **estado** campo está establecido en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="f199b-150">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f199b-151">El valor de la **cantidad** campo de SamplePO2.xml es 700.</span><span class="sxs-lookup"><span data-stu-id="f199b-151">The value of the **Quantity** field in SamplePO2.xml is 700.</span></span> <span data-ttu-id="f199b-152">La versión 1.3 de la **ProcessPurchaseOrder** directiva compara este valor con 1000 en vez de compararlo con 500, tal y como se hacía la versión 1.2.</span><span class="sxs-lookup"><span data-stu-id="f199b-152">Version 1.3 of the **ProcessPurchaseOrder** policy compares this value with 1000 instead of comparing it with 500 as version 1.2 did.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="f199b-153">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f199b-153">Comments</span></span>  
  
-   <span data-ttu-id="f199b-154">Una directiva publicada no se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="f199b-154">A published policy cannot be modified.</span></span> <span data-ttu-id="f199b-155">Para modificarla, hay que crear una nueva versión de la directiva.</span><span class="sxs-lookup"><span data-stu-id="f199b-155">You must create a new version of the policy to modify it.</span></span> <span data-ttu-id="f199b-156">Del mismo modo, un vocabulario publicado tampoco se puede modificar.</span><span class="sxs-lookup"><span data-stu-id="f199b-156">Similarly, a published vocabulary cannot be modified.</span></span> <span data-ttu-id="f199b-157">Para modificarlo, hay que crear una nueva versión del vocabulario.</span><span class="sxs-lookup"><span data-stu-id="f199b-157">You must create a new version of the vocabulary to modify it.</span></span>  
  
-   <span data-ttu-id="f199b-158">La orquestación que invoca una directiva mediante el uso de la **reglas de llamada** forma usa la última versión implementada de la directiva.</span><span class="sxs-lookup"><span data-stu-id="f199b-158">The orchestration invoking a policy by using the **Call Rules** shape uses the latest deployed version of the policy.</span></span> <span data-ttu-id="f199b-159">Por ejemplo, si tiene implementadas las versiones 1.0, 1.1, 1.2 y 1.3 de la directiva, la orquestación usa la versión 1.3.</span><span class="sxs-lookup"><span data-stu-id="f199b-159">For example, if you have versions 1.0, 1.1, 1.2, and 1.3 of the policy deployed, the orchestration uses version 1.3.</span></span> <span data-ttu-id="f199b-160">Si no está implementada la versión 1.3 y sí lo está la 1.2, la orquestación usará esta última.</span><span class="sxs-lookup"><span data-stu-id="f199b-160">If version 1.3 is not deployed and version 1.2 is deployed, the orchestration uses version 1.2.</span></span> <span data-ttu-id="f199b-161">Por lo tanto, si desea usar la versión 1.2, tan sólo necesita anular la implementación de la versión 1.3 y asegurarse de que la versión 1.2 está implementada.</span><span class="sxs-lookup"><span data-stu-id="f199b-161">Therefore if you want to switch back to using version 1.2, you just need to undeploy version 1.3, and make sure that version 1.2 is deployed.</span></span>  
  
-   <span data-ttu-id="f199b-162">Para utilizar una versión específica de una directiva desde una orquestación, debe usar un **expresión** forma e invocar el motor de reglas para ejecutar la directiva mediante programación utilizando la **Policy.Execute** método.</span><span class="sxs-lookup"><span data-stu-id="f199b-162">To use a specific version of a policy from an orchestration, you should use an **Expression** shape and invoke the rule engine to execute the policy programmatically by using the **Policy.Execute** method.</span></span>  
  
-   <span data-ttu-id="f199b-163">Observe que la versión 1.3 de la directiva usa las definiciones de vocabulario tanto de la versión 1.0 como de la versión 1.1 del vocabulario POVocabulary.</span><span class="sxs-lookup"><span data-stu-id="f199b-163">Note that version 1.3 of the policy uses the vocabulary definitions from both version 1.0 and version 1.1 of the POVocabulary vocabulary.</span></span> <span data-ttu-id="f199b-164">Si exporta la versión 1.3 de la directiva a un archivo XML y lo importa para crear la directiva en un equipo diferente, el proceso de importación busca ambas versiones del vocabulario.</span><span class="sxs-lookup"><span data-stu-id="f199b-164">If you export version 1.3 of the policy to an XML file, and import it to create the policy on a different computer, the import process looks for both versions of the vocabulary.</span></span> <span data-ttu-id="f199b-165">Por lo tanto, necesitará exportar tanto la versión 1.0 como la 1.1 del vocabulario e importarlas antes de importar la versión 1.3 de la directiva.</span><span class="sxs-lookup"><span data-stu-id="f199b-165">Therefore you need to export both version 1.0 and version 1.1 of the vocabulary and import them before importing version 1.3 of the policy.</span></span>  
  
-   <span data-ttu-id="f199b-166">Después de implementar una versión más actual de la directiva, debe esperar aproximadamente 60 segundos antes de probar la solución.</span><span class="sxs-lookup"><span data-stu-id="f199b-166">After you deploy a newer version of the policy, you should wait approximately 60 seconds before testing the solution.</span></span> <span data-ttu-id="f199b-167">El servicio de actualización del motor de reglas busca actualizaciones de directivas cada 60 segundos de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="f199b-167">The rule engine update service looks for any updates to a policy every 60 seconds (1 minute) by default.</span></span> <span data-ttu-id="f199b-168">Si existieran, actualiza la caché con la nueva información.</span><span class="sxs-lookup"><span data-stu-id="f199b-168">If there are updates, it refreshes the cache with the updated information.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="f199b-169">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="f199b-169">Next Steps</span></span>  
  
-   <span data-ttu-id="f199b-170">Ahora que ha completado este tutorial, realice la [Tutorial: ejecución de la directiva de seguimiento](../core/walkthrough-tracking-policy-execution.md) tutorial, que encontrará instrucciones paso a paso para realizar el seguimiento de los detalles de ejecución de directiva.</span><span class="sxs-lookup"><span data-stu-id="f199b-170">Now that you have completed this walkthrough, perform the [Walkthrough: Tracking Policy Execution](../core/walkthrough-tracking-policy-execution.md) walkthrough, which gives you step-by-step instructions for tracking policy execution details.</span></span>