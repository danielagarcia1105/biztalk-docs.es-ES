---
title: "Trabajar en el Diseñador de itinerarios | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 06742cb8-f6d6-46e2-adc0-6be9a3d6a447
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d54d742b883ec843d56610b25fdfb91371dbe4b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="working-in-itinerary-designer"></a><span data-ttu-id="5acea-102">Trabajar en el Diseñador de itinerarios</span><span class="sxs-lookup"><span data-stu-id="5acea-102">Working in Itinerary Designer</span></span>
<span data-ttu-id="5acea-103">Después de crear un proyecto de Microsoft Visual C#, puede crear nuevos modelos itinerarios y agregar itinerarios existentes al proyecto.</span><span class="sxs-lookup"><span data-stu-id="5acea-103">After you create a Microsoft Visual C# project, you can create new itinerary models and add existing itineraries to the project.</span></span> <span data-ttu-id="5acea-104">Los pasos siguientes describen cómo crear un nuevo itinerario, agregar un modelo de itinerarios existente o cambiar el nombre de un itinerario.</span><span class="sxs-lookup"><span data-stu-id="5acea-104">The following steps describe how to create a new itinerary, add an existing itinerary model, or change the name of an itinerary.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5acea-105">Antes de trabajar con el Diseñador de itinerario, debe instalar Microsoft.Practices.ESB.CORE Windows Installer (archivo .msi) desde el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] la carpeta de instalación.</span><span class="sxs-lookup"><span data-stu-id="5acea-105">Before working with the Itinerary Designer, you must install the Microsoft.Practices.ESB.CORE Windows Installer (.msi file) from the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] install folder.</span></span> <span data-ttu-id="5acea-106">Este paso instala a los ensamblados de tiempo de ejecución necesarios a la caché global de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="5acea-106">This step installs the required run-time assemblies to the global assembly cache.</span></span>  
  
## <a name="basic-operations"></a><span data-ttu-id="5acea-107">Operaciones básicas</span><span class="sxs-lookup"><span data-stu-id="5acea-107">Basic Operations</span></span>  

#### <a name="create-an-itinerary"></a><span data-ttu-id="5acea-108">Crear un itinerario</span><span class="sxs-lookup"><span data-stu-id="5acea-108">Create an itinerary</span></span>  
  
1.  <span data-ttu-id="5acea-109">En el Explorador de soluciones, haga clic en el nombre del proyecto de C#, seleccione **agregar**y, a continuación, haga clic en **itinerario nueva**.</span><span class="sxs-lookup"><span data-stu-id="5acea-109">In Solution Explorer, right-click the C# project name, point to **Add**, and then click **New Itinerary**.</span></span>  
  
2.  <span data-ttu-id="5acea-110">En el **nombre** en la parte inferior del cuadro de diálogo, escriba el nombre para el itinerario y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="5acea-110">In the **Name** box at the bottom of the dialog box, type the name for the itinerary, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5acea-111">Se crea y se muestra en el Diseñador de itinerario el itinerario nueva, y se crea un archivo .itinerary correspondiente y se muestra en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="5acea-111">The new itinerary is created and displayed in Itinerary Designer, and a corresponding .itinerary file is created and displayed in Solution Explorer.</span></span>  
  
#### <a name="add-an-existing-itinerary-to-the-project"></a><span data-ttu-id="5acea-112">Agregue un itinerario existente al proyecto</span><span class="sxs-lookup"><span data-stu-id="5acea-112">Add an existing itinerary to the project</span></span>
  
1.  <span data-ttu-id="5acea-113">En el Explorador de soluciones, haga clic con el nombre del proyecto de C#, seleccione **agregar**y, a continuación, haga clic en **elemento existente**.</span><span class="sxs-lookup"><span data-stu-id="5acea-113">In Solution explorer, right click the C# project name, point to **Add**, and then click **Existing Item**.</span></span>  
  
2.  <span data-ttu-id="5acea-114">En el **Agregar elemento existente** cuadro de diálogo, desplácese al directorio que contiene los itinerarios, haga clic en el itinerario y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="5acea-114">In the **Add Existing Item** dialog box, navigate to the directory that contains the itinerary, click the itinerary, and then click **Add**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5acea-115">El itinerario se agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="5acea-115">The itinerary is added to the project.</span></span>  
  
#### <a name="change-the-name-of-an-itinerary"></a><span data-ttu-id="5acea-116">Cambiar el nombre de un itinerario</span><span class="sxs-lookup"><span data-stu-id="5acea-116">Change the name of an itinerary</span></span>  
  
1.  <span data-ttu-id="5acea-117">En el Explorador de soluciones, haga clic en el archivo .itinerary que desea cambiar y, a continuación, haga clic en **cambiar el nombre de**.</span><span class="sxs-lookup"><span data-stu-id="5acea-117">In Solution Explorer, right-click the .itinerary file you want to rename, and then click **Rename**.</span></span>  
  
2.  <span data-ttu-id="5acea-118">Escriba el nuevo nombre de archivo y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="5acea-118">Type the new file name, and then press ENTER.</span></span>  
  
#### <a name="save-an-itinerary"></a><span data-ttu-id="5acea-119">Guardar un itinerario</span><span class="sxs-lookup"><span data-stu-id="5acea-119">Save an itinerary</span></span>  
  
<span data-ttu-id="5acea-120">En el **archivo** menú, haga clic en **guardar \<nombre itinerario >**.</span><span class="sxs-lookup"><span data-stu-id="5acea-120">On the **File** menu, click **Save \<itinerary name>**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5acea-121">Archivos itinerarios se guardan como modelos DSL en formato XML correspondiente.</span><span class="sxs-lookup"><span data-stu-id="5acea-121">Itinerary files are saved as DSL models in corresponding XML format.</span></span>  
  
#### <a name="set-itinerary-export-properties"></a><span data-ttu-id="5acea-122">Establecer las propiedades de exportación itinerarios</span><span class="sxs-lookup"><span data-stu-id="5acea-122">Set itinerary export properties</span></span>  
  
1.  <span data-ttu-id="5acea-123">En la ventana Propiedades, escriba un **nombre** propiedad.</span><span class="sxs-lookup"><span data-stu-id="5acea-123">In the Properties window, type a **Name** property.</span></span>  
  
2.  <span data-ttu-id="5acea-124">En la ventana Propiedades, escriba un **versión** propiedad.</span><span class="sxs-lookup"><span data-stu-id="5acea-124">In the Properties window, type a **Version** property.</span></span>  
  
3.  <span data-ttu-id="5acea-125">En la ventana Propiedades, especifique la **es la respuesta de solicitud** propiedad mediante la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5acea-125">In the Properties window, specify the **Is Request Response** property using the drop-down list.</span></span> <span data-ttu-id="5acea-126">Establezca esta propiedad en **true** si el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] aplicación cliente se comunica con un aumento con el patrón de intercambio de mensajes de solicitud y respuesta.</span><span class="sxs-lookup"><span data-stu-id="5acea-126">Set this property to **true** if the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] client application communicates with an on-ramp using request-response message exchange pattern.</span></span>  
  
4.  <span data-ttu-id="5acea-127">En la ventana Propiedades, establezca la **exportar modo** propiedad **predeterminado** o **Strict**.</span><span class="sxs-lookup"><span data-stu-id="5acea-127">In the Properties window, set the **Export Mode** property to **Default** or **Strict**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5acea-128">Al crear [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerarios utilizando el Diseñador de itinerario, el **exportar modo** propiedad puede utilizarse para definir dónde se ejecutará el servicio.</span><span class="sxs-lookup"><span data-stu-id="5acea-128">When creating [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itineraries using the Itinerary Designer, the **Export Mode** property can be used to define where the service will execute.</span></span> <span data-ttu-id="5acea-129">Establecer el **exportar modo** propiedad **Strict** garantiza que el itinerario servicio se ejecuta en su contenedor prescrita; en este caso, cada servicio itinerario en el itinerario XML tiene una propiedad de la fase que Especifica la canalización en el que se ejecuta el servicio.</span><span class="sxs-lookup"><span data-stu-id="5acea-129">Setting the **Export Mode** property to **Strict** ensures that the itinerary service executes in its prescribed container; in this case, each itinerary service in the XML itinerary has a stage property that specifies the pipeline in which the service executes.</span></span> <span data-ttu-id="5acea-130">Si esta propiedad se establece en **predeterminado**, se crea un itinerario compatible con Microsoft ESB, con ninguna fase especificada, y el servicio itinerario se ejecuta en el orden establecido, pero no necesariamente en la fase de canalización deseado.</span><span class="sxs-lookup"><span data-stu-id="5acea-130">If this property is set to **Default**, an itinerary compatible with Microsoft ESB is created, with no stage specified, and the itinerary service executes in the order prescribed, but not necessarily in the pipeline stage desired.</span></span>  
  
#### <a name="export-an-itinerary-to-a-file"></a><span data-ttu-id="5acea-131">Exportar un itinerario a un archivo</span><span class="sxs-lookup"><span data-stu-id="5acea-131">Export an itinerary to a file</span></span>  
  
1.  <span data-ttu-id="5acea-132">En la ventana Propiedades, haga clic en **XML itinerario exportador** en el **modelo exportador** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5acea-132">In the Properties window, click **XML Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
2.  <span data-ttu-id="5acea-133">En la ventana Propiedades, establezca la **archivo XML de itinerario** propiedad a un nuevo valor.</span><span class="sxs-lookup"><span data-stu-id="5acea-133">In the Properties window, set the **Itinerary XML file** property to a new value.</span></span>  
  
#### <a name="export-an-itinerary-to-a-database"></a><span data-ttu-id="5acea-134">Exportar un itinerario a una base de datos</span><span class="sxs-lookup"><span data-stu-id="5acea-134">Export an itinerary to a database</span></span>  
  
1.  <span data-ttu-id="5acea-135">En la ventana Propiedades, haga clic en **base de datos de itinerario exportador** en el **modelo exportador** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="5acea-135">In the Properties window, click **Database Itinerary Exporter** in the **Model Exporter** drop-down list.</span></span>  
  
2.  <span data-ttu-id="5acea-136">En la ventana Propiedades, establezca la **base de datos de itinerario** cadena de conexión de la propiedad para que apunte a la base de datos de itinerario.</span><span class="sxs-lookup"><span data-stu-id="5acea-136">In the Properties window, set the **Itinerary Database** property connection string to point to the itinerary database.</span></span>  
  
3.  <span data-ttu-id="5acea-137">En la ventana Propiedades, establezca la **estado de itinerario** propiedad **publicada** o **implementadas**.</span><span class="sxs-lookup"><span data-stu-id="5acea-137">In the Properties window, set the **Itinerary Status** property to **Published** or **Deployed**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5acea-138">Cuando se exporta un itinerario para una base de datos con **estado de itinerario** establecido en **publicada**, el itinerarios no son eficaces para el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] tiempo hasta el de ejecución después de que la propiedad se establece en  **Implementar**.</span><span class="sxs-lookup"><span data-stu-id="5acea-138">When an itinerary is exported to a database with **Itinerary Status** set to **Published**, the itinerary will not become effective for the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] run time until after the property is set to **Deployed**.</span></span>  
  
## <a name="security-operations"></a><span data-ttu-id="5acea-139">Operaciones de seguridad</span><span class="sxs-lookup"><span data-stu-id="5acea-139">Security Operations</span></span>  
 <span data-ttu-id="5acea-140">Mediante el Diseñador de itinerario, puede proteger información confidencial, como contraseñas y otras credenciales se almacenan en un [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerarios, mediante el cifrado de esta información utilizando certificados X.509.</span><span class="sxs-lookup"><span data-stu-id="5acea-140">By using the Itinerary Designer, you can protect sensitive information, such as passwords and other credentials stored in a [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary, by encrypting this information using X.509 certificates.</span></span>  
  
#### <a name="select-the-x509-certificate-for-an-itinerary"></a><span data-ttu-id="5acea-141">Seleccione el certificado X.509 para un itinerario</span><span class="sxs-lookup"><span data-stu-id="5acea-141">Select the X.509 certificate for an itinerary</span></span>  
  
1.  <span data-ttu-id="5acea-142">En la ventana Propiedades del Diseñador de itinerario, expanda la **certificado de cifrado** propiedad y, a continuación, haga clic en el **ubicación del almacén de** lista desplegable y seleccione el **CurrentUser**o **LocalMachine**.</span><span class="sxs-lookup"><span data-stu-id="5acea-142">In the Itinerary Designer Properties window, expand the **Encryption Certificate** property, and then click the **Store Location** drop-down list, and select the **CurrentUser** or **LocalMachine**.</span></span> <span data-ttu-id="5acea-143">Esto asocia el almacén de certificados X.509 con el usuario actual o el equipo local.</span><span class="sxs-lookup"><span data-stu-id="5acea-143">This associates the X.509 certificate store with the current user or the local computer.</span></span>  
  
2.  <span data-ttu-id="5acea-144">En la ventana Propiedades, haga clic en el **almacenar nombre** lista desplegable y seleccione el valor que se corresponde con el almacén de certificados.</span><span class="sxs-lookup"><span data-stu-id="5acea-144">In the Properties window, click the **Store Name** drop-down list and select the value which corresponds to your certificate store.</span></span>  
  
3.  <span data-ttu-id="5acea-145">En la ventana Propiedades, haga clic en el botón de puntos suspensivos (...) junto a la propiedad de certificado de cifrado y, a continuación, seleccione la **certificado X.509** en el **Seleccionar certificado** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="5acea-145">In the Properties window, click the ellipsis button (...) next to the Encryption Certificate property, and then select the **X.509 certificate** in the **Select Certificate** dialog box.</span></span>  
  
#### <a name="remove-the-x509-certificate-from-an-itinerary"></a><span data-ttu-id="5acea-146">Quitar el certificado X.509 de un itinerario</span><span class="sxs-lookup"><span data-stu-id="5acea-146">Remove the X.509 certificate from an itinerary</span></span>  
  
-   <span data-ttu-id="5acea-147">En la ventana Propiedades del Diseñador de itinerario, expanda la **certificado de cifrado** propiedad y, a continuación, establezca el **ubicación del almacén de** propiedad en un valor diferente.</span><span class="sxs-lookup"><span data-stu-id="5acea-147">In the Itinerary Designer Properties window, expand the **Encryption Certificate** property, and then set the **Store Location** property to a different value.</span></span> <span data-ttu-id="5acea-148">Esto desasocia el certificado antiguo con el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] modelo itinerario.</span><span class="sxs-lookup"><span data-stu-id="5acea-148">This disassociates the old certificate with the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] itinerary model.</span></span>  
  
#### <a name="disable-the-x509-certificate-validation"></a><span data-ttu-id="5acea-149">Deshabilitar la validación del certificado X.509</span><span class="sxs-lookup"><span data-stu-id="5acea-149">Disable the X.509 certificate validation</span></span>  
  
<span data-ttu-id="5acea-150">En el Editor del registro, vaya a la subclave **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**y, a continuación, establezca el **RequireX509Certificate** valor de propiedad  **false**.</span><span class="sxs-lookup"><span data-stu-id="5acea-150">In the Registry Editor, go to the subkey **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BizTalk ESB Toolkit\2.0\Designer**, and then set the **RequireX509Certificate** property value to **false**.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5acea-151">Si instaló el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] en un sistema operativo que tenga compatibilidad con 64 bits, la subclave es **HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**.</span><span class="sxs-lookup"><span data-stu-id="5acea-151">If you installed the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] on an operating system that has 64-bit support, the subkey is **HKEY_LOCAL_MACHINE\SOFTWARE\SysWOW64\Microsoft\BizTalk ESB Toolkit\2.0\Designer**.</span></span>