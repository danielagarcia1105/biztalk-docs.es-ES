---
title: 'Paso 2: Creación de LOBWebApplication de Fabrikam | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOBWebApplication
- LOBWebApplication
ms.assetid: 2ff8bd20-7fbc-4e16-b177-bb4afac7f7c3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9c55234d8ee9c123c9efe9e7ec66b7c0db590b54
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966629"
---
# <a name="step-2-creating-the-fabrikam-lobwebapplication"></a><span data-ttu-id="17f6e-102">Paso 2: Creación de LOBWebApplication de Fabrikam</span><span class="sxs-lookup"><span data-stu-id="17f6e-102">Step 2: Creating the Fabrikam LOBWebApplication</span></span>
<span data-ttu-id="17f6e-103">En este paso, creará la aplicación de LOB que Fabrikam usa para enviar una solicitud de 3A2 PIP a Contoso.</span><span class="sxs-lookup"><span data-stu-id="17f6e-103">In this step, you create the LOB application that Fabrikam uses to submit a 3A2 PIP request to Contoso.</span></span> <span data-ttu-id="17f6e-104">El proyecto LOBWebApplication está instalado en el [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span><span class="sxs-lookup"><span data-stu-id="17f6e-104">The LOBWebApplication project is installed in the [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK.</span></span> <span data-ttu-id="17f6e-105">Para ejecutar la aplicación Web, tendrá que crear un directorio virtual de Microsoft Internet Information Services (IIS) y compile el proyecto LOBWebApplication.</span><span class="sxs-lookup"><span data-stu-id="17f6e-105">To run the Web application, you have to create a Microsoft Internet Information Services (IIS) virtual directory and build the LOBWebApplication project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="17f6e-106">Si ha completado el tutorial de DoubleAction, no es necesario realizar este paso.</span><span class="sxs-lookup"><span data-stu-id="17f6e-106">If you completed the DoubleAction tutorial, you do not need to perform this step.</span></span>  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a><span data-ttu-id="17f6e-107">Para crear el directorio virtual LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="17f6e-107">To create the LOBWebApplication virtual directory</span></span>  
  
1.  <span data-ttu-id="17f6e-108">Haga clic en **iniciar**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-108">Click **Start**, point to **Administrative Tools**, and then click **Internet Information Services Manager**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="17f6e-109">Si ya ha hecho el tutorial de doble acción, ya habrá creado el directorio virtual LOBWebApplication de ese tutorial.</span><span class="sxs-lookup"><span data-stu-id="17f6e-109">If you have already done the Double Action tutorial, you will already have created the LOBWebApplication virtual directory for that tutorial.</span></span> <span data-ttu-id="17f6e-110">Si es así, no es necesario llevar a cabo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="17f6e-110">If so, you do not have to perform these steps.</span></span> <span data-ttu-id="17f6e-111">Sin embargo, deberá cambiar los permisos para el directorio virtual de **ejecutar secuencias de comandos** a **lectura**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-111">You will, however, have to change the permissions for the virtual directory from **Run scripts** to **Read**.</span></span>  
  
2.  <span data-ttu-id="17f6e-112">En el Administrador de Internet Information Services, expanda **< nombre_equipo > (equipo local)** y, a continuación, expanda **sitios Web**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-112">In Internet Information Services Manager, expand **<computer_name> (local computer)**, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="17f6e-113">Haga clic con el botón secundario en **Sitio Web predeterminado**, elija **Nuevo**y, a continuación, haga clic en **Directorio virtual**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-113">Right-click **Default Web Site**, point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="17f6e-114">En el **Welcometo la página del Asistente para crear un directorio Virtual**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-114">On the **Welcometo the Virtual Directory Creation Wizard page**, click **Next**.</span></span>  
  
5.  <span data-ttu-id="17f6e-115">En la página **Alias del directorio virtual** , en el cuadro **Alias** , escriba **LOBWebApplication**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-115">On the **Virtual Directory Alias** page, in the **Alias** box, type **LOBWebApplication**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="17f6e-116">En el **directorio de contenido del sitio Web** página, haga clic en **examinar**, seleccione el  **\<unidad\>: \Program Files\Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication** carpeta y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-116">On the **Web Site Content Directory** page, click **Browse**, select the **\<drive\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication** folder, and then click **OK**.</span></span> <span data-ttu-id="17f6e-117">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-117">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="17f6e-118">En el **permisos de acceso del directorio Virtual** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-118">On the **Virtual Directory Access Permissions** page, click **Next**.</span></span>  
  
8.  <span data-ttu-id="17f6e-119">Haga clic en **finalizar** para crear el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="17f6e-119">Click **Finish** to create the virtual directory.</span></span>  
  
### <a name="excluding-lobwebapplication-from-sharepoint"></a><span data-ttu-id="17f6e-120">Exclusión de LOBWebApplication de SharePoint</span><span class="sxs-lookup"><span data-stu-id="17f6e-120">Excluding LOBWebApplication from SharePoint</span></span>  
  
1.  <span data-ttu-id="17f6e-121">Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administración central de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-121">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="17f6e-122">Si ya ha hecho el tutorial de doble acción, que ya habrá excluya el directorio virtual LOBWebApplication del SharePoint para este tutorial.</span><span class="sxs-lookup"><span data-stu-id="17f6e-122">If you have already done the Double Action tutorial, you will already have excluded the LOBWebApplication virtual directory from SharePoint for that tutorial.</span></span> <span data-ttu-id="17f6e-123">Si es así, no es necesario llevar a cabo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="17f6e-123">If so, you do not have to perform these steps.</span></span>  
  
2.  <span data-ttu-id="17f6e-124">En el **Administración Central** página, en el **configuración del servidor Virtual** sección, seleccione **extender o actualizar el servidor virtual**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-124">On the **Central Administration** page, in the **Virtual Server Configuration** section, select **Extend or upgrade virtual server**.</span></span>  
  
3.  <span data-ttu-id="17f6e-125">Si no ve la dirección URL configurada en el equipo, haga clic en **Lista completa**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-125">If you do not see the URL configured on the computer, click **Complete list**.</span></span>  
  
4.  <span data-ttu-id="17f6e-126">Seleccione **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-126">Select **Default Web Site**.</span></span>  
  
5.  <span data-ttu-id="17f6e-127">En la sección **Administración del servidor virtual** , haga clic en **Definir rutas de acceso administradas**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-127">In the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
6.  <span data-ttu-id="17f6e-128">En el **agregar nueva ruta de acceso** sección la **ruta de acceso** , escriba "/ LOBWebApplication".</span><span class="sxs-lookup"><span data-stu-id="17f6e-128">In the **Add New Path** section, in the **Path** box, type "/LOBWebApplication".</span></span> <span data-ttu-id="17f6e-129">En **Tipo**, seleccione **Ruta excluida**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-129">For **Type**, select **Excluded Path**, and then click **OK**.</span></span>  
  
### <a name="to-build-the-lobwebapplication-project"></a><span data-ttu-id="17f6e-130">Para compilar el proyecto LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="17f6e-130">To build the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="17f6e-131">Inicie **Microsoft Visual Studio 2012**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-131">Start **Microsoft Visual Studio 2012**.</span></span>  
  
2.  <span data-ttu-id="17f6e-132">Desde el **archivo** menú, elija **abierto**y, a continuación, haga clic en **Project\Solution**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-132">From the **File** menu, point to **Open**, and then click **Project\Solution**.</span></span>  
  
3.  <span data-ttu-id="17f6e-133">En el cuadro de diálogo Abrir proyecto en **buscar en**, mover a  **\<unidad\>: \Program Files\Microsoft BizTalk \<versión\> Acelerador para SDK\ de menú LOBWebApplication**, seleccione el **LOBWebApplication.sln** solución y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-133">In the Open Project dialog box, in **Look In**, move to **\<drive\>:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\ SDK\LOBWebApplication**, select the **LOBWebApplication.sln** solution, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="17f6e-134">En el Explorador de soluciones, haga clic en el nodo superior (http://localhost/LOBWebApplication)y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-134">In Solution Explorer, right-click the top node (http://localhost/LOBWebApplication), and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="17f6e-135">En el cuadro de diálogo Agregar referencia, haga clic en **examinar** y mover a **\<unidad\>: \Program Files\Microsoft BizTalk \<versión\> Accelerator for RosettaNet\bin**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-135">In the Add Reference dialog box, click **Browse** and move to **\<drive\>:\Program Files\Microsoft  BizTalk \<version\> Accelerator for RosettaNet\bin**.</span></span>  
  
6.  <span data-ttu-id="17f6e-136">**Seleccione el Microsoft.Solutions.BTARN.ConfigurationManager.dll y Microsoft.Solutions.BTARN.Shared.dll** ensamblados **y, a continuación, haga clic en Aceptar.**</span><span class="sxs-lookup"><span data-stu-id="17f6e-136">**Select the Microsoft.Solutions.BTARN.ConfigurationManager.dll and Microsoft.Solutions.BTARN.Shared.dll** assemblies **and then click OK.**</span></span>  
  
7.  <span data-ttu-id="17f6e-137">En el **compilar** menú, haga clic en **Generar sitio Web**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-137">On the **Build** menu, click **Build Web Site**.</span></span>  
  
### <a name="to-run-the-lobwebapplication-project"></a><span data-ttu-id="17f6e-138">Para ejecutar el proyecto LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="17f6e-138">To run the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="17f6e-139">En el Explorador de soluciones, haga clic en **default.aspx**y, a continuación, seleccione **establecer como página principal**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-139">In Solution Explorer, right-click **default.aspx**, and then select **Set As Start Page**.</span></span>  
  
2.  <span data-ttu-id="17f6e-140">En el **depurar** menú, haga clic en **iniciar sin depurar**.</span><span class="sxs-lookup"><span data-stu-id="17f6e-140">On the **Debug** menu, click **Start Without Debugging**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17f6e-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="17f6e-141">See Also</span></span>  
 [<span data-ttu-id="17f6e-142">Probar la solución</span><span class="sxs-lookup"><span data-stu-id="17f6e-142">Testing the Solution</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)