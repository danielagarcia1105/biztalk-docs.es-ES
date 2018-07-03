---
title: Configurar las propiedades de enlace para el adaptador de SAP | Microsoft Docs
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
ms.assetid: 259a5895-c19d-409c-b2fc-bfdf59d5d74b
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ef599f91675d4604d9e9f56aafdef3677d2583a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001973"
---
# <a name="configure-the-binding-properties-for-the-sap-adapter"></a><span data-ttu-id="de46a-102">Configurar las propiedades de enlace para el adaptador de SAP</span><span class="sxs-lookup"><span data-stu-id="de46a-102">Configure the binding properties for the SAP adapter</span></span>
<span data-ttu-id="de46a-103">La [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expone varias propiedades de enlace que le permiten controlar algunos de sus características de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="de46a-103">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="de46a-104">Esta sección proporciona información acerca de cómo establecer las propiedades de enlace de Visual Studio (tiempo de diseño) y de la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración (tiempo de ejecución).</span><span class="sxs-lookup"><span data-stu-id="de46a-104">This section provides information about setting the binding properties from Visual Studio (design time) and from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console (run time).</span></span> <span data-ttu-id="de46a-105">En tiempo de diseño, debe especificar las propiedades de enlace para generar esquemas para operaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="de46a-105">At design time, you must specify the binding properties to generate schema for specific operations.</span></span> <span data-ttu-id="de46a-106">En tiempo de ejecución, debe especificar las propiedades de enlace como parte de envío o puerto de recepción para enviar o recibir mensajes desde el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="de46a-106">At run time, you must specify the binding properties as part of the send or receive port for sending or receiving messages from the SAP system.</span></span>  

 <span data-ttu-id="de46a-107">Para obtener información acerca de las propiedades de enlace, incluida una lista de propiedades de enlace [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="de46a-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  

## <a name="enter-binding-properties-at-design-time"></a><span data-ttu-id="de46a-108">Escribir propiedades de enlace en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="de46a-108">Enter Binding Properties at Design Time</span></span>  
 <span data-ttu-id="de46a-109">Para el tiempo de diseño, puede especificar las propiedades de enlace mediante la [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de46a-109">For design time, you can specify the binding properties using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

### <a name="enter-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="de46a-110">Escribir propiedades de enlace mediante el complemento Consume Adapter Service</span><span class="sxs-lookup"><span data-stu-id="de46a-110">Enter binding properties using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="de46a-111">Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="de46a-111">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="de46a-112">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="de46a-112">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="de46a-113">Use</span><span class="sxs-lookup"><span data-stu-id="de46a-113">Use this</span></span>|<span data-ttu-id="de46a-114">Para</span><span class="sxs-lookup"><span data-stu-id="de46a-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="de46a-115">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="de46a-115">**Categories**</span></span>|<span data-ttu-id="de46a-116">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="de46a-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="de46a-117">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="de46a-117">**Templates**</span></span>|<span data-ttu-id="de46a-118">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="de46a-118">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="de46a-119">Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="de46a-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="de46a-120">En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **sapBinding**y haga clic en **configurar** .</span><span class="sxs-lookup"><span data-stu-id="de46a-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  

5.  <span data-ttu-id="de46a-121">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** pestaña y, a continuación, especifique las propiedades de enlace diferente.</span><span class="sxs-lookup"><span data-stu-id="de46a-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and then specify the different binding properties.</span></span>  

6.  <span data-ttu-id="de46a-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="de46a-122">Click **OK**.</span></span>  

### <a name="enter-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="de46a-123">Escribir propiedades de enlace mediante el Asistente para agregar metadatos de adaptador</span><span class="sxs-lookup"><span data-stu-id="de46a-123">Enter binding properties using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="de46a-124">Haga clic en el proyecto de BizTalk, elija **agregar**y, a continuación, haga clic en **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="de46a-124">Right-click your BizTalk project, point to **Add**, and then click **Add Generated Items**.</span></span>  

2. <span data-ttu-id="de46a-125">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="de46a-125">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="de46a-126">Use</span><span class="sxs-lookup"><span data-stu-id="de46a-126">Use this</span></span>    |           <span data-ttu-id="de46a-127">Para</span><span class="sxs-lookup"><span data-stu-id="de46a-127">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="de46a-128">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="de46a-128">**Categories**</span></span> |     <span data-ttu-id="de46a-129">Haga clic en **agregar adaptador**.</span><span class="sxs-lookup"><span data-stu-id="de46a-129">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="de46a-130">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="de46a-130">**Templates**</span></span>  | <span data-ttu-id="de46a-131">Haga clic en **agregar metadatos de adaptador**.</span><span class="sxs-lookup"><span data-stu-id="de46a-131">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="de46a-132">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="de46a-132">Click **Add**.</span></span> <span data-ttu-id="de46a-133">Se abrirá [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="de46a-133">The [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] opens.</span></span>  

4. <span data-ttu-id="de46a-134">En el Asistente para agregar adaptador, seleccione **SAP de WCF**.</span><span class="sxs-lookup"><span data-stu-id="de46a-134">In the Add Adapter Wizard, select **WCF-SAP**.</span></span> <span data-ttu-id="de46a-135">Seleccione el equipo donde está instalado BizTalk Server y el nombre de la base de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="de46a-135">Select the computer on which BizTalk Server is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="de46a-136">Si ya tiene un puerto de SAP de WCF configurado en BizTalk, seleccione el puerto desde el **puerto** lista.</span><span class="sxs-lookup"><span data-stu-id="de46a-136">If you already have a WCF-SAP port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="de46a-137">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="de46a-137">Click **Next**.</span></span>  

6. <span data-ttu-id="de46a-138">En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **sapBinding**y haga clic en **configurar** .</span><span class="sxs-lookup"><span data-stu-id="de46a-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **sapBinding**, and click **Configure**.</span></span>  

7. <span data-ttu-id="de46a-139">Haga clic en el **propiedades de enlace** pestaña y especificar los valores de enlace, si existe, que deben especificarse antes de generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="de46a-139">Click the **Binding Properties** tab and specify the binding values, if any, which are required to be specified before generating the schema.</span></span> <span data-ttu-id="de46a-140">Por ejemplo, debe especificar un valor para el **GenerateFlatFileCompatibleIDoc** propiedad antes de generar el esquema para recibir IDOC desde un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="de46a-140">For example, you must specify a value for the **GenerateFlatFileCompatibleIDoc** property before generating schema for receiving IDOC from an SAP system.</span></span> <span data-ttu-id="de46a-141">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre el adaptador de BizTalk para las propiedades de enlace de mySAP Business Suite](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="de46a-141">For more information about binding properties, see [Read about BizTalk Adapter for mySAP Business Suite binding properties](../../adapters-and-accelerators/adapter-sap/read-about-biztalk-adapter-for-mysap-business-suite-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="de46a-142">Si ha seleccionado un puerto de envío WCF-SAP existente, no necesita especificar las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="de46a-142">If you selected an existing WCF-SAP send port, you need not specify the binding properties.</span></span> <span data-ttu-id="de46a-143">Se seleccionan las propiedades de enlace de la configuración de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="de46a-143">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="de46a-144">Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si existe.</span><span class="sxs-lookup"><span data-stu-id="de46a-144">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="de46a-145">En este caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="de46a-145">In such case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="de46a-146">Sin embargo, en tiempo de ejecución los valores especificados para las propiedades de enlace en la configuración del puerto de envío será aplicable.</span><span class="sxs-lookup"><span data-stu-id="de46a-146">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

8. <span data-ttu-id="de46a-147">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="de46a-147">Click **OK**.</span></span>  

## <a name="enter-binding-properties-at-run-time"></a><span data-ttu-id="de46a-148">Escribir propiedades de enlace en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="de46a-148">Enter Binding Properties at Run Time</span></span>  
 <span data-ttu-id="de46a-149">Para el tiempo de ejecución, puede especificar las propiedades de enlace como parte del puerto de WCF-Custom o configuración de SAP de WCF en el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="de46a-149">For run time, you can specify the binding properties as part of the WCF-Custom port or WCF-SAP configuration in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

### <a name="enter-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="de46a-150">Especifique las propiedades de enlace para el puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="de46a-150">Enter binding properties for the WCF-Custom port</span></span>  

1. <span data-ttu-id="de46a-151">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="de46a-151">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="de46a-152">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="de46a-152">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="de46a-153">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="de46a-153">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="de46a-154">En el **propiedades de puerto** cuadro de diálogo desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="de46a-154">In the **Port Properties** dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="de46a-155">Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="de46a-155">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="de46a-156">En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="de46a-156">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  

5. <span data-ttu-id="de46a-157">Desde el **BindingType** lista desplegable, seleccione **sapBinding**.</span><span class="sxs-lookup"><span data-stu-id="de46a-157">From the **Binding Type** drop-down list, select **sapBinding**.</span></span>  

6. <span data-ttu-id="de46a-158">En el **configuración** cuadro, especifique los valores de las propiedades de enlace diferente y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="de46a-158">In the **Configuration** box, specify the values for the different binding properties, and then click **OK**.</span></span>  

### <a name="enter-binging-properties-for-the-wcf-sap-port"></a><span data-ttu-id="de46a-159">Especifique las propiedades de enlace para el puerto de SAP de WCF</span><span class="sxs-lookup"><span data-stu-id="de46a-159">Enter binging properties for the WCF-SAP port</span></span>  

1. <span data-ttu-id="de46a-160">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="de46a-160">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="de46a-161">Agregar el adaptador SAP de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="de46a-161">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="de46a-162">Para obtener instrucciones, consulte [agregar el adaptador SAP a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="de46a-162">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="de46a-163">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="de46a-163">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="de46a-164">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="de46a-164">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="de46a-165">En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el adaptador SAP de WCF que agregó anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="de46a-165">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="de46a-166">Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="de46a-166">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="de46a-167">En el cuadro de diálogo Propiedades de transporte, haga clic en el **enlace** pestaña y especificar los valores de propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="de46a-167">In the transport properties dialog box, click the **Binding** tab and specify values for binding properties.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="de46a-168">Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="de46a-168">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="de46a-169">Por ejemplo, operaciones relacionadas con entrada de enlace de propiedades no están disponibles al configurar un puerto de envío debido a operaciones de entrada requieren una configuración de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="de46a-169">For example, binding properties related to inbound operations are not available while configuring a send port because inbound operations require a receive port configuration.</span></span>  

6. <span data-ttu-id="de46a-170">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="de46a-170">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="de46a-171">Vea también</span><span class="sxs-lookup"><span data-stu-id="de46a-171">See Also</span></span>  
[<span data-ttu-id="de46a-172">Bloques de creación para crear aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="de46a-172">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)