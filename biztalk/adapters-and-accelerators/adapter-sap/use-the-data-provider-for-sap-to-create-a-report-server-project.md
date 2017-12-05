---
title: Usar el proveedor de datos de SAP para crear un proyecto de servidor de informes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5fe985b5-ba67-4179-a31c-4f41106c32be
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e9c7905fc7114feeca8b53589e1aa32a09495ca1
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="use-the-data-provider-for-sap-to-create-a-report-server-project"></a><span data-ttu-id="32bfd-102">Usar el proveedor de datos de SAP para crear un proyecto de servidor de informes</span><span class="sxs-lookup"><span data-stu-id="32bfd-102">Use the Data Provider for SAP to Create a Report Server Project</span></span>
<span data-ttu-id="32bfd-103">Debe crear un servidor de informes del proyecto, con el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], para generar informes de los datos disponibles en un sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="32bfd-103">You must create a Report Server project, using the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)], to generate reports for the data available in an SAP system.</span></span> <span data-ttu-id="32bfd-104">Este tema proporciona instrucciones sobre cómo crear un proyecto de servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="32bfd-104">This topic provides instructions on how to create a Report Server project.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="32bfd-105">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="32bfd-105">Prerequisites</span></span>  
 <span data-ttu-id="32bfd-106">Antes de realizar los procedimientos proporcionados en este tema, asegúrese de que ha instalado el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] durante la instalación de la [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] como parte de la [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación.</span><span class="sxs-lookup"><span data-stu-id="32bfd-106">Before performing the procedures provided in this topic, make sure you installed the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] while installing the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] as part of the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation.</span></span> <span data-ttu-id="32bfd-107">Para obtener más información acerca de [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] instalación, consulte la Guía de instalación disponible en \< *unidad de instalación*\>: \Program [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span><span class="sxs-lookup"><span data-stu-id="32bfd-107">For more information about [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] installation, refer to the installation guide available at \<*installation drive*\>:\Program Files\Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]\Documents.</span></span>  
  
### <a name="to-create-a-report-server-project"></a><span data-ttu-id="32bfd-108">Para crear un proyecto de servidor de informes</span><span class="sxs-lookup"><span data-stu-id="32bfd-108">To create a Report Server project</span></span>  
  
1.  <span data-ttu-id="32bfd-109">Iniciar [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y cree un proyecto de servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="32bfd-109">Start [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and create a Report Server project.</span></span> <span data-ttu-id="32bfd-110">Para crear un proyecto de servidor de informes, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="32bfd-110">To create a Report Server project, do the following:</span></span>  
  
    1.  <span data-ttu-id="32bfd-111">Haga clic en el **archivo** menú, haga clic en **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-111">Click the **File** menu, click **New**, and then click **Project**.</span></span>  
  
    2.  <span data-ttu-id="32bfd-112">En el **nuevo proyecto** cuadro de diálogo, desde el **tipos de proyecto** lista, seleccione **proyectos de Business Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-112">In the **New Project** dialog box, from the **Project types** list, select **Business Intelligence Projects**.</span></span> <span data-ttu-id="32bfd-113">De **plantillas instaladas de Visual Studio** lista, seleccione **Report Server Project**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-113">From **the Visual Studio installed templates** list, select **Report Server Project**.</span></span>  
  
    3.  <span data-ttu-id="32bfd-114">Especifique un nombre y ubicación del proyecto y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-114">Specify a name and location of the project and click **OK**.</span></span> <span data-ttu-id="32bfd-115">De este tema, especifique el nombre del proyecto como `SAP_ Report`.</span><span class="sxs-lookup"><span data-stu-id="32bfd-115">For this topic, specify the name of the project as `SAP_ Report`.</span></span>  
  
2.  <span data-ttu-id="32bfd-116">Agregar un nuevo origen de datos:</span><span class="sxs-lookup"><span data-stu-id="32bfd-116">Add a new data source:</span></span>  
  
    1.  <span data-ttu-id="32bfd-117">En el Explorador de soluciones, haga clic en **orígenes de datos compartidos**y haga clic en **Agregar nuevo origen de datos**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-117">From the Solution Explorer, right-click **Shared Data Sources**, and click **Add New Data Source**.</span></span>  
  
    2.  <span data-ttu-id="32bfd-118">En el **origen de datos compartido** cuadro de diálogo, en la **General** ficha, especifique un nombre para el origen de datos.</span><span class="sxs-lookup"><span data-stu-id="32bfd-118">In the **Shared Data Source** dialog box, in the **General** tab, specify a name for the data source.</span></span> <span data-ttu-id="32bfd-119">De este tema, especifique el nombre como `SAPDataSource`.</span><span class="sxs-lookup"><span data-stu-id="32bfd-119">For this topic, specify the name as `SAPDataSource`.</span></span>  
  
    3.  <span data-ttu-id="32bfd-120">Desde el **tipo** lista, seleccione **proveedor de datos para SAP**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-120">From the **Type** list, select **Data Provider for SAP**.</span></span>  
  
    4.  <span data-ttu-id="32bfd-121">En el **cadena de conexión** , especifique la cadena de conexión para el [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="32bfd-121">In the **Connection String** box, specify the connection string for the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)].</span></span> <span data-ttu-id="32bfd-122">Para obtener información sobre la [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] cadena de conexión, consulte [más información sobre los tipos de proveedor de datos de la cadena de conexión de SAP](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span><span class="sxs-lookup"><span data-stu-id="32bfd-122">For information about the [!INCLUDE[adoprovidersapshort](../../includes/adoprovidersapshort-md.md)] connection string, see [Read about Data Provider types for the SAP Connection String](../../adapters-and-accelerators/adapter-sap/read-about-data-provider-types-for-the-sap-connection-string.md).</span></span>  
  
         <span data-ttu-id="32bfd-123">![Crear un origen de datos](../../adapters-and-accelerators/adapter-sap/media/8494c1a5-5e68-4178-a005-a6ea56d97ad7.gif "8494c1a5-5e68-4178-a005-a6ea56d97ad7")</span><span class="sxs-lookup"><span data-stu-id="32bfd-123">![Create a data source](../../adapters-and-accelerators/adapter-sap/media/8494c1a5-5e68-4178-a005-a6ea56d97ad7.gif "8494c1a5-5e68-4178-a005-a6ea56d97ad7")</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="32bfd-124">Puede elegir especificar las credenciales como parte de la cadena de conexión o especificarlos tal y como se describe en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="32bfd-124">You can choose to specify the credentials as part of the connection string or specify them as described in the next step.</span></span>  
  
    5.  <span data-ttu-id="32bfd-125">En el **credenciales** ficha, elija una de las siguientes acciones y, a continuación, haga clic en **Aceptar**:</span><span class="sxs-lookup"><span data-stu-id="32bfd-125">In the **Credentials** tab, choose one of the following, and then click **OK**:</span></span>  
  
        |<span data-ttu-id="32bfd-126">Use</span><span class="sxs-lookup"><span data-stu-id="32bfd-126">Use this</span></span>|<span data-ttu-id="32bfd-127">Para</span><span class="sxs-lookup"><span data-stu-id="32bfd-127">To do this</span></span>|  
        |--------------|----------------|  
        |<span data-ttu-id="32bfd-128">**Utilizar un nombre de usuario y una contraseña específicos**</span><span class="sxs-lookup"><span data-stu-id="32bfd-128">**Use a specific user name and password**</span></span>|<span data-ttu-id="32bfd-129">Especifique un nombre de usuario y una contraseña para conectarse al sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="32bfd-129">Specify a user name and password to connect to the SAP system.</span></span>|  
        |<span data-ttu-id="32bfd-130">**Pedir credenciales**</span><span class="sxs-lookup"><span data-stu-id="32bfd-130">**Prompt for credentials**</span></span>|<span data-ttu-id="32bfd-131">Escriba las credenciales para el sistema SAP mientras se genera el informe.</span><span class="sxs-lookup"><span data-stu-id="32bfd-131">Enter the credentials for the SAP system while the report is generated.</span></span> <span data-ttu-id="32bfd-132">**Nota:** las credenciales que especifique para esta opción invalidará las credenciales, si se especifica como parte de la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="32bfd-132">**Note:**  The credentials you specify for this option will override the credentials, if specified, as part of the connection string.</span></span>|  
        |<span data-ttu-id="32bfd-133">**Sin credenciales**</span><span class="sxs-lookup"><span data-stu-id="32bfd-133">**No credentials**</span></span>|<span data-ttu-id="32bfd-134">Elija esta opción si va a proporcionar el nombre de usuario y la contraseña como parte de la cadena de conexión.</span><span class="sxs-lookup"><span data-stu-id="32bfd-134">Choose this option if you are providing the user name and password as part of the connection string.</span></span>|  
  
        > [!NOTE]
        >  <span data-ttu-id="32bfd-135">No se admite el modo de autenticación de Windows para los proyectos de servidor de informes.</span><span class="sxs-lookup"><span data-stu-id="32bfd-135">The Windows Authentication mode is not supported for Report Server projects.</span></span>  
  
3.  <span data-ttu-id="32bfd-136">Agregar un nuevo informe:</span><span class="sxs-lookup"><span data-stu-id="32bfd-136">Add a new report:</span></span>  
  
    1.  <span data-ttu-id="32bfd-137">En el Explorador de soluciones, haga clic en **informes**y, a continuación, haga clic en **Agregar nuevo informe**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-137">From the Solution Explorer, right-click **Reports**, and then click **Add New Report**.</span></span>  
  
         <span data-ttu-id="32bfd-138">Esto inicia al Asistente para informes.</span><span class="sxs-lookup"><span data-stu-id="32bfd-138">This starts the Report Wizard.</span></span>  
  
    2.  <span data-ttu-id="32bfd-139">Lea la información en la pantalla de bienvenida y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-139">Read the information on the welcome screen, and then click **Next**.</span></span>  
  
    3.  <span data-ttu-id="32bfd-140">En el **Seleccionar origen de datos** diálogo cuadro, elija la **origen de datos compartido** opción, seleccione la **SAPDataSource** que creó en el paso anterior y, a continuación, haga clic en  **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-140">In the **Select the Data Source** dialog box, choose the **Shared data source** option, select the **SAPDataSource** you created in the previous step, and then click **Next**.</span></span>  
  
    4.  <span data-ttu-id="32bfd-141">Si ha elegido el **pedir credenciales** opción para especificar las credenciales de usuario al crear el origen de datos, un **escribir credenciales de origen de datos** aparece el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="32bfd-141">If you chose the **Prompt for credentials** option to specify the user credentials while creating the data source, an **Enter Data Source Credentials** dialog box appears.</span></span> <span data-ttu-id="32bfd-142">Especificar el nombre de usuario y una contraseña para conectarse al sistema SAP y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-142">Specify the user name and password to connect to the SAP system, and then click **OK**.</span></span>  
  
         <span data-ttu-id="32bfd-143">Si elige cualquier otra opción para especificar las credenciales, el asistente continúa con el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="32bfd-143">If you chose any other option for specifying credentials, the wizard proceeds to the next step.</span></span>  
  
    5.  <span data-ttu-id="32bfd-144">En el **diseñar la consulta** cuadro de diálogo, especifique una cadena de consulta que se usa para generar un informe.</span><span class="sxs-lookup"><span data-stu-id="32bfd-144">In the **Design the Query** dialog box, specify a query string that is used to generate a report.</span></span> <span data-ttu-id="32bfd-145">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="32bfd-145">For example:</span></span>  
  
        ```  
        SELECT TOP 2 KUNNR, NAME1 FROM KNA1 WHERE NAME1 LIKE @PARAM  
        ```  
  
         <span data-ttu-id="32bfd-146">Esta consulta recuperará los dos registros superiores de la tabla de KNA1 donde el nombre1 es el nombre que se especifican al generar el informe.</span><span class="sxs-lookup"><span data-stu-id="32bfd-146">This query will retrieve the top two records from the KNA1 table where the NAME1 is the name that you will specify while generating the report.</span></span>  
  
         <span data-ttu-id="32bfd-147">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-147">Click **Next**.</span></span>  
  
    6.  <span data-ttu-id="32bfd-148">En los cuadros de diálogo siguientes puede diseñar el formato en el que desea que aparezca el informe.</span><span class="sxs-lookup"><span data-stu-id="32bfd-148">In the subsequent dialog boxes you can design the format in which you want the report to appear.</span></span> <span data-ttu-id="32bfd-149">Si desea usar el formato predeterminado, haga clic en **finalizar >> &#124;** para ir directamente a la **finalizar** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="32bfd-149">If you want to use the default format, click **Finish >>&#124;** to directly go to the **Finish** dialog box.</span></span>  
  
    7.  <span data-ttu-id="32bfd-150">En el **finalización del Asistente para** cuadro de diálogo, especifique un nombre para el informe, revise el resumen y, a continuación, haga clic en **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="32bfd-150">In the **Completing the Wizard** dialog box, specify a name for the report, review the summary, and then click **Finish**.</span></span> <span data-ttu-id="32bfd-151">De este tema, especifique el nombre del informe como `SAPReport`.</span><span class="sxs-lookup"><span data-stu-id="32bfd-151">For this topic, specify the name of the report as `SAPReport`.</span></span>  
  
     <span data-ttu-id="32bfd-152">Ahora puede ver el informe.</span><span class="sxs-lookup"><span data-stu-id="32bfd-152">You can now view the report.</span></span> <span data-ttu-id="32bfd-153">Para obtener instrucciones sobre cómo ver el informe, vea [ver los informes de SAP](../../adapters-and-accelerators/adapter-sap/view-the-reports-for-sap.md).</span><span class="sxs-lookup"><span data-stu-id="32bfd-153">For instructions about how to view the report, see [view the Reports for SAP](../../adapters-and-accelerators/adapter-sap/view-the-reports-for-sap.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32bfd-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="32bfd-154">See Also</span></span>  
 [<span data-ttu-id="32bfd-155">Usar el proveedor de datos para SAP con SSRS</span><span class="sxs-lookup"><span data-stu-id="32bfd-155">Use the Data Provider for SAP with SSRS</span></span>](../../adapters-and-accelerators/adapter-sap/use-the-data-provider-for-sap-with-ssrs.md)