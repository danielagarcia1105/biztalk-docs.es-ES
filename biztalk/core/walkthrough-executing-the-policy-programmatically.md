---
title: "Tutorial: Ejecutar la directiva mediante programación | Documentos de Microsoft"
ms.custom: 
ms.date: 2016-04-05
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6398e7af-2ed1-4596-879c-3b7d000b8de2
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5afbe8bd29f18e71999ff32e0a1100de8a65fcc4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="walkthrough-executing-the-policy-programmatically"></a><span data-ttu-id="a0d0a-102">Tutorial: Ejecutar la directiva mediante programación</span><span class="sxs-lookup"><span data-stu-id="a0d0a-102">Walkthrough: Executing the Policy Programmatically</span></span>
<span data-ttu-id="a0d0a-103">Este tutorial proporciona procedimientos paso a paso para invocar la directiva creada en el [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial desde una aplicación de consola mediante programación.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-103">This walkthrough provides step-by-step procedures for invoking the policy you created in the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough from a console application programmatically.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a0d0a-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a0d0a-104">Prerequisites</span></span>  
 <span data-ttu-id="a0d0a-105">Debe completar la [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial antes de realizar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before you perform this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="a0d0a-106">Información general de este tutorial</span><span class="sxs-lookup"><span data-stu-id="a0d0a-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="a0d0a-107">Este tutorial contiene dos procedimientos, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-107">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="a0d0a-108">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="a0d0a-108">Procedure title</span></span>|<span data-ttu-id="a0d0a-109">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="a0d0a-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="a0d0a-110">Para invocar una directiva ProcessPurchaseOrder mediante el método Policy.Execute</span><span class="sxs-lookup"><span data-stu-id="a0d0a-110">To invoke the ProcessPurchaseOrder policy by using the Policy.Execute method</span></span>|<span data-ttu-id="a0d0a-111">Proporciona instrucciones paso a paso para invocar una directiva mediante la **Policy.Execute** método.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-111">Provides step-by-step instructions for invoking a policy by using the **Policy.Execute** method.</span></span>|  
|<span data-ttu-id="a0d0a-112">Para invocar una directiva ProcessPurchaseOrder mediante el método RuleEngine.Execute</span><span class="sxs-lookup"><span data-stu-id="a0d0a-112">To invoke the ProcessPurchaseOrder policy by using the RuleEngine.Execute method</span></span>|<span data-ttu-id="a0d0a-113">Proporciona instrucciones paso a paso para invocar una directiva mediante la **RuleEngine.Execute** método.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-113">Provides step-by-step instructions for invoking a policy by using the **RuleEngine.Execute** method.</span></span>|  
  
### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-policyexecute-method"></a><span data-ttu-id="a0d0a-114">Para invocar una directiva ProcessPurchaseOrder mediante el método Policy.Execute</span><span class="sxs-lookup"><span data-stu-id="a0d0a-114">To invoke the ProcessPurchaseOrder policy by using the Policy.Execute method</span></span>  
  
1.  <span data-ttu-id="a0d0a-115">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-115">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="a0d0a-116">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-116">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="a0d0a-117">En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-117">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a0d0a-118">Use</span><span class="sxs-lookup"><span data-stu-id="a0d0a-118">Use this</span></span>|<span data-ttu-id="a0d0a-119">Para</span><span class="sxs-lookup"><span data-stu-id="a0d0a-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a0d0a-120">**Tipos de proyecto**</span><span class="sxs-lookup"><span data-stu-id="a0d0a-120">**Project types**</span></span>|<span data-ttu-id="a0d0a-121">Haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-121">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="a0d0a-122">**Plantillas**</span><span class="sxs-lookup"><span data-stu-id="a0d0a-122">**Templates**</span></span>|<span data-ttu-id="a0d0a-123">Haga clic en **aplicación de consola**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-123">Click **Console Application**.</span></span>|  
    |<span data-ttu-id="a0d0a-124">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a0d0a-124">**Name**</span></span>|<span data-ttu-id="a0d0a-125">Tipo de **ConsoleClient**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-125">Type **ConsoleClient**.</span></span>|  
    |<span data-ttu-id="a0d0a-126">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="a0d0a-126">**Location**</span></span>|<span data-ttu-id="a0d0a-127">Especifique una carpeta en la que desea guardar los archivos del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-127">Specify a folder where you want to save the project files.</span></span>|  
    |<span data-ttu-id="a0d0a-128">**Nombre de solución**</span><span class="sxs-lookup"><span data-stu-id="a0d0a-128">**Solution Name**</span></span>|<span data-ttu-id="a0d0a-129">Tipo de **ConsoleClientSol**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-129">Type **ConsoleClientSol**.</span></span>|  
    |<span data-ttu-id="a0d0a-130">**Crear directorio para la solución**</span><span class="sxs-lookup"><span data-stu-id="a0d0a-130">**Create directory for solution**</span></span>|<span data-ttu-id="a0d0a-131">Seleccione esta casilla para crear un directorio para los archivos de la solución.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-131">Select this check box to create a directory for the solution files.</span></span>|  
  
4.  <span data-ttu-id="a0d0a-132">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-132">Click **OK**.</span></span> <span data-ttu-id="a0d0a-133">El **ConsoleClient** proyecto debe aparecer en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-133">The **ConsoleClient** project should appear in Solution Explorer.</span></span> <span data-ttu-id="a0d0a-134">Si no ve el Explorador de soluciones, haga clic en **el Explorador de soluciones** en el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-134">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="a0d0a-135">En el Explorador de soluciones, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-135">In Solution Explorer, right-click **References**, and then click **Add Reference**.</span></span>  
  
6.  <span data-ttu-id="a0d0a-136">Haga clic en **examinar**, vaya a la **\Program Files\Common Files\Microsoft BizTalk**y, a continuación, haga doble clic en **Microsoft.RuleEngine.dll**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-136">Click **Browse**, browse to the **\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.RuleEngine.dll**.</span></span>  
  
7.  <span data-ttu-id="a0d0a-137">Agregue las líneas siguientes a la parte superior de la **Program.cs** archivo después de las existentes `using` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-137">Add the following lines to the top of the **Program.cs** file after the existing `using` statements:</span></span>  
  
    ```  
    //To use the XmlDocument class  
    using System.Xml;  
    //To use the TypedXmlDocument and Policy classes  
    using Microsoft.RuleEngine;   
    ```  
  
8.  <span data-ttu-id="a0d0a-138">Agregue el código siguiente a la **Main** función para crear un **TypedXmlDocument** objeto basado en el documento XML:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-138">Add the following code to the **Main** function to create a **TypedXmlDocument** object based on the XML document:</span></span>  
  
    ```  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    //Change the directory as needed  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    ```  
  
9. <span data-ttu-id="a0d0a-139">Agregue el código siguiente a la **Main** función que se ejecuta la directiva:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-139">Add the following code to the **Main** function to execute the policy:</span></span>  
  
    ```  
    //Create a policy object based on the name, ProcessPurchaseOrder  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    //Execute the policy by invoking Policy.Execute method and   
    //by passing the typed xml document as a fact.   
    policy.Execute(txd);   
    ```  
  
10. <span data-ttu-id="a0d0a-140">Imprimir la salida XML para confirmar que el valor de la **estado** campo está establecido en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-140">Print the output XML to confirm that the value of the **Status** field is set to **Approved**.</span></span> <span data-ttu-id="a0d0a-141">Tenga en cuenta que a diferencia del compositor de reglas de negocios, invocar el **Policy.Execute** método no cambia el documento original.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-141">Note that unlike the Business Rule Composer, invoking the **Policy.Execute** method does not change the original document.</span></span>  
  
    ```  
    //Print the output document  
    Console.WriteLine(txd.Document.OuterXml);   
    ```  
  
11. <span data-ttu-id="a0d0a-142">En el **generar** menú, haga clic en **generar ConsoleClient**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-142">On the **Build** menu, click **Build ConsoleClient**.</span></span>  
  
12. <span data-ttu-id="a0d0a-143">Presione CTRL+F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-143">Press CTRL+F5 to execute the application.</span></span> <span data-ttu-id="a0d0a-144">Confirme que el valor de la **estado** campo está establecido en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-144">Confirm that the value of the **Status** field is set to **Approved**.</span></span>  
  
### <a name="to-invoke-the-processpurchaseorder-policy-by-using-the-ruleengineexecute-method"></a><span data-ttu-id="a0d0a-145">Para invocar una directiva ProcessPurchaseOrder mediante el método RuleEngine.Execute</span><span class="sxs-lookup"><span data-stu-id="a0d0a-145">To invoke the ProcessPurchaseOrder policy by using the RuleEngine.Execute method</span></span>  
  
1.  <span data-ttu-id="a0d0a-146">En el Explorador de soluciones, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-146">In Solution Explorer, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="a0d0a-147">Haga clic en **examinar**, vaya a **\Program Files\Common Files\Microsoft BizTalk**y, a continuación, haga doble clic en **Microsoft.BizTalk.RuleEngineExtensions.dll**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-147">Click **Browse**, browse to **\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.BizTalk.RuleEngineExtensions.dll**.</span></span>  
  
3.  <span data-ttu-id="a0d0a-148">Comentario de las líneas siguientes en el **Program.cs** archivo:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-148">Comment out the following lines in the **Program.cs** file:</span></span>  
  
    ```  
    //Create a policy object based on the name, ProcessPurchaseOrder  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    //Execute the policy by invoking Policy.Execute method and   
    //by passing the typed xml document as a fact.   
    policy.Execute(txd);   
    ```  
  
4.  <span data-ttu-id="a0d0a-149">Agregue el código siguiente después del código marcado como comentario para obtener acceso a la base de datos del motor de reglas:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-149">Add the following code after the commented-out code to get access to the Rule Engine database:</span></span>  
  
    ```  
    //Get access to the SQL rule store   
    Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
    dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
    SqlRuleStore sqlRuleStore = (SqlRuleStore)dd.GetRuleStore();  
    ```  
  
5.  <span data-ttu-id="a0d0a-150">Agregue el código siguiente para obtener acceso a **RuleSetInfoCollection** de la directiva ProcessPurchaseOrder:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-150">Add the following code to get access to **RuleSetInfoCollection** for the ProcessPurchaseOrder policy:</span></span>  
  
    ```  
    //Get access to RuleSetInfoCollection for the   
    //ProcessPurchaseOrder policy  
    RuleSetInfoCollection rsic = sqlRuleStore.GetRuleSets("ProcessPurchaseOrder", RuleStore.Filter.All);  
    ```  
  
6.  <span data-ttu-id="a0d0a-151">Agregue el código siguiente para crear un **RuleSet** objeto basado en la información del conjunto de reglas de la directiva ProcessPurchaseOrder:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-151">Add the following code to create a **RuleSet** object based on the rule set information for the ProcessPurchaseOrder policy:</span></span>  
  
    ```  
    //Create a RuleSet object based on the rule set information   
    //for the ProcessPurchaseOrder policy  
    RuleSet rs = sqlRuleStore.GetRuleSet(rsic[0]);  
    ```  
  
7.  <span data-ttu-id="a0d0a-152">Agregue el código siguiente para crear el **RuleEngine** objeto:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-152">Add the following code to create the **RuleEngine** object:</span></span>  
  
    ```  
    //Create the RuleEngine object  
    Microsoft.RuleEngine.RuleEngine engine = new Microsoft.RuleEngine.RuleEngine(rs);  
    ```  
  
8.  <span data-ttu-id="a0d0a-153">Agregue el código siguiente para imponer la **TypedXmlDocument** objeto en la memoria de trabajo del motor de reglas:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-153">Add the following code to assert the **TypedXmlDocument** object into the working memory of the rule engine:</span></span>  
  
    ```  
    //Assert the TypedXmlDocument object into working memory  
    //of the rule engine  
    engine.Assert(txd);  
    ```  
  
9. <span data-ttu-id="a0d0a-154">Ahora agregue el código para ejecutar la directiva mediante la **RuleEngine.Execute** método:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-154">Now add the code to execute the policy by using the **RuleEngine.Execute** method:</span></span>  
  
    ```  
    //Execute the policy by invoking RuleEngine.Execute method  
    engine.Execute();  
    ```  
  
10. <span data-ttu-id="a0d0a-155">Asegúrese de que el **Console.WriteLine** instrucción es la última instrucción en el **Main** función.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-155">Make sure that the **Console.WriteLine** statement is the last statement in the **Main** function.</span></span>  
  
11. <span data-ttu-id="a0d0a-156">En el **generar** menú, haga clic en **generar ConsoleClient**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-156">On the **Build** menu, click **Build ConsoleClient**.</span></span>  
  
12. <span data-ttu-id="a0d0a-157">Presione CTRL+F5 para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-157">Press CTRL+F5 to execute the application.</span></span> <span data-ttu-id="a0d0a-158">Confirme que el valor de la **estado** campo está establecido en **aprobado**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-158">Confirm that the value of the **Status** field is set to **Approved**.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="a0d0a-159">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a0d0a-159">Comments</span></span>  
  
-   <span data-ttu-id="a0d0a-160">Complete el código para el **Main** función que se ejecuta la directiva ProcessPurchaseOrder mediante el uso de la **Policy.Execute** método es como sigue:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-160">Complete code for the **Main** function to execute the ProcessPurchaseOrder policy by using the **Policy.Execute** method is as follows:</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
    XmlDocument doc = new XmlDocument();  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    Policy policy = new Policy("ProcessPurchaseOrder");  
    policy.Execute(txd);  
    Console.WriteLine(txd.Document.OuterXml);   
    }  
    ```  
  
-   <span data-ttu-id="a0d0a-161">Completar código para ejecutar la directiva ProcessPurchaseOrder mediante el uso de la **RuleEngine.Execute** método es como sigue:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-161">Complete code for executing the ProcessPurchaseOrder policy by using the **RuleEngine.Execute** method is as follows:</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
    XmlDocument doc = new XmlDocument();  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver dd;  
    dd = new Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver();  
    SqlRuleStore sqlRuleStore = (SqlRuleStore)dd.GetRuleStore();  
    RuleSetInfoCollection rsic = sqlRuleStore.GetRuleSets("ProcessPurchaseOrder", RuleStore.Filter.All);  
    RuleSet rs = sqlRuleStore.GetRuleSet(rsic[0]);  
    Microsoft.RuleEngine.RuleEngine engine = new Microsoft.RuleEngine.RuleEngine(rs);  
    engine.Assert(txd);  
    engine.Execute();  
    Console.WriteLine(txd.Document.OuterXml);   
    }  
    ```  
  
-   <span data-ttu-id="a0d0a-162">Puede que desee agregar un **Console.ReadLine ()** instrucción al final de la **Main** función para que la aplicación espera a que termine la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-162">You may want to add a **Console.ReadLine()** statement at the end of the **Main** function so that the application waits for you to terminate the application.</span></span>  
  
-   <span data-ttu-id="a0d0a-163">En este tutorial, el cliente envía sólo un hecho a la directiva ProcessPurchaseOrder.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-163">In this walkthrough, the client submits only one fact to the ProcessPurchaseOrder policy.</span></span> <span data-ttu-id="a0d0a-164">Si el cliente necesita enviar más de un hecho a la directiva, debe crear una matriz de hechos y usar sobrecargado **Execute** método que toma una matriz como parámetro.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-164">If the client needs to submit more than one fact to a policy, it needs to create an array of facts and use the overloaded **Execute** method that takes an array as a parameter.</span></span> <span data-ttu-id="a0d0a-165">El siguiente código de ejemplo muestra cómo hacerlo:</span><span class="sxs-lookup"><span data-stu-id="a0d0a-165">The following sample code shows how to do that:</span></span>  
  
    ```  
    Policy policy = new Policy("PolicyName");  
    object[] facts = new object[2];  
    facts[0] = txd;  
    facts[1] = new MyClass();  
    policy.Execute(facts);  
    policy.Dispose();  
    ```  
  
-   <span data-ttu-id="a0d0a-166">El primer parámetro a la **TypedXmlDocument** constructor en el código es el nombre del tipo utilizado para crear la directiva.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-166">The first parameter to the **TypedXmlDocument** constructor in the code is the name of the type you used to build the policy.</span></span>  
  
-   <span data-ttu-id="a0d0a-167">El **Policy.Execute** método es básicamente un contenedor alrededor de la **RuleEngine.Execute** método.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-167">The **Policy.Execute** method is basically a wrapper around the **RuleEngine.Execute** method.</span></span> <span data-ttu-id="a0d0a-168">Por tanto, se usan los **Policy.Execute** método es la manera más fácil de invocar una directiva, como se ha visto en este tutorial.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-168">Therefore, using the **Policy.Execute** method is the easiest way of invoking a policy, as you have seen in this walkthrough.</span></span>  
  
-   <span data-ttu-id="a0d0a-169">Para tener más control sobre la ejecución de la directiva, puede utilizar el **RuleEngine.Execute** método en lugar de usar **Policy.Execute**.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-169">For more control over the execution of the policy, you may want to use the **RuleEngine.Execute** method instead of using **Policy.Execute**.</span></span> <span data-ttu-id="a0d0a-170">Por ejemplo, puede detener el motor temporalmente mediante el uso de la **detener** función y, a continuación, reanudar utilizando la **Execute** función.</span><span class="sxs-lookup"><span data-stu-id="a0d0a-170">For example, you can halt the engine temporarily by using the **Halt** function, and then resume it by using the **Execute** function.</span></span> <span data-ttu-id="a0d0a-171">Para obtener más información, consulte [detener](../core/halt.md).</span><span class="sxs-lookup"><span data-stu-id="a0d0a-171">For more information, see [Halt](../core/halt.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0d0a-172">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0d0a-172">See Also</span></span>  
 [<span data-ttu-id="a0d0a-173">Cómo ejecutar directivas</span><span class="sxs-lookup"><span data-stu-id="a0d0a-173">How to Execute Policies</span></span>](../core/how-to-execute-policies.md)