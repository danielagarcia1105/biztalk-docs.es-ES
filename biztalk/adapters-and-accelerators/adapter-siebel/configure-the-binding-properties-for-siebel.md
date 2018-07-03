---
title: Configurar las propiedades de enlace de Siebel | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at design time
- binding properties, specifying at run time
- how to, specify binding properties at design time
- how to, specify binding properties at run time
ms.assetid: 063e9507-8172-4fb0-8b9f-2f95e8a82f21
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e09f3ce0f5e21c6ac1df6bb7c361674629fa4d36
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992373"
---
# <a name="configure-the-binding-properties-for-siebel"></a><span data-ttu-id="320bc-102">Configurar las propiedades de enlace de Siebel</span><span class="sxs-lookup"><span data-stu-id="320bc-102">Configure the binding properties for Siebel</span></span>
<span data-ttu-id="320bc-103">La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expone varias propiedades de enlace que le permiten controlar algunos de sus características de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="320bc-103">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="320bc-104">Esta sección proporciona información acerca de cómo establecer las propiedades de enlace de Visual Studio (tiempo de diseño) y de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración (tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="320bc-104">This section provides information about setting the binding properties from Visual Studio (design time) and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console (run time).</span></span> <span data-ttu-id="320bc-105">En tiempo de diseño, debe especificar las propiedades de enlace para generar esquemas para operaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="320bc-105">At design time, you must specify the binding properties to generate schema for specific operations.</span></span> <span data-ttu-id="320bc-106">En tiempo de ejecución, debe especificar las propiedades de enlace como parte del puerto de envío para enviar mensajes al sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="320bc-106">At run time, you must specify the binding properties as part of the send port for sending messages to the Siebel system.</span></span>  

 <span data-ttu-id="320bc-107">Para obtener información acerca de las propiedades de enlace, incluida una lista de propiedades de enlace [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="320bc-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

## <a name="enter-the-binding-properties-at-design-time"></a><span data-ttu-id="320bc-108">Escriba las propiedades de enlace en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="320bc-108">Enter the binding properties at design time</span></span>  
 <span data-ttu-id="320bc-109">Para el tiempo de diseño, debe especificar las propiedades de enlace desde el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="320bc-109">For design time, you must specify the binding properties from the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] dialog box.</span></span>  

#### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="320bc-110">Escribir propiedades de enlace mediante el complemento Consume Adapter Service</span><span class="sxs-lookup"><span data-stu-id="320bc-110">Enter binding properties using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="320bc-111">Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="320bc-111">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="320bc-112">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="320bc-112">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="320bc-113">Use</span><span class="sxs-lookup"><span data-stu-id="320bc-113">Use this</span></span>|<span data-ttu-id="320bc-114">Para</span><span class="sxs-lookup"><span data-stu-id="320bc-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="320bc-115">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="320bc-115">**Categories**</span></span>|<span data-ttu-id="320bc-116">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="320bc-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="320bc-117">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="320bc-117">**Templates**</span></span>|<span data-ttu-id="320bc-118">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="320bc-118">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="320bc-119">Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="320bc-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="320bc-120">En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **siebelBinding**y haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="320bc-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  

5.  <span data-ttu-id="320bc-121">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** pestaña y especificar los valores de enlace, si existe, que deben especificarse antes de generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="320bc-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="320bc-122">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="320bc-122">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

6.  <span data-ttu-id="320bc-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="320bc-123">Click **OK**.</span></span>  

#### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="320bc-124">Escribir propiedades de enlace mediante el Asistente para agregar metadatos de adaptador</span><span class="sxs-lookup"><span data-stu-id="320bc-124">Enter binding properties using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="320bc-125">Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="320bc-125">Right-click your BizTalk project, point to **Add**, and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="320bc-126">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="320bc-126">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="320bc-127">Use</span><span class="sxs-lookup"><span data-stu-id="320bc-127">Use this</span></span>    |           <span data-ttu-id="320bc-128">Para</span><span class="sxs-lookup"><span data-stu-id="320bc-128">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="320bc-129">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="320bc-129">**Categories**</span></span> |     <span data-ttu-id="320bc-130">Haga clic en **agregar adaptador**.</span><span class="sxs-lookup"><span data-stu-id="320bc-130">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="320bc-131">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="320bc-131">**Templates**</span></span>  | <span data-ttu-id="320bc-132">Haga clic en **agregar metadatos de adaptador**.</span><span class="sxs-lookup"><span data-stu-id="320bc-132">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="320bc-133">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="320bc-133">Click **Add**.</span></span> <span data-ttu-id="320bc-134">Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="320bc-134">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="320bc-135">En el Asistente para agregar adaptador, seleccione **WCF-Siebel**.</span><span class="sxs-lookup"><span data-stu-id="320bc-135">In the Add Adapter Wizard, select **WCF-Siebel**.</span></span> <span data-ttu-id="320bc-136">Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="320bc-136">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="320bc-137">Si ya tiene un puerto de WCF-Siebel configurado en BizTalk, seleccione el puerto desde el **puerto** lista.</span><span class="sxs-lookup"><span data-stu-id="320bc-137">If you already have a WCF-Siebel port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="320bc-138">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="320bc-138">Click **Next**.</span></span>  

6. <span data-ttu-id="320bc-139">En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **siebelBinding**y haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="320bc-139">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **siebelBinding**, and click **Configure**.</span></span>  

7. <span data-ttu-id="320bc-140">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** pestaña y especificar los valores de enlace, si existe, que deben especificarse antes de generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="320bc-140">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="320bc-141">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="320bc-141">For more information about binding properties, see [Read about BizTalk Adapter for Siebel Binding Properties](../../adapters-and-accelerators/adapter-siebel/read-about-biztalk-adapter-for-siebel-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="320bc-142">Si ha seleccionado un puerto de envío WCF-Siebel existente, no necesita especificar las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="320bc-142">If you selected an existing WCF-Siebel send port, you need not specify the binding properties.</span></span> <span data-ttu-id="320bc-143">Se seleccionan las propiedades de enlace de la configuración de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="320bc-143">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="320bc-144">Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si existe.</span><span class="sxs-lookup"><span data-stu-id="320bc-144">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="320bc-145">En este caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="320bc-145">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="320bc-146">Sin embargo, en tiempo de ejecución los valores especificados para las propiedades de enlace en la configuración del puerto de envío será aplicable.</span><span class="sxs-lookup"><span data-stu-id="320bc-146">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

8. <span data-ttu-id="320bc-147">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="320bc-147">Click **OK**.</span></span>  

## <a name="enter-binding-properties-at-run-time"></a><span data-ttu-id="320bc-148">Escribir propiedades de enlace en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="320bc-148">Enter binding properties at run time</span></span>  
 <span data-ttu-id="320bc-149">Para el tiempo de ejecución, debe especificar las propiedades de enlace como parte de la WCF-Custom o la configuración del puerto de WCF-Siebel en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="320bc-149">For run time, you must specify the binding properties as part of the WCF-Custom or the WCF-Siebel port configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

#### <a name="enter-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="320bc-150">Especifique las propiedades de enlace para el puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="320bc-150">Enter binding properties for the WCF-Custom port</span></span>  

1. <span data-ttu-id="320bc-151">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="320bc-151">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="320bc-152">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío** .</span><span class="sxs-lookup"><span data-stu-id="320bc-152">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="320bc-153">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="320bc-153">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="320bc-154">En el **propiedades de puerto** cuadro de diálogo desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="320bc-154">In the **Port Properties** dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

4. <span data-ttu-id="320bc-155">En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="320bc-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  

5. <span data-ttu-id="320bc-156">Desde el **BindingType** lista desplegable, seleccione **siebelBinding**.</span><span class="sxs-lookup"><span data-stu-id="320bc-156">From the **Binding Type** drop-down list, select **siebelBinding**.</span></span>  

6. <span data-ttu-id="320bc-157">En el **configuración** , especifique los valores de las propiedades de enlace diferente y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="320bc-157">In the **Configuration** box, specify the values for the different binding properties and click **OK**.</span></span>  

#### <a name="enter-binding-properties-for-the-wcf-siebel-port"></a><span data-ttu-id="320bc-158">Especifique las propiedades de enlace para el puerto de WCF-Siebel</span><span class="sxs-lookup"><span data-stu-id="320bc-158">Enter binding properties for the WCF-Siebel port</span></span>  

1. <span data-ttu-id="320bc-159">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="320bc-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="320bc-160">Agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="320bc-160">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="320bc-161">Para obtener instrucciones, consulte [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="320bc-161">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="320bc-162">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y, a continuación, haga clic en **puertos de envío** .</span><span class="sxs-lookup"><span data-stu-id="320bc-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="320bc-163">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="320bc-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="320bc-164">En el **propiedades de puerto** cuadro de diálogo desde el **tipo** la lista desplegable, seleccione el puerto de WCF-Siebel que agregó anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="320bc-164">In the **Port Properties** dialog box, from the **Type** drop-down list, select the WCF-Siebel port you added earlier, and then click **Configure**.</span></span>  

5. <span data-ttu-id="320bc-165">En el cuadro de diálogo Propiedades de transporte, haga clic en el **enlace** pestaña y especificar los valores de las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="320bc-165">In the transport properties dialog box, click the **Binding** tab and specify values for the binding properties.</span></span>  

6. <span data-ttu-id="320bc-166">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="320bc-166">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="320bc-167">Vea también</span><span class="sxs-lookup"><span data-stu-id="320bc-167">See Also</span></span>  
[<span data-ttu-id="320bc-168">Bloques de creación para crear aplicaciones de BizTalk con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="320bc-168">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)