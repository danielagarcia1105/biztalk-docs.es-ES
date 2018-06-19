---
title: 'Tutorial: Crear un creador de hechos | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 041c8f73-c72e-43fd-8446-144cecdc95ef
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a1c91417cb58eb53e35c724513d4f955e4e6b6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290308"
---
# <a name="walkthrough-creating-a-fact-creator"></a><span data-ttu-id="a563d-102">Tutorial: Crear un creador de hechos</span><span class="sxs-lookup"><span data-stu-id="a563d-102">Walkthrough: Creating a Fact Creator</span></span>
<span data-ttu-id="a563d-103">Este tutorial proporciona procedimientos paso a paso para crear un componente de creador de hechos, **POFactCreator**, que puede utilizar para probar el **ProcessPurchaseOrder** directiva creada en versiones anteriores tutoriales.</span><span class="sxs-lookup"><span data-stu-id="a563d-103">This walkthrough provides step-by-step procedures for creating a fact creator component, **POFactCreator**, which you can use to test the **ProcessPurchaseOrder** policy you created in earlier walkthroughs.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a563d-104">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="a563d-104">Prerequisites</span></span>  
 <span data-ttu-id="a563d-105">Debe completar la [Tutorial: crear una directiva empresarial sencilla](../core/walkthrough-creating-a-simple-business-policy.md) tutorial antes de realizar este tutorial.</span><span class="sxs-lookup"><span data-stu-id="a563d-105">You must complete the [Walkthrough: Creating a Simple Business Policy](../core/walkthrough-creating-a-simple-business-policy.md) walkthrough before you perform this walkthrough.</span></span>  
  
## <a name="overview-of-this-walkthrough"></a><span data-ttu-id="a563d-106">Información general de este tutorial</span><span class="sxs-lookup"><span data-stu-id="a563d-106">Overview of This Walkthrough</span></span>  
 <span data-ttu-id="a563d-107">Este tutorial contiene dos procedimientos, tal y como se muestra en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="a563d-107">This walkthrough contains two procedures, as described in the following table.</span></span>  
  
|<span data-ttu-id="a563d-108">Título del procedimiento</span><span class="sxs-lookup"><span data-stu-id="a563d-108">Procedure title</span></span>|<span data-ttu-id="a563d-109">Descripción del procedimiento</span><span class="sxs-lookup"><span data-stu-id="a563d-109">Procedure description</span></span>|  
|---------------------|---------------------------|  
|<span data-ttu-id="a563d-110">Para crear el componente POFactCreator</span><span class="sxs-lookup"><span data-stu-id="a563d-110">To create the POFactCreator component</span></span>|<span data-ttu-id="a563d-111">Proporciona instrucciones paso a paso para crear un componente de creador de hechos, **POFactCreator**.</span><span class="sxs-lookup"><span data-stu-id="a563d-111">Provides step-by-step instructions for creating a fact creator component, **POFactCreator**.</span></span>|  
|<span data-ttu-id="a563d-112">Para probar la directiva ProcessPurchaseOrder mediante POFactCreator</span><span class="sxs-lookup"><span data-stu-id="a563d-112">To test the ProcessPurchaseOrder policy using POFactCreator</span></span>|<span data-ttu-id="a563d-113">Proporciona instrucciones paso a paso para usar la herramienta de Compositor de reglas de negocio para probar el **ProcessPurchaseOrder** directiva mediante el uso de la **POFactCreator** componente.</span><span class="sxs-lookup"><span data-stu-id="a563d-113">Provides step-by-step instructions for using the Business Rule Composer tool to test the **ProcessPurchaseOrder** policy by using the **POFactCreator** component.</span></span>|  
  
### <a name="to-create-the-pofactcreator-component"></a><span data-ttu-id="a563d-114">Para crear el componente POFactCreator</span><span class="sxs-lookup"><span data-stu-id="a563d-114">To create the POFactCreator component</span></span>  
  
1.  <span data-ttu-id="a563d-115">Iniciar **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="a563d-115">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="a563d-116">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="a563d-116">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="a563d-117">En el **nuevo proyecto** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a563d-117">In the **New Project** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a563d-118">Use</span><span class="sxs-lookup"><span data-stu-id="a563d-118">Use this</span></span>|<span data-ttu-id="a563d-119">Para</span><span class="sxs-lookup"><span data-stu-id="a563d-119">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a563d-120">**Tipos de proyecto**</span><span class="sxs-lookup"><span data-stu-id="a563d-120">**Project types**</span></span>|<span data-ttu-id="a563d-121">Haga clic en **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="a563d-121">Click **Visual C#**.</span></span>|  
    |<span data-ttu-id="a563d-122">**Plantillas**</span><span class="sxs-lookup"><span data-stu-id="a563d-122">**Templates**</span></span>|<span data-ttu-id="a563d-123">Haga clic en **biblioteca de clases**.</span><span class="sxs-lookup"><span data-stu-id="a563d-123">Click **Class Library**.</span></span>|  
    |<span data-ttu-id="a563d-124">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="a563d-124">**Name**</span></span>|<span data-ttu-id="a563d-125">Tipo de **POFactCreatorLib**.</span><span class="sxs-lookup"><span data-stu-id="a563d-125">Type **POFactCreatorLib**.</span></span>|  
    |<span data-ttu-id="a563d-126">**Ubicación**</span><span class="sxs-lookup"><span data-stu-id="a563d-126">**Location**</span></span>|<span data-ttu-id="a563d-127">Especifique **C:\BRE-Walkthroughs** como la ubicación.</span><span class="sxs-lookup"><span data-stu-id="a563d-127">Specify **C:\BRE-Walkthroughs** as the location.</span></span>|  
    |<span data-ttu-id="a563d-128">**Nombre de solución**</span><span class="sxs-lookup"><span data-stu-id="a563d-128">**Solution Name**</span></span>|<span data-ttu-id="a563d-129">Tipo de **POFactCreatorSol**.</span><span class="sxs-lookup"><span data-stu-id="a563d-129">Type **POFactCreatorSol**.</span></span>|  
    |<span data-ttu-id="a563d-130">**Crear directorio para la solución**</span><span class="sxs-lookup"><span data-stu-id="a563d-130">**Create directory for solution**</span></span>|<span data-ttu-id="a563d-131">Seleccione esta casilla para crear un directorio para los archivos de la solución.</span><span class="sxs-lookup"><span data-stu-id="a563d-131">Select this check box to create a directory for the solution files.</span></span>|  
  
4.  <span data-ttu-id="a563d-132">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a563d-132">Click **OK**.</span></span> <span data-ttu-id="a563d-133">El **POFactCreatorLib** proyecto debe aparecer en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="a563d-133">The **POFactCreatorLib** project should appear in Solution Explorer.</span></span> <span data-ttu-id="a563d-134">Si no ve el Explorador de soluciones, haga clic en **el Explorador de soluciones** en el **vista** menú.</span><span class="sxs-lookup"><span data-stu-id="a563d-134">If you do not see Solution Explorer, click **Solution Explorer** on the **View** menu.</span></span>  
  
5.  <span data-ttu-id="a563d-135">En la ventana Propiedades, cambie el nombre del archivo, **Class1.cs**a **POFactCreator.cs**.</span><span class="sxs-lookup"><span data-stu-id="a563d-135">In the Properties window, change the name of the file, **Class1.cs**, to **POFactCreator.cs**.</span></span>  
  
6.  <span data-ttu-id="a563d-136">En la ventana Explorador de soluciones, haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="a563d-136">In the Solution Explorer window, right-click **References**, and then click **Add Reference**.</span></span>  
  
7.  <span data-ttu-id="a563d-137">Haga clic en **examinar**, vaya a **C:\Program programa\Archivos comunes\Microsoft BizTalk**y, a continuación, haga doble clic en **Microsoft.RuleEngine.dll**.</span><span class="sxs-lookup"><span data-stu-id="a563d-137">Click **Browse**, navigate to **C:\Program Files\Common Files\Microsoft BizTalk**, and then double-click **Microsoft.RuleEngine.dll**.</span></span>  
  
8.  <span data-ttu-id="a563d-138">Agregue las líneas siguientes a la parte superior de la **POFactCreator.cs** archivo después de las existentes `using` instrucciones:</span><span class="sxs-lookup"><span data-stu-id="a563d-138">Add the following lines to the top of the **POFactCreator.cs** file after the existing `using` statements:</span></span>  
  
    ```  
    //To use the XmlDocument class  
    using System.Xml;  
    //To use the TypedXmlDocument and Policy classes  
    using Microsoft.RuleEngine;   
    ```  
  
9. <span data-ttu-id="a563d-139">Modificar el **POFactCreator** clase se deriva de la **IFactCreator** interfaz:</span><span class="sxs-lookup"><span data-stu-id="a563d-139">Modify the **POFactCreator** class to derive from the **IFactCreator** interface:</span></span>  
  
    ```  
    public class POFactCreator : IFactCreator  
    {  
    }  
    ```  
  
10. <span data-ttu-id="a563d-140">Haga clic en **IFactCreator**, seleccione **Implementar interfaz**y, a continuación, haga clic en **Implementar interfaz**.</span><span class="sxs-lookup"><span data-stu-id="a563d-140">Right-click **IFactCreator**, point to **Implement Interface**, and then click **Implement Interface**.</span></span>  
  
     <span data-ttu-id="a563d-141">![BRE &#45; Tutorial &#45; ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")</span><span class="sxs-lookup"><span data-stu-id="a563d-141">![BRE&#45;Walkthrough&#45;ImplementInterface](../core/media/ca1ae06c-ad24-4eac-94c3-5a06ad0f7305.gif "ca1ae06c-ad24-4eac-94c3-5a06ad0f7305")</span></span>  
  
11. <span data-ttu-id="a563d-142">Agregue un constructor público para el **POFactCreator** clase tal y como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="a563d-142">Add a public constructor to the **POFactCreator** class as shown below:</span></span>  
  
    ```  
    public POFactCreator()  
    {  
    }  
    ```  
  
12. <span data-ttu-id="a563d-143">Quite la instrucción única en el **CreateFacts** método.</span><span class="sxs-lookup"><span data-stu-id="a563d-143">Remove the lone statement in the **CreateFacts** method.</span></span>  
  
13. <span data-ttu-id="a563d-144">Agregue el código siguiente a la **CreateFacts** método para crear un **TypedXmlDocument** objeto basado en la **SamplePO.xml** documento:</span><span class="sxs-lookup"><span data-stu-id="a563d-144">Add the following code to the **CreateFacts** method to create a **TypedXmlDocument** object based on the **SamplePO.xml** document:</span></span>  
  
    ```  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
    ```  
  
14. <span data-ttu-id="a563d-145">Agregue el código siguiente para crear una matriz de hechos con el **TypedXmlDocument** objeto como único hecho:</span><span class="sxs-lookup"><span data-stu-id="a563d-145">Add the following code to create an array of facts with the **TypedXmlDocument** object as the only fact:</span></span>  
  
    ```  
    object[] facts = new object[1];  
    facts[0] = txd;   
    ```  
  
15. <span data-ttu-id="a563d-146">Devuelve la matriz de hechos de la **CreateFacts** método:</span><span class="sxs-lookup"><span data-stu-id="a563d-146">Return the facts array from the **CreateFacts** method:</span></span>  
  
    ```  
    return facts;  
    ```  
  
16. <span data-ttu-id="a563d-147">Compruebe que el código completo en el **CreateFacts** método es similar al siguiente:</span><span class="sxs-lookup"><span data-stu-id="a563d-147">Verify that the complete code in the **CreateFacts** method looks like the following:</span></span>  
  
    ```  
    public object[] CreateFacts(RuleSetInfo ruleSetInfo)  
    {  
    XmlDocument doc = new XmlDocument();  
    //Loading the XML from SamplePO.xml file.  
    doc.Load(@"C:\BRE-Walkthroughs\SamplePO.xml");  
    TypedXmlDocument txd = new TypedXmlDocument("RuleTest.PO", doc);  
  
    object[] facts = new object[1];  
    facts[0] = txd;  
    return facts;  
    }  
    ```  
  
17. <span data-ttu-id="a563d-148">Quite la instrucción única en el **GetFactTypes** método.</span><span class="sxs-lookup"><span data-stu-id="a563d-148">Remove the lone statement in the **GetFactTypes** method.</span></span>  
  
18. <span data-ttu-id="a563d-149">Agregue el código siguiente a la **GetFactTypes** método para devolver una matriz de tipos que contiene el tipo de la **TypedXmlDocument** clase:</span><span class="sxs-lookup"><span data-stu-id="a563d-149">Add the following code to the **GetFactTypes** method to return an array of types containing the type of the **TypedXmlDocument** class:</span></span>  
  
    ```  
    Type[] t = new Type[1];  
    t[0] = typeof(TypedXmlDocument);  
    return t;  
    ```  
  
19. <span data-ttu-id="a563d-150">Iniciar **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="a563d-150">Start **Visual Studio Command Prompt**.</span></span>  
  
20. <span data-ttu-id="a563d-151">Cambie el directorio a **C:\BRE-Walkthroughs\POFactCreatorSol**y, a continuación, ejecute el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="a563d-151">Change the directory to **C:\BRE-Walkthroughs\POFactCreatorSol**, and then execute the following command:</span></span>  
  
     <span data-ttu-id="a563d-152">**Sn -k POFactCreator.snk**</span><span class="sxs-lookup"><span data-stu-id="a563d-152">**Sn -k POFactCreator.snk**</span></span>  
  
21. <span data-ttu-id="a563d-153">En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, expanda **propiedades**y, a continuación, haga doble clic en **AssemblyInfo.cs**.</span><span class="sxs-lookup"><span data-stu-id="a563d-153">In [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], in Solution Explorer, expand **Properties**, and then double-click **AssemblyInfo.cs**.</span></span>  
  
22. <span data-ttu-id="a563d-154">Agregue la instrucción siguiente a la **AssemblyInfo.cs** archivo al final:</span><span class="sxs-lookup"><span data-stu-id="a563d-154">Add the following statement to the **AssemblyInfo.cs** file at the end:</span></span>  
  
    ```  
    [assembly: AssemblyKeyFile(@"C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreator.snk")]  
    ```  
  
23. <span data-ttu-id="a563d-155">En la ventana Explorador de soluciones, haga clic en **POFactCreatorLib**y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="a563d-155">In the Solution Explorer window, right-click **POFactCreatorLib**, and then click **Build**.</span></span>  
  
24. <span data-ttu-id="a563d-156">En el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] símbolo del sistema, cambie al directorio **C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**y, a continuación, ejecute el siguiente comando para registrar el **POFactCreator** componente con la GAC (caché global de ensamblados).</span><span class="sxs-lookup"><span data-stu-id="a563d-156">At the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Command Prompt, change the directory to **C:\BRE-Walkthroughs\POFactCreatorSol\POFactCreatorLib\Bin\Debug**, and then execute the following command to register the **POFactCreator** component with the GAC (global assembly cache).</span></span> <span data-ttu-id="a563d-157">Si no tiene el símbolo del sistema abierto, siga el paso 19 para abrirlo.</span><span class="sxs-lookup"><span data-stu-id="a563d-157">If you do not have the command prompt open, follow step 19 to open it.</span></span>  
  
     <span data-ttu-id="a563d-158">**Gacutil -i POFactCreatorLib.dll**</span><span class="sxs-lookup"><span data-stu-id="a563d-158">**Gacutil -i POFactCreatorLib.dll**</span></span>  
  
### <a name="to-test-the-processpurchaseorder-policy-using-pofactcreator"></a><span data-ttu-id="a563d-159">Para probar la directiva ProcessPurchaseOrder mediante POFactCreator</span><span class="sxs-lookup"><span data-stu-id="a563d-159">To test the ProcessPurchaseOrder policy using POFactCreator</span></span>  
  
1.  <span data-ttu-id="a563d-160">En el **iniciar** menú, elija **todos los programas**, seleccione [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="a563d-160">On the **Start** menu, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rule Composer**.</span></span> <span data-ttu-id="a563d-161">Si el Compositor de reglas de negocio ya está abierto, presione F5 para actualizarlo.</span><span class="sxs-lookup"><span data-stu-id="a563d-161">If you have the Business Rule Composer already open, press F5 to refresh it.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a563d-162">En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.</span><span class="sxs-lookup"><span data-stu-id="a563d-162">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="a563d-163">Para ello, haga clic en la aplicación y, a continuación, seleccione **ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="a563d-163">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="a563d-164">En la ventana Explorador de directivas, expanda **directivas**, expanda **ProcessPurchaseOrder**, haga clic en la versión más reciente y, a continuación, haga clic en **probar directiva**.</span><span class="sxs-lookup"><span data-stu-id="a563d-164">In the Policy Explorer window, expand **Policies**, expand **ProcessPurchaseOrder**, right-click the latest version, and then click **Test Policy**.</span></span>  
  
     <span data-ttu-id="a563d-165">![Compositor de reglas de negocios &#45; TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")</span><span class="sxs-lookup"><span data-stu-id="a563d-165">![Business Rule Composer&#45;TestPolicyMenu](../core/media/af63c437-aeba-4e6a-a772-3346e7babee5.gif "af63c437-aeba-4e6a-a772-3346e7babee5")</span></span>  
  
3.  <span data-ttu-id="a563d-166">En la parte inferior del cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="a563d-166">At the bottom of the dialog box, click **Add**.</span></span>  
  
4.  <span data-ttu-id="a563d-167">En el **ensamblados .NET** cuadro de diálogo, seleccione **POFactCreatorLib**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a563d-167">In the **.NET Assemblies** dialog box, select **POFactCreatorLib**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="a563d-168">En el **Seleccionar enlace** cuadro de diálogo, haga clic en **POFactCreator** en **POFactCreatorLib, 10.0.0**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="a563d-168">In the **Select Binding** dialog box, click **POFactCreator** in **POFactCreatorLib, 10.0.0**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="a563d-169">Haga clic en **prueba**.</span><span class="sxs-lookup"><span data-stu-id="a563d-169">Click **Test**.</span></span>  
  
7.  <span data-ttu-id="a563d-170">Compruebe que la **ApprovalRule** se activa en la ventana de salida.</span><span class="sxs-lookup"><span data-stu-id="a563d-170">Verify that the **ApprovalRule** is fired in the Output window.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="a563d-171">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a563d-171">Comments</span></span>  
  
-   <span data-ttu-id="a563d-172">Para probar una directiva que utiliza métodos no estáticos de una clase .NET mediante el Compositor de reglas de negocio, es preciso crear un componente de creador de hechos.</span><span class="sxs-lookup"><span data-stu-id="a563d-172">To test a policy that uses non-static methods of a .NET class by using the Business Rule Composer, you must create a fact creator component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a563d-173">Vea también</span><span class="sxs-lookup"><span data-stu-id="a563d-173">See Also</span></span>  
 [<span data-ttu-id="a563d-174">Cómo crear un administrador de almacenes</span><span class="sxs-lookup"><span data-stu-id="a563d-174">How to Create a Fact Retriever</span></span>](../core/how-to-create-a-fact-retriever.md)