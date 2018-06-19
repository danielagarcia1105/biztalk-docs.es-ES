---
title: Cómo crear un programa de instalación de Web para el servicio Web publicado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, Web services
- Web services, deploying
- Web services, installing
- Web services, .msi file
- .msi files, Web services
ms.assetid: 77c86242-1d27-4d99-ae00-fe2614bc13ef
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 87c5ec4fe61c8649fe951460917cfde8788f2e57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249684"
---
# <a name="how-to-create-a-web-setup-for-your-published-web-service"></a><span data-ttu-id="78143-102">Cómo crear una configuración Web para el servicio Web publicado</span><span class="sxs-lookup"><span data-stu-id="78143-102">How to Create a Web Setup for Your Published Web Service</span></span>
<span data-ttu-id="78143-103">Puede crear un paquete de instalación para facilitar la configuración del servicio Web en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="78143-103">You can create an installation package to facilitate setting up your Web service in a production environment.</span></span> <span data-ttu-id="78143-104">Esto produce un archivo .MSI.</span><span class="sxs-lookup"><span data-stu-id="78143-104">This produces an .MSI file.</span></span>  
  
### <a name="to-create-an-installation-package-to-produce-an-msi-file-using-visual-studio"></a><span data-ttu-id="78143-105">Para crear un paquete de instalación y producir un archivo .MSI mediante Visual Studio</span><span class="sxs-lookup"><span data-stu-id="78143-105">To create an installation package to produce an .MSI file using Visual Studio</span></span>  
  
1.  <span data-ttu-id="78143-106">Abra el proyecto del servicio Web ASP.NET publicado.</span><span class="sxs-lookup"><span data-stu-id="78143-106">Open your published ASP.NET Web service project.</span></span>  
  
2.  <span data-ttu-id="78143-107">En el Explorador de soluciones, haga clic en el nodo de soluciones, haga clic en **agregar**y, a continuación, haga clic en **nuevo proyecto**.</span><span class="sxs-lookup"><span data-stu-id="78143-107">In Solution Explorer, right-click the solution node, click **Add**, and then click **New Project**.</span></span>  
  
3.  <span data-ttu-id="78143-108">En el **Agregar nuevo proyecto** cuadro de diálogo, en la **tipos de proyecto** área, expanda **otros tipos de proyectos**, expanda **el programa de instalación y proyectos de implementación**y, a continuación, seleccione **instalador de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="78143-108">In the **Add New Project** dialog box, in the **Project Types** area, expand **Other Project Types**, expand **Setup and Deployment Projects**, and then select **Visual Studio Installer**.</span></span> <span data-ttu-id="78143-109">En el **plantillas** área, seleccione **Web Setup Project**.</span><span class="sxs-lookup"><span data-stu-id="78143-109">In the **Templates** area, select **Web Setup Project**.</span></span>  
  
4.  <span data-ttu-id="78143-110">En el **nombre** cuadro de texto, escriba un nombre para el proyecto de instalación Web.</span><span class="sxs-lookup"><span data-stu-id="78143-110">In the **Name** text box, type a name for the Web Setup Project.</span></span> <span data-ttu-id="78143-111">Puede usar el mismo nombre que el proyecto de servicio Web ASP.NET y agregar "_Setup" como sufijo y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="78143-111">You can use the same name as the ASP.NET Web Service project and add "_Setup" as a suffix and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="78143-112">En el Explorador de soluciones, haga clic en el nodo del proyecto de instalación Web recién creado y seleccione **vista**y, a continuación, haga clic en **sistema de archivos**.</span><span class="sxs-lookup"><span data-stu-id="78143-112">In Solution Explorer, right-click the newly created Web setup project node, and point to **View**, and then click **File System**.</span></span>  
  
6.  <span data-ttu-id="78143-113">En el **sistema de archivos** ventana, haga clic en el **carpeta de aplicación Web** nodo y seleccione **agregar**, a continuación, haga clic en **resultado del proyecto**.</span><span class="sxs-lookup"><span data-stu-id="78143-113">In the **File System** window, right-click the **Web Application Folder** node and point to **Add**, then click **Project Output**.</span></span>  
  
7.  <span data-ttu-id="78143-114">En el **Agregar grupo de resultados del proyecto** cuadro de diálogo, seleccione **salida principal** y **archivos de contenido** desde el servicio Web ASP.NET del proyecto y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="78143-114">In the **Add Project Output Group** dialog box, select **Primary Output** and **Content Files** from the ASP.NET Web Service project and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="78143-115">En el Explorador de soluciones, expanda la **Dependencias detectadas** nodo bajo el proyecto de instalación Web.</span><span class="sxs-lookup"><span data-stu-id="78143-115">In Solution Explorer, expand the **Detected Dependencies** node under the Web setup project.</span></span>  
  
9. <span data-ttu-id="78143-116">Seleccione todas las dependencias.</span><span class="sxs-lookup"><span data-stu-id="78143-116">Select all dependencies.</span></span> <span data-ttu-id="78143-117">En el **propiedades** ventana, establezca el **excluir** propiedad **True**.</span><span class="sxs-lookup"><span data-stu-id="78143-117">In the **Properties** window, set the **Exclude** property to **True**.</span></span>  
  
10. <span data-ttu-id="78143-118">Cree su proyecto de instalación Web.</span><span class="sxs-lookup"><span data-stu-id="78143-118">Build your Web setup project.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="78143-119">Para obtener más información acerca de cómo crear proyectos de instalación Web, vea "Cómo para crear o agregar a Web Setup Project" en el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ayudar a la colección [http://go.microsoft.com/fwlink/?LinkId=62268](http://go.microsoft.com/fwlink/?LinkId=62268).</span><span class="sxs-lookup"><span data-stu-id="78143-119">For more information about creating Web setup projects, see "How to Create or Add a Web Setup Project" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62268](http://go.microsoft.com/fwlink/?LinkId=62268).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78143-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="78143-120">See Also</span></span>  
 [<span data-ttu-id="78143-121">Implementar servicios Web publicados en un equipo que no tenga Visual Studio</span><span class="sxs-lookup"><span data-stu-id="78143-121">Deploying Published Web Services on a Non-Visual Studio Computer</span></span>](../core/deploying-published-web-services-on-a-non-visual-studio-computer.md)