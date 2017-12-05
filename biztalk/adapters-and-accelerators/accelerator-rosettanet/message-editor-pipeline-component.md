---
title: "Componente de canalización del Editor de mensajes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, Message Editor Pipeline Component
- Message Editor Pipeline Component
- messages, editing
- pipelines, Message Editor Pipeline Component
ms.assetid: f2b22dea-54e8-410b-868f-2978139f438b
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f5877fe04a87a8387340c8e4b004300f41e609e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="message-editor-pipeline-component"></a><span data-ttu-id="f42bf-102">Componente de canalización del editor de mensajes</span><span class="sxs-lookup"><span data-stu-id="f42bf-102">Message Editor Pipeline Component</span></span>
<span data-ttu-id="f42bf-103">Este componente permite editar automáticamente cualquier parte de un mensaje de varias partes dentro de una canalización de envío o recepción.</span><span class="sxs-lookup"><span data-stu-id="f42bf-103">This component lets you edit automatically any part of a multipart message within a send or receive pipeline.</span></span> <span data-ttu-id="f42bf-104">Este componente se agrega a una canalización existente para configurar el reemplazo como parte del procesamiento normal.</span><span class="sxs-lookup"><span data-stu-id="f42bf-104">You add this component to an existing pipeline to set up the replacement as part of typical processing.</span></span>  
  
## <a name="building-the-message-editor-pipeline-component-into-an-existing-pipeline"></a><span data-ttu-id="f42bf-105">Crear el componente de canalización del editor de mensajes en una canalización existente</span><span class="sxs-lookup"><span data-stu-id="f42bf-105">Building the Message Editor Pipeline Component into an Existing Pipeline</span></span>  
 <span data-ttu-id="f42bf-106">Para usar el componente de canalización del editor de mensajes, debe agregar el componente a una canalización existente.</span><span class="sxs-lookup"><span data-stu-id="f42bf-106">To use the Message Editor Pipeline Component, you have to add the component to an existing pipeline.</span></span> <span data-ttu-id="f42bf-107">Para obtener más información, vea "Crear canalizaciones con Diseñador de canalizaciones" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="f42bf-107">For more information, see "Creating Pipelines with Pipeline Designer" in BizTalk Server Help.</span></span>  
  
#### <a name="to-add-the-message-editor-pipeline-component-to-an-existing-pipeline"></a><span data-ttu-id="f42bf-108">Para agregar el componente de canalización del editor de mensajes en una canalización existente</span><span class="sxs-lookup"><span data-stu-id="f42bf-108">To add the Message Editor Pipeline Component to an existing pipeline</span></span>  
  
1.  <span data-ttu-id="f42bf-109">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f42bf-109">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="f42bf-110">En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-110">On the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
3.  <span data-ttu-id="f42bf-111">Vaya a C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component, seleccione **MessageEditor.csproj**y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-111">Move to C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component, select **MessageEditor.csproj**, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="f42bf-112">Inicie el símbolo del sistema de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="f42bf-112">Start Visual Studio command prompt.</span></span>  
  
5.  <span data-ttu-id="f42bf-113">En el símbolo del sistema, vaya a C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug.</span><span class="sxs-lookup"><span data-stu-id="f42bf-113">At the command prompt, move to C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug.</span></span>  
  
6.  <span data-ttu-id="f42bf-114">En el símbolo del sistema, escriba **sn -k MessageEditor.snk** para crear una clave y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="f42bf-114">At the command prompt, type **sn -k MessageEditor.snk** to create a key, and then press ENTER.</span></span>  
  
7.  <span data-ttu-id="f42bf-115">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el Explorador de soluciones, haga clic en **MessageEditor**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-115">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Solution Explorer, right-click **MessageEditor**, and then click **Properties**.</span></span>  
  
8.  <span data-ttu-id="f42bf-116">En la página **Propiedad de MessageEditor** , haga clic en la ficha **Firma** y, a continuación, haga clic en la casilla **Firmar el ensamblado** .</span><span class="sxs-lookup"><span data-stu-id="f42bf-116">In the **MessageEditor Property** page, click **Signing** tab, and then click **Sign the assembly** checkbox.</span></span>  
  
9. <span data-ttu-id="f42bf-117">En el menú desplegable **Elegir un archivo de clave de nombre seguro** , vaya a C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug, seleccione **MessageEditor.snk** y haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-117">In **Choose a strong name key file** drop-down, browse to C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\ SDK\Message Editor Pipeline Component\obj\debug and select **MessageEditor.snk** and then click **Open**.</span></span>  
  
10. <span data-ttu-id="f42bf-118">En el Explorador de soluciones, haga clic con el botón derecho en **MessageEditor**y, a continuación, haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-118">In Solution Explorer, right-click **MessageEditor**, and then click **Build**.</span></span> <span data-ttu-id="f42bf-119">En el panel de salida, compruebe que la compilación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f42bf-119">Verify in the Output pane that the build succeeded.</span></span>  
  
11. <span data-ttu-id="f42bf-120">Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Accesorios**y, a continuación, haga clic en **Explorador de Windows**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-120">Click **Start**, point to **All Programs**, point to **Accessories**, and then click **Windows Explorer**.</span></span>  
  
12. <span data-ttu-id="f42bf-121">En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] pulse el botón derecho en el explorador, vaya a C:\Program Files\Microsoft BizTalk 2013 Accelerator para RosettaNet\SDK\Message Editor Pipeline Component\obj\debug, **Microsoft.Solutions.BTARN.SDK.MessageEditor.dll**, y, a continuación, haga clic en **copia**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-121">In [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, move to C:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\Message Editor Pipeline Component\obj\debug, right-click **Microsoft.Solutions.BTARN.SDK.MessageEditor.dll**, and then click **Copy**.</span></span>  
  
13. <span data-ttu-id="f42bf-122">Vaya a C:\Program Files\Microsoft BizTalk Server 2013\Pipeline Components, haga clic con el botón derecho en **Componentes de canalización**y haga clic en **Pegar**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-122">Move to C:\Program Files\Microsoft BizTalk Server 2013\Pipeline Components, right-click **Pipeline Components**, and then click **Paste**.</span></span>  
  
14. <span data-ttu-id="f42bf-123">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **archivo** menú, elija **abiertos**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-123">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **File** menu, point to **Open**, and then click **Project**.</span></span>  
  
15. <span data-ttu-id="f42bf-124">Abra el proyecto que contiene la canalización a la que desea agregar el editor.</span><span class="sxs-lookup"><span data-stu-id="f42bf-124">Open the project that contains the pipeline to which you want to add the editor.</span></span>  
  
16. <span data-ttu-id="f42bf-125">En el Explorador de soluciones, haga doble clic en el nombre de la canalización para abrir la canalización en el Diseñador de canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="f42bf-125">In Solution Explorer, double-click the pipeline name to open the pipeline in Pipeline Designer.</span></span>  
  
17. <span data-ttu-id="f42bf-126">Haga clic con el botón derecho en el panel de componentes de canalización de BizTalk del panel Cuadro de herramientas y, a continuación, haga clic en **Agregar o quitar elementos**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-126">Right-click in the BizTalk Pipeline Components pane of the Toolbox pane, and then click **Add/Remove Items**.</span></span>  
  
18. <span data-ttu-id="f42bf-127">En el cuadro de diálogo **Personalizar cuadro de herramientas** de la pestaña **Componentes de canalización de BizTalk** , seleccione **Componente del editor de mensajes de BTARN**y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-127">In the **Customize Toolbox** dialog box, on the **BizTalk Pipeline Components** tab, select **BTARN Message Editor Component**, and then click **OK**.</span></span>  
  
19. <span data-ttu-id="f42bf-128">En el panel de componentes de canalización de BizTalk del panel Cuadro de herramientas, mantenga presionado **Componente del editor de mensajes de BTARN**y arrastre el componente a la posición que desee en la canalización.</span><span class="sxs-lookup"><span data-stu-id="f42bf-128">In the BizTalk Pipeline Components pane of the Toolbox pane, click and hold **BTARN Message Editor Component**, and then drag the component to the position that you want in the pipeline.</span></span>  
  
20. <span data-ttu-id="f42bf-129">En el panel de componentes de canalización de BizTalk del panel Cuadro de herramientas, mantenga presionado **Componente del editor de mensajes de BTARN**y arrastre el componente a la posición que desee en la canalización.</span><span class="sxs-lookup"><span data-stu-id="f42bf-129">In the BizTalk Pipeline Components pane of the Toolbox pane, click and hold **BTARN Message Editor Component**, and then drag the component to the position that you want in the pipeline.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f42bf-130">Se recomienda agregar el componente de canalización del editor de mensajes después de la fase de desensamblado del componente de canalización de recepción o en la fase de preensamblado del componente de canalización de envío.</span><span class="sxs-lookup"><span data-stu-id="f42bf-130">It is recommended that you add the Message Editor Pipeline Component after the Disassemble stage in the receive pipeline component or in the Pre-Assemble stage of the send pipeline component.</span></span>  
  
21. <span data-ttu-id="f42bf-131">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en el Diseñador de canalizaciones, seleccione la **componente Editor de mensajes de BTARN** forma.</span><span class="sxs-lookup"><span data-stu-id="f42bf-131">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], in Pipeline Designer, select the **BTARN Message Editor Component** shape.</span></span>  
  
22. <span data-ttu-id="f42bf-132">En el panel de propiedades, en el cuadro de texto asociado a **Consulta XPath**, escriba el nombre del elemento XPath para el que desea cambiar el valor.</span><span class="sxs-lookup"><span data-stu-id="f42bf-132">In the Properties pane, in the text box associated with **XPath Query**, type the name of the XPath element for which you want to change the value.</span></span>  
  
23. <span data-ttu-id="f42bf-133">En el cuadro de texto asociado a **Valor XPath**, escriba el valor en el que desea establecer el elemento XPath.</span><span class="sxs-lookup"><span data-stu-id="f42bf-133">In the text box associated with **XPath Value**, type the value to which you want to set the XPath element.</span></span>  
  
24. <span data-ttu-id="f42bf-134">En el Explorador de soluciones, haga clic con el botón derecho en el nombre del proyecto y, a continuación, haga clic en **Compilar**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-134">In Solutions Explorer, right-click the project name, and then click **Build**.</span></span> <span data-ttu-id="f42bf-135">Compruebe que la compilación se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="f42bf-135">Verify that the build succeeds.</span></span>  
  
25. <span data-ttu-id="f42bf-136">En el Explorador de soluciones, haga clic con el botón derecho en el nombre del proyecto y, a continuación, haga clic en **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="f42bf-136">In Solutions Explorer, right-click the project name, and then click **Deploy**.</span></span> <span data-ttu-id="f42bf-137">Compruebe que la implementación se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="f42bf-137">Verify that the deployment succeeds.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f42bf-138">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f42bf-138">Example</span></span>  
 <span data-ttu-id="f42bf-139">Para cambiar el valor del elemento `ProprietaryDocumentIdentifier` en el esquema de PIP 0C1, agregue la consulta XPath que se muestra en la sección de código siguiente a la propiedad de la consulta XPath del componente de canalización del editor de mensajes.</span><span class="sxs-lookup"><span data-stu-id="f42bf-139">To change the value of the element `ProprietaryDocumentIdentifier` in the 0C1 PIP Schema, add the XPath Query shown in the following Code section to the XPath Query property of the Message Editor Pipeline Component.</span></span>  
  
```  
/*[local-name()='Pip0C1AsynchronousTestNotification' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='thisDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']/*[local-name()='ProprietaryDocumentIdentifier' and namespace-uri()='http://schemas.microsoft.com/biztalk/btarn/2004/0C1_MS_R01_02_AsynchronousTestNotification.dtd']  
```  
  
 <span data-ttu-id="f42bf-140">Para obtener una consulta XPath completa, abra el esquema en el Editor de BizTalk y, a continuación, copie Xpath de la propiedad `Instance XPath` que aparece en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="f42bf-140">To obtain a complete XPath Query, open the schema in BizTalk Editor, and then copy the Xpath from the `Instance XPath` property under the Properties window.</span></span> <span data-ttu-id="f42bf-141">La consulta XPath que proporcione debe incluir todas las referencias de espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="f42bf-141">The XPath Query that you provide should have all the namespace references in it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f42bf-142">Vea también</span><span class="sxs-lookup"><span data-stu-id="f42bf-142">See Also</span></span>  
 [<span data-ttu-id="f42bf-143">Utilidades</span><span class="sxs-lookup"><span data-stu-id="f42bf-143">Utilities</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)