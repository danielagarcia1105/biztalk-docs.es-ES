---
title: "Cómo agregar el comportamiento del Interceptor BAM al archivo Machine.config | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ea09925-264f-4976-8e34-f63bad70f886
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abc8845333389c95ea52d440437935d4c4867dc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-the-bam-interceptor-behavior-to-the-machineconfig-file"></a><span data-ttu-id="cddda-102">Cómo agregar el comportamiento del interceptor de BAM al archivo Machine.config.</span><span class="sxs-lookup"><span data-stu-id="cddda-102">How to Add the BAM Interceptor Behavior to the Machine.config File</span></span>
<span data-ttu-id="cddda-103">Para interceptar datos en BAM, debe agregar el comportamiento del interceptor de BAM al archivo machine.config de Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="cddda-103">To intercept data in BAM, you must add the BAM interceptor behavior to the Microsoft .NET machine.config file.</span></span> <span data-ttu-id="cddda-104">Hay dos maneras de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="cddda-104">You can do this in two ways:</span></span>  
  
-   <span data-ttu-id="cddda-105">Editar de forma manual el archivo machine.config para incluir el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="cddda-105">Manually edit the machine.config file to include the behavior.</span></span>  
  
-   <span data-ttu-id="cddda-106">Usar el editor de configuración de servicio para incluir el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="cddda-106">Use the Service Configuration Editor to include the behavior.</span></span>  
  
### <a name="to-manually-edit-the-machineconfig-file"></a><span data-ttu-id="cddda-107">Para editar de forma manual el archivo machine.config</span><span class="sxs-lookup"><span data-stu-id="cddda-107">To manually edit the machine.config file</span></span>  
  
1.  <span data-ttu-id="cddda-108">Edite el archivo machine.config situado en la carpeta de configuración de Microsoft .NET.</span><span class="sxs-lookup"><span data-stu-id="cddda-108">Edit the machine.config file located in the Microsoft .NET configuration folder.</span></span> <span data-ttu-id="cddda-109">Para ello, haga clic en **iniciar**, haga clic en **ejecutar**, escriba notepad c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="cddda-109">To do this, click **Start**, click **Run**, type notepad c:\WINDOWS\Microsoft.NET\Framework\v4.0.30319\Config\machine.config, and then click **OK**.</span></span>  
  
2.  <span data-ttu-id="cddda-110">Actualice el archivo machine.config con las siguientes extensiones de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="cddda-110">Update the machine.config file with the following behavior extensions.</span></span>  
  
    ```  
    <system.serviceModel>  
      <extensions>  
        <behaviorExtensions>  
          <add name="BAMEndPointBehaviorExtension" type="Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior, Microsoft.BizTalk.Bam.Interceptors, Version=3.0.1.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />  
        </behaviorExtensions>  
      </extensions>  
    </system.serviceModel>  
    ```  
  
3.  <span data-ttu-id="cddda-111">Cierre y guarde el archivo machine.config.</span><span class="sxs-lookup"><span data-stu-id="cddda-111">Close and save the machine.config file.</span></span>  
  
#### <a name="to-edit-the-machineconfig-file-using-the-service-configuration-editor"></a><span data-ttu-id="cddda-112">Para editar el archivo machine.config mediante el uso del editor de configuración de servicio</span><span class="sxs-lookup"><span data-stu-id="cddda-112">To edit the machine.config file using the Service Configuration Editor</span></span>  
  
1.  <span data-ttu-id="cddda-113">Abra el editor de configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="cddda-113">Open the Service Configuration Editor.</span></span> <span data-ttu-id="cddda-114">Para obtener información acerca de cómo utilizar el Editor de configuración de servicio, consulte [http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557).</span><span class="sxs-lookup"><span data-stu-id="cddda-114">For information about using the Service Configuration Editor, see [http://go.microsoft.com/fwlink/?LinkId=83557](http://go.microsoft.com/fwlink/?LinkId=83557).</span></span>  
  
2.  <span data-ttu-id="cddda-115">En el panel de vista de árbol (con la etiqueta **configuración**), expanda el árbol de nodos.</span><span class="sxs-lookup"><span data-stu-id="cddda-115">In the tree view pane (labeled **Configuration**), expand the node tree.</span></span> <span data-ttu-id="cddda-116">Haga clic en el **avanzadas** carpeta, haga clic en el **extensiones** carpeta y, a continuación, seleccione la **las extensiones de elemento de comportamiento** elemento.</span><span class="sxs-lookup"><span data-stu-id="cddda-116">Click the **Advanced** folder, click the **Extensions** folder, and then select the **behavior element extensions** element.</span></span>  
  
3.  <span data-ttu-id="cddda-117">Cree una nueva extensión de elemento de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="cddda-117">Create a new behavior element extension.</span></span> <span data-ttu-id="cddda-118">Haga clic en el **New** botón para abrir el cuadro de diálogo Editor de elementos de configuración de extensiones.</span><span class="sxs-lookup"><span data-stu-id="cddda-118">Click the **New** button to open the Extension Configuration Element Editor dialog box.</span></span> <span data-ttu-id="cddda-119">En **nombre de configuración** escriba un nombre único para el comportamiento, por ejemplo, BAMEndPointBehaviorExtension.</span><span class="sxs-lookup"><span data-stu-id="cddda-119">In **Configuration Name** enter a unique name for the behavior, for example BAMEndPointBehaviorExtension.</span></span>  
  
     <span data-ttu-id="cddda-120">![Editor de elementos de configuración de extensiones](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")</span><span class="sxs-lookup"><span data-stu-id="cddda-120">![Extension Configuration Element Editor](../core/media/00a053ba-1993-4e52-a336-e452cc60691c.gif "00a053ba-1993-4e52-a336-e452cc60691c")</span></span>  
  
4.  <span data-ttu-id="cddda-121">Haga clic en el **tipo** campo y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) para abrir el cuadro de diálogo del explorador de tipos de extensión de comportamiento.</span><span class="sxs-lookup"><span data-stu-id="cddda-121">Click the **Type** field, and then click the ellipsis button (**...**) button to open the Behavior Extension Type Browser dialog box.</span></span>  
  
5.  <span data-ttu-id="cddda-122">Haga clic en el icono de la caché de ensamblados global (GAC) para enumerar las DLL en GAC.</span><span class="sxs-lookup"><span data-stu-id="cddda-122">Click the global assembly cache (GAC) icon to list the DLLs in GAC.</span></span>  
  
6.  <span data-ttu-id="cddda-123">Seleccione el ensamblado Microsoft.BizTalk.Bam.Interceptors.</span><span class="sxs-lookup"><span data-stu-id="cddda-123">Select the Microsoft.BizTalk.Bam.Interceptors assembly.</span></span>  
  
7.  <span data-ttu-id="cddda-124">Haga clic en el **abiertos** botón para seleccionar el ensamblado y, a continuación, cierre el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="cddda-124">Click the **Open** button to select the assembly, and then close the dialog box.</span></span>  
  
     <span data-ttu-id="cddda-125">![Explorador de tipos de extensión Bejavopr](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")</span><span class="sxs-lookup"><span data-stu-id="cddda-125">![Bejavopr Extension Type Browser](../core/media/0d525d4c-927c-42d6-96b7-0ebaf2691c6c.gif "0d525d4c-927c-42d6-96b7-0ebaf2691c6c")</span></span>  
  
8.  <span data-ttu-id="cddda-126">En el panel Nombre de tipo del cuadro de diálogo del explorador del tipo de extensión de comportamiento, haga doble clic en el tipo Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior (resaltado en la siguiente pantalla).</span><span class="sxs-lookup"><span data-stu-id="cddda-126">In the Type Name pane of the Behavior Extension Type Browser dialog box, double-click the Microsoft.BizTalk.Bam.Interceptors.Wcf.BamEndpointBehavior type (as highlighted in the following screen).</span></span>  
  
     <span data-ttu-id="cddda-127">![Explorador de tipos de extensión Bejavopr](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")</span><span class="sxs-lookup"><span data-stu-id="cddda-127">![Bejavopr Extension Type Browser](../core/media/67186ad6-8802-4214-be46-11e50e4ff15d.gif "67186ad6-8802-4214-be46-11e50e4ff15d")</span></span>  
  
     <span data-ttu-id="cddda-128">Con esto se abre el editor de elementos de configuración de extensiones.</span><span class="sxs-lookup"><span data-stu-id="cddda-128">This opens the Extension Configuration Element Editor.</span></span>  
  
9. <span data-ttu-id="cddda-129">Haga clic en **Aceptar** para cerrar el cuadro de diálogo Editor de elementos de configuración de extensiones.</span><span class="sxs-lookup"><span data-stu-id="cddda-129">Click **OK** to close the Extension Configuration Element Editor dialog box.</span></span>  
  
10. <span data-ttu-id="cddda-130">En el panel de detalles del editor de configuración de servicio, compruebe que aparece BAMEndPointBehaviorExtension.</span><span class="sxs-lookup"><span data-stu-id="cddda-130">In the details pane of the Service Configuration Editor, verify that the BAMEndPointBehaviorExtension appears.</span></span>  
  
11. <span data-ttu-id="cddda-131">Cierre el editor de configuración de servicio.</span><span class="sxs-lookup"><span data-stu-id="cddda-131">Close the Service Configuration Editor.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="cddda-132">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cddda-132">Next Steps</span></span>  
 [<span data-ttu-id="cddda-133">Cómo configurar la intercepción de WCF de BAM</span><span class="sxs-lookup"><span data-stu-id="cddda-133">How to Configure the BAM WCF Interception</span></span>](../core/how-to-configure-the-bam-wcf-interception.md)  
  
## <a name="see-also"></a><span data-ttu-id="cddda-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="cddda-134">See Also</span></span>  
 [<span data-ttu-id="cddda-135">Configurar el adaptador WCF para interceptar datos BAM</span><span class="sxs-lookup"><span data-stu-id="cddda-135">Configuring the WCF Adapter to Intercept BAM Data</span></span>](../core/configuring-the-wcf-adapter-to-intercept-bam-data.md)