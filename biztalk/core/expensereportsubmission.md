---
title: ExpenseReportSubmission | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
ms.assetid: d0bacab3-7092-44b8-a1c6-6f574a2db8bd
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09cec8e16b8b145206a2cd6b2a30859e502ce8b3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967901"
---
# <a name="expensereportsubmission"></a><span data-ttu-id="c5513-102">ExpenseReportSubmission</span><span class="sxs-lookup"><span data-stu-id="c5513-102">ExpenseReportSubmission</span></span>
<span data-ttu-id="c5513-103">El ejemplo ExpenseReportSubmission indica cómo enviar un documento a una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde una aplicación cliente enriquecida como Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="c5513-103">The ExpenseReportSubmission sample demonstrates how to submit a document to a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration from a rich client such as Microsoft Excel.</span></span>  

 <span data-ttu-id="c5513-104">Las aplicaciones cliente enriquecidas le permiten realizar una serie de acciones, como la validación de datos y cálculos previos, en el equipo cliente.</span><span class="sxs-lookup"><span data-stu-id="c5513-104">Rich clients enable you to perform a number of actions, such as data validation and preliminary calculations, on the client.</span></span> <span data-ttu-id="c5513-105">Esto ayuda a minimizar las interacciones con el servidor de servicios de fondo, lo que puede resultar útil cuando solo hay disponibles conexiones con poco ancho de banda.</span><span class="sxs-lookup"><span data-stu-id="c5513-105">This helps to minimize interactions with the back-end server, which can be useful when only low bandwidth connections are available.</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="c5513-106">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c5513-106">Prerequisites</span></span>  
 <span data-ttu-id="c5513-107">Debe asegurarse de que el entorno de desarrollo está configurado y habilitado para funcionar con los servicios web de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5513-107">You must ensure that your development environment is configured and enabled to work with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Web services.</span></span> <span data-ttu-id="c5513-108">Para obtener más información, consulte [habilitar los servicios Web](../core/enabling-web-services.md).</span><span class="sxs-lookup"><span data-stu-id="c5513-108">For more information, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="c5513-109">Descripción del ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5513-109">What This Sample Does</span></span>  
 <span data-ttu-id="c5513-110">Este ejemplo indica cómo enviar un informe de gastos a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directamente desde Excel, mediante la siguiente secuencia de pasos:</span><span class="sxs-lookup"><span data-stu-id="c5513-110">This sample shows how you can submit an expense report to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directly from Excel, using the following sequence of steps:</span></span>  

1. <span data-ttu-id="c5513-111">El usuario realiza los pasos manuales del ejemplo que se proporcionan en la hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="c5513-111">The user performs the manual sample steps provided in the Excel spreadsheet.</span></span>  

2. <span data-ttu-id="c5513-112">El código de macros de la hoja de cálculo convierte los datos de ésta en formato de Lenguaje de marcado extensible (XML) y, mediante una conexión HTTP, envía el mensaje XML a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5513-112">Macro code in the spreadsheet converts the spreadsheet data to Extensible Markup Language (XML) format, and submits the XML message to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] using an HTTP connection.</span></span>  

3. <span data-ttu-id="c5513-113">El equipo que está ejecutando [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recupera el mensaje de informe de gastos XML, valida su formato usando el esquema proporcionado y lo coloca en una carpeta distinta.</span><span class="sxs-lookup"><span data-stu-id="c5513-113">The computer running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] retrieves the XML expense report message, validates its format using the provided schema, and then drops it into a different folder.</span></span>  

4. <span data-ttu-id="c5513-114">En la práctica, más allá del alcance de este ejemplo, otra aplicación como, por ejemplo, un sistema de planeamiento de recursos empresariales (ERP) recuperaría el archivo de la hoja de cálculo para un procesamiento posterior.</span><span class="sxs-lookup"><span data-stu-id="c5513-114">In practice, beyond the scope of this sample, another application such as an Enterprise Resource Planning (ERP) system would then retrieve the spreadsheet file for further processing.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="c5513-115">Ubicación del ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5513-115">Where to Find This Sample</span></span>  
 <span data-ttu-id="c5513-116">\<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\ExpenseReportSubmission\\</span><span class="sxs-lookup"><span data-stu-id="c5513-116">\<*Samples Path*\>\AdaptersUsage\ExpenseReportSubmission\\</span></span>  

 <span data-ttu-id="c5513-117">En la tabla siguiente se enumeran los archivos del ejemplo y se describe su propósito.</span><span class="sxs-lookup"><span data-stu-id="c5513-117">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                                            <span data-ttu-id="c5513-118">Archivos</span><span class="sxs-lookup"><span data-stu-id="c5513-118">File(s)</span></span>                                                            |                                                                                           <span data-ttu-id="c5513-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5513-119">Description</span></span>                                                                                            |
|-------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                          <span data-ttu-id="c5513-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="c5513-120">Cleanup.bat</span></span>                                                          | <span data-ttu-id="c5513-121">Anula la implementación de ensamblados y los elimina de la caché de ensamblados global (GAC); elimina puertos de envío y de recepción; elimina directorios virtuales de los Servicios de Microsoft Internet Information Server (IIS) según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="c5513-121">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span> |
|                                                    <span data-ttu-id="c5513-122">ExpenseReport.15.3.xls</span><span class="sxs-lookup"><span data-stu-id="c5513-122">ExpenseReport.15.3.xls</span></span>                                                     |                                              <span data-ttu-id="c5513-123">Hoja de cálculo de Excel con el diseño de informe de gastos, macros asociadas y botones para invocar las macros.</span><span class="sxs-lookup"><span data-stu-id="c5513-123">Excel spreadsheet with the expense report layout, associated macros, and buttons to invoke the macros.</span></span>                                              |
|                                                      <span data-ttu-id="c5513-124">MessageExample.xml</span><span class="sxs-lookup"><span data-stu-id="c5513-124">MessageExample.xml</span></span>                                                       |                                                                            <span data-ttu-id="c5513-125">Ejemplo de formato de informe de gastos XML.</span><span class="sxs-lookup"><span data-stu-id="c5513-125">Example of the XML expense report format.</span></span>                                                                             |
|                                                           <span data-ttu-id="c5513-126">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="c5513-126">Setup.bat</span></span>                                                           |                                                                               <span data-ttu-id="c5513-127">Crea e inicializa este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c5513-127">Builds and initializes this sample.</span></span>                                                                                |
| <span data-ttu-id="c5513-128">En la carpeta \BTSExpenseDemo:</span><span class="sxs-lookup"><span data-stu-id="c5513-128">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="c5513-129">AssemblyInfo.cs,</span><span class="sxs-lookup"><span data-stu-id="c5513-129">AssemblyInfo.cs,</span></span><br /><br /> <span data-ttu-id="c5513-130">BTSExpenseDemo.btproj,</span><span class="sxs-lookup"><span data-stu-id="c5513-130">BTSExpenseDemo.btproj,</span></span><br /><br /> <span data-ttu-id="c5513-131">BTSExpenseDemo.sln</span><span class="sxs-lookup"><span data-stu-id="c5513-131">BTSExpenseDemo.sln</span></span> |                                                                  <span data-ttu-id="c5513-132">Proporciona archivos de proyectos, de soluciones y archivos relacionados para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c5513-132">Provides project, solution, and related files for this sample.</span></span>                                                                  |
|                             <span data-ttu-id="c5513-133">En la carpeta \BTSExpenseDemo:</span><span class="sxs-lookup"><span data-stu-id="c5513-133">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="c5513-134">BTSExpenseDemoBinding.xml</span><span class="sxs-lookup"><span data-stu-id="c5513-134">BTSExpenseDemoBinding.xml</span></span>                              |                                                                         <span data-ttu-id="c5513-135">Se utiliza para la instalación automatizada, como el enlace de puertos.</span><span class="sxs-lookup"><span data-stu-id="c5513-135">Used for automated setup, such as port binding.</span></span>                                                                          |
|                            <span data-ttu-id="c5513-136">En la carpeta \BTSExpenseDemo:</span><span class="sxs-lookup"><span data-stu-id="c5513-136">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="c5513-137">BTSExpenseOrchestration.odx</span><span class="sxs-lookup"><span data-stu-id="c5513-137">BTSExpenseOrchestration.odx</span></span>                             |                                   <span data-ttu-id="c5513-138">Proporciona una orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c5513-138">Provides a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for this sample.</span></span>                                   |
|                              <span data-ttu-id="c5513-139">En la carpeta \BTSExpenseDemo:</span><span class="sxs-lookup"><span data-stu-id="c5513-139">In the \BTSExpenseDemo folder:</span></span><br /><br /> <span data-ttu-id="c5513-140">SchemaExpenseReport.xsd</span><span class="sxs-lookup"><span data-stu-id="c5513-140">SchemaExpenseReport.xsd</span></span>                               |                                                                       <span data-ttu-id="c5513-141">Proporciona un esquema para el formato de informe de gastos XML.</span><span class="sxs-lookup"><span data-stu-id="c5513-141">Provides a schema for the XML expense report format.</span></span>                                                                       |

### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="c5513-142">Para generar e inicializar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5513-142">To build and initialize this sample</span></span>  

1. <span data-ttu-id="c5513-143">En una ventana de comandos, desplácese a la siguiente carpeta:</span><span class="sxs-lookup"><span data-stu-id="c5513-143">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="c5513-144">\<*Ejemplos de la ruta de acceso*\>\AdaptersUsage\ExpenseReportSubmission</span><span class="sxs-lookup"><span data-stu-id="c5513-144">\<*Samples Path*\>\AdaptersUsage\ExpenseReportSubmission</span></span>  

2. <span data-ttu-id="c5513-145">Ejecute el archivo Setup.bat que realiza las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5513-145">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="c5513-146">Compila el proyecto de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para este ejemplo e implementa el ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="c5513-146">Compiles the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] project for this sample, and deploys the resulting assembly.</span></span>  

   - <span data-ttu-id="c5513-147">Crea y enlaza los puertos de envío y recepción de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5513-147">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="c5513-148">Este ejemplo muestra las siguientes advertencias al crear y enlazar los puertos:</span><span class="sxs-lookup"><span data-stu-id="c5513-148">This sample displays the following warnings when creating and binding the ports:</span></span>  
     >   
     >  `Warning: Receive handler not specified for receive location "BTSExpenseReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  <span data-ttu-id="c5513-149">`Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.BTSExpenseDemo.BTSOrchestration"; updating with first available host`.</span><span class="sxs-lookup"><span data-stu-id="c5513-149">`Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.BTSExpenseDemo.BTSOrchestration"; updating with first available host`.</span></span>  
     >   
     >  <span data-ttu-id="c5513-150">Puede omitir estas advertencias de forma segura.</span><span class="sxs-lookup"><span data-stu-id="c5513-150">You can safely ignore these warnings.</span></span> <span data-ttu-id="c5513-151">(Para dar cabida a posibles diferencias de nombre en las instalaciones de usuario, se han omitido del archivo de enlace el nombre del host y el controlador de recepción).</span><span class="sxs-lookup"><span data-stu-id="c5513-151">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  

   - <span data-ttu-id="c5513-152">Habilita la ubicación de recepción e inicia el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="c5513-152">Enables the receive location, and starts the send port.</span></span>  

   - <span data-ttu-id="c5513-153">Configura IIS.</span><span class="sxs-lookup"><span data-stu-id="c5513-153">Configures IIS.</span></span>  

   - <span data-ttu-id="c5513-154">Enlaza e inicia la orquestación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c5513-154">Binds and starts the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration.</span></span>  

   - <span data-ttu-id="c5513-155">Establece la dirección HTTP para la ubicación que espera la hoja de cálculo de Excel.</span><span class="sxs-lookup"><span data-stu-id="c5513-155">Sets the HTTP address to the location expected by the Excel spreadsheet.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="c5513-156">Para obtener más información sobre el filtro ISAPI de BizTalk, consulte [cómo configurar IIS para una ubicación de recepción HTTP](../core/how-to-configure-iis-for-an-http-receive-location.md).</span><span class="sxs-lookup"><span data-stu-id="c5513-156">For more information about the BizTalk ISAPI filter, see [How to Configure IIS for an HTTP Receive Location](../core/how-to-configure-iis-for-an-http-receive-location.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="c5513-157">Antes de intentar ejecutar este ejemplo, debe confirmar que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no ha informado de ningún error durante el proceso de generación e inicialización.</span><span class="sxs-lookup"><span data-stu-id="c5513-157">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="c5513-158">Si selecciona abrir y crear el proyecto de este ejemplo sin ejecutar el archivo Setup.bat, debe crear, en primer lugar, un par de claves de nombre seguro mediante la Utilidad de nombre seguro de .NET Framework (sn.exe).</span><span class="sxs-lookup"><span data-stu-id="c5513-158">If you choose to open and build the project in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="c5513-159">Utilice este par de claves para firmar el ensamblado resultante.</span><span class="sxs-lookup"><span data-stu-id="c5513-159">Use this key pair to sign the resulting assembly.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="c5513-160">Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat.</span><span class="sxs-lookup"><span data-stu-id="c5513-160">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="c5513-161">Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat por segunda vez.</span><span class="sxs-lookup"><span data-stu-id="c5513-161">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

3. <span data-ttu-id="c5513-162">El archivo setup.bat configura el directorio virtual de este ejemplo para ejecutarlo en el grupo de aplicaciones de IIS asociado al sitio Web predeterminado.</span><span class="sxs-lookup"><span data-stu-id="c5513-162">The setup.bat file configures the virtual directory for this sample to run in the IIS application pool associated with the default web site.</span></span>  <span data-ttu-id="c5513-163">Para configurar el directorio virtual para este ejemplo y ejecutarlo en el contexto de un usuario en el **usuarios de hosts aislados de BizTalk** y **IIS_WPG** grupos de usuarios, debe configurar el directorio virtual para ejecutarlo en una nueva Grupo de aplicaciones de IIS.</span><span class="sxs-lookup"><span data-stu-id="c5513-163">To configure the virtual directory for this sample to run under the context of a user in the **BizTalk Isolated Host Users** and **IIS_WPG** user groups, you should configure the virtual directory to run in a new IIS application pool.</span></span>  <span data-ttu-id="c5513-164">Configure el directorio virtual para ejecutarlo en un grupo de aplicaciones IIS nuevo realizando los pasos que se indican a continuación:</span><span class="sxs-lookup"><span data-stu-id="c5513-164">Configure the virtual directory to run in a new IIS application pool by completing the following steps:</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="c5513-165">Si ya ha creado un grupo de aplicaciones nuevo para otro ejemplo de SDK, puede continuar con el último punto que aparece más abajo.</span><span class="sxs-lookup"><span data-stu-id="c5513-165">If you have already created a new application pool for another SDK sample then you can proceed to the last bullet item below.</span></span>  

   1.  <span data-ttu-id="c5513-166">Haga clic en **iniciar**, apunte a **programas**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="c5513-166">Click **Start**, point to **Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  

   2.  <span data-ttu-id="c5513-167">En el **Internet Information Services (IIS) Manager**, navegue hasta la **grupos de aplicaciones** carpeta.</span><span class="sxs-lookup"><span data-stu-id="c5513-167">In the **Internet Information Services (IIS) Manager**, navigate to the **Application Pools** folder.</span></span>  

   3.  <span data-ttu-id="c5513-168">Haga clic en el **grupos de aplicaciones** carpeta y haga clic en **New**, **grupo de aplicaciones...**</span><span class="sxs-lookup"><span data-stu-id="c5513-168">Right-click the **Application Pools** folder and click **New**, **Application Pool...**</span></span>  

   4.  <span data-ttu-id="c5513-169">Escriba un nombre para el **Id. de grupo de aplicaciones:** como BizTalkSDKSamples, compruebe que la **usar configuración predeterminada para el nuevo grupo de aplicaciones** opción está seleccionada y haga clic en **Aceptar** a Crear nuevo grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="c5513-169">Enter a name for the **Application Pool ID:** such as BizTalkSDKSamples, verify that the **Use default settings for new application pool** option is selected and click **OK** to create the new application pool.</span></span>  

   5.  <span data-ttu-id="c5513-170">Haga clic en el nuevo grupo de aplicaciones y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="c5513-170">Right-click the new application pool and then click **Properties**.</span></span>  

   6.  <span data-ttu-id="c5513-171">Haga clic en el **identidad** ficha del cuadro de diálogo de propiedades cuadro y cambiar la identidad bajo la que se ejecuta este grupo de aplicaciones a un usuario que sea miembro de la **usuarios de hosts aislados de BizTalk** grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="c5513-171">Click the **Identity** tab of the properties dialog box and change the identity under which this application pool runs to a user that is a member of the **BizTalk Isolated Host Users** user group.</span></span>  <span data-ttu-id="c5513-172">Este usuario también debe ser miembro de la variable local **IIS_WPG** grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="c5513-172">This user should also be a member of the local **IIS_WPG** user group.</span></span>  

   7.  <span data-ttu-id="c5513-173">Configure el directorio virtual de este ejemplo SDK para ejecutarlo en el grupo de aplicaciones nuevo.</span><span class="sxs-lookup"><span data-stu-id="c5513-173">Configure the virtual directory for this SDK sample to run under the new application pool.</span></span> <span data-ttu-id="c5513-174">El **grupo de aplicaciones:** opción está disponible en el **directorio Virtual** ficha del cuadro de diálogo de propiedades de directorio Virtual.</span><span class="sxs-lookup"><span data-stu-id="c5513-174">The **Application pool:** setting is available on the **Virtual Directory** tab of the Virtual Directory properties dialog box.</span></span> <span data-ttu-id="c5513-175">El directorio virtual creado para este ejemplo es **ExpenseReportSubmission**.</span><span class="sxs-lookup"><span data-stu-id="c5513-175">The virtual directory created for this sample is **ExpenseReportSubmission**.</span></span>  

4. <span data-ttu-id="c5513-176">Agregue una extensión de servicio Web a IIS para HTTPReceive.dll</span><span class="sxs-lookup"><span data-stu-id="c5513-176">Add a web service extension to IIS for HTTPReceive.dll</span></span>  

   1.  <span data-ttu-id="c5513-177">En el **Internet Information Services (IIS) Manager**, navegue hasta la **extensiones de servicio Web** carpeta.</span><span class="sxs-lookup"><span data-stu-id="c5513-177">In the **Internet Information Services (IIS) Manager**, navigate to the **Web Service Extensions** folder.</span></span>  

   2.  <span data-ttu-id="c5513-178">Haga clic en el **extensiones de servicio Web** carpeta y seleccione **agregar una nueva extensión de servicio Web** para mostrar el **nueva extensión de servicio Web** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c5513-178">Right-click the **Web Service Extensions** folder and select **Add a new Web service extension** to display the **New Web Service Extension** dialog box.</span></span>  

   3.  <span data-ttu-id="c5513-179">Escriba **ExpenseReportSubmission** para **nombre de la extensión:**</span><span class="sxs-lookup"><span data-stu-id="c5513-179">Enter **ExpenseReportSubmission** for **Extension name:**</span></span>  

   4.  <span data-ttu-id="c5513-180">Haga clic en **agregar** para mostrar el **Agregar archivo** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="c5513-180">Click **Add** to display the **Add file** dialog box.</span></span>  

   5.  <span data-ttu-id="c5513-181">Haga clic en **examinar** para mostrar el **abierto** diálogo cuadro y vaya a  *\<carpeta de instalación de BizTalk Server\>* \HttpReceive\ BTSHTTPReceive.dll y haga clic en **abierto**, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c5513-181">Click **Browse** to display the **Open** dialog box and navigate to *\<BizTalk Server Installation folder\>* \HttpReceive\BTSHTTPReceive.dll and click **Open**, then click **OK**.</span></span>  

   6.  <span data-ttu-id="c5513-182">Habilitar la opción de **Establecer estado de la extensión a permitido** y haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="c5513-182">Enable the option to **Set extension status to Allowed** and click **OK**.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="c5513-183">Ejecución del ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5513-183">Running This Sample</span></span>  
 <span data-ttu-id="c5513-184">Utilice el siguiente procedimiento para ejecutar el ejemplo ExpenseReportSubmission.</span><span class="sxs-lookup"><span data-stu-id="c5513-184">Use the following procedure to run the ExpenseReportSubmission sample.</span></span>  

> [!NOTE]
>  <span data-ttu-id="c5513-185">Si está utilizando las características de seguridad mejorada de Microsoft Excel, es posible que las macros estén deshabilitadas en la hoja de cálculo.</span><span class="sxs-lookup"><span data-stu-id="c5513-185">If you are using the enhanced security features of Microsoft Excel, the macros in the spreadsheet may be disabled.</span></span> <span data-ttu-id="c5513-186">Siga las instrucciones proporcionadas por Excel sobre cómo ejecutar macros no asignadas desde una fuente confiable.</span><span class="sxs-lookup"><span data-stu-id="c5513-186">Follow the instructions provided by Excel about how to run unsigned macros from a trusted source.</span></span>  

#### <a name="to-run-this-sample"></a><span data-ttu-id="c5513-187">Para ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="c5513-187">To run this sample</span></span>  

1.  <span data-ttu-id="c5513-188">Abra el archivo de Excel ExpenseReport.15.3.xls que se incluye con este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c5513-188">Open the Excel file ExpenseReport.15.3.xls included with this sample.</span></span>  

2.  <span data-ttu-id="c5513-189">Si lo desea, cambie los datos del ejemplo en la hoja de cálculo sin cambiar su formato.</span><span class="sxs-lookup"><span data-stu-id="c5513-189">Optionally, change the sample data in the spreadsheet without changing its format.</span></span>  

3.  <span data-ttu-id="c5513-190">En la hoja de cálculo, haga clic en **iniciar** para realizar cálculos locales.</span><span class="sxs-lookup"><span data-stu-id="c5513-190">In the spreadsheet, click **Start** to perform local calculations.</span></span>  

     <span data-ttu-id="c5513-191">El texto del botón cambia de **iniciar** a **enviar**.</span><span class="sxs-lookup"><span data-stu-id="c5513-191">The text of the button changes from **Start** to **Submit**.</span></span>  

4.  <span data-ttu-id="c5513-192">En la hoja de cálculo, haga clic en **enviar**.</span><span class="sxs-lookup"><span data-stu-id="c5513-192">In the spreadsheet, click **Submit**.</span></span>  

5.  <span data-ttu-id="c5513-193">Observe el texto del mensaje enviado, el resultado en la parte superior de la tabla con el fondo amarillo (celda C7) y el código devuelto y la descripción de texto en la parte inferior y a la derecha (celda G23).</span><span class="sxs-lookup"><span data-stu-id="c5513-193">Observe the text of the submitted message, the result above the table with yellow background (cell C7), and the actual return code and text description below and to the right (cell G23).</span></span>  

     <span data-ttu-id="c5513-194">Si el envío no se produce correctamente, vuelva a intentarlo.</span><span class="sxs-lookup"><span data-stu-id="c5513-194">If submission fails, try again.</span></span> <span data-ttu-id="c5513-195">Además, vea la tabla de solución de problemas que aparece en la sección Comentarios.</span><span class="sxs-lookup"><span data-stu-id="c5513-195">Also, refer to the troubleshooting table in the Comments section.</span></span>  

## <a name="comments"></a><span data-ttu-id="c5513-196">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c5513-196">Comments</span></span>  
 <span data-ttu-id="c5513-197">Escenarios como éste se pueden dar cuando, por ejemplo, un equipo de ventas de campo está equipado con versiones anteriores de Microsoft Windows que no admiten .NET Framework y para el que no es viable el requisito de actualizar a una versión más actual.</span><span class="sxs-lookup"><span data-stu-id="c5513-197">Scenarios such as this can occur when, for example, a field sales force is equipped with older versions of Microsoft Windows that do not support the .NET Framework, and for which the requirement to upgrade to a more current version of Windows is not a viable option.</span></span>  

 <span data-ttu-id="c5513-198">Las características esenciales que se muestran en este ejemplo son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="c5513-198">Essential features demonstrated in this sample are:</span></span>  

- <span data-ttu-id="c5513-199">Envío desde una aplicación cliente enriquecida (que no esté basada en .NET)</span><span class="sxs-lookup"><span data-stu-id="c5513-199">Submission from a rich client (not .NET-based)</span></span>  

- <span data-ttu-id="c5513-200">Integración con Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="c5513-200">Microsoft Office integration</span></span>  

- <span data-ttu-id="c5513-201">Conexiones de recepción HTTP</span><span class="sxs-lookup"><span data-stu-id="c5513-201">HTTP receive connections</span></span>  

- <span data-ttu-id="c5513-202">Orquestaciones sencillas</span><span class="sxs-lookup"><span data-stu-id="c5513-202">Simple orchestration</span></span>  

- <span data-ttu-id="c5513-203">Adaptador de archivo</span><span class="sxs-lookup"><span data-stu-id="c5513-203">File adapter</span></span>  

  <span data-ttu-id="c5513-204">En la siguiente tabla se muestran algunos posibles errores de envío y sus soluciones.</span><span class="sxs-lookup"><span data-stu-id="c5513-204">The following table shows some possible submission errors and their solutions.</span></span>  

|<span data-ttu-id="c5513-205">Código de error HTTP</span><span class="sxs-lookup"><span data-stu-id="c5513-205">HTTP error code</span></span>|<span data-ttu-id="c5513-206">Acciones posibles</span><span class="sxs-lookup"><span data-stu-id="c5513-206">Possible action</span></span>|  
|---------------------|---------------------|  
|<span data-ttu-id="c5513-207">401 No autorizado</span><span class="sxs-lookup"><span data-stu-id="c5513-207">401 Unauthorized</span></span>|<span data-ttu-id="c5513-208">Habilitar el acceso anónimo al directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="c5513-208">Enable anonymous access on the virtual directory.</span></span>|  
|<span data-ttu-id="c5513-209">503 Servicio no disponible y la mayoría del resto de códigos HTTP en los rangos 400 y 500</span><span class="sxs-lookup"><span data-stu-id="c5513-209">503 Service Unavailable, and most other HTTP codes in the 400 and 500 ranges</span></span>|<span data-ttu-id="c5513-210">Asegurarse de que se ejecuta el host y de que se ha implementado el servicio, está enlazado al puerto correcto y se ha iniciado.</span><span class="sxs-lookup"><span data-stu-id="c5513-210">Ensure that the host runs and that the service is deployed, bound to the correct port, and started.</span></span>|  

## <a name="see-also"></a><span data-ttu-id="c5513-211">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5513-211">See Also</span></span>  
 [<span data-ttu-id="c5513-212">Ejemplos de adaptadores: uso</span><span class="sxs-lookup"><span data-stu-id="c5513-212">Adapter Samples - Usage</span></span>](../core/adapter-samples-usage.md)