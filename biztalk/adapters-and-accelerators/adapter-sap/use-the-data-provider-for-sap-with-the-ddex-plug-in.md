---
title: Usar el proveedor de datos para SAP con el complemento DDEX | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DDEX plug-in
- DDEX plug-in, Data Provider for SAP
- Data Provider for SAP, using with DDEX plug-in
ms.assetid: b16c8634-172a-4630-87ed-2073a75afdec
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2a1dd348b6d897e147d6add49499e9716a67aeb
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25963466"
---
# <a name="use-the-data-provider-for-sap-with-the-ddex-plug-in"></a><span data-ttu-id="673c0-102">Usar el proveedor de datos para SAP con el complemento DDEX</span><span class="sxs-lookup"><span data-stu-id="673c0-102">Use the Data Provider for SAP with the DDEX Plug-in</span></span>
<span data-ttu-id="673c0-103">Si decide instalar la [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] junto con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación, el programa de instalación instala un [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] complemento DDEX.</span><span class="sxs-lookup"><span data-stu-id="673c0-103">If you chose to install the [!INCLUDE[adoprovidersaplong](../../includes/adoprovidersaplong-md.md)] along with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, the setup program installs a [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] DDEX plug-in.</span></span> <span data-ttu-id="673c0-104">Puede usar este complemento para examinar objetos SAP mediante [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="673c0-104">You can use this plug-in to browse SAP objects using [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="673c0-105">Esta sección proporciona información acerca de cómo utilizar el complemento DDEX.</span><span class="sxs-lookup"><span data-stu-id="673c0-105">This section provides information about using the DDEX plug-in.</span></span>  
  
 <span data-ttu-id="673c0-106">Puede usar el complemento para establecer la conectividad con el sistema SAP, agregar las tablas del sistema SAP y agregar módulos de función del sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="673c0-106">You can use the plug-in to establish connectivity with the SAP system, add tables from the SAP system, and add function modules from the SAP system.</span></span> <span data-ttu-id="673c0-107">Después de agregar las tablas y los módulos de función mediante el complemento de Visual Studio, los módulos de función y las tablas recién agregadas se reflejan en el archivo SAPDiscoveredObjects.xml.</span><span class="sxs-lookup"><span data-stu-id="673c0-107">After you have added the tables and function modules using the Visual Studio plug-in, the newly added tables and function modules are reflected in the SAPDiscoveredObjects.xml file.</span></span> <span data-ttu-id="673c0-108">Para obtener más información acerca de este archivo, consulte [sobre el archivo SAPDiscoveredObjects.xml en SAP](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md).</span><span class="sxs-lookup"><span data-stu-id="673c0-108">For more information about this file, see [About the SAPDiscoveredObjects.xml File in SAP](../../adapters-and-accelerators/adapter-sap/about-the-sapdiscoveredobjects-xml-file-in-sap.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="673c0-109">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="673c0-109">Prerequisites</span></span>  
 <span data-ttu-id="673c0-110">Asegúrese de que eligió instalar los [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] junto con el [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="673c0-110">Make sure you chose to install the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] along with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation.</span></span>  
  
### <a name="to-connect-to-an-sap-system-using-the-ddex-plug-in"></a><span data-ttu-id="673c0-111">Para conectarse a un sistema SAP mediante el complemento DDEX</span><span class="sxs-lookup"><span data-stu-id="673c0-111">To connect to an SAP system using the DDEX plug-in</span></span>  
  
1.  <span data-ttu-id="673c0-112">Inicie Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="673c0-112">Start Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
2.  <span data-ttu-id="673c0-113">En [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], en la **vista** menú, haga clic en **Explorador de servidores**.</span><span class="sxs-lookup"><span data-stu-id="673c0-113">In [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], on the **View** menu, click **Server Explorer**.</span></span>  
  
3.  <span data-ttu-id="673c0-114">En el **Explorador de servidores**, haga clic en **las conexiones de datos**y seleccione **Agregar conexión**.</span><span class="sxs-lookup"><span data-stu-id="673c0-114">In the **Server Explorer**, right-click **Data Connections**, and select **Add Connection**.</span></span>  
  
4.  <span data-ttu-id="673c0-115">En el **cambiar origen de datos** cuadro de diálogo, desde el **origen de datos** cuadro, seleccione  **\<otros\>**.</span><span class="sxs-lookup"><span data-stu-id="673c0-115">In the **Change Data Source** dialog box, from the **Data source** box, select **\<other\>**.</span></span>  
  
5.  <span data-ttu-id="673c0-116">Desde el **proveedor de datos** lista desplegable, seleccione **.NET Framework Data Provider para mySAP Business Suite** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="673c0-116">From the **Data provider** drop-down list, select **.NET Framework Data Provider for mySAP Business Suite** and click **OK**.</span></span> <span data-ttu-id="673c0-117">El **Agregar conexión** abre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="673c0-117">The **Add Connection** dialog box opens.</span></span>  
  
6.  <span data-ttu-id="673c0-118">El **Agregar conexión** cuadro de diálogo enumera los parámetros de conexión diferente para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="673c0-118">The **Add Connection** dialog box lists the different connection parameters to connect to an SAP system.</span></span> <span data-ttu-id="673c0-119">Una cadena de conexión típica para conectarse a un sistema SAP mediante el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requiere:</span><span class="sxs-lookup"><span data-stu-id="673c0-119">A typical connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] requires:</span></span>  
  
    -   <span data-ttu-id="673c0-120">Los parámetros de conexión para un tipo de conexión.</span><span class="sxs-lookup"><span data-stu-id="673c0-120">The connection parameters for a connection type.</span></span> <span data-ttu-id="673c0-121">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] es compatible con los tipos de conexión A, B y D. Para conectarse a un sistema SAP debe proporcionar parámetros de conexión para cualquier *una* de estos tipos de conexión.</span><span class="sxs-lookup"><span data-stu-id="673c0-121">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports connection types A, B, and D. To connect to an SAP system you must provide connection parameters for any *one* of these connection types.</span></span> <span data-ttu-id="673c0-122">Por ejemplo, para el tipo de conexión A, debe proporcionar el nombre del host de servidor de aplicación y el número del sistema.</span><span class="sxs-lookup"><span data-stu-id="673c0-122">For example, for connection type A, you must provide the name of the application server host and the system number.</span></span>  
  
    -   <span data-ttu-id="673c0-123">La información de inicio de sesión para conectarse a un sistema SAP como nombre de usuario y la contraseña.</span><span class="sxs-lookup"><span data-stu-id="673c0-123">The login information to connect to an SAP system such as username and password.</span></span>  
  
     <span data-ttu-id="673c0-124">Para obtener más información acerca de la cadena de conexión para conectarse a un sistema SAP mediante la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], consulte [más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span><span class="sxs-lookup"><span data-stu-id="673c0-124">For more information about the connection string to connect to an SAP system using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
     <span data-ttu-id="673c0-125">En el **Agregar conexión** diálogo cuadro, especifique:</span><span class="sxs-lookup"><span data-stu-id="673c0-125">In the **Add Connection** dialog box, specify:</span></span>  
  
    -   <span data-ttu-id="673c0-126">Los parámetros de conexión para cualquier tipo de una conexión.</span><span class="sxs-lookup"><span data-stu-id="673c0-126">The connection parameters for any one connection type.</span></span>  
  
    -   <span data-ttu-id="673c0-127">La información de inicio de sesión para conectarse a un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="673c0-127">The login information to connect to an SAP system.</span></span>  
  
    -   <span data-ttu-id="673c0-128">Si desea habilitar la depuración de GUI de SAP.</span><span class="sxs-lookup"><span data-stu-id="673c0-128">Whether you want to enable SAP GUI debugging.</span></span>  
  
    -   <span data-ttu-id="673c0-129">Si desea utilizar el seguimiento de RFC SDK.</span><span class="sxs-lookup"><span data-stu-id="673c0-129">Whether you want to use RFC SDK tracing.</span></span>  
  
     <span data-ttu-id="673c0-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="673c0-130">Click **OK**.</span></span> <span data-ttu-id="673c0-131">Se crea un nuevo nodo de conexión en el **las conexiones de datos** nodo con el nombre del servidor especificado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="673c0-131">A new connection node is created under the **Data Connections** node with the server name you specified in the previous step.</span></span>  
  
7.  <span data-ttu-id="673c0-132">Expanda el nodo de conexión nueva para ver el **tablas** y **módulos de función** nodos.</span><span class="sxs-lookup"><span data-stu-id="673c0-132">Expand the new connection node to view the **Tables** and **Function Modules** nodes.</span></span>  
  
     <span data-ttu-id="673c0-133">La siguiente ilustración muestra el Explorador de servidores una vez establecida la conexión.</span><span class="sxs-lookup"><span data-stu-id="673c0-133">The following figure shows the Server Explorer after the connection is established.</span></span>  
  
     <span data-ttu-id="673c0-134">![Plug DDEX&#45;en para el proveedor de ADO.NET de SAP](../../adapters-and-accelerators/adapter-sap/media/158afc11-9c90-4333-bc62-5901f8d0c794.gif "158afc11-9c90-4333-bc62-5901f8d0c794")</span><span class="sxs-lookup"><span data-stu-id="673c0-134">![DDEX plug&#45;in for SAP ADO.NET Provider](../../adapters-and-accelerators/adapter-sap/media/158afc11-9c90-4333-bc62-5901f8d0c794.gif "158afc11-9c90-4333-bc62-5901f8d0c794")</span></span>  
  
### <a name="to-add-tables-from-an-sap-system-using-the-ddex-plug-in"></a><span data-ttu-id="673c0-135">Para agregar las tablas de un sistema SAP mediante el complemento DDEX</span><span class="sxs-lookup"><span data-stu-id="673c0-135">To add tables from an SAP system using the DDEX plug-in</span></span>  
  
1.  <span data-ttu-id="673c0-136">En el **Explorador de servidores**, haga clic en el **tablas** nodo y haga clic en **buscar y agregar tablas**.</span><span class="sxs-lookup"><span data-stu-id="673c0-136">In the **Server Explorer**, right-click the **Tables** node and click **Search and Add Tables**.</span></span>  
  
2.  <span data-ttu-id="673c0-137">En el **nombre de la tabla de búsqueda** texto, especifique una cadena de búsqueda para buscar tablas en el sistema SAP y haga clic en **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="673c0-137">In the **Search table name** text box, specify a search string to search tables in the SAP system, and click **Search**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="673c0-138">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] admite el uso de solo el carácter comodín de asterisco (\*) para buscar tablas.</span><span class="sxs-lookup"><span data-stu-id="673c0-138">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports the use of only the asterisk (\*) wildcard character for searching tables.</span></span>  
  
3.  <span data-ttu-id="673c0-139">El **resultados de búsqueda** cuadro muestra los nombres de tabla que cumplen los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="673c0-139">The **Search results** box lists the table names that satisfy the search criteria.</span></span>  
  
     <span data-ttu-id="673c0-140">![Plug DDEX&#45;en el cuadro de diálogo de nombre de búsqueda y agregar tablas](../../adapters-and-accelerators/adapter-sap/media/737fc9c3-5258-4693-a2f3-5b5b8d2483e9.gif "737fc9c3-5258-4693-a2f3-5b5b8d2483e9")</span><span class="sxs-lookup"><span data-stu-id="673c0-140">![DDEX plug&#45;in Search and Add Tables name dialog box](../../adapters-and-accelerators/adapter-sap/media/737fc9c3-5258-4693-a2f3-5b5b8d2483e9.gif "737fc9c3-5258-4693-a2f3-5b5b8d2483e9")</span></span>  
  
4.  <span data-ttu-id="673c0-141">Active la casilla de verificación correspondientes a las tablas que desea agregar y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="673c0-141">Select the check box corresponding to the tables you want to add and click **Add**.</span></span> <span data-ttu-id="673c0-142">Para seleccionar todas las tablas, haga clic en **seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="673c0-142">To select all the tables, click **Select All**.</span></span> <span data-ttu-id="673c0-143">Para borrar todas las selecciones, haga clic en **Borrar todo**.</span><span class="sxs-lookup"><span data-stu-id="673c0-143">To clear all the selections, click **Clear All**.</span></span>  
  
5.  <span data-ttu-id="673c0-144">Un cuadro de diálogo le informa de que sea visibles en las tablas agregadas después de actualizar el **tablas** nodo.</span><span class="sxs-lookup"><span data-stu-id="673c0-144">A dialog box informs you that the added tables would be visible after you refresh the **Tables** node.</span></span> <span data-ttu-id="673c0-145">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="673c0-145">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="673c0-146">Haga clic en el **tablas** nodo y seleccione **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="673c0-146">Right-click the **Tables** node and select **Refresh**.</span></span> <span data-ttu-id="673c0-147">Las tablas seleccionadas aparecen en la **tablas** nodo.</span><span class="sxs-lookup"><span data-stu-id="673c0-147">The selected tables appear under the **Tables** node.</span></span> <span data-ttu-id="673c0-148">Haga clic en un nombre de tabla para ver las propiedades de tabla en la **propiedades** panel.</span><span class="sxs-lookup"><span data-stu-id="673c0-148">Click a table name to see the table properties in the **Properties** pane.</span></span>  
  
7.  <span data-ttu-id="673c0-149">Expandir un nombre de tabla para ver los campos de la tabla.</span><span class="sxs-lookup"><span data-stu-id="673c0-149">Expand a table name to see the fields for the table.</span></span> <span data-ttu-id="673c0-150">Haga clic en un nombre de campo para ver las propiedades de campo en el **propiedades** panel.</span><span class="sxs-lookup"><span data-stu-id="673c0-150">Click a field name to see the field properties in the **Properties** pane.</span></span>  
  
### <a name="to-add-rfcs-from-an-sap-system-using-the-ddex-plug-in"></a><span data-ttu-id="673c0-151">Para agregar las solicitudes de cambio de un sistema SAP mediante el complemento DDEX</span><span class="sxs-lookup"><span data-stu-id="673c0-151">To add RFCs from an SAP system using the DDEX plug-in</span></span>  
  
1.  <span data-ttu-id="673c0-152">En el **Explorador de servidores**, haga clic en el **módulos de función** nodo y haga clic en **buscar y agregar módulos de función**.</span><span class="sxs-lookup"><span data-stu-id="673c0-152">In the **Server Explorer**, right-click the **Function Modules** node and click **Search and Add Function Modules**.</span></span>  
  
2.  <span data-ttu-id="673c0-153">En el **módulo de función de búsqueda** texto, especifique una cadena de búsqueda para buscar los módulos de función en el sistema SAP y haga clic en **búsqueda**.</span><span class="sxs-lookup"><span data-stu-id="673c0-153">In the **Search function module** text box, specify a search string to search function modules in the SAP system, and click **Search**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="673c0-154">El [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] admite el uso de solo el carácter comodín de asterisco (\*) para buscar módulos funcionales.</span><span class="sxs-lookup"><span data-stu-id="673c0-154">The [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] supports the use of only the asterisk (\*) wildcard character for searching functional modules.</span></span>  
  
3.  <span data-ttu-id="673c0-155">El **resultados de búsqueda** cuadro muestra los módulos de función que cumplen los criterios de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="673c0-155">The **Search results** box lists the function modules that satisfy the search criteria.</span></span>  
  
     <span data-ttu-id="673c0-156">![Plug DDEX&#45;en el cuadro de diálogo Buscar y agregar módulos](../../adapters-and-accelerators/adapter-sap/media/8c7f9081-80aa-4bfe-8f06-2c751758ddd0.gif "8c7f9081-80aa-4bfe-8f06-2c751758ddd0")</span><span class="sxs-lookup"><span data-stu-id="673c0-156">![DDEX plug&#45;in Search and Add Modules dialog box](../../adapters-and-accelerators/adapter-sap/media/8c7f9081-80aa-4bfe-8f06-2c751758ddd0.gif "8c7f9081-80aa-4bfe-8f06-2c751758ddd0")</span></span>  
  
4.  <span data-ttu-id="673c0-157">Active la casilla correspondiente a los módulos de función que desea agregar y haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="673c0-157">Select the check box corresponding to the function modules you want to add and click **Add**.</span></span> <span data-ttu-id="673c0-158">Para seleccionar todos los módulos, haga clic en **seleccionar todo**.</span><span class="sxs-lookup"><span data-stu-id="673c0-158">To select all the modules, click **Select All**.</span></span> <span data-ttu-id="673c0-159">Para borrar todas las selecciones, haga clic en **Borrar todo**.</span><span class="sxs-lookup"><span data-stu-id="673c0-159">To clear all the selections, click **Clear All**.</span></span>  
  
5.  <span data-ttu-id="673c0-160">Un cuadro de diálogo le informa de que los módulos de función agregado sería visibles después de actualizar el **módulos de función** nodo.</span><span class="sxs-lookup"><span data-stu-id="673c0-160">A dialog box informs you that the added function modules would be visible after you refresh the **Function Modules** node.</span></span> <span data-ttu-id="673c0-161">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="673c0-161">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="673c0-162">Haga clic en el **módulos de función** nodo y seleccione **actualizar**.</span><span class="sxs-lookup"><span data-stu-id="673c0-162">Right-click the **Function Modules** node and select **Refresh**.</span></span> <span data-ttu-id="673c0-163">Los módulos de la función seleccionada aparecen en la **módulos de función** nodo.</span><span class="sxs-lookup"><span data-stu-id="673c0-163">The selected function modules appear under the **Function Modules** node.</span></span> <span data-ttu-id="673c0-164">Haga clic en un nombre de módulo de función para ver las propiedades en el **propiedades** panel.</span><span class="sxs-lookup"><span data-stu-id="673c0-164">Click a function module name to see the properties in the **Properties** pane.</span></span>  
  
7.  <span data-ttu-id="673c0-165">Expanda el nombre de un módulo de función para ver los nodos para importar, exportar, cambiar y parámetros de la tabla.</span><span class="sxs-lookup"><span data-stu-id="673c0-165">Expand a function module name to see nodes for import, export, changing, and table parameters.</span></span>  
  
8.  <span data-ttu-id="673c0-166">Expanda el **importar** nodo para mostrar los parámetros de importación del módulo de función.</span><span class="sxs-lookup"><span data-stu-id="673c0-166">Expand the **Import** node to list the import parameters for the function module.</span></span> <span data-ttu-id="673c0-167">De forma similar, expanda la **exportar** y **tablas** nodos para ver la lista de exportación y la tabla de parámetros para el módulo de función.</span><span class="sxs-lookup"><span data-stu-id="673c0-167">Similarly, expand the **Export** and **Tables** nodes to see the list of export and table parameters for the function module.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="673c0-168">Vea también</span><span class="sxs-lookup"><span data-stu-id="673c0-168">See Also</span></span>  
 [<span data-ttu-id="673c0-169">Uso del proveedor de datos de .NET Framework para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="673c0-169">Use the .NET Framework Data Provider for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-net-framework-data-provider-for-mysap-business-suite.md)