---
title: Generar y publicar formularios de MT MX en el sitio de SharePoint | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4adf7117-11ad-4a8e-8d6a-fd78c5e496a3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c8bd8248a916d1e98571551a8561119b6377329
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="generating-and-publishing-mtmx-forms-on-the-sharepoint-site"></a><span data-ttu-id="0a00d-102">Generar y publicar formularios de MT/MX en el sitio de SharePoint</span><span class="sxs-lookup"><span data-stu-id="0a00d-102">Generating and Publishing MT/MX Forms on the SharePoint Site</span></span>
<span data-ttu-id="0a00d-103">**Para generar y publicar MT/MX formularios en un sitio de SharePoint:**</span><span class="sxs-lookup"><span data-stu-id="0a00d-103">**To generate and publish MT/MX forms on a SharePoint site:**</span></span>  
  
1.  <span data-ttu-id="0a00d-104">Descargar la utilidad de generador del formulario y lo guarda localmente en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0a00d-104">Download the Form Generator Utility and save it locally on the computer.</span></span>  
  
2.  <span data-ttu-id="0a00d-105">Abra la **FormGenerator.sln** desde la carpeta descargó anteriormente y compile la solución.</span><span class="sxs-lookup"><span data-stu-id="0a00d-105">Open the **FormGenerator.sln** from the folder downloaded above and compile the solution.</span></span>  
  
3.  <span data-ttu-id="0a00d-106">En un símbolo del sistema, tener acceso a la carpeta del archivo ejecutable compilado (FormGenerator.exe).</span><span class="sxs-lookup"><span data-stu-id="0a00d-106">At a command prompt, access the folder of compiled executable (FormGenerator.exe).</span></span> <span data-ttu-id="0a00d-107">Por ejemplo, si ha creado la utilidad en modo de depuración, tener acceso a la **... \bin\Debug** carpeta.</span><span class="sxs-lookup"><span data-stu-id="0a00d-107">For example, if you have built the utility in debug mode, access the **..\bin\debug** folder.</span></span>  
  
4.  <span data-ttu-id="0a00d-108">Escriba FormGenerator.exe [-b] [-\<no.</span><span class="sxs-lookup"><span data-stu-id="0a00d-108">Type FormGenerator.exe [-b] [-\<No.</span></span> <span data-ttu-id="0a00d-109">de las rutas de acceso de carpeta de plantilla\>]</span><span class="sxs-lookup"><span data-stu-id="0a00d-109">of Template folder paths\>]</span></span>  
  
     <span data-ttu-id="0a00d-110">`<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`.</span><span class="sxs-lookup"><span data-stu-id="0a00d-110">`<TemplateFolderPath> <DestinationFolderPath> <DocumentSchemaLocation> {[<SpaceSeparatedDocumentSchemaList>] | [-f <NameOfFileContainingSchemaList>]}`.</span></span> <span data-ttu-id="0a00d-111">Reemplace los parámetros con los nombres de carpeta recién creada.</span><span class="sxs-lookup"><span data-stu-id="0a00d-111">Replace the parameters with the newly-created folder names.</span></span>  
  
5.  <span data-ttu-id="0a00d-112">El comando anterior también generará el esquema de sobres necesario para la reparación de mensajes de MX.</span><span class="sxs-lookup"><span data-stu-id="0a00d-112">The above command will also generate the Envelope schema needed for MX message repair.</span></span>  
  
6.  <span data-ttu-id="0a00d-113">Vaya a la carpeta de salida \<DestinationFolderPath\>.</span><span class="sxs-lookup"><span data-stu-id="0a00d-113">Go to output folder \<DestinationFolderPath\>.</span></span> <span data-ttu-id="0a00d-114">En \<DestinationFolderPath\>, abra la carpeta de la plantilla de formulario de InfoPath para los que desea generar el formulario.</span><span class="sxs-lookup"><span data-stu-id="0a00d-114">In \<DestinationFolderPath\>, open the folder of the InfoPath form template for which you want to generate the form.</span></span> <span data-ttu-id="0a00d-115">Por ejemplo, si desea generar el formulario de InfoPath MT103, a continuación, abra la carpeta MT103 en la DestinationFolderPath y abra el TemplateDS.sln.</span><span class="sxs-lookup"><span data-stu-id="0a00d-115">For example, if you want to generate the MT103 InfoPath form, then open the MT103 folder at the DestinationFolderPath and open the TemplateDS.sln.</span></span>  
  
7.  <span data-ttu-id="0a00d-116">En el Explorador de soluciones, haga doble clic en el **manifest.xsf**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-116">In the Solution Explorer, double click the **manifest.xsf**.</span></span> <span data-ttu-id="0a00d-117">Se abrirá el archivo de diseño del formulario de InfoPath que tardará algún tiempo en obtener abierto.</span><span class="sxs-lookup"><span data-stu-id="0a00d-117">It will open the design file of the InfoPath form which will take some time to get opened.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0a00d-118">El archivo manifest.xsf mensajes de MX puede tardar 2 y 5 minutos en obtener abierto.</span><span class="sxs-lookup"><span data-stu-id="0a00d-118">The MX messages manifest.xsf might take 2-5 minutes to get opened.</span></span>  
  
8.  <span data-ttu-id="0a00d-119">En el archivo manifest.xsf, vaya a **Herramientas -> Opciones de formato - > seguridad y confianza** opción de menú.</span><span class="sxs-lookup"><span data-stu-id="0a00d-119">In the manifest.xsf, go to **Tools ->Form Options-> Security and Trust** menu option.</span></span> <span data-ttu-id="0a00d-120">Compruebe el **plena confianza** opción debe estar habilitada para el permiso.</span><span class="sxs-lookup"><span data-stu-id="0a00d-120">Check the **Full Trust** option must be enabled for the permission.</span></span>  
  
9. <span data-ttu-id="0a00d-121">Seleccione el **firmar esta plantilla de formulario** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="0a00d-121">Select the **Sign this form Template** checkbox.</span></span> <span data-ttu-id="0a00d-122">Haga clic en **Seleccionar certificado**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-122">Click **Select certificate**.</span></span> <span data-ttu-id="0a00d-123">En este caso, seleccione el certificado con el que va a firmar el formulario.</span><span class="sxs-lookup"><span data-stu-id="0a00d-123">In this, select the certificate with which you want to sign the form.</span></span> <span data-ttu-id="0a00d-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-124">Click **OK**.</span></span>  
  
10. <span data-ttu-id="0a00d-125">Guardar **manifest.xsf**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-125">Save **manifest.xsf**.</span></span>  
  
11. <span data-ttu-id="0a00d-126">Vaya a **Ver -> tareas de diseño**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-126">Go to **View -> Design Tasks**.</span></span> <span data-ttu-id="0a00d-127">En el panel de tareas de diseño, haga clic en **publicar la plantilla de formulario** opción.</span><span class="sxs-lookup"><span data-stu-id="0a00d-127">On the Design Tasks pane, click **Publish Form Template** option.</span></span>  
  
12. <span data-ttu-id="0a00d-128">En la ventana del Asistente para publicación, seleccione **a una ubicación de red** y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-128">In the publishing wizard window, select **To a network location** and click **Next**.</span></span>  
  
13. <span data-ttu-id="0a00d-129">En el formulario plantilla ruta de acceso y cuadro de texto Nombre, escriba **http://localhost/sites/BASSite/Templates/\<MessageType\>.xsn** y tipo  **\<MessageType\>**  en la plantilla de formulario de cuadro de texto Nombre y haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-129">In the Form template path and file name textbox, type **http://localhost/sites/BASSite/Templates/\<MessageType\>.xsn** and type **\<MessageType\>** in the Form Template name textbox and click **Next**.</span></span>  
  
14. <span data-ttu-id="0a00d-130">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-130">Click **Next**.</span></span>  
  
15. <span data-ttu-id="0a00d-131">Haga clic en **publicar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-131">Click **Publish and close**.</span></span>  
  
16. <span data-ttu-id="0a00d-132">En Internet Explorer, abra el sitio de SharePoint **http://localhost/sites/bassite/templates**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-132">In the Internet Explorer, open your SharePoint site **http://localhost/sites/bassite/templates**.</span></span>  
  
17. <span data-ttu-id="0a00d-133">Seleccione  **\<MessageType\>**, haga clic en la flecha abajo situada junto a él y, a continuación, haga clic en **editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-133">Point to **\<MessageType\>**, click the down arrow next to it, and then click **Edit Properties**.</span></span>  
  
18. <span data-ttu-id="0a00d-134">En las plantillas:\< MessageType\> ventana, en el cuadro Namespace:</span><span class="sxs-lookup"><span data-stu-id="0a00d-134">In the Templates:\< MessageType\> window, in the Namespace box:</span></span>  
  
    -   <span data-ttu-id="0a00d-135">Si va a generar los formularios de InfoPath de MT, escriba: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**</span><span class="sxs-lookup"><span data-stu-id="0a00d-135">If you are generating MT InfoPath forms, type: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMTxxx**</span></span>  
  
    -   <span data-ttu-id="0a00d-136">Si va a generar los formularios de InfoPath MX, escriba: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX _\<MessageName\>**</span><span class="sxs-lookup"><span data-stu-id="0a00d-136">If you are generating MX InfoPath forms, type: **http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/EnvelopeMX_\<MessageName\>**</span></span>  
  
         <span data-ttu-id="0a00d-137">Esto le ayudará a identificar la instancia de mensaje con la plantilla correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0a00d-137">This will help in identifying the message instance with the corresponding template.</span></span>  
  
19. <span data-ttu-id="0a00d-138">Haga clic en **guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0a00d-138">Click **Save and Close**.</span></span>