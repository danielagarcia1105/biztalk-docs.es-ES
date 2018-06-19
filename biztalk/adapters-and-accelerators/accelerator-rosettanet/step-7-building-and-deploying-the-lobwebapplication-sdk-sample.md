---
title: 'Paso 7: Crear e implementar el ejemplo de SDK de LOBWebApplication | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, building solutions
- double action tutorial, deploying solutions
ms.assetid: f61de666-ebda-4831-9669-598e9284e4c1
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92b101b47e2f83a0390a47cf6b1e4fc9a210950d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25966322"
---
# <a name="step-7-building-and-deploying-the-lobwebapplication-sdk-sample"></a><span data-ttu-id="f6a99-102">Paso 7: Crear e implementar el ejemplo de SDK de LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="f6a99-102">Step 7: Building and Deploying the LOBWebApplication SDK Sample</span></span>
<span data-ttu-id="f6a99-103">En este paso, creará la aplicación de línea de negocio (LOB) que Fabrikam usa para enviar solicitudes de Proceso de interfaz de socio (PIP) a Contoso.</span><span class="sxs-lookup"><span data-stu-id="f6a99-103">In this step, you create the line-of-business (LOB) application that Fabrikam uses to submit Partner Interface Process (PIP) requests to Contoso.</span></span> <span data-ttu-id="f6a99-104">Puede encontrar el proyecto LOBWebApplication en la [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] carpeta del SDK.</span><span class="sxs-lookup"><span data-stu-id="f6a99-104">You can find the LOBWebApplication project in the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] SDK folder.</span></span> <span data-ttu-id="f6a99-105">Para ejecutar la aplicación Web, tendrá que crear un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] directorio virtual de Internet Information Services (IIS) y, a continuación, compile el proyecto de LOBWebApplication.</span><span class="sxs-lookup"><span data-stu-id="f6a99-105">To run the Web application, you have to create a [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Internet Information Services (IIS) virtual directory, and then build the LOBWebApplication project.</span></span>  
  
### <a name="to-create-the-lobwebapplication-virtual-directory"></a><span data-ttu-id="f6a99-106">Para crear el directorio virtual LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="f6a99-106">To create the LOBWebApplication virtual directory</span></span>  
  
1.  <span data-ttu-id="f6a99-107">Haga clic en **Inicio**, elija **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administrador de Internet Information Services (IIS)**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-107">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="f6a99-108">En la ventana Administrador de Internet Information Services, expanda **< nombre_equipo > (equipo local)** y, a continuación, expanda **sitios Web**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-108">In the Internet Information Services Manager window, expand **<computer_name> (local computer)**, and then expand **Web Sites**.</span></span>  
  
3.  <span data-ttu-id="f6a99-109">Haga clic con el botón secundario en **Sitio Web predeterminado**, elija **Nuevo**y, a continuación, haga clic en **Directorio virtual**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-109">Right-click **Default Web Site**, point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="f6a99-110">En el **Welcometo el Asistente para creación de directorio Virtual** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-110">On the **Welcometo the Virtual Directory Creation Wizard** page, click **Next**.</span></span>  
  
5.  <span data-ttu-id="f6a99-111">En la página **Alias del directorio virtual** , en el cuadro **Alias** , escriba **LOBWebApplication**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-111">On the **Virtual Directory Alias** page, in the **Alias** box, type **LOBWebApplication**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="f6a99-112">En la página **Directorio de contenido del sitio Web** , haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-112">On the **Web Site Content Directory** page, click **Browse**.</span></span> <span data-ttu-id="f6a99-113">En el cuadro de diálogo Buscar carpeta, vaya a   ***\<unidad\>*: \Program BizTalk \<versión\> Acelerador para RosettaNet\SDK\ LOBWebApplication**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-113">In the Browse For Folder dialog box, move to ***\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication**, and then click **OK**.</span></span> <span data-ttu-id="f6a99-114">Haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-114">Click **Next**.</span></span>  
  
7.  <span data-ttu-id="f6a99-115">En la página **Permisos de acceso de directorio virtual** , anule la selección de **Leer**, seleccione **Ejecutar scripts (por ejemplo, ASP)** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-115">On the **Virtual Directory Access Permissions** page, deselect **Read**, select **Run scripts (such as ASP)**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="f6a99-116">En la página **Ha completado correctamente el Asistente para crear un directorio Virtual** , haga clic en **Finalizar** para crear el directorio virtual.</span><span class="sxs-lookup"><span data-stu-id="f6a99-116">On the **You have successfully completed the Virtual Directory Creation Wizard** page, click **Finish** to create the virtual directory.</span></span>  
  
### <a name="to-exclude-the-lobwebapplication-web-site-from-the-sharepoint-configuration"></a><span data-ttu-id="f6a99-117">Para excluir el sitio web LOBWebApplication de la configuración de SharePoint</span><span class="sxs-lookup"><span data-stu-id="f6a99-117">To exclude the LOBWebApplication Web site from the SharePoint configuration</span></span>  
  
1.  <span data-ttu-id="f6a99-118">Haga clic en **Inicio**, seleccione **Todos los programas**, seleccione **Herramientas administrativas**y, a continuación, haga clic en **Administración central de SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-118">Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **SharePoint Central Administration**.</span></span>  
  
2.  <span data-ttu-id="f6a99-119">En la página web **Administración central** , en la sección **Configuración del servidor virtual** , seleccione **Extender o actualizar el servidor virtual**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-119">On the **Central Administration** Web page, in the **Virtual Server Configuration** section, select **Extend or upgrade virtual server**.</span></span>  
  
3.  <span data-ttu-id="f6a99-120">Si no ve la dirección URL configurada en el equipo, haga clic en **Lista completa**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-120">If you do not see the URL configured on the computer, click **Complete list**.</span></span>  
  
4.  <span data-ttu-id="f6a99-121">En la página **Lista de servidor virtual** , seleccione **Sitio web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-121">On the **Virtual Server List** page, select **Default Web Site**.</span></span>  
  
5.  <span data-ttu-id="f6a99-122">En la sección **Administración del servidor virtual** , haga clic en **Definir rutas de acceso administradas**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-122">In the **Virtual Server Management** section, click **Define managed paths**.</span></span>  
  
6.  <span data-ttu-id="f6a99-123">En la sección **Agregar nueva ruta de acceso** , en el cuadro **Ruta de acceso** , escriba **/LOBWebApplication**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-123">In the **Add New Path** section, in the **Path** box, type **/LOBWebApplication**.</span></span>  
  
7.  <span data-ttu-id="f6a99-124">En **Tipo**, seleccione **Ruta excluida**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-124">For **Type**, select **Excluded Path**, and then click **OK**.</span></span>  
  
### <a name="to-build-the-lobwebapplication-project"></a><span data-ttu-id="f6a99-125">Para compilar el proyecto LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="f6a99-125">To build the LOBWebApplication project</span></span>  
  
1.  <span data-ttu-id="f6a99-126">Haga clic en **Inicio**, elija **Todos los programas**, **Microsoft Visual Studio 2008**y, a continuación, haga clic en **Microsoft Visual Studio 2008**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-126">Click **Start**, point to **All Programs**, point to **Microsoft Visual Studio 2008**, and then click **Microsoft Visual Studio 2008**.</span></span>  
  
2.  <span data-ttu-id="f6a99-127">En el menú **Archivo** , seleccione **Abrir**y haga clic en **Proyecto o solución**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-127">On the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="f6a99-128">En el cuadro de diálogo Abrir proyecto, vaya a   ***\<unidad\>*: \Program BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication** , seleccione la **LOBWebApplication.sln** archivo de solución y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-128">In the Open Project dialog box, move to ***\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication**, select the **LOBWebApplication.sln** solution file, and then click **Open**.</span></span>  
  
4.  <span data-ttu-id="f6a99-129">En el Explorador de soluciones, haga clic con el botón derecho en **http://localhost/LOBWebApplication**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-129">In Solution Explorer, right-click **http://localhost/LOBWebApplication**, and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="f6a99-130">En el cuadro de diálogo Agregar referencia, haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-130">In the Add Reference dialog box, click **Browse**.</span></span> <span data-ttu-id="f6a99-131">En el cuadro de diálogo Agregar referencia, vaya a   ***\<unidad\>*: \Program BizTalk \<versión\> Accelerator for RosettaNet\Bin** carpeta.</span><span class="sxs-lookup"><span data-stu-id="f6a99-131">In the Add Reference dialog box, move to ***\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin** folder.</span></span>  
  
6.  <span data-ttu-id="f6a99-132">En la carpeta Bin, seleccione los ensamblados **Microsoft.Solutions.BTARN.ConfigurationManager.dll** y **Microsoft.Solutions.BTARN.Shared.dll** assemblies, y then click **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-132">From the Bin folder, select the **Microsoft.Solutions.BTARN.ConfigurationManager.dll** and **Microsoft.Solutions.BTARN.Shared.dll** assemblies, and then click **Open.**</span></span>  
  
7.  <span data-ttu-id="f6a99-133">Haga clic en **Aceptar** para cerrar el cuadro de diálogo **Agregar referencia** .</span><span class="sxs-lookup"><span data-stu-id="f6a99-133">Click **OK** to close the **Add Reference** dialog box.</span></span>  
  
8.  <span data-ttu-id="f6a99-134">En el explorador de soluciones, haga clic con el botón derecho en **Solución 'LOBWebApplication'** y, luego, haga clic en **Compilar solución**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-134">In Solution Explorer, right-click **Solution 'LOBWebApplication'** and then click **Build Solution**.</span></span>  
  
9. <span data-ttu-id="f6a99-135">Haga clic con el botón derecho en **default.aspx**y, a continuación, haga clic en **Establecer como página de inicio**.</span><span class="sxs-lookup"><span data-stu-id="f6a99-135">Right-click **default.aspx**, and then click **Set as Start Page**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6a99-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="f6a99-136">See Also</span></span>  
 [<span data-ttu-id="f6a99-137">Prueba del tutorial de doble acción</span><span class="sxs-lookup"><span data-stu-id="f6a99-137">Testing the Double Action Tutorial</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-double-action-tutorial.md)