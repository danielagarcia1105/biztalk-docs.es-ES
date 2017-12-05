---
title: 'Paso 2: Crear Fabrikam LOBWebApplication | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOBWebApplication
- LOBWebApplication
ms.assetid: 2ff8bd20-7fbc-4e16-b177-bb4afac7f7c3
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0732322d663e51c27bbaab957caa5474cc685326
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-2-creating-the-fabrikam-lobwebapplication"></a><span data-ttu-id="f7e1c-102">Paso 2: Crear el Fabrikam LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="f7e1c-102">Step 2: Creating the Fabrikam LOBWebApplication</span></span>
<span data-ttu-id="f7e1c-103">En este paso, creará la aplicación de LOB que Fabrikam usa para enviar una solicitud PIP 3A2 a Contoso.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-103">In this step, you create the LOB application that Fabrikam uses to submit a 3A2 PIP request to Contoso.</span></span> <span data-ttu-id="f7e1c-104">El proyecto LOBWebApplication está instalado en el [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-104">The LOBWebApplication project is installed in the [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="f7e1c-105">Para ejecutar la aplicación Web, tendrá que crear un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] directorio virtual de Internet Information Services (IIS) y compile el proyecto LOBWebApplication.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-105">To run the Web application, you have to create a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Internet Information Services (IIS) virtual directory and build the LOBWebApplication project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7e1c-106">Si completó el tutorial de DoubleAction, no es necesario realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-106">If you completed the DoubleAction tutorial, you do not need to perform this step.</span></span>  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a><span data-ttu-id="f7e1c-107">Para crear el directorio virtual LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="f7e1c-107">To create the LOBWebApplication virtual directory</span></span>  
  
1.  <span data-ttu-id="f7e1c-108">Haga clic en **iniciar**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-108">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services Manager**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f7e1c-109">Si ya ha hecho el tutorial de doble acción, ya habrá creado el directorio virtual LOBWebApplication para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-109">If you have already done the Double Action tutorial, you will already have created the LOBWebApplication virtual directory for that tutorial.</span></span> <span data-ttu-id="f7e1c-110">Si es así, no es necesario llevar a cabo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-110">If so, you do not have to perform these steps.</span></span> <span data-ttu-id="f7e1c-111">Sin embargo, tendrá que cambiar los permisos para el directorio virtual de **ejecutar secuencias de comandos** a **lectura**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-111">You will, however, have to change the permissions for the virtual directory from **Run scripts** to **Read**.</span></span>  
  
2.  <span data-ttu-id="f7e1c-112">En el Administrador de Internet Information Services, expanda **< nombre_equipo > (equipo local)**y, a continuación, expanda **sitios Web**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-112">In Internet Information Services Manager, expand **<computer_name> (local computer)**, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="f7e1c-113">Haga clic con el botón secundario en **Sitio Web predeterminado**, elija **Nuevo**y, a continuación, haga clic en **Directorio virtual**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-113">Right-click **Default Web Site**, point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="f7e1c-114">En el **Welcometo la página del Asistente para crear un directorio Virtual**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-114">On the **Welcometo the Virtual Directory Creation Wizard page**, click **Next**.</span></span>  
  
5.  <span data-ttu-id="f7e1c-115">En la página **Alias del directorio virtual** , en el cuadro **Alias** , escriba **LOBWebApplication**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-115">On the **Virtual Directory Alias** page, in the **Alias** box, type **LOBWebApplication**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="f7e1c-116">En el **directorio de contenido del sitio Web** página, haga clic en **examinar**, seleccione la  **\<unidad\>: \Program BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication** carpeta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-116">On the **Web Site Content Directory** page, click **Browse**, select the **\<drive\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication** folder, and then click **OK**.</span></span> <span data-ttu-id="f7e1c-117">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-117">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="f7e1c-118">En el **permisos de acceso de directorio Virtual** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-118">On the **Virtual Directory Access Permissions** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="f7e1c-119">Haga clic en **finalizar** para crear el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-119">Click **Finish** to create the virtual directory.</span></span>  
  
### <a name="excluding-lobwebapplication-from-sharepoint"></a><span data-ttu-id="f7e1c-120">Exclusión de LOBWebApplication de SharePoint</span><span class="sxs-lookup"><span data-stu-id="f7e1c-120">Excluding LOBWebApplication from SharePoint</span></span>  
  
1.  <span data-ttu-id="f7e1c-121">Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administración central de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-121">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f7e1c-122">Si ya ha hecho el tutorial de doble acción, que ya habrá excluido el directorio virtual LOBWebApplication de SharePoint para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-122">If you have already done the Double Action tutorial, you will already have excluded the LOBWebApplication virtual directory from SharePoint for that tutorial.</span></span> <span data-ttu-id="f7e1c-123">Si es así, no es necesario llevar a cabo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-123">If so, you do not have to perform these steps.</span></span>  
  
2.  <span data-ttu-id="f7e1c-124">En el **Administración Central** página, en la **configuración del servidor Virtual** sección, seleccione **extender o actualizar el servidor virtual**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-124">On the **Central Administration** page, in the **Virtual Server Configuration** section, select **Extend or upgrade virtual server**.</span></span>  
  
3.  <span data-ttu-id="f7e1c-125">Si no ve la dirección URL configurada en el equipo, haga clic en **Lista completa**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-125">If you do not see the URL configured on the computer, click **Complete list**.</span></span>  
  
4.  <span data-ttu-id="f7e1c-126">Seleccione **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-126">Select **Default Web Site**.</span></span>  
  
5.  <span data-ttu-id="f7e1c-127">En la sección **Administración del servidor virtual** , haga clic en **Definir rutas de acceso administradas**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-127">In the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
6.  <span data-ttu-id="f7e1c-128">En el **agregar nueva ruta de acceso** sección, en la **ruta de acceso** , escriba "/ LOBWebApplication".</span><span class="sxs-lookup"><span data-stu-id="f7e1c-128">In the **Add New Path** section, in the **Path** box, type "/LOBWebApplication".</span></span> <span data-ttu-id="f7e1c-129">En **Tipo**, seleccione **Ruta excluida**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-129">For **Type**, select **Excluded Path**, and then click **OK**.</span></span>  
  
### <a name="to-build-the-lobwebapplication-project"></a><span data-ttu-id="f7e1c-130">Para compilar el proyecto LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="f7e1c-130">To build the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="f7e1c-131">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-131">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="f7e1c-132">Desde el **archivo** menú, elija **abiertos**y, a continuación, haga clic en **Project\Solution**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-132">From the **File** menu, point to **Open**, and then click **Project\Solution**.</span></span>  
  
3.  <span data-ttu-id="f7e1c-133">En el cuadro de diálogo Abrir proyecto, en **buscar en**, mover a  **\<unidad\>: \Program BizTalk \<versión\> Acelerador para RosettaNet\ SDK\ LOBWebApplication**, seleccione la **LOBWebApplication.sln** solución y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-133">In the Open Project dialog box, in **Look In**, move to **\<drive\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\ SDK\LOBWebApplication**, select the **LOBWebApplication.sln** solution, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="f7e1c-134">En el Explorador de soluciones, haga clic en el nodo superior (http://localhost/LOBWebApplication) y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-134">In Solution Explorer, right-click the top node (http://localhost/LOBWebApplication), and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="f7e1c-135">En el cuadro de diálogo Agregar referencia, haga clic en **examinar** y mover a  **\<unidad\>: \Program BizTalk \<versión\> Accelerator for RosettaNet\bin** .</span><span class="sxs-lookup"><span data-stu-id="f7e1c-135">In the Add Reference dialog box, click **Browse** and move to **\<drive\>:\Program Files\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\bin**.</span></span>  
  
6.  <span data-ttu-id="f7e1c-136">**Seleccione el Microsoft.Solutions.BTARN.ConfigurationManager.dll y Microsoft.Solutions.BTARN.Shared.dll** ensamblados **y, a continuación, haga clic en Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="f7e1c-136">**Select the Microsoft.Solutions.BTARN.ConfigurationManager.dll and Microsoft.Solutions.BTARN.Shared.dll** assemblies **and then click OK.**</span></span>  
  
7.  <span data-ttu-id="f7e1c-137">En el **generar** menú, haga clic en **Generar sitio Web**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-137">On the **Build** menu, click **Build Web Site**.</span></span>  
  
### <a name="to-run-the-lobwebapplication-project"></a><span data-ttu-id="f7e1c-138">Para ejecutar el proyecto LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="f7e1c-138">To run the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="f7e1c-139">En el Explorador de soluciones, haga clic en **default.aspx**y, a continuación, seleccione **establecer como página principal**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-139">In Solution Explorer, right-click **default.aspx**, and then select **Set As Start Page**.</span></span>  
  
2.  <span data-ttu-id="f7e1c-140">En el **depurar** menú, haga clic en **iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="f7e1c-140">On the **Debug** menu, click **Start Without Debugging**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7e1c-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7e1c-141">See Also</span></span>  
 [<span data-ttu-id="f7e1c-142">Probar la solución</span><span class="sxs-lookup"><span data-stu-id="f7e1c-142">Testing the Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)