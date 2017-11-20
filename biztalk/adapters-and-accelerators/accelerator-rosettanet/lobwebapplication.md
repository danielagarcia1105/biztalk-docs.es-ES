---
title: LOBWebApplication | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows SharePoint Services, LOBWebApplication
- ASPX pages, LOBWebApplication utility
- virtual servers
- ASPX pages, submitting actions
- LOBWebApplication
- ASPX pages, response messages
- LOBWebApplication utility
ms.assetid: 2d578efd-72a9-4621-9274-30792bf94b6c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b00e29b51eac2c58ac7843cca75994efceb4085
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="lobwebapplication"></a><span data-ttu-id="2b031-102">LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="2b031-102">LOBWebApplication</span></span>
<span data-ttu-id="2b031-103">Use la utilidad LOBWebApplication para enviar un mensaje de acción o respuesta de una página ASPX a un socio comercial, simulando una aplicación Web de línea de negocio real.</span><span class="sxs-lookup"><span data-stu-id="2b031-103">You use the LOBWebApplication utility to submit an action or response message from an ASPX page to a trading partner, simulating an actual line-of-business Web application.</span></span>  
  
 <span data-ttu-id="2b031-104">Una vez haya configurado la página ASPX, la página de inicio y escriba los parámetros de un mensaje: el principal y organizaciones asociadas; el código PIP, versión y un identificador de instancia; y la categoría del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2b031-104">After you have set up the ASPX page, you start the page, and enter the parameters for a message: the home and partner organizations; the PIP code, version, and instance ID; and the message category.</span></span> <span data-ttu-id="2b031-105">A continuación, puede modificar el contenido del servicio y enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="2b031-105">You can then modify the service content, and submit the message.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="2b031-106">Ubicación en SDK</span><span class="sxs-lookup"><span data-stu-id="2b031-106">Location in SDK</span></span>  
 <span data-ttu-id="2b031-107">\<*unidad*> \Program BizTalk 2013 Accelerator for RosettaNet\SDK\LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="2b031-107">\<*drive*>\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\LOBWebApplication</span></span>  
  
## <a name="adding-a-virtual-server-for-lobwebapplication"></a><span data-ttu-id="2b031-108">Agregar un servidor Virtual para LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="2b031-108">Adding a Virtual Server for LOBWebApplication</span></span>  
  
#### <a name="to-add-a-virtual-server"></a><span data-ttu-id="2b031-109">Para agregar un servidor virtual</span><span class="sxs-lookup"><span data-stu-id="2b031-109">To add a virtual server</span></span>  
  
1.  <span data-ttu-id="2b031-110">Haga clic en **iniciar**, seleccione **AllPrograms**, seleccione **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="2b031-110">Click **Start**, point to **AllPrograms**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="2b031-111">En el Administrador de servicios de información, expanda  **\<nombre_equipo > (equipo local)**, expanda **sitios Web**y, a continuación, haga clic en **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="2b031-111">In Information Services Manager, expand **\<Computer name> (local computer)**, expand **Web Sites**, and then right-click **Default Web Site**.</span></span>  
  
3.  <span data-ttu-id="2b031-112">Seleccione **New**y, a continuación, haga clic en **directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="2b031-112">Point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="2b031-113">En el **Asistente para crear un directorio Virtual** página, haga clic en **siguiente**y, a continuación, escriba un alias para el sitio, como **LOBWebApplication**.</span><span class="sxs-lookup"><span data-stu-id="2b031-113">On the **Virtual Directory Creation Wizard** page, click **Next**, and then type an alias for the site, such as **LOBWebApplication**.</span></span>  
  
5.  <span data-ttu-id="2b031-114">En el **directorio de contenido del sitio Web** página, haga clic en **examinar**, mover a \< *unidad*> \Program BizTalk 2013 Accelerator for RosettaNet\ SDK\LOBWebApplication, haga clic en **Aceptar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2b031-114">On the **Web Site Content Directory** page, click **Browse**, move to \<*drive*>\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\LOBWebApplication, click **OK**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="2b031-115">En el **permisos de acceso de directorio Virtual** página, seleccione **lectura** y **ejecutar secuencias de comandos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2b031-115">On the **Virtual Directory Access Permissions** page, select **Read** and **Run scripts**, and then click **Next**.</span></span> <span data-ttu-id="2b031-116">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="2b031-116">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="2b031-117">Agregue el usuario de la cuenta de servicio que se usó para configurar BTARN, por ejemplo, hostsvc, para el STS_WPG.</span><span class="sxs-lookup"><span data-stu-id="2b031-117">Add the service account user that was used to configure BTARN, for example, hostsvc, to the STS_WPG.</span></span>  
  
8.  <span data-ttu-id="2b031-118">Eliminar todos los archivos de C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files.</span><span class="sxs-lookup"><span data-stu-id="2b031-118">Delete all files from C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files.</span></span> <span data-ttu-id="2b031-119">Tendrá que ejecutar el programa iisreset para desbloquear los archivos antes de que se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="2b031-119">You may have to run the iisreset program to unlock the files before you can delete them.</span></span>  
  
9. <span data-ttu-id="2b031-120">En el Administrador de IIS, configurar LOBWebApplication para ejecutarse en el BTARNHTTPReceivePool del grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="2b031-120">In IIS Manager, set the LOBWebApplication to run under the Application Pool BTARNHTTPReceivePool.</span></span>  
  
10. <span data-ttu-id="2b031-121">En el Administrador de IIS, en la sección de propiedades de seguridad del directorio de la utilidad de LOBWebApplication, deshabilite la opción para el directorio virtual para que se ejecute como anónimo.</span><span class="sxs-lookup"><span data-stu-id="2b031-121">In IIS Manager, in the Directory Security Properties section for the LOBWebApplication utility, disable the option for the virtual directory to run as anonymous.</span></span>  
  
## <a name="building-lobwebapplication"></a><span data-ttu-id="2b031-122">Generar LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="2b031-122">Building LOBWebApplication</span></span>  
  
#### <a name="to-build-lobwebapplication"></a><span data-ttu-id="2b031-123">Para compilar LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="2b031-123">To build LOBWebApplication</span></span>  
  
1.  <span data-ttu-id="2b031-124">Inicie [!INCLUDE[vs2012](../../includes/vs2012-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b031-124">Start [!INCLUDE[vs2012](../../includes/vs2012-md.md)].</span></span>  
  
2.  <span data-ttu-id="2b031-125">En el **archivo**, seleccione **abiertos**y, a continuación, haga clic en **Abrir solución**.</span><span class="sxs-lookup"><span data-stu-id="2b031-125">On the **File**, point to **Open**, and then click **Open Solution**.</span></span>  
  
3.  <span data-ttu-id="2b031-126">Mover a \< *unidad*> \Program BizTalk 2013 Accelerator for RosettaNet\SDK\LOBWebApplication, seleccione **LOBWebApplication.sln**y, a continuación, haga clic en  **Abra**.</span><span class="sxs-lookup"><span data-stu-id="2b031-126">Move to \<*drive*>\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\SDK\LOBWebApplication, select **LOBWebApplication.sln**, and then click **Open**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2b031-127">Si no ha agregado un servidor virtual de LOBWebApplication, no se abrirá correctamente en la solución [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b031-127">If you have not added a virtual server for LOBWebApplication, the solution will not open correctly in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
4.  <span data-ttu-id="2b031-128">Haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="2b031-128">Right-click **References**, and then click **Add Reference**.</span></span>  
  
5.  <span data-ttu-id="2b031-129">En el **Agregar referencia** cuadro de diálogo, haga clic en **examinar**, mover a \< *unidad*>: \Program BizTalk 2013 Accelerator for RosettaNet\Bin, Seleccione los archivos Microsoft.Solutions.BTARN.ConfigurationManager.dll y Microsoft.Solutions.BTARN.Shared.dll y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="2b031-129">In the **Add Reference** dialog box, click **Browse**, move to \<*drive*>:\Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet\Bin, select the Microsoft.Solutions.BTARN.ConfigurationManager.dll and Microsoft.Solutions.BTARN.Shared.dll files, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="2b031-130">Haga clic en **LOBWebApplication**y, a continuación, haga clic en **generar**.</span><span class="sxs-lookup"><span data-stu-id="2b031-130">Right-click **LOBWebApplication**, and then click **Build**.</span></span>  
  
## <a name="running-lobwebapplication"></a><span data-ttu-id="2b031-131">Ejecutando LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="2b031-131">Running LOBWebApplication</span></span>  
  
#### <a name="to-run-lobwebapplication-and-submit-a-message"></a><span data-ttu-id="2b031-132">Para ejecutar LOBWebApplication y enviar un mensaje</span><span class="sxs-lookup"><span data-stu-id="2b031-132">To run LOBWebApplication and submit a message</span></span>  
  
1.  <span data-ttu-id="2b031-133">Haga clic en **iniciar**, seleccione **todos los programas**y, a continuación, haga clic en **Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="2b031-133">Click **Start**, point to **All Programs**, and then click **Internet Explorer**.</span></span>  
  
2.  <span data-ttu-id="2b031-134">En Internet Explorer, en el **dirección** , escriba http://localhost/LOBWebApplication y, a continuación, haga clic en **vaya**.</span><span class="sxs-lookup"><span data-stu-id="2b031-134">In Internet Explorer, in the **Address** box, type http://localhost/LOBWebApplication, and then click **Go**.</span></span>  
  
3.  <span data-ttu-id="2b031-135">En el **enviar mensaje** diálogo cuadro, escriba la organización principal, la organización del asociado, el código PIP, la versión PIP, el identificador de instancia de PIP y la categoría del mensaje.</span><span class="sxs-lookup"><span data-stu-id="2b031-135">In the **Submit Message** dialog box, type the home organization, the partner organization, the PIP code, the PIP version, the PIP Instance ID, and the message category.</span></span>  
  
4.  <span data-ttu-id="2b031-136">Modifique el contenido del servicio según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="2b031-136">Modify the service content as needed.</span></span>  
  
5.  <span data-ttu-id="2b031-137">Haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="2b031-137">Click **Submit**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b031-138">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2b031-138">Remarks</span></span>  
 <span data-ttu-id="2b031-139">La utilidad de LOBWebApplication genera una instancia del mensaje a partir del PIP especificado y escribe el contenido del servicio de la instancia de mensaje generado en la página ASPX.</span><span class="sxs-lookup"><span data-stu-id="2b031-139">The LOBWebApplication utility generates an instance of the message from the specified PIP, and enters service content from the generated message instance into the ASPX page.</span></span> <span data-ttu-id="2b031-140">Para ello, la utilidad utiliza la misma técnica que usa para generar una instancia de mensaje correcto directamente desde un PIP.</span><span class="sxs-lookup"><span data-stu-id="2b031-140">To do this, the utility uses the same technique that it uses to generate a well-formed message instance directly from a PIP.</span></span> <span data-ttu-id="2b031-141">Para obtener más información, consulte [crear una instancia de mensaje bien formado a partir de un PIP](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md).</span><span class="sxs-lookup"><span data-stu-id="2b031-141">For more information, see [Creating a Well-Formed Message Instance from a PIP](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md).</span></span> <span data-ttu-id="2b031-142">Puede rellenar cualquier campo de contenido del servicio en la página ASPX con datos reales para generar una instancia de mensaje real.</span><span class="sxs-lookup"><span data-stu-id="2b031-142">You can populate any field of the service content in the ASPX page with actual data to generate an actual message instance.</span></span>  
  
 <span data-ttu-id="2b031-143">Use la utilidad LOBWebApplication para simular una aplicación Web de línea de negocio enviando un mensaje.</span><span class="sxs-lookup"><span data-stu-id="2b031-143">You use the LOBWebApplication utility to simulate a line-of-business Web application submitting a message.</span></span> <span data-ttu-id="2b031-144">Use la utilidad LOBApplication para simular una aplicación de escritorio de línea de negocio enviando un mensaje.</span><span class="sxs-lookup"><span data-stu-id="2b031-144">You use the LOBApplication utility to simulate a line-of-business desktop application submitting a message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b031-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="2b031-145">See Also</span></span>  
 <span data-ttu-id="2b031-146">[Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="2b031-146">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="2b031-147">LOBApplication</span><span class="sxs-lookup"><span data-stu-id="2b031-147">LOBApplication</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)