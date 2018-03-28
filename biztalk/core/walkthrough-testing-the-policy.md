---
title: 'Tutorial: Probar la directiva | Documentos de Microsoft'
ms.custom: ''
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 53ed915d-0f3a-48ea-bfd5-a1f89b9b689c
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a6f879111a28d5cbf9b2a75c7b3f3b3b865fb38
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="walkthrough-testing-the-policy"></a><span data-ttu-id="098cc-102">Tutorial: Probar la directiva</span><span class="sxs-lookup"><span data-stu-id="098cc-102">Walkthrough: Testing the Policy</span></span>
<span data-ttu-id="098cc-103">Este tutorial proporciona procedimientos paso a paso para probar la directiva que creó en el [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial.</span><span class="sxs-lookup"><span data-stu-id="098cc-103">This walkthrough provides step-by-step procedures for testing the policy you created in the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="098cc-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="098cc-104">Prerequisites</span></span>  
 <span data-ttu-id="098cc-105">Debe completar la [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial antes de realizar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="098cc-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before you perform this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="098cc-106">Información general de este tutorial</span><span class="sxs-lookup"><span data-stu-id="098cc-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="098cc-107">Este tutorial contiene dos procedimientos, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="098cc-107">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="098cc-108">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="098cc-108">Procedure title</span></span>|<span data-ttu-id="098cc-109">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="098cc-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="098cc-110">Para crear los archivos de prueba</span><span class="sxs-lookup"><span data-stu-id="098cc-110">To create the test files</span></span>|<span data-ttu-id="098cc-111">Proporciona instrucciones paso a paso para crear XML de ejemplo dos archivos, uno con el valor del campo Quantity, 400 (\<= 500) y el otro con el valor del campo Quantity establecido en 700 (> 500).</span><span class="sxs-lookup"><span data-stu-id="098cc-111">Provides step-by-step instructions for creating two sample XML files, one with the value of the Quantity field as 400 (\<= 500) and the other one with the value of the Quantity field as 700 (> 500).</span></span>|  
|<span data-ttu-id="098cc-112">Para probar la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="098cc-112">To test the ProcessPurchaseOrder policy</span></span>|<span data-ttu-id="098cc-113">Proporciona instrucciones descritas paso a paso para probar la directiva mediante el Compositor de reglas de negocio.</span><span class="sxs-lookup"><span data-stu-id="098cc-113">Provides step-by-step instructions for testing the policy using Business Rule Composer.</span></span>|  
  
### <a name="to-create-the-test-files"></a><span data-ttu-id="098cc-114">Para crear los archivos de prueba</span><span class="sxs-lookup"><span data-stu-id="098cc-114">To create the test files</span></span>  
  
1.  <span data-ttu-id="098cc-115">En el **iniciar** menú Abrir **el Bloc de notas**.</span><span class="sxs-lookup"><span data-stu-id="098cc-115">On the **Start** menu, open **Notepad**.</span></span>  
  
2.  <span data-ttu-id="098cc-116">Copie el texto XML siguiente en el Bloc de notas:</span><span class="sxs-lookup"><span data-stu-id="098cc-116">Copy the following XML to Notepad:</span></span>  
  
    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>400</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>    
    ```  
  
3.  <span data-ttu-id="098cc-117">En el **archivo** menú, haga clic en **guardar Archivodetexto1.txt como**.</span><span class="sxs-lookup"><span data-stu-id="098cc-117">On the **File** menu, click **Save TextFile1.txt As**.</span></span>  
  
4.  <span data-ttu-id="098cc-118">Cambie el valor de **Guardar como tipo** de **documentos de texto (\*.txt)** a **todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="098cc-118">Change the value for **Save As type** from **Text Documents(\*.txt)** to **All Files**.</span></span>  
  
5.  <span data-ttu-id="098cc-119">Cambie el directorio a **C:\BRE-Walkthroughs**.</span><span class="sxs-lookup"><span data-stu-id="098cc-119">Change the directory to **C:\BRE-Walkthroughs**.</span></span>  
  
6.  <span data-ttu-id="098cc-120">Tipo de **SamplePO.xml** para **nombre de archivo**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="098cc-120">Type **SamplePO.xml** for **File name**, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="098cc-121">En el menú **Archivo** , haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="098cc-121">On the **File** menu, click **New**.</span></span>  
  
8.  <span data-ttu-id="098cc-122">Copie el texto XML siguiente en el Bloc de notas:</span><span class="sxs-lookup"><span data-stu-id="098cc-122">Copy the following XML to Notepad:</span></span>  
  
    ```  
    <ns0:PurchaseOrder xmlns:ns0="http://EAISolution.PurchaseOrder">  
      <Header>  
        <ReqID>ReqID_0</ReqID>  
        <Date>Date_0</Date>  
      </Header>  
      <Item>  
        <Description>Description_0</Description>  
        <Quantity>700</Quantity>  
        <UnitPrice>20</UnitPrice>  
      </Item>  
      <Status>XYZ</Status>  
    </ns0:PurchaseOrder>   
    ```  
  
9. <span data-ttu-id="098cc-123">En el **archivo** menú, haga clic en **guardar Archivodetexto1.txt como**.</span><span class="sxs-lookup"><span data-stu-id="098cc-123">On the **File** menu, click **Save TextFile1.txt As**.</span></span>  
  
10. <span data-ttu-id="098cc-124">Cambie el valor de **Guardar como tipo** de **documentos de texto (\*.txt)** a **todos los archivos**.</span><span class="sxs-lookup"><span data-stu-id="098cc-124">Change the value for **Save As type** from **Text Documents(\*.txt)** to **All Files**.</span></span>  
  
11. <span data-ttu-id="098cc-125">Cambie el directorio a **C:\BRE-Walkthroughs**.</span><span class="sxs-lookup"><span data-stu-id="098cc-125">Change the directory to **C:\BRE-Walkthroughs**.</span></span>  
  
12. <span data-ttu-id="098cc-126">Tipo de **SamplePO2.xml** para **nombre de archivo**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="098cc-126">Type **SamplePO2.xml** for **File name**, and then click **Save**.</span></span>  
  
13. <span data-ttu-id="098cc-127">Cierre el Bloc de notas.</span><span class="sxs-lookup"><span data-stu-id="098cc-127">Close Notepad.</span></span>  
  
### <a name="to-test-the-processpurchaseorder-policy"></a><span data-ttu-id="098cc-128">Para probar la directiva ProcessPurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="098cc-128">To test the ProcessPurchaseOrder policy</span></span>  
  
1.  <span data-ttu-id="098cc-129">En el **iniciar** menú Abrir **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="098cc-129">On the **Start** menu, open **Business Rule Composer**.</span></span> <span data-ttu-id="098cc-130">Si tienes Compositor de reglas de negocio ya abierto, presione F5 para actualizarla.</span><span class="sxs-lookup"><span data-stu-id="098cc-130">If you have Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="098cc-131">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="098cc-131">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="098cc-132">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="098cc-132">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="098cc-133">En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en **versión 1.0**y, a continuación, haga clic en **probar directiva**.</span><span class="sxs-lookup"><span data-stu-id="098cc-133">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click **Version 1.0**, and then click **Test Policy**.</span></span>  
  
3.  <span data-ttu-id="098cc-134">En el **XMLDocuments** nodo, seleccione **RuleTest.PO**y, a continuación, haga clic en **Agregar instancia**.</span><span class="sxs-lookup"><span data-stu-id="098cc-134">In the **XMLDocuments** node, select **RuleTest.PO**, and then click **Add Instance**.</span></span>  
  
     <span data-ttu-id="098cc-135">![Compositor de reglas de negocios&#45;TestPolicySelectFacts](../core/media/7115f0d4-0c12-4292-81a5-eb78d62c5543.gif "7115f0d4-0c12-4292-81a5-eb78d62c5543")</span><span class="sxs-lookup"><span data-stu-id="098cc-135">![Business Rule Composer&#45;TestPolicySelectFacts](../core/media/7115f0d4-0c12-4292-81a5-eb78d62c5543.gif "7115f0d4-0c12-4292-81a5-eb78d62c5543")</span></span>  
  
4.  <span data-ttu-id="098cc-136">Seleccione el **SamplePO.xml** archivos que creó anteriormente y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="098cc-136">Select the **SamplePO.xml** file that you created earlier, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="098cc-137">Haga clic en **prueba**.</span><span class="sxs-lookup"><span data-stu-id="098cc-137">Click **Test**.</span></span>  
  
6.  <span data-ttu-id="098cc-138">Revise el resultado en la ventana Salida.</span><span class="sxs-lookup"><span data-stu-id="098cc-138">Review the output in the Output window.</span></span> <span data-ttu-id="098cc-139">Para obtener una explicación sobre la salida, vea la sección "Análisis de la salida de la primera prueba (samplepo.xml)".</span><span class="sxs-lookup"><span data-stu-id="098cc-139">See the "Analysis of the Output from the First Test (samplepo.xml)" section for an explanation of the output you see.</span></span>  
  
7.  <span data-ttu-id="098cc-140">Abra **SamplePO.xml** en el Bloc de notas y observe que el valor de la **estado** campo está establecido en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="098cc-140">Open **SamplePO.xml** in Notepad and notice that the value of the **Status** field is set to **Approved**.</span></span>  
  
8.  <span data-ttu-id="098cc-141">Haga clic en **versión 1.0**y, a continuación, haga clic en **probar directiva**.</span><span class="sxs-lookup"><span data-stu-id="098cc-141">Right-click **Version 1.0**, and then click **Test Policy**.</span></span>  
  
9. <span data-ttu-id="098cc-142">Seleccione **SamplePO.xml**, haga clic en **quitar instancia**y, a continuación, haga clic en **Agregar instancia**.</span><span class="sxs-lookup"><span data-stu-id="098cc-142">Select **SamplePO.xml**, click **Remove instance**, and then click **Add Instance**.</span></span>  
  
10. <span data-ttu-id="098cc-143">Seleccione el **SamplePO2.xml** archivos que creó anteriormente y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="098cc-143">Select the **SamplePO2.xml** file that you created earlier, and then click **Open**.</span></span>  
  
11. <span data-ttu-id="098cc-144">Haga clic en **prueba**.</span><span class="sxs-lookup"><span data-stu-id="098cc-144">Click **Test**.</span></span> <span data-ttu-id="098cc-145">Para obtener una explicación sobre la salida, vea la sección "Análisis de la salida de la segunda prueba (samplepo2.xml)".</span><span class="sxs-lookup"><span data-stu-id="098cc-145">See the "Analysis of the Output from the Second Test (samplepo2.xml)" section for an explanation of the output you see.</span></span>  
  
12. <span data-ttu-id="098cc-146">Abra la **SamplePO2.xml** un archivo en el Bloc de notas y observe que el valor de la **estado** campo sigue siendo **XYZ**.</span><span class="sxs-lookup"><span data-stu-id="098cc-146">Open the **SamplePO2.xml** file in Notepad and notice that the value of the **Status** field is still **XYZ**.</span></span>  
  
## <a name="analysis-of-the-output-from-the-first-test-samplepoxml"></a><span data-ttu-id="098cc-147">Análisis del resultado de la primera prueba (samplepo.xml)</span><span class="sxs-lookup"><span data-stu-id="098cc-147">Analysis of the Output from the First Test (samplepo.xml)</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="098cc-148">El texto de salida aparece en negrita y la explicación aparece a continuación de éste.</span><span class="sxs-lookup"><span data-stu-id="098cc-148">The output text is bold and the explanation follows the output text.</span></span>  
  
 <span data-ttu-id="098cc-149">**SEGUIMIENTO de motor de reglas para conjunto de reglas: ProcessPurchaseOrder 31/8/2006 1:33:10 P.M.**</span><span class="sxs-lookup"><span data-stu-id="098cc-149">**RULE ENGINE TRACE for RULESET: ProcessPurchaseOrder 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="098cc-150">El seguimiento de motor de reglas para la ejecución de la directiva de **ProcessPurchaseOrder** se inició a 31/8/2006 1:33:10 P.M.</span><span class="sxs-lookup"><span data-stu-id="098cc-150">The rule engine trace for the execution of policy **ProcessPurchaseOrder** started at 8/31/2006 1:33:10 PM.</span></span>  
  
 <span data-ttu-id="098cc-151">**ACTIVIDAD DE HECHOS 31/8/2006 1:33:10 P.M.**</span><span class="sxs-lookup"><span data-stu-id="098cc-151">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="098cc-152">**Identificador de la instancia de motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="098cc-152">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="098cc-153">**Nombre de conjunto de reglas: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-153">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-154">**Operación: Assert**</span><span class="sxs-lookup"><span data-stu-id="098cc-154">**Operation: Assert**</span></span>  
  
 <span data-ttu-id="098cc-155">**Tipo de objeto: TypedXmlDocument:PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-155">**Object Type: TypedXmlDocument:PurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-156">**Identificador de instancia de objeto: 14626574**</span><span class="sxs-lookup"><span data-stu-id="098cc-156">**Object Instance Identifier: 14626574**</span></span>  
  
 <span data-ttu-id="098cc-157">Al hacer clic en **prueba**, sucede lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="098cc-157">When you click **Test**, the following things happen:</span></span>  
  
1.  <span data-ttu-id="098cc-158">El Compositor de reglas de negocios crea una **RuleEngine.Policy** objeto, que a su vez crea una nueva instancia de motor de reglas o adquiere una instancia de motor de reglas de la caché del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="098cc-158">The Business Rule Composer creates a **RuleEngine.Policy** object, which in turn creates a new rule engine instance or acquires a rule engine instance from the rule engine cache.</span></span>  
  
2.  <span data-ttu-id="098cc-159">El Compositor de reglas de negocios crea una **TypedXmlDocument** objeto basado en el archivo SamplePO.xml.</span><span class="sxs-lookup"><span data-stu-id="098cc-159">The Business Rule Composer creates a **TypedXmlDocument** object based on the SamplePO.xml file.</span></span>  
  
3.  <span data-ttu-id="098cc-160">El Compositor de reglas de negocio, se invoca el **Policy.Execute** método con el **TypedXmlDocument** objeto como parámetro.</span><span class="sxs-lookup"><span data-stu-id="098cc-160">The Business Rule Composer invokes the **Policy.Execute** method with the **TypedXmlDocument** object as a parameter.</span></span>  
  
4.  <span data-ttu-id="098cc-161">El **Policy.Execute** método impone (agrega) la **TypedXmlDocument** objeto como un hecho en la memoria de trabajo del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="098cc-161">The **Policy.Execute** method asserts (adds) the **TypedXmlDocument** object as a fact into the working memory of the rule engine.</span></span>  
  
5.  <span data-ttu-id="098cc-162">El motor de reglas utiliza el **TypedXmlDocument** objeto como un hecho y ejecuta el **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="098cc-162">The rule engine uses the **TypedXmlDocument** object as a fact and executes the **ProcessPurchaseOrder** policy.</span></span>  
  
 <span data-ttu-id="098cc-163">**ACTIVIDAD DE HECHOS 31/8/2006 1:33:10 P.M.**</span><span class="sxs-lookup"><span data-stu-id="098cc-163">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="098cc-164">**Identificador de la instancia de motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="098cc-164">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="098cc-165">**Nombre de conjunto de reglas: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-165">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-166">**Operación: Assert**</span><span class="sxs-lookup"><span data-stu-id="098cc-166">**Operation: Assert**</span></span>  
  
 <span data-ttu-id="098cc-167">**Tipo de objeto: TypedXmlDocument:PurchaseOrder: / PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-167">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-168">**Identificador de instancia de objeto: 64530307**</span><span class="sxs-lookup"><span data-stu-id="098cc-168">**Object Instance Identifier: 64530307**</span></span>  
  
 <span data-ttu-id="098cc-169">**ACTIVIDAD DE HECHOS 31/8/2006 1:33:10 P.M.**</span><span class="sxs-lookup"><span data-stu-id="098cc-169">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="098cc-170">**Identificador de la instancia de motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="098cc-170">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="098cc-171">**Nombre de conjunto de reglas: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-171">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-172">**Operación: Assert**</span><span class="sxs-lookup"><span data-stu-id="098cc-172">**Operation: Assert**</span></span>  
  
 <span data-ttu-id="098cc-173">**Tipo de objeto: TypedXmlDocument:PurchaseOrder: / PurchaseOrder/Item**</span><span class="sxs-lookup"><span data-stu-id="098cc-173">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item**</span></span>  
  
 <span data-ttu-id="098cc-174">**Identificador de instancia de objeto: 43901854**</span><span class="sxs-lookup"><span data-stu-id="098cc-174">**Object Instance Identifier: 43901854**</span></span>  
  
1.  <span data-ttu-id="098cc-175">El motor de reglas determina qué secundarios **TypedXmlDocument** objetos se deben crear según los selectores XPath que estén definidos en las reglas.</span><span class="sxs-lookup"><span data-stu-id="098cc-175">The rule engine determines which child **TypedXmlDocument** objects to create based on the XPath selectors defined in the rules.</span></span> <span data-ttu-id="098cc-176">Al compilar las reglas en el Compositor de reglas de negocios, el valor del selector XPath predeterminado es el nodo por encima del nodo seleccionado en el **esquemas XML** pestaña en el Explorador de hechos.</span><span class="sxs-lookup"><span data-stu-id="098cc-176">When you build rules in the Business Rule Composer, the XPath selector value defaults to the node above the node selected in the **XML Schemas** tab in Facts Explorer.</span></span> <span data-ttu-id="098cc-177">El valor predeterminado del campo XPath es el nodo seleccionado en sí, con respecto al nodo primario.</span><span class="sxs-lookup"><span data-stu-id="098cc-177">The XPath field value defaults to the selected node itself, relative to its parent node.</span></span> <span data-ttu-id="098cc-178">Sin embargo, si el nodo seleccionado tiene elementos secundarios, sólo se crea un enlace del selector XPath para señalar al nodo seleccionado y no se crea ningún enlace del campo XPath.</span><span class="sxs-lookup"><span data-stu-id="098cc-178">However, if the node you selected has children, only an XPath selector binding is created to point to the node that you selected, and no XPath field binding is created.</span></span>  
  
2.  <span data-ttu-id="098cc-179">En la tabla siguiente se muestra el Selector XPath y XPath Field valores de enlace para los campos utilizados en el **ProcessPurchaseOrder** directiva.</span><span class="sxs-lookup"><span data-stu-id="098cc-179">The following table shows the XPath Selector and XPath Field binding values for the fields used in the **ProcessPurchaseOrder** policy.</span></span> <span data-ttu-id="098cc-180">(La directiva sólo tiene una regla: ApprovalRule.)</span><span class="sxs-lookup"><span data-stu-id="098cc-180">(The policy has only one rule, ApprovalRule.)</span></span>  
  
|<span data-ttu-id="098cc-181">Nombre de campo</span><span class="sxs-lookup"><span data-stu-id="098cc-181">Field name</span></span>|<span data-ttu-id="098cc-182">Selector XPath</span><span class="sxs-lookup"><span data-stu-id="098cc-182">XPath Selector</span></span>|<span data-ttu-id="098cc-183">Campo XPath</span><span class="sxs-lookup"><span data-stu-id="098cc-183">XPath Field</span></span>|<span data-ttu-id="098cc-184">Selector XPath (forma simplificada)</span><span class="sxs-lookup"><span data-stu-id="098cc-184">XPath Selector (simplified form)</span></span>|<span data-ttu-id="098cc-185">Campo XPath</span><span class="sxs-lookup"><span data-stu-id="098cc-185">XPath Field</span></span><br /><br /> <span data-ttu-id="098cc-186">(forma simplificada)</span><span class="sxs-lookup"><span data-stu-id="098cc-186">(simplified form)</span></span>|  
|----------------|--------------------|-----------------|----------------------------------------|-----------------------------------------|  
|<span data-ttu-id="098cc-187">Cantidad</span><span class="sxs-lookup"><span data-stu-id="098cc-187">Quantity</span></span>|<span data-ttu-id="098cc-188">/ * [local-name () = 'PurchaseOrder' y el espacio ='http://EAISolution.PurchaseOrder'] /\*[local-name () = 'Item' y el espacio ='']</span><span class="sxs-lookup"><span data-stu-id="098cc-188">/*[local-name()='PurchaseOrder' and namespace-uri()='http://EAISolution.PurchaseOrder']/\*[local-name()='Item' and namespace-uri()='']</span></span>|<span data-ttu-id="098cc-189">\*[local-name()='Quantity' and namespace-uri()='']</span><span class="sxs-lookup"><span data-stu-id="098cc-189">\*[local-name()='Quantity' and namespace-uri()='']</span></span>|<span data-ttu-id="098cc-190">/PurchaseOrder/Item</span><span class="sxs-lookup"><span data-stu-id="098cc-190">/PurchaseOrder/Item</span></span>|<span data-ttu-id="098cc-191">Cantidad</span><span class="sxs-lookup"><span data-stu-id="098cc-191">Quantity</span></span>|  
|<span data-ttu-id="098cc-192">Estado</span><span class="sxs-lookup"><span data-stu-id="098cc-192">Status</span></span>|<span data-ttu-id="098cc-193">/ \* [local-name () = 'PurchaseOrder' y el espacio ='http://EAISolution.PurchaseOrder']</span><span class="sxs-lookup"><span data-stu-id="098cc-193">/\*[local-name()='PurchaseOrder' and namespace-uri()='http://EAISolution.PurchaseOrder']</span></span>|<span data-ttu-id="098cc-194">\*[local-name()='Status' and namespace-uri()='']</span><span class="sxs-lookup"><span data-stu-id="098cc-194">\*[local-name()='Status' and namespace-uri()='']</span></span>|<span data-ttu-id="098cc-195">/PurchaseOrder</span><span class="sxs-lookup"><span data-stu-id="098cc-195">/PurchaseOrder</span></span>|<span data-ttu-id="098cc-196">Estado</span><span class="sxs-lookup"><span data-stu-id="098cc-196">Status</span></span>|  
  
#### <a name="to-view-the-xpath-selector-and-xpath-field-bindings-for-the-quantity-and-status-fields"></a><span data-ttu-id="098cc-197">Para ver los enlaces de Selector Xpath y Campo Xpath de los campos Quantity y Status</span><span class="sxs-lookup"><span data-stu-id="098cc-197">To view the Xpath Selector and Xpath Field bindings for the Quantity and Status fields</span></span>  
  
1.  <span data-ttu-id="098cc-198">En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**y, a continuación, expanda **versión 1.0**.</span><span class="sxs-lookup"><span data-stu-id="098cc-198">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, and then expand **Version 1.0**.</span></span>  
  
2.  <span data-ttu-id="098cc-199">Haga clic en **ApprovalRule**.</span><span class="sxs-lookup"><span data-stu-id="098cc-199">Click **ApprovalRule**.</span></span>  
  
3.  <span data-ttu-id="098cc-200">En el panel si de la derecha, haga clic en **PO: / PurchaseOrder/Item/Quantity**.</span><span class="sxs-lookup"><span data-stu-id="098cc-200">In the IF pane on the right, click **PO:/PurchaseOrder/Item/Quantity**.</span></span>  
  
4.  <span data-ttu-id="098cc-201">Compruebe que ve el valor mostrado en la tabla anterior para el **Selector XPath** y **XPath Field** enlaces en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="098cc-201">Verify that you see the value shown in the preceding table for the **XPath Selector** and **XPath Field** bindings in the Properties window.</span></span>  
  
5.  <span data-ttu-id="098cc-202">Repita los pasos 3 y 4 para el **PO: / PurchaseOrder/Status** campo.</span><span class="sxs-lookup"><span data-stu-id="098cc-202">Repeat steps 3 and 4 for the **PO:/PurchaseOrder/Status** field.</span></span>  
  
 <span data-ttu-id="098cc-203">El motor de reglas crea un elemento secundario **TypedXmlDocument** objeto desde la versión original **TypedXmlDocument** enviado para cada selector XPath.</span><span class="sxs-lookup"><span data-stu-id="098cc-203">The rule engine creates a child **TypedXmlDocument** object from the original **TypedXmlDocument** you submitted for each XPath selector.</span></span> <span data-ttu-id="098cc-204">Dado que hay dos selectores XPath distintos utilizados en la directiva (**/PurchaseOrder/Item** para el **cantidad** campo y **/PurchaseOrder** para el  **Estado** campo), el motor de reglas crea dos secundarios **TypedXmlDocument** objetos y los impone en la memoria de trabajo del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="098cc-204">Because there are two distinct XPath selectors used in the policy (**/PurchaseOrder/Item** for the **Quantity** field and **/PurchaseOrder** for the **Status** field), the rule engine creates two child **TypedXmlDocument** objects and asserts them into the working memory of the rule engine.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="098cc-205">Para ver el seguimiento de salida nuevo, haga clic en **versión 1.0** en la ventana Explorador de directivas.</span><span class="sxs-lookup"><span data-stu-id="098cc-205">To see the trace output again, click **Version 1.0** in the Policy Explorer window.</span></span>  
  
 <span data-ttu-id="098cc-206">**PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 31/8/2006 1:33:10 P.M.**</span><span class="sxs-lookup"><span data-stu-id="098cc-206">**CONDITION EVALUATION TEST (MATCH) 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="098cc-207">**Identificador de la instancia de motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="098cc-207">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="098cc-208">**Nombre de conjunto de reglas: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-208">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-209">**Expresión de prueba: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**</span><span class="sxs-lookup"><span data-stu-id="098cc-209">**Test Expression: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity <= 500**</span></span>  
  
 <span data-ttu-id="098cc-210">**Deja el valor del operando: 400**</span><span class="sxs-lookup"><span data-stu-id="098cc-210">**Left Operand Value: 400**</span></span>  
  
 <span data-ttu-id="098cc-211">**Valor del operando de la derecha: 500**</span><span class="sxs-lookup"><span data-stu-id="098cc-211">**Right Operand Value: 500**</span></span>  
  
 <span data-ttu-id="098cc-212">**Resultado de pruebas: True**</span><span class="sxs-lookup"><span data-stu-id="098cc-212">**Test Result: True**</span></span>  
  
 <span data-ttu-id="098cc-213">**ACTUALIZACIÓN DE AGENDA 31/8/2006 1:33:10 P.M.**</span><span class="sxs-lookup"><span data-stu-id="098cc-213">**AGENDA UPDATE 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="098cc-214">**Identificador de la instancia de motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="098cc-214">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="098cc-215">**Nombre de conjunto de reglas: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-215">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-216">**Operación: agregar**</span><span class="sxs-lookup"><span data-stu-id="098cc-216">**Operation: Add**</span></span>  
  
 <span data-ttu-id="098cc-217">**Nombre de regla: ApprovalRule**</span><span class="sxs-lookup"><span data-stu-id="098cc-217">**Rule Name: ApprovalRule**</span></span>  
  
 <span data-ttu-id="098cc-218">**Criterios de resolución de conflictos: 0**</span><span class="sxs-lookup"><span data-stu-id="098cc-218">**Conflict Resolution Criteria: 0**</span></span>  
  
 <span data-ttu-id="098cc-219">Para ejecutar las directivas, el motor de reglas usa el algoritmo de tres fases Evaluación de condición – Resolución de conflictos – Ejecución de acciones.</span><span class="sxs-lookup"><span data-stu-id="098cc-219">The rule engine uses the three-stage Condition Evaluation-Conflict Resolution-Action Execution algorithm to execute policies.</span></span> <span data-ttu-id="098cc-220">En la fase Evaluación de la condición, el motor de reglas evalúa las condiciones de todas las reglas de la directiva y agrega las reglas cuyas condiciones se evalúan como `true` para la agenda.</span><span class="sxs-lookup"><span data-stu-id="098cc-220">In the Condition Evaluation stage, the rule engine evaluates the conditions in all the rules in the policy and adds the rules whose conditions evaluate to `true` to the agenda.</span></span> <span data-ttu-id="098cc-221">En este sencillo ejemplo, la **ProcessPurchaseOrder** directiva sólo tiene una regla, **ApprovalRule**.</span><span class="sxs-lookup"><span data-stu-id="098cc-221">In this simple example, the **ProcessPurchaseOrder** policy has only one rule, **ApprovalRule**.</span></span> <span data-ttu-id="098cc-222">Por lo tanto, el motor de reglas evalúa la condición, **cantidad < = 500**, en la **ApprovalRule** utilizando el valor de la **cantidad** campo en el documento XML enviado, ¿Cuál es **400**.</span><span class="sxs-lookup"><span data-stu-id="098cc-222">Therefore, the rule engine evaluates the condition, **Quantity <= 500**, in the **ApprovalRule** using the value of the **Quantity** field in the submitted XML document, which is **400**.</span></span> <span data-ttu-id="098cc-223">La salida anterior muestra los valores del operando izquierdo, el operando derecho y el resultado de la prueba.</span><span class="sxs-lookup"><span data-stu-id="098cc-223">The output above shows you the values of the left operand, right operand, and test result.</span></span>  
  
 <span data-ttu-id="098cc-224">En la segunda fase, Criterios de resolución de conflictos, las reglas cuyas condiciones se evalúan como `true` se agregan a la agenda en orden según su prioridad.</span><span class="sxs-lookup"><span data-stu-id="098cc-224">In the second stage, the Conflict Resolution Criteria stage, the rules whose conditions evaluate to `true` are added to the agenda in order based on their priority.</span></span> <span data-ttu-id="098cc-225">En este escenario, el motor de reglas agrega la **ApprovalRule** a la agenda porque la condición para la **ApprovalRule** evalúan a `true`.</span><span class="sxs-lookup"><span data-stu-id="098cc-225">In this scenario, the rule engine adds the **ApprovalRule** to the agenda because the condition for the **ApprovalRule** evaluated to `true`.</span></span> <span data-ttu-id="098cc-226">Los criterios de resolución de conflictos se muestra en la salida anterior es sólo la prioridad de la regla (**ApprovalRule**).</span><span class="sxs-lookup"><span data-stu-id="098cc-226">The Conflict Resolution Criteria shown in the output above is only the priority on the rule (**ApprovalRule**).</span></span> <span data-ttu-id="098cc-227">Si hace clic en el **ApprovalRule** nodo en la ventana Explorador de directivas, puede ver el valor de la **prioridad** propiedad en la regla en la ventana de propiedades como **0**, que es el valor predeterminado de una regla.</span><span class="sxs-lookup"><span data-stu-id="098cc-227">If you click the **ApprovalRule** node in the Policy Explorer window, you can see the value of the **Priority** property on the rule in the Properties window as **0**, which is the default value of a rule.</span></span> <span data-ttu-id="098cc-228">Si hay varias reglas en una directiva y desea asegurarse de que las acciones de una regla se ejecutan después de las acciones de otra, debe establecer la prioridad correctamente.</span><span class="sxs-lookup"><span data-stu-id="098cc-228">If you have multiple rules in a policy, and you want to make sure that actions in one rule are executed after actions in another rule, you should set the priority appropriately.</span></span> <span data-ttu-id="098cc-229">Cuanto mayor es el número, mayor es la prioridad.</span><span class="sxs-lookup"><span data-stu-id="098cc-229">The larger the number, the higher the priority.</span></span>  
  
 <span data-ttu-id="098cc-230">**REGLA ACTIVADA 31/8/2006 1:33:10 P.M.**</span><span class="sxs-lookup"><span data-stu-id="098cc-230">**RULE FIRED 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="098cc-231">**Identificador de la instancia de motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="098cc-231">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="098cc-232">**Nombre de conjunto de reglas: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-232">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-233">**Nombre de regla: ApprovalRule**</span><span class="sxs-lookup"><span data-stu-id="098cc-233">**Rule Name: ApprovalRule**</span></span>  
  
 <span data-ttu-id="098cc-234">**Criterios de resolución de conflictos: 0**</span><span class="sxs-lookup"><span data-stu-id="098cc-234">**Conflict Resolution Criteria: 0**</span></span>  
  
 <span data-ttu-id="098cc-235">En la última fase, Ejecución de acción, el motor de reglas inicia la ejecución de las acciones de la regla.</span><span class="sxs-lookup"><span data-stu-id="098cc-235">In the last stage, the Action Execution stage, the rule engine starts executing the actions in the rule.</span></span> <span data-ttu-id="098cc-236">Hay una acción en el **ApprovalRule**, que establece el valor de la **estado** campo en el documento XML enviado a **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="098cc-236">There is one action in the **ApprovalRule**, which sets the value of the **Status** field in the submitted XML document to **Approved**.</span></span>  
  
 <span data-ttu-id="098cc-237">**ACTIVIDAD DE HECHOS 31/8/2006 1:33:10 P.M.**</span><span class="sxs-lookup"><span data-stu-id="098cc-237">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="098cc-238">**Identificador de la instancia de motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="098cc-238">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="098cc-239">**Nombre de conjunto de reglas: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-239">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-240">**Operación: retirar**</span><span class="sxs-lookup"><span data-stu-id="098cc-240">**Operation: Retract**</span></span>  
  
 <span data-ttu-id="098cc-241">**Tipo de objeto: TypedXmlDocument:PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-241">**Object Type: TypedXmlDocument:PurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-242">**Identificador de instancia de objeto: 14626574**</span><span class="sxs-lookup"><span data-stu-id="098cc-242">**Object Instance Identifier: 14626574**</span></span>  
  
 <span data-ttu-id="098cc-243">**ACTIVIDAD DE HECHOS 31/8/2006 1:33:10 P.M.**</span><span class="sxs-lookup"><span data-stu-id="098cc-243">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="098cc-244">**Identificador de la instancia de motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="098cc-244">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="098cc-245">**Nombre de conjunto de reglas: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-245">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-246">**Operación: retirar**</span><span class="sxs-lookup"><span data-stu-id="098cc-246">**Operation: Retract**</span></span>  
  
 <span data-ttu-id="098cc-247">**Tipo de objeto: TypedXmlDocument:PurchaseOrder: / PurchaseOrder/Item**</span><span class="sxs-lookup"><span data-stu-id="098cc-247">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item**</span></span>  
  
 <span data-ttu-id="098cc-248">**Identificador de instancia de objeto: 43901854**</span><span class="sxs-lookup"><span data-stu-id="098cc-248">**Object Instance Identifier: 43901854**</span></span>  
  
 <span data-ttu-id="098cc-249">**ACTIVIDAD DE HECHOS 31/8/2006 1:33:10 P.M.**</span><span class="sxs-lookup"><span data-stu-id="098cc-249">**FACT ACTIVITY 8/31/2006 1:33:10 PM**</span></span>  
  
 <span data-ttu-id="098cc-250">**Identificador de la instancia de motor de reglas: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span><span class="sxs-lookup"><span data-stu-id="098cc-250">**Rule Engine Instance Identifier: bc4f1cf5-e9a2-49d0-9cdd-76a2ac057240**</span></span>  
  
 <span data-ttu-id="098cc-251">**Nombre de conjunto de reglas: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-251">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-252">**Operación: retirar**</span><span class="sxs-lookup"><span data-stu-id="098cc-252">**Operation: Retract**</span></span>  
  
 <span data-ttu-id="098cc-253">**Tipo de objeto: TypedXmlDocument:PurchaseOrder: / PurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-253">**Object Type: TypedXmlDocument:PurchaseOrder:/PurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-254">**Identificador de la instancia de objeto:** 64530307</span><span class="sxs-lookup"><span data-stu-id="098cc-254">**Object Instance Identifier:** 64530307</span></span>  
  
 <span data-ttu-id="098cc-255">Todos los hechos enviados (**PurchaseOrder**) a la regla de motor y los hechos secundarios creados por el motor de reglas se basan en los selectores XPath (**\PurchaseOrder** y **\PurchaseOrder\Item**) se retiran (quitan) de la memoria de trabajo del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="098cc-255">All the facts submitted (**PurchaseOrder**) to the rule engine and the child facts created by the rule engine based on XPath selectors (**\PurchaseOrder** and **\PurchaseOrder\Item**) are retracted (removed) from the working memory of the rule engine.</span></span>  
  
## <a name="analysis-of-the-output-from-the-second-test-samplepo2xml"></a><span data-ttu-id="098cc-256">Análisis del resultado de la segunda prueba (samplepo2.xml)</span><span class="sxs-lookup"><span data-stu-id="098cc-256">Analysis of the Output from the Second Test (samplepo2.xml)</span></span>  
 <span data-ttu-id="098cc-257">**PRUEBA DE EVALUACIÓN DE CONDICIÓN (COINCIDENCIA) 5/9/2006 5:24:42 P.M.**</span><span class="sxs-lookup"><span data-stu-id="098cc-257">**CONDITION EVALUATION TEST (MATCH) 9/5/2006 5:24:42 PM**</span></span>  
  
 <span data-ttu-id="098cc-258">**Identificador de la instancia de motor de reglas: b749d2fd-a883-4c2f-9974-5cf688010622**</span><span class="sxs-lookup"><span data-stu-id="098cc-258">**Rule Engine Instance Identifier: b749d2fd-a883-4c2f-9974-5cf688010622**</span></span>  
  
 <span data-ttu-id="098cc-259">**Nombre de conjunto de reglas: ProcessPurchaseOrder**</span><span class="sxs-lookup"><span data-stu-id="098cc-259">**Ruleset Name: ProcessPurchaseOrder**</span></span>  
  
 <span data-ttu-id="098cc-260">**Expresión de prueba: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity < = 500**</span><span class="sxs-lookup"><span data-stu-id="098cc-260">**Test Expression: TypedXmlDocument:PurchaseOrder:/PurchaseOrder/Item.Quantity <= 500**</span></span>  
  
 <span data-ttu-id="098cc-261">**Deja el valor del operando: 700**</span><span class="sxs-lookup"><span data-stu-id="098cc-261">**Left Operand Value: 700**</span></span>  
  
 <span data-ttu-id="098cc-262">**Valor del operando de la derecha: 500**</span><span class="sxs-lookup"><span data-stu-id="098cc-262">**Right Operand Value: 500**</span></span>  
  
 <span data-ttu-id="098cc-263">**Resultado de la prueba:** False</span><span class="sxs-lookup"><span data-stu-id="098cc-263">**Test Result:** False</span></span>  
  
 <span data-ttu-id="098cc-264">El motor de reglas evalúa la condición (**cantidad < = 500**) en el **ApprovalRule** con la única **elemento** objeto.</span><span class="sxs-lookup"><span data-stu-id="098cc-264">The rule engine evaluates the condition (**Quantity <= 500**) in the **ApprovalRule** using the lone **Item** object.</span></span> <span data-ttu-id="098cc-265">Puede ver que el valor del operando izquierdo es el valor de la **cantidad** elemento en el documento XML, **700**.</span><span class="sxs-lookup"><span data-stu-id="098cc-265">You can see that left operand value is the value of the **Quantity** element in the XML document, **700**.</span></span> <span data-ttu-id="098cc-266">El resultado de prueba es `false` porque **700 < = 500**, por lo que la regla no se agrega a la agenda del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="098cc-266">The test result is `false` because **700 <= 500**, so the rule is not added to the agenda of the rule engine.</span></span> <span data-ttu-id="098cc-267">No hay ninguna regla en la agenda.</span><span class="sxs-lookup"><span data-stu-id="098cc-267">There is no rule in the agenda.</span></span> <span data-ttu-id="098cc-268">Por lo tanto, hay ninguna acción para ejecutar y el valor de la **estado** campo sigue siendo **XYZ**.</span><span class="sxs-lookup"><span data-stu-id="098cc-268">Therefore, there are no actions to execute, and the value of the **Status** field remains **XYZ**.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="098cc-269">Comentarios</span><span class="sxs-lookup"><span data-stu-id="098cc-269">Comments</span></span>  
  
-   <span data-ttu-id="098cc-270">Se recomienda probar las directivas antes de utilizarlas desde aplicaciones cliente, como aplicaciones de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="098cc-270">We recommend that you test the policies before using them from client applications such as BizTalk applications.</span></span>  
  
-   <span data-ttu-id="098cc-271">Cuando se prueba una directiva que utiliza hechos de base de datos con la **DataConnection** enlace en el Compositor de reglas de negocios, un **DataConnection** objeto se crea automáticamente para usted.</span><span class="sxs-lookup"><span data-stu-id="098cc-271">When you test a policy that uses database facts with the **DataConnection** binding in the Business Rule Composer, a **DataConnection** object is automatically built for you.</span></span> <span data-ttu-id="098cc-272">Sin embargo, cuando se llama a la misma directiva desde una orquestación mediante el uso de la **reglas de llamada** forma, no **DataConnection** objeto se pasa automáticamente a la directiva.</span><span class="sxs-lookup"><span data-stu-id="098cc-272">However, when you call the same policy from an orchestration by using the **Call Rules** shape, no **DataConnection** object is passed to the policy automatically.</span></span> <span data-ttu-id="098cc-273">Debe crear un **DataConnection** objeto en la orquestación y pasarlo como parámetro o crear un componente de almacenes de datos de hechos que imponga el **DataConnection** de objetos y configurar la directiva de el componente recuperador de datos.</span><span class="sxs-lookup"><span data-stu-id="098cc-273">You should create a **DataConnection** object in the orchestration and pass it as a parameter or create a fact retriever component that asserts the **DataConnection** object, and configure the policy to use the fact retriever component.</span></span>  
  
-   <span data-ttu-id="098cc-274">Para probar una directiva que utiliza un hecho. NET, debe crear un componente de creador de hechos y especificarlo en el **Seleccionar hechos** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="098cc-274">To test a policy that uses a .NET fact, you should create a fact creator component and specify it in the **Select Facts** dialog box.</span></span> <span data-ttu-id="098cc-275">Para obtener más información acerca de cómo crear creadores de hechos, vea [cómo crear un administrador de almacenes](../core/how-to-create-a-fact-retriever.md).</span><span class="sxs-lookup"><span data-stu-id="098cc-275">For more information about creating fact creators, see [How to Create a Fact Retriever](../core/how-to-create-a-fact-retriever.md).</span></span> <span data-ttu-id="098cc-276">Puede hacer lo mismo cuando la directiva utiliza hechos de base de datos (**TypedDataConnection** o **TypedDataTable** o **TypedDataRow**) o hechos XML ( **TypedXmlDocument**).</span><span class="sxs-lookup"><span data-stu-id="098cc-276">You can do the same thing when the policy uses database facts (**TypedDataConnection** or **TypedDataTable** or **TypedDataRow**) or XML facts (**TypedXmlDocument**).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="098cc-277">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="098cc-277">Next Steps</span></span>  
 <span data-ttu-id="098cc-278">Ahora que ha completado este tutorial, realice la [Tutorial: invocar la directiva desde una orquestación](../core/walkthrough-invoking-the-policy-from-an-orchestration.md) tutorial, que encontrará instrucciones paso a paso para invocar la **ProcessPurchaseOrder**  directiva desde una orquestación.</span><span class="sxs-lookup"><span data-stu-id="098cc-278">Now that you have completed this walkthrough, perform the [Walkthrough: Invoking the Policy from an Orchestration](../core/walkthrough-invoking-the-policy-from-an-orchestration.md) walkthrough, which gives you step-by-step instructions for invoking the **ProcessPurchaseOrder** policy from an orchestration.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="098cc-279">Vea también</span><span class="sxs-lookup"><span data-stu-id="098cc-279">See Also</span></span>  
 <span data-ttu-id="098cc-280">[Resultado de seguimiento de pruebas de directivas](../core/policy-test-trace-output.md) </span><span class="sxs-lookup"><span data-stu-id="098cc-280">[Policy Test Trace Output](../core/policy-test-trace-output.md) </span></span>  
 <span data-ttu-id="098cc-281">[Evaluación de condiciones y ejecución de acciones](../core/condition-evaluation-and-action-execution.md) </span><span class="sxs-lookup"><span data-stu-id="098cc-281">[Condition Evaluation and Action Execution](../core/condition-evaluation-and-action-execution.md) </span></span>  
 [<span data-ttu-id="098cc-282">Agenda y prioridad</span><span class="sxs-lookup"><span data-stu-id="098cc-282">Agenda and Priority</span></span>](../core/agenda-and-priority.md)