---
title: Configurar las propiedades de enlace para la base de datos de Oracle | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding properties, specifying at run time
- binding properties, specifying at design time
ms.assetid: c59a1b5c-b52b-4161-82de-c4d89bfce5c7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96922feab7c343893bfaa04ccbccd7c7e2f6a743
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981085"
---
# <a name="configure-the-binding-properties-for-oracle-database"></a><span data-ttu-id="27eb7-102">Configurar las propiedades de enlace para la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="27eb7-102">Configure the binding properties for Oracle Database</span></span>
<span data-ttu-id="27eb7-103">La [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] expone varias propiedades de enlace que le permiten controlar algunos de sus características de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="27eb7-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] surfaces several binding properties that enable you to control some of its behavioral characteristics.</span></span> <span data-ttu-id="27eb7-104">Esta sección proporciona información acerca de cómo establecer las propiedades de enlace desde Visual Studio y desde la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="27eb7-104">This section provides information about setting the binding properties from Visual Studio and from the BizTalk Server Administration console.</span></span> <span data-ttu-id="27eb7-105">Desde Visual Studio, debe especificar las propiedades de enlace al generar el esquema para operaciones específicas.</span><span class="sxs-lookup"><span data-stu-id="27eb7-105">From Visual Studio, you must specify the binding properties while generating schema for specific operations.</span></span> <span data-ttu-id="27eb7-106">Desde BizTalk Server, debe especificar las propiedades de enlace como parte de envío o puerto de recepción para enviar o recibir mensajes desde la base de datos de Oracle.</span><span class="sxs-lookup"><span data-stu-id="27eb7-106">From BizTalk Server, you must specify the binding properties as part of the send or receive port for sending or receiving messages from the Oracle database.</span></span>  

 <span data-ttu-id="27eb7-107">Para obtener información acerca de las propiedades de enlace, incluida una lista de propiedades de enlace [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="27eb7-107">For information about the binding properties, including a list of binding properties for [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  

## <a name="specifying-binding-properties-from-visual-studio"></a><span data-ttu-id="27eb7-108">Especificar propiedades de enlace desde Visual Studio</span><span class="sxs-lookup"><span data-stu-id="27eb7-108">Specifying Binding Properties from Visual Studio</span></span>  
 <span data-ttu-id="27eb7-109">Desde Visual Studio, debe especificar las credenciales mediante el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] o [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="27eb7-109">From Visual Studio, you must specify the credentials using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span>  

#### <a name="to-specify-binding-properties-using-consume-adapter-service-add-in"></a><span data-ttu-id="27eb7-110">Para especificar las propiedades de enlace mediante el complemento Consume Adapter Service</span><span class="sxs-lookup"><span data-stu-id="27eb7-110">To specify binding properties using Consume Adapter Service Add-in</span></span>  

1.  <span data-ttu-id="27eb7-111">Haga clic en el proyecto de BizTalk y, a continuación, seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-111">Right-click your BizTalk project and then select **Add Generated Items**.</span></span>  

2.  <span data-ttu-id="27eb7-112">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27eb7-112">In the **Add Generated Items** dialog box, do the following:</span></span>  

    |<span data-ttu-id="27eb7-113">Use</span><span class="sxs-lookup"><span data-stu-id="27eb7-113">Use this</span></span>|<span data-ttu-id="27eb7-114">Para</span><span class="sxs-lookup"><span data-stu-id="27eb7-114">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="27eb7-115">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="27eb7-115">**Categories**</span></span>|<span data-ttu-id="27eb7-116">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-116">Click **Consume Adapter Service**.</span></span>|  
    |<span data-ttu-id="27eb7-117">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="27eb7-117">**Templates**</span></span>|<span data-ttu-id="27eb7-118">Haga clic en **Consume Adapter Service**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-118">Click **Consume Adapter Service**.</span></span>|  

3.  <span data-ttu-id="27eb7-119">Para iniciar el **Consume Adapter Service** cuadro de diálogo, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-119">To start the **Consume Adapter Service** dialog box, click **Add**.</span></span>  

4.  <span data-ttu-id="27eb7-120">En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **oracleDBBinding**y haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-120">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **oracleDBBinding**, and click **Configure**.</span></span>  

5.  <span data-ttu-id="27eb7-121">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** pestaña y especificar las propiedades de enlace diferente.</span><span class="sxs-lookup"><span data-stu-id="27eb7-121">In the **Configure Adapter** dialog box, click the **Binding Properties** tab and specify the different binding properties.</span></span>  

6.  <span data-ttu-id="27eb7-122">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-122">Click **OK**.</span></span>  

#### <a name="to-specify-binding-properties-using-add-adapter-metadata-wizard"></a><span data-ttu-id="27eb7-123">Para especificar las propiedades de enlace mediante el Asistente para agregar metadatos de adaptador</span><span class="sxs-lookup"><span data-stu-id="27eb7-123">To specify binding properties using Add Adapter Metadata Wizard</span></span>  

1. <span data-ttu-id="27eb7-124">Haga clic en el proyecto de BizTalk y, a continuación, seleccione **agregar elementos generados**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-124">Right-click your BizTalk project and then select **Add Generated Items**.</span></span>  

2. <span data-ttu-id="27eb7-125">En el **agregar elementos generados** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="27eb7-125">In the **Add Generated Items** dialog box, do the following:</span></span>  


   |    <span data-ttu-id="27eb7-126">Use</span><span class="sxs-lookup"><span data-stu-id="27eb7-126">Use this</span></span>    |           <span data-ttu-id="27eb7-127">Para</span><span class="sxs-lookup"><span data-stu-id="27eb7-127">To do this</span></span>            |
   |----------------|---------------------------------|
   | <span data-ttu-id="27eb7-128">**Categorías**</span><span class="sxs-lookup"><span data-stu-id="27eb7-128">**Categories**</span></span> |     <span data-ttu-id="27eb7-129">Haga clic en **agregar adaptador**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-129">Click **Add Adapter**.</span></span>      |
   | <span data-ttu-id="27eb7-130">**Templates** (Plantillas [C++])</span><span class="sxs-lookup"><span data-stu-id="27eb7-130">**Templates**</span></span>  | <span data-ttu-id="27eb7-131">Haga clic en **agregar metadatos de adaptador**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-131">Click **Add Adapter Metadata**.</span></span> |


3. <span data-ttu-id="27eb7-132">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-132">Click **Add**.</span></span> <span data-ttu-id="27eb7-133">Se abre el Asistente para agregar metadatos de adaptador.</span><span class="sxs-lookup"><span data-stu-id="27eb7-133">The Add Adapter Metadata Wizard opens.</span></span>  

4. <span data-ttu-id="27eb7-134">En el Asistente para agregar metadatos de adaptador, seleccione **WCF-OracleDB**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-134">In the Add Adapter Metadata Wizard, select **WCF-OracleDB**.</span></span> <span data-ttu-id="27eb7-135">Seleccione el equipo en el que [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] está instalado y el nombre de la base de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="27eb7-135">Select the computer on which [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] is installed and the name of the BizTalk database.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="27eb7-136">Si ya tiene un puerto de WCF-OracleDB configurado en BizTalk, seleccione el puerto desde el **puerto** lista.</span><span class="sxs-lookup"><span data-stu-id="27eb7-136">If you already have a WCF-OracleDB port configured in BizTalk, select the port from the **Port** list.</span></span>  

5. <span data-ttu-id="27eb7-137">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-137">Click **Next**.</span></span>  

6. <span data-ttu-id="27eb7-138">En el **Consume Adapter Service** cuadro de diálogo desde el **selecciona un enlace** lista desplegable, seleccione **oracleDBBinding**y haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-138">In the **Consume Adapter Service** dialog box, from the **Select a binding** drop-down list select **oracleDBBinding**, and click **Configure**.</span></span>  

7. <span data-ttu-id="27eb7-139">En el **configurar el adaptador** cuadro de diálogo, haga clic en el **propiedades de enlace** pestaña y especificar los valores de enlace, si existe, que son necesarios antes de generar el esquema.</span><span class="sxs-lookup"><span data-stu-id="27eb7-139">In the **Configure Adapter** dialog box, click the **Binding Properties** tab, and specify the binding values, if any, which are required before generating the schema.</span></span> <span data-ttu-id="27eb7-140">Para obtener más información acerca de las propiedades de enlace, consulte [Obtenga información sobre las propiedades de enlace del adaptador de base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span><span class="sxs-lookup"><span data-stu-id="27eb7-140">For more information about binding properties, see [Read about the Oracle Database adapter binding properties](../../adapters-and-accelerators/adapter-oracle-database/read-about-the-oracle-database-adapter-binding-properties.md).</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="27eb7-141">Si ha seleccionado un puerto de envío WCF-OracleDB existente, no necesita especificar las propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="27eb7-141">If you selected an existing WCF-OracleDB send port, you need not specify the binding properties.</span></span> <span data-ttu-id="27eb7-142">Se seleccionan las propiedades de enlace de la configuración de puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="27eb7-142">The binding properties are picked from the send port configuration.</span></span> <span data-ttu-id="27eb7-143">Sin embargo, puede especificar las propiedades de enlace que son necesarias en tiempo de diseño, si existe.</span><span class="sxs-lookup"><span data-stu-id="27eb7-143">However, you may choose to specify the binding properties that are required at design-time, if any.</span></span> <span data-ttu-id="27eb7-144">En tal caso, se utilizará los nuevos valores de propiedades de enlace en tiempo de diseño al generar los metadatos.</span><span class="sxs-lookup"><span data-stu-id="27eb7-144">In such a case, the new values for binding properties will be used at design-time while generating the metadata.</span></span> <span data-ttu-id="27eb7-145">Sin embargo, en tiempo de ejecución los valores especificados para las propiedades de enlace en la configuración del puerto de envío será aplicable.</span><span class="sxs-lookup"><span data-stu-id="27eb7-145">However, at run-time the values specified for binding properties in the send port configuration will be applicable.</span></span>  

8. <span data-ttu-id="27eb7-146">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-146">Click **OK**.</span></span>  

## <a name="specifying-binding-properties-from-the-biztalk-server-administration-console"></a><span data-ttu-id="27eb7-147">Especificar propiedades de enlace desde la consola de administración de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="27eb7-147">Specifying Binding Properties from the BizTalk Server Administration Console</span></span>  
 <span data-ttu-id="27eb7-148">Desde la consola de administración de BizTalk Server, debe especificar las propiedades de enlace como parte de la configuración del puerto WCF-Custom o WCF-OracleDB.</span><span class="sxs-lookup"><span data-stu-id="27eb7-148">From the BizTalk Server Administration console, you must specify the binding properties as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span>  

#### <a name="to-specify-binding-properties-for-the-wcf-custom-port"></a><span data-ttu-id="27eb7-149">Para especificar las propiedades de enlace para el puerto de WCF-Custom</span><span class="sxs-lookup"><span data-stu-id="27eb7-149">To specify binding properties for the WCF-Custom port</span></span>  

1. <span data-ttu-id="27eb7-150">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="27eb7-150">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="27eb7-151">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-151">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="27eb7-152">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="27eb7-152">In the right pane, you can choose to create a port or select an existing port.</span></span>  

3. <span data-ttu-id="27eb7-153">En el cuadro de diálogo Propiedades de puerto, desde el **tipo** lista desplegable, seleccione **WCF-Custom**y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-153">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="27eb7-154">Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-154">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

4. <span data-ttu-id="27eb7-155">En el **propiedades de transporte WCF-Custom** cuadro de diálogo, haga clic en el **enlace** ficha.</span><span class="sxs-lookup"><span data-stu-id="27eb7-155">In the **WCF-Custom Transport Properties** dialog box, click the **Binding** tab.</span></span>  

5. <span data-ttu-id="27eb7-156">Desde el **BindingType** lista desplegable, seleccione **oracleDBBinding**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-156">From the **Binding Type** drop-down list, select **oracleDBBinding**.</span></span>  

6. <span data-ttu-id="27eb7-157">En el **configuración** , especifique los valores de las propiedades de enlace diferente y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-157">In the **Configuration** box, specify the values for the different binding properties and click **OK**.</span></span>  

#### <a name="to-specify-binding-properties-for-the-wcf-oracledb-port"></a><span data-ttu-id="27eb7-158">Para especificar las propiedades de enlace para el puerto de WCF-OracleDB</span><span class="sxs-lookup"><span data-stu-id="27eb7-158">To specify binding properties for the WCF-OracleDB port</span></span>  

1. <span data-ttu-id="27eb7-159">Iniciar el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="27eb7-159">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

2. <span data-ttu-id="27eb7-160">Agregar el adaptador de WCF-OracleDB a la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="27eb7-160">Add the WCF-OracleDB adapter to the BizTalk Server Administration console.</span></span> <span data-ttu-id="27eb7-161">Para obtener instrucciones, consulte [agregación del adaptador de base de datos de Oracle a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="27eb7-161">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  

3. <span data-ttu-id="27eb7-162">En el árbol de consola, expanda **grupo de BizTalk**, a continuación, expanda **aplicaciones**y, a continuación, expanda la aplicación en la que desea crear un puerto y haga clic en **puertos de envío** o **Puertos de recepción**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-162">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then expand the application under which you want to create a port, and click **Send Ports** or **Receive Ports**.</span></span> <span data-ttu-id="27eb7-163">En el panel derecho, puede elegir crear un puerto o seleccionar un puerto existente.</span><span class="sxs-lookup"><span data-stu-id="27eb7-163">In the right pane, you can choose to create a port or select an existing port.</span></span>  

4. <span data-ttu-id="27eb7-164">En el cuadro de diálogo Propiedades de puerto, desde el **tipo** la lista desplegable, seleccione el adaptador de WCF-OracleDB que agregó anteriormente y, a continuación, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-164">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleDB adapter you added earlier, and then click **Configure**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="27eb7-165">Para ver el cuadro de diálogo de propiedades de ubicación para un puerto de recepción, haga clic en el **ubicación de recepción** pestaña en el panel izquierdo del cuadro de diálogo de propiedades de puerto y, a continuación, haga clic en **New**.</span><span class="sxs-lookup"><span data-stu-id="27eb7-165">To see the location properties dialog box for a receive port, click the **Receive Location** tab on the left pane of the port properties dialog box, and then click **New**.</span></span>  

5. <span data-ttu-id="27eb7-166">En el cuadro de diálogo Propiedades de transporte, haga clic en el **enlace** pestaña y especificar los valores de propiedades de enlace.</span><span class="sxs-lookup"><span data-stu-id="27eb7-166">In the transport properties dialog box, click the **Binding** tab, and specify values for binding properties.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="27eb7-167">Se muestran las propiedades de enlace en función de si está configurando un puerto de envío o un puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="27eb7-167">The binding properties are displayed based on whether you are configuring a send port or a receive port.</span></span> <span data-ttu-id="27eb7-168">Por ejemplo, las propiedades de enlace relacionadas con las notificaciones no están disponibles al configurar un puerto de envío porque las notificaciones son operaciones de entrada y requieren una configuración de puerto de recepción.</span><span class="sxs-lookup"><span data-stu-id="27eb7-168">For example, binding properties related to notifications are not available while configuring a send port because notifications are inbound operations and require a receive port configuration.</span></span>  

## <a name="see-also"></a><span data-ttu-id="27eb7-169">Vea también</span><span class="sxs-lookup"><span data-stu-id="27eb7-169">See Also</span></span>  
[<span data-ttu-id="27eb7-170">Bloques de creación para desarrollar aplicaciones de BizTalk con la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="27eb7-170">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)