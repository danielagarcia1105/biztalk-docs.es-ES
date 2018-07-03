---
title: 'Tutorial: Crear y usar un vocabulario en la directiva | Microsoft Docs'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2c306a6e-3384-4f43-9c75-c5407cd9aed2
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92a2f458d3ae4aa43befff248d564c92d78ef132
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974773"
---
# <a name="walkthrough-creating-and-using-a-vocabulary-in-the-policy"></a><span data-ttu-id="9445a-102">Tutorial: Crear y usar un vocabulario en la directiva</span><span class="sxs-lookup"><span data-stu-id="9445a-102">Walkthrough: Creating and Using a Vocabulary in the Policy</span></span>
<span data-ttu-id="9445a-103">Este tutorial proporciona procedimientos paso a paso para crear un vocabulario y usarlo en el **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="9445a-103">This walkthrough provides step-by-step procedures for creating a vocabulary and using the vocabulary in the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9445a-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="9445a-104">Prerequisites</span></span>  
 <span data-ttu-id="9445a-105">Debe completar el [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial antes de realizar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="9445a-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before performing this walkthrough.</span></span> <span data-ttu-id="9445a-106">Sin embargo, se recomienda realizar previamente todos los tutoriales que aparecen enumerados antes de éste en la documentación.</span><span class="sxs-lookup"><span data-stu-id="9445a-106">However, we recommend that you complete all the walkthroughs that are listed before this walkthrough in the documentation.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="9445a-107">Información general de este tutorial</span><span class="sxs-lookup"><span data-stu-id="9445a-107">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="9445a-108">Este tutorial contiene tres procedimientos, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="9445a-108">This walkthrough contains three procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="9445a-109">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="9445a-109">Procedure title</span></span>|<span data-ttu-id="9445a-110">Descripción de procedimiento</span><span class="sxs-lookup"><span data-stu-id="9445a-110">Procedure descritpion</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="9445a-111">Para crear el vocabulario POVocabulary</span><span class="sxs-lookup"><span data-stu-id="9445a-111">To create the POVocabulary vocabulary</span></span>|<span data-ttu-id="9445a-112">Proporciona instrucciones paso a paso para crear el **POVocabulary** vocabulario con tres definiciones: cantidad solicitada, el máximo número de elementos permitidos y estado de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="9445a-112">Provides step-by-step instructions for creating the **POVocabulary** vocabulary with three definitions: Requested Quantity, Maximum Number of Items Allowed, and Request Status.</span></span>|  
|<span data-ttu-id="9445a-113">Para usar el POVocabulary en la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="9445a-113">To use the POVocabulary in the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="9445a-114">Proporciona instrucciones paso a paso para crear una nueva versión de la **ProcessPurchaseOrder** directiva con **POVocabulary**.</span><span class="sxs-lookup"><span data-stu-id="9445a-114">Provides step-by-step instructions for creating a new version of the **ProcessPurchaseOrder** policy using **POVocabulary**.</span></span>|  
|<span data-ttu-id="9445a-115">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="9445a-115">To test the solution</span></span>|<span data-ttu-id="9445a-116">Proporciona instrucciones paso a paso para probar la solución.</span><span class="sxs-lookup"><span data-stu-id="9445a-116">Provides step-by-step instructions for testing the solution.</span></span>|  
  
### <a name="to-create-the-povocabulary-vocabulary"></a><span data-ttu-id="9445a-117">Para crear el vocabulario POVocabulary</span><span class="sxs-lookup"><span data-stu-id="9445a-117">To create the POVocabulary vocabulary</span></span>  
  
1.  <span data-ttu-id="9445a-118">En el **iniciar** menú Abrir **compositor**.</span><span class="sxs-lookup"><span data-stu-id="9445a-118">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="9445a-119">Si el Compositor de reglas de negocio ya está abierto, presione F5 para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="9445a-119">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9445a-120">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="9445a-120">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="9445a-121">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="9445a-121">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="9445a-122">En la ventana Explorador de hechos, haga clic en el **vocabularios** ficha.</span><span class="sxs-lookup"><span data-stu-id="9445a-122">In the Facts Explorer window, click the **Vocabularies** tab.</span></span>  
  
3.  <span data-ttu-id="9445a-123">Haga clic en **vocabularios**, haga clic en **Agregar nuevo vocabulario**y, a continuación, escriba **POVocabulary** como el nombre del vocabulario.</span><span class="sxs-lookup"><span data-stu-id="9445a-123">Right-click **Vocabularies**, click **Add New Vocabulary**, and then type **POVocabulary** as the name for the vocabulary.</span></span>  
  
4.  <span data-ttu-id="9445a-124">Si no cambió el nombre del vocabulario a POVocabulary en el paso 3, cambie el nombre del vocabulario a **POVocabulary**en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="9445a-124">If you did not change the name of the vocabulary to POVocabulary in step 3, change the name of the vocabulary to **POVocabulary**in the Properties window.</span></span>  
  
5.  <span data-ttu-id="9445a-125">Haga clic en **versión 1.0 (sin guardar)** en **POVocabulary**y, a continuación, haga clic en **agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="9445a-125">Right-click **Version 1.0(not saved)** in **POVocabulary**, and then click **Add New Definition**.</span></span>  
  
6.  <span data-ttu-id="9445a-126">En el Asistente para definición de vocabulario, seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9445a-126">In the Vocabulary Definition Wizard, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="9445a-127">Para el **nombre de la definición**, tipo **cantidad solicitada**.</span><span class="sxs-lookup"><span data-stu-id="9445a-127">For the **Definition name**, type **Requested Quantity**.</span></span>  
  
8.  <span data-ttu-id="9445a-128">Haga clic en **examinar**y seleccione el **PO.xsd** que ha creado en [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md).</span><span class="sxs-lookup"><span data-stu-id="9445a-128">Click **Browse**, and select the **PO.xsd** file you created in [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md).</span></span>  
  
9. <span data-ttu-id="9445a-129">En el **Seleccionar enlace** cuadro de diálogo, expanda **PurchaseOrder**, expanda **elemento**y, a continuación, haga doble clic en **cantidad**.</span><span class="sxs-lookup"><span data-stu-id="9445a-129">In the **Select Binding** dialog box, expand **PurchaseOrder**, expand **Item**, and then double-click **Quantity**.</span></span>  
  
10. <span data-ttu-id="9445a-130">Asegúrese de que el **tipo de documento** está establecido en **RuleTest.PO**.</span><span class="sxs-lookup"><span data-stu-id="9445a-130">Make sure that the **document type** is set to **RuleTest.PO**.</span></span> <span data-ttu-id="9445a-131">Si no es así, cambie el tipo de documento a RuleTest.PO.</span><span class="sxs-lookup"><span data-stu-id="9445a-131">If it is not, change the document type to RuleTest.PO.</span></span> <span data-ttu-id="9445a-132">Este paso es muy importante.</span><span class="sxs-lookup"><span data-stu-id="9445a-132">This step is very important.</span></span>  
  
     <span data-ttu-id="9445a-133">![BRE&#45;tutorial&#45;ChangeDocType2](../core/media/090f0bce-0594-4a67-87d0-3cd22fbb1796.gif "090f0bce-0594-4a67-87d0-3cd22fbb1796")</span><span class="sxs-lookup"><span data-stu-id="9445a-133">![BRE&#45;Walkthrough&#45;ChangeDocType2](../core/media/090f0bce-0594-4a67-87d0-3cd22fbb1796.gif "090f0bce-0594-4a67-87d0-3cd22fbb1796")</span></span>  
  
11. <span data-ttu-id="9445a-134">Especifique el **Seleccionar operación** en el **Seleccionar operación** grupo como **realizar la operación Get**.</span><span class="sxs-lookup"><span data-stu-id="9445a-134">Specify the **select operation** in the **Select operation** group as **Perform Get Operation**.</span></span>  
  
     <span data-ttu-id="9445a-135">![BRE&#45;tutorial&#45;SelectGet](../core/media/3034649a-2d81-4f08-8044-3ab66a201672.gif "3034649a-2d81-4f08-8044-3ab66a201672")</span><span class="sxs-lookup"><span data-stu-id="9445a-135">![BRE&#45;Walkthrough&#45;SelectGet](../core/media/3034649a-2d81-4f08-8044-3ab66a201672.gif "3034649a-2d81-4f08-8044-3ab66a201672")</span></span>  
  
12. <span data-ttu-id="9445a-136">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9445a-136">Click **Finish**.</span></span>  
  
13. <span data-ttu-id="9445a-137">Haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="9445a-137">Right-click **Version 1.0(not saved)**, and then click **Add New Definition**.</span></span>  
  
14. <span data-ttu-id="9445a-138">Seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9445a-138">Select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
15. <span data-ttu-id="9445a-139">Para el **nombre de la definición**, tipo **estado de la solicitud**.</span><span class="sxs-lookup"><span data-stu-id="9445a-139">For the **Definition name**, type **Request Status**.</span></span>  
  
16. <span data-ttu-id="9445a-140">Haga clic en **examinar**y seleccione el **PO.xsd** archivo.</span><span class="sxs-lookup"><span data-stu-id="9445a-140">Click **Browse**, and select the **PO.xsd** file.</span></span>  
  
17. <span data-ttu-id="9445a-141">En el **Seleccionar enlace** cuadro de diálogo, expanda **PurchaseOrder**y, a continuación, haga doble clic en **estado**.</span><span class="sxs-lookup"><span data-stu-id="9445a-141">In the **Select Binding** dialog box, expand **PurchaseOrder**, and then double-click **Status**.</span></span>  
  
18. <span data-ttu-id="9445a-142">Cambiar el **tipo de documento** a **RuleTest.PO**.</span><span class="sxs-lookup"><span data-stu-id="9445a-142">Change the **document type** to **RuleTest.PO**.</span></span> <span data-ttu-id="9445a-143">Este paso es muy importante.</span><span class="sxs-lookup"><span data-stu-id="9445a-143">This step is very important.</span></span>  
  
19. <span data-ttu-id="9445a-144">Asegúrese de que el **operación realizar Set** opción está seleccionada y, a continuación, haga clic en **siguiente.**</span><span class="sxs-lookup"><span data-stu-id="9445a-144">Make sure that the  **Perform Set operation** option is selected, and then click **Next.**</span></span>  
  
20. <span data-ttu-id="9445a-145">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9445a-145">Click **Finish**.</span></span>  
  
21. <span data-ttu-id="9445a-146">Haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="9445a-146">Right-click **Version 1.0(not saved)**, and then click **Add New Definition**.</span></span>  
  
22. <span data-ttu-id="9445a-147">Asegúrese de que **constante de valor, rango de valores o conjunto de valores** está seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9445a-147">Make sure that **Constant Value, Range of Values, or Set of Values** is selected, and then click **Next**.</span></span>  
  
23. <span data-ttu-id="9445a-148">Para el **nombre de la definición**, tipo **máximo número de elementos permitidos**.</span><span class="sxs-lookup"><span data-stu-id="9445a-148">For the **Definition name**, type **Maximum Number of Items Allowed**.</span></span>  
  
24. <span data-ttu-id="9445a-149">Asegúrese de que **tipo de definición de valor constante** está seleccionada y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="9445a-149">Make sure that **Constant Value definition type** is selected, and then click **Next**.</span></span>  
  
25. <span data-ttu-id="9445a-150">Tipo **500** para el valor y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="9445a-150">Type **500** for the value, and then click **Finish**.</span></span>  
  
26. <span data-ttu-id="9445a-151">Haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="9445a-151">Right-click **Version 1.0(not saved)**, and then click **Save**.</span></span>  
  
27. <span data-ttu-id="9445a-152">Haga clic en **versión 1.0 (sin guardar)** y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="9445a-152">Right-click **Version 1.0(not saved)**, and then click **Publish**.</span></span>  
  
### <a name="to-use-the-povocabulary-in-the-processpurchaseorder-policy"></a><span data-ttu-id="9445a-153">Para usar el POVocabulary en la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="9445a-153">To use the POVocabulary in the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="9445a-154">En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.0**y, a continuación, haga clic en **copiar**.</span><span class="sxs-lookup"><span data-stu-id="9445a-154">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Copy**.</span></span>  
  
2.  <span data-ttu-id="9445a-155">Haga clic en **ProcessPurchaseOrder** y, a continuación, haga clic en **Pegar versión de directiva**.</span><span class="sxs-lookup"><span data-stu-id="9445a-155">Right-click **ProcessPurchaseOrder** and then click **Paste Policy Version**.</span></span>  
  
3.  <span data-ttu-id="9445a-156">Haga clic en **ApprovalRule** en **versión 1.1 (sin guardar)**.</span><span class="sxs-lookup"><span data-stu-id="9445a-156">Click **ApprovalRule** in **Version 1.1(not saved)**.</span></span>  
  
4.  <span data-ttu-id="9445a-157">En la ventana Explorador de hechos, expanda **vocabularios**, expanda **POVocabulary**, expanda **versión 1.0**y, a continuación, arrastre **cantidad solicitada**al panel si para sustituir la parte izquierda (LHS) argumento del predicado LessThanOrEqual.</span><span class="sxs-lookup"><span data-stu-id="9445a-157">In the Facts Explorer window, expand **Vocabularies**, expand **POVocabulary**, expand **Version 1.0**, and then drag **Requested Quantity** to the IF pane to replace the left hand side (LHS) argument of the LessThanOrEqual predicate.</span></span>  
  
     <span data-ttu-id="9445a-158">![BRE&#45;tutorial&#45;DragReqQty](../core/media/f5ec8bca-344e-4099-a347-0a2298a3f088.gif "f5ec8bca-344e-4099-a347-0a2298a3f088")</span><span class="sxs-lookup"><span data-stu-id="9445a-158">![BRE&#45;Walkthrough&#45;DragReqQty](../core/media/f5ec8bca-344e-4099-a347-0a2298a3f088.gif "f5ec8bca-344e-4099-a347-0a2298a3f088")</span></span>  
  
     <span data-ttu-id="9445a-159">![BRE&#45;tutorial&#45;ReqQty](../core/media/7afddd71-31ce-4868-94c1-d7ffd81f1e47.gif "7afddd71-31ce-4868-94c1-d7ffd81f1e47")</span><span class="sxs-lookup"><span data-stu-id="9445a-159">![BRE&#45;Walkthrough&#45;ReqQty](../core/media/7afddd71-31ce-4868-94c1-d7ffd81f1e47.gif "7afddd71-31ce-4868-94c1-d7ffd81f1e47")</span></span>  
  
5.  <span data-ttu-id="9445a-160">Arrastre **máximo número de elementos permitidos** para reemplazar el derecho (RHS) argumento de la condición (**500**).</span><span class="sxs-lookup"><span data-stu-id="9445a-160">Drag **Maximum Number of Items Allowed** to replace the right hand side (RHS) argument of the condition (**500**).</span></span>  
  
6.  <span data-ttu-id="9445a-161">Seleccione la acción existente en el panel, a continuación, contextual y, a continuación, haga clic en **Eliminar acción**.</span><span class="sxs-lookup"><span data-stu-id="9445a-161">Select the existing action in the THEN pane, right-click, and then click **Delete action**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9445a-162">También puede presionar SUPRIMIR después de seleccionar la acción que va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="9445a-162">You can also press DELETE after selecting the action to delete the action.</span></span>  
  
7.  <span data-ttu-id="9445a-163">Arrastre **estado de la solicitud** a la **, a continuación,** panel.</span><span class="sxs-lookup"><span data-stu-id="9445a-163">Drag **Request Status** to the **THEN** pane.</span></span>  
  
8.  <span data-ttu-id="9445a-164">Haga clic en **\<una cadena vacía\>** y, a continuación, escriba **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="9445a-164">Click **\<empty string\>** and then type **Approved**.</span></span>  
  
9. <span data-ttu-id="9445a-165">Haga clic en **versión 1.1 (sin guardar)** en la ventana Explorador de directivas y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="9445a-165">Right-click **Version 1.1(not saved)** in the Policy Explorer window, and then click **Save**.</span></span>  
  
10. <span data-ttu-id="9445a-166">Haga clic en **versión 1.1 (sin guardar)** en la ventana Explorador de directivas y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="9445a-166">Right-click **Version 1.1(not saved)** in the Policy Explorer window, and then click **Publish**.</span></span>  
  
### <a name="to-test-the-solution"></a><span data-ttu-id="9445a-167">Para probar la solución</span><span class="sxs-lookup"><span data-stu-id="9445a-167">To test the solution</span></span>  
  
1.  <span data-ttu-id="9445a-168">En el Compositor de reglas de negocio, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.0 - implementada**y, a continuación, haga clic en **anularlaimplementación**.</span><span class="sxs-lookup"><span data-stu-id="9445a-168">In Business Rule Composer, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0 - Deployed**, and then click **Undeploy**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9445a-169">Este paso es opcional porque la orquestación siempre toma la última versión implementada de la directiva, que es la 1.1 después de realizar el paso 2.</span><span class="sxs-lookup"><span data-stu-id="9445a-169">This step is optional because the orchestration always picks the latest deployed version of the policy, which is 1.1 after you perform step 2.</span></span>  
  
2.  <span data-ttu-id="9445a-170">Haga clic en **versión 1.1 - publicada**y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="9445a-170">Right-click **Version 1.1- Published**, and then click **Deploy**.</span></span>  
  
3.  <span data-ttu-id="9445a-171">Espere aproximadamente **60** segundos.</span><span class="sxs-lookup"><span data-stu-id="9445a-171">Wait for approximately **60** seconds.</span></span> <span data-ttu-id="9445a-172">El servicio de actualización del motor de reglas actualiza su caché cada 60 segundos si hay actualizaciones en una directiva que almacena.</span><span class="sxs-lookup"><span data-stu-id="9445a-172">The rule engine update service refreshes its cache every 60 seconds if there are any updates to a policy that it caches.</span></span> <span data-ttu-id="9445a-173">No importa si ha realizado o no el paso 1 porque la orquestación toma la última versión implementada de la directiva, que es la 1.1.</span><span class="sxs-lookup"><span data-stu-id="9445a-173">It does not matter whether you perform step 1—the orchestration picks up the latest deployed version of the policy, which is 1.1</span></span>  
  
4.  <span data-ttu-id="9445a-174">Abra **SamplePO.xml** y **SamplePO2.xml** en el Bloc de notas y cambie el valor de la **estado** campo **XYZ**.</span><span class="sxs-lookup"><span data-stu-id="9445a-174">Open **SamplePO.xml** and **SamplePO2.xml** in Notepad and change the value of the **Status** field to **XYZ**.</span></span>  
  
5.  <span data-ttu-id="9445a-175">Copia el **SamplePO.xml** archivo desde el directorio C:\BRE-Walkthroughs al directorio C:\BRE-Walkthroughs\RuleTestSol\Input para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="9445a-175">Copy the **SamplePO.xml** file from C:\BRE-Walkthroughs directory to C:\BRE-Walkthroughs\RuleTestSol\Input directory for the orchestration.</span></span>  
  
6.  <span data-ttu-id="9445a-176">Debería ver un archivo de salida en el directorio C:\BRE-Walkthroughs\RuleTestSol\Output para la orquestación.</span><span class="sxs-lookup"><span data-stu-id="9445a-176">You should see an output file in the C:\BRE-Walkthroughs\RuleTestSol\Output directory for the orchestration.</span></span> <span data-ttu-id="9445a-177">Abra el archivo XML de salida y observe que el valor de la **estado** campo se establece en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="9445a-177">Open the output XML file and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
7.  <span data-ttu-id="9445a-178">Repita los pasos 5 y 6 con **SamplePO2.xml**y tenga en cuenta que el valor de la **estado** campo en el documento de salida es igual que en el documento de entrada (**XYZ**).</span><span class="sxs-lookup"><span data-stu-id="9445a-178">Repeat steps 5 and 6 with **SamplePO2.xml**, and notice that the value of the **Status** field in the output document is the same as in the input document (**XYZ**).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9445a-179">El valor de la **estado** campo sigue siendo el mismo (XYZ) porque el motor de reglas no ejecuta la acción en el **ApprovalRule** regla porque la condición se evaluó como `false`.</span><span class="sxs-lookup"><span data-stu-id="9445a-179">The value of the **Status** field remains the same (XYZ) because the rule engine does not execute the action in the **ApprovalRule** rule because the condition evaluated to `false`.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="9445a-180">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9445a-180">Comments</span></span>  
  
- <span data-ttu-id="9445a-181">Después de guardar el vocabulario, puede modificarla.</span><span class="sxs-lookup"><span data-stu-id="9445a-181">After you save the vocabulary, you can still modify it.</span></span> <span data-ttu-id="9445a-182">En cambio, después de publicarlo, no puede modificar el vocabulario.</span><span class="sxs-lookup"><span data-stu-id="9445a-182">After you publish the vocabulary, you cannot modify it.</span></span>  
  
- <span data-ttu-id="9445a-183">Si necesita modificar una definición, agregar una nueva o eliminar una definición, debería crear una versión nueva del vocabulario.</span><span class="sxs-lookup"><span data-stu-id="9445a-183">If you need to modify a definition, add a new definition, or delete a definition, you should create a new version of the vocabulary.</span></span>  
  
- <span data-ttu-id="9445a-184">En las directivas sólo se pueden usar vocabularios publicados.</span><span class="sxs-lookup"><span data-stu-id="9445a-184">Only published vocabularies can be used in policies.</span></span>  
  
- <span data-ttu-id="9445a-185">En el procedimiento "para crear el vocabulario POVocabulary", ha cambiado el tipo de documento para **RuleTest.PO**.</span><span class="sxs-lookup"><span data-stu-id="9445a-185">In the "To create the POVocabulary vocabulary" procedure, you changed the document type to **RuleTest.PO**.</span></span> <span data-ttu-id="9445a-186">Para ver los resultados de este cambio, en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en **PO.xsd**.</span><span class="sxs-lookup"><span data-stu-id="9445a-186">To see the results of this change, in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, click **PO.xsd**.</span></span> <span data-ttu-id="9445a-187">En la ventana Propiedades, tenga en cuenta que **RuleTest** es el nombre del espacio de nombres, y **PO** es el nombre de la **tipo**.</span><span class="sxs-lookup"><span data-stu-id="9445a-187">In the Properties window, note that **RuleTest** is the name of the namespace, and **PO** is the name of the **Type**.</span></span>  
  
- <span data-ttu-id="9445a-188">En este tutorial, sólo usó un documento XML como un hecho para la directiva.</span><span class="sxs-lookup"><span data-stu-id="9445a-188">In this walkthrough, you used only an XML document as a fact to the policy.</span></span> <span data-ttu-id="9445a-189">También puede usar hechos .NET y hechos de la base de datos al crear directivas.</span><span class="sxs-lookup"><span data-stu-id="9445a-189">You can also use .NET facts and database facts when you create policies</span></span>  
  
- <span data-ttu-id="9445a-190">Al seleccionar **realizar operación "Set"** en la segunda página del Asistente para definición de vocabulario, puede especificar un **cadena de formato de presentación** en la página siguiente.</span><span class="sxs-lookup"><span data-stu-id="9445a-190">When you select **Perform "Set" operation** on the second page of the Vocabulary Definition Wizard, you can specify a **Display format string** on the page that follows.</span></span> <span data-ttu-id="9445a-191">Por ejemplo, puede cambiar la cadena de formato de presentación de **estado de la solicitud {0}**  a **solicitar el estado es: {0}**  antes de hacer clic **finalizar** en el paso 20 del procedimiento "crear el vocabulario".</span><span class="sxs-lookup"><span data-stu-id="9445a-191">For example, you could change the display format string from **Request Status {0}** to **Request status is: {0}** before clicking **Finish** in the step 20 of the "create vocabulary" procedure.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9445a-192">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="9445a-192">Next Steps</span></span>  
 <span data-ttu-id="9445a-193">Ahora que ha realizado este tutorial, realice el [Tutorial: agregar una regla a la directiva](../core/walkthrough-adding-a-rule-to-the-policy.md) tutorial, lo que le ofrece instrucciones paso a paso para agregar una nueva regla a la **ProcessPurchaseOrder**directiva.</span><span class="sxs-lookup"><span data-stu-id="9445a-193">Now that you have completed this walkthrough, perform the [Walkthrough: Adding a Rule to the Policy](../core/walkthrough-adding-a-rule-to-the-policy.md) walkthrough, which gives you step-by-step instructions for adding a new rule to the **ProcessPurchaseOrder** policy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9445a-194">Vea también</span><span class="sxs-lookup"><span data-stu-id="9445a-194">See Also</span></span>  
 <span data-ttu-id="9445a-195">[Vocabularios](../core/vocabularies.md) </span><span class="sxs-lookup"><span data-stu-id="9445a-195">[Vocabularies](../core/vocabularies.md) </span></span>  
 <span data-ttu-id="9445a-196">[Cómo desarrollar vocabularios](../core/how-to-develop-vocabularies.md) </span><span class="sxs-lookup"><span data-stu-id="9445a-196">[How to Develop Vocabularies](../core/how-to-develop-vocabularies.md) </span></span>  
 <span data-ttu-id="9445a-197">[Evaluación de condiciones y ejecución de acciones](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="9445a-197">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 [<span data-ttu-id="9445a-198">Agenda y prioridad</span><span class="sxs-lookup"><span data-stu-id="9445a-198">Agenda and Priority</span></span>](../core/agenda-and-priority.md)