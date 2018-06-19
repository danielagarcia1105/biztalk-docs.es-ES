---
title: Requisitos previos para las actividades de desarrollo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 54c91405-f9a4-4676-b5c5-fe90b3b51b45
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dbc79fd31e78581d98ecad34579958ff90f3b1e1
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26006261"
---
# <a name="prerequisites-for-the-development-activities"></a><span data-ttu-id="05d5c-102">Requisitos previos para las actividades de desarrollo</span><span class="sxs-lookup"><span data-stu-id="05d5c-102">Prerequisites for the Development Activities</span></span>
<span data-ttu-id="05d5c-103">Esta sección describe cómo preparar el entorno para completar los pasos descritos en las actividades de desarrollo que se incluyen como parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05d5c-103">This section describes how to prepare your environment to complete the steps in the development activities that are included as part of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].</span></span> <span data-ttu-id="05d5c-104">Complete la configuración siguiente antes de intentar cualquiera de los procedimientos descritos en las actividades de desarrollo:</span><span class="sxs-lookup"><span data-stu-id="05d5c-104">Complete the following setup before you attempt any of the procedures in the development activities:</span></span>  
  
## <a name="set-up-your-computer-to-perform-the-procedures-in-the-biztalk-esb-toolkit-development-activities"></a><span data-ttu-id="05d5c-105">Configurar el equipo para realizar los procedimientos de las actividades de desarrollo del Kit de herramientas de ESB de BizTalk</span><span class="sxs-lookup"><span data-stu-id="05d5c-105">Set up your computer to perform the procedures in the BizTalk ESB Toolkit development activities</span></span>  
  
1.  <span data-ttu-id="05d5c-106">Instalar e implementar la aplicación de ejemplo de itinerario, la aplicación de ejemplo de resolución dinámica y la aplicación de ejemplo de varios servicios Web.</span><span class="sxs-lookup"><span data-stu-id="05d5c-106">Install and deploy the Itinerary sample application, the Dynamic Resolution sample application, and the Multiple Web Services sample application.</span></span> <span data-ttu-id="05d5c-107">Para obtener más información sobre cómo instalar e implementar estas aplicaciones, consulte [aplicaciones de ejemplo de BizTalk ESB Toolkit](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md).</span><span class="sxs-lookup"><span data-stu-id="05d5c-107">For more information about installing and deploying these applications, see [BizTalk ESB Toolkit Sample Applications](../esb-toolkit/biztalk-esb-toolkit-sample-applications.md).</span></span>  
  
2.  <span data-ttu-id="05d5c-108">Ejecute la utilidad de editor UDDI.</span><span class="sxs-lookup"><span data-stu-id="05d5c-108">Run the UDDI Publisher Utility.</span></span>  
  
3.  <span data-ttu-id="05d5c-109">En el equipo de desarrollo, en el Explorador de Windows, cree las rutas de acceso siguientes:</span><span class="sxs-lookup"><span data-stu-id="05d5c-109">On your development computer, in Windows Explorer, create the following paths:</span></span>  
  
    -   <span data-ttu-id="05d5c-110">C:\HowTos</span><span class="sxs-lookup"><span data-stu-id="05d5c-110">C:\HowTos</span></span>  
  
    -   <span data-ttu-id="05d5c-111">C:\HowTos\Itineraries</span><span class="sxs-lookup"><span data-stu-id="05d5c-111">C:\HowTos\Itineraries</span></span>  
  
    -   <span data-ttu-id="05d5c-112">C:\HowTos\DropFolder</span><span class="sxs-lookup"><span data-stu-id="05d5c-112">C:\HowTos\DropFolder</span></span>  
  
    -   <span data-ttu-id="05d5c-113">C:\HowTos\Out</span><span class="sxs-lookup"><span data-stu-id="05d5c-113">C:\HowTos\Out</span></span>  
  
4.  <span data-ttu-id="05d5c-114">Asegúrese de que la cuenta de servicio de BizTalk Server tiene **Control total** permisos para la estructura de directorios C:\HowTos.</span><span class="sxs-lookup"><span data-stu-id="05d5c-114">Ensure that your BizTalk Server service account has **Full Control** permissions to the C:\HowTos directory structure.</span></span>  
  
5.  <span data-ttu-id="05d5c-115">Asegúrese de que la cuenta de servicio de Microsoft BizTalk Server tiene **escribir** permisos para C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out.</span><span class="sxs-lookup"><span data-stu-id="05d5c-115">Ensure that your Microsoft BizTalk Server service account has **Write** permissions to C:\Projects\Microsoft.Practices.ESB\Source\Samples\DynamicResolution\Test\Filedrop\Out.</span></span>  
  
6.  <span data-ttu-id="05d5c-116">Copie el siguiente mensaje de prueba en la carpeta C:\HowTos:</span><span class="sxs-lookup"><span data-stu-id="05d5c-116">Copy the following test message to the C:\HowTos folder:</span></span>  
  
    -   <span data-ttu-id="05d5c-117">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Test\Data\NAOrderDoc.Xml</span><span class="sxs-lookup"><span data-stu-id="05d5c-117">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Test\Data\NAOrderDoc.xml</span></span>  
  
7.  <span data-ttu-id="05d5c-118">En la carpeta C:\HowTos, cree un acceso directo a la aplicación de cliente de prueba de itinerario que se encuentra en la siguiente ubicación:</span><span class="sxs-lookup"><span data-stu-id="05d5c-118">In the C:\HowTos folder, create a shortcut to the Itinerary Test Client application, found at the following location:</span></span>  
  
    -   <span data-ttu-id="05d5c-119">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB. Itinerary.Test\bin\Debug\ESB. Itinerary.Test.exe</span><span class="sxs-lookup"><span data-stu-id="05d5c-119">C:\Projects\Microsoft.Practices.ESB\Source\Samples\Itinerary\Source\ESB.Itinerary.Test\bin\Debug\ESB.Itinerary.Test.exe</span></span>  
  
## <a name="create-the-visual-studio-solution"></a><span data-ttu-id="05d5c-120">Crear la solución de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="05d5c-120">Create the Visual Studio solution</span></span>  
  
1.  <span data-ttu-id="05d5c-121">En Visual Studio, en el menú archivo, seleccione **New**y, a continuación, haga clic en **proyecto**.</span><span class="sxs-lookup"><span data-stu-id="05d5c-121">In Visual Studio, on the File menu, point to **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="05d5c-122">En el **nuevo proyecto** cuadro de diálogo, en el panel tipos de proyecto, haga clic en **Visual C#** y, a continuación, haga clic en **biblioteca de clases** en el panel Plantillas.</span><span class="sxs-lookup"><span data-stu-id="05d5c-122">In the **New Project** dialog box, in the Project types pane, click **Visual C#**, and then click **Class Library** in the Templates pane.</span></span>  
  
3.  <span data-ttu-id="05d5c-123">En el **nombre** , escriba **ItineraryLibrary**.</span><span class="sxs-lookup"><span data-stu-id="05d5c-123">In the **Name** box, type **ItineraryLibrary**.</span></span>  
  
4.  <span data-ttu-id="05d5c-124">En el **ubicación** , escriba **C:\HowTos**.</span><span class="sxs-lookup"><span data-stu-id="05d5c-124">In the **Location** box, type **C:\HowTos**.</span></span>  
  
5.  <span data-ttu-id="05d5c-125">Seleccione el **crear directorio para la solución** casilla de verificación.</span><span class="sxs-lookup"><span data-stu-id="05d5c-125">Select the **Create directory for solution** check box.</span></span>  
  
6.  <span data-ttu-id="05d5c-126">En el **nombre de la solución** , escriba **patrones**y, a continuación, haga clic en **Aceptar** para crear la solución.</span><span class="sxs-lookup"><span data-stu-id="05d5c-126">In the **Solution Name** box, type **Patterns**, and then click **OK** to create the solution.</span></span>  
  
7.  <span data-ttu-id="05d5c-127">Eliminar el **Class1.cs** de archivos desde el **ItineraryLibrary** proyecto.</span><span class="sxs-lookup"><span data-stu-id="05d5c-127">Delete the **Class1.cs** file from the **ItineraryLibrary** project.</span></span>