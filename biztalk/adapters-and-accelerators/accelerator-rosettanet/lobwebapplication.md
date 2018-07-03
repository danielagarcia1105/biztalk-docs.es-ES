---
title: LOBWebApplication | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9120d9078303092740fdbfc27b6932b7849cc6a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002109"
---
# <a name="lobwebapplication"></a><span data-ttu-id="ec8b6-102">LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="ec8b6-102">LOBWebApplication</span></span>
<span data-ttu-id="ec8b6-103">Use la utilidad de LOBWebApplication para enviar un mensaje de acción o respuesta de una página ASPX a un socio comercial, simulando una aplicación Web de línea de negocio real.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-103">You use the LOBWebApplication utility to submit an action or response message from an ASPX page to a trading partner, simulating an actual line-of-business Web application.</span></span>  
  
 <span data-ttu-id="ec8b6-104">Una vez haya configurado la página ASPX, la página de inicio y escriba los parámetros de un mensaje: el principal y organizaciones asociadas; el código PIP, versión y el Id. de instancia; y la categoría del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-104">After you have set up the ASPX page, you start the page, and enter the parameters for a message: the home and partner organizations; the PIP code, version, and instance ID; and the message category.</span></span> <span data-ttu-id="ec8b6-105">A continuación, puede modificar el contenido del servicio y enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-105">You can then modify the service content, and submit the message.</span></span>  
  
## <a name="location-in-sdk"></a><span data-ttu-id="ec8b6-106">Ubicación en SDK</span><span class="sxs-lookup"><span data-stu-id="ec8b6-106">Location in SDK</span></span>  
 <span data-ttu-id="ec8b6-107">\<*unidad*\>\Program Files (86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="ec8b6-107">\<*drive*\>\Program Files (86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication</span></span>  
  
## <a name="adding-a-virtual-server-for-lobwebapplication"></a><span data-ttu-id="ec8b6-108">Agregar un servidor Virtual de LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="ec8b6-108">Adding a Virtual Server for LOBWebApplication</span></span>  
  
#### <a name="to-add-a-virtual-server"></a><span data-ttu-id="ec8b6-109">Para agregar un servidor virtual</span><span class="sxs-lookup"><span data-stu-id="ec8b6-109">To add a virtual server</span></span>  
  
1.  <span data-ttu-id="ec8b6-110">Haga clic en **iniciar**, apunte a **AllPrograms**, apunte a **herramientas administrativas**y, a continuación, haga clic en **Internet Information Services (IIS) Manager**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-110">Click **Start**, point to **AllPrograms**, point to **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**.</span></span>  
  
2.  <span data-ttu-id="ec8b6-111">En el Administrador de servicios de información, expanda  **\<nombre_equipo\> (equipo local)**, expanda **sitios Web**y, a continuación, haga clic en **sitio Web predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-111">In Information Services Manager, expand **\<Computer name\> (local computer)**, expand **Web Sites**, and then right-click **Default Web Site**.</span></span>  
  
3.  <span data-ttu-id="ec8b6-112">Seleccione **New**y, a continuación, haga clic en **directorio Virtual**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-112">Point to **New**, and then click **Virtual Directory**.</span></span>  
  
4.  <span data-ttu-id="ec8b6-113">En el **Asistente para crear un directorio Virtual** página, haga clic en **siguiente**y, a continuación, escriba un alias para el sitio, como **LOBWebApplication**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-113">On the **Virtual Directory Creation Wizard** page, click **Next**, and then type an alias for the site, such as **LOBWebApplication**.</span></span>  
  
5.  <span data-ttu-id="ec8b6-114">En el **directorio de contenido del sitio Web** página, haga clic en **examinar**, mover a \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication, haga clic en **Aceptar**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-114">On the **Web Site Content Directory** page, click **Browse**, move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication, click **OK**, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="ec8b6-115">En el **permisos de acceso del directorio Virtual** página, seleccione **lectura** y **ejecutar secuencias de comandos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-115">On the **Virtual Directory Access Permissions** page, select **Read** and **Run scripts**, and then click **Next**.</span></span> <span data-ttu-id="ec8b6-116">Haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-116">Click **Finish**.</span></span>  
  
7.  <span data-ttu-id="ec8b6-117">Agregue el usuario de la cuenta de servicio que se usó para configurar BTARN, por ejemplo, hostsvc a la STS_WPG.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-117">Add the service account user that was used to configure BTARN, for example, hostsvc, to the STS_WPG.</span></span>  
  
8.  <span data-ttu-id="ec8b6-118">Eliminar todos los archivos de los archivos ASP.NET C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-118">Delete all files from C:\WINDOWS\Microsoft.NET\Framework\v2.0.\Temporary ASP.NET Files.</span></span> <span data-ttu-id="ec8b6-119">Es posible que deba ejecutar el programa iisreset para desbloquear los archivos antes de que se pueden eliminar.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-119">You may have to run the iisreset program to unlock the files before you can delete them.</span></span>  
  
9. <span data-ttu-id="ec8b6-120">En el Administrador de IIS, establezca LOBWebApplication para ejecutarse en el BTARNHTTPReceivePool del grupo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-120">In IIS Manager, set the LOBWebApplication to run under the Application Pool BTARNHTTPReceivePool.</span></span>  
  
10. <span data-ttu-id="ec8b6-121">En el Administrador de IIS, en la sección de propiedades de seguridad del directorio de la utilidad de LOBWebApplication, deshabilite la opción para el directorio virtual para ejecutarlo como anónimo.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-121">In IIS Manager, in the Directory Security Properties section for the LOBWebApplication utility, disable the option for the virtual directory to run as anonymous.</span></span>  
  
## <a name="building-lobwebapplication"></a><span data-ttu-id="ec8b6-122">Creación LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="ec8b6-122">Building LOBWebApplication</span></span>  
  
#### <a name="to-build-lobwebapplication"></a><span data-ttu-id="ec8b6-123">Para compilar LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="ec8b6-123">To build LOBWebApplication</span></span>  
  
1. <span data-ttu-id="ec8b6-124">Inicie Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-124">Start Visual Studio.</span></span>  
  
2. <span data-ttu-id="ec8b6-125">En el **archivo**, apunte a **abierto**y, a continuación, haga clic en **Abrir solución**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-125">On the **File**, point to **Open**, and then click **Open Solution**.</span></span>  
  
3. <span data-ttu-id="ec8b6-126">Mover a \< *unidad*\>\Program Files (x86) \Microsoft BizTalk \<versión\> Accelerator for RosettaNet\SDK\LOBWebApplication, seleccione  **LOBWebApplication.sln**y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-126">Move to \<*drive*\>\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\LOBWebApplication, select **LOBWebApplication.sln**, and then click **Open**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ec8b6-127">Si no ha agregado un servidor virtual de LOBWebApplication, no se abrirá correctamente en la solución [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ec8b6-127">If you have not added a virtual server for LOBWebApplication, the solution will not open correctly in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span>  
  
4. <span data-ttu-id="ec8b6-128">Haga clic en **referencias**y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-128">Right-click **References**, and then click **Add Reference**.</span></span>  
  
5. <span data-ttu-id="ec8b6-129">En el **Agregar referencia** cuadro de diálogo, haga clic en **examinar**, mover a \< *unidad*\>: \Program Files (x86) \Microsoft BizTalk \< versión\> Accelerator for RosettaNet\Bin, seleccione los archivos Microsoft.Solutions.BTARN.ConfigurationManager.dll y Microsoft.Solutions.BTARN.Shared.dll y, a continuación, haga clic en **abierto**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-129">In the **Add Reference** dialog box, click **Browse**, move to \<*drive*\>:\Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin, select the Microsoft.Solutions.BTARN.ConfigurationManager.dll and Microsoft.Solutions.BTARN.Shared.dll files, and then click **Open**.</span></span>  
  
6. <span data-ttu-id="ec8b6-130">Haga clic en **LOBWebApplication**y, a continuación, haga clic en **compilar**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-130">Right-click **LOBWebApplication**, and then click **Build**.</span></span>  
  
## <a name="running-lobwebapplication"></a><span data-ttu-id="ec8b6-131">Ejecución de LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="ec8b6-131">Running LOBWebApplication</span></span>  
  
#### <a name="to-run-lobwebapplication-and-submit-a-message"></a><span data-ttu-id="ec8b6-132">Para ejecutar LOBWebApplication y enviar un mensaje</span><span class="sxs-lookup"><span data-stu-id="ec8b6-132">To run LOBWebApplication and submit a message</span></span>  
  
1.  <span data-ttu-id="ec8b6-133">Haga clic en **iniciar**, apunte a **todos los programas**y, a continuación, haga clic en **Internet Explorer**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-133">Click **Start**, point to **All Programs**, and then click **Internet Explorer**.</span></span>  
  
2.  <span data-ttu-id="ec8b6-134">En Internet Explorer, en el **dirección** , escriba http://localhost/LOBWebApplicationy, a continuación, haga clic en **vaya**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-134">In Internet Explorer, in the **Address** box, type http://localhost/LOBWebApplication, and then click **Go**.</span></span>  
  
3.  <span data-ttu-id="ec8b6-135">En el **enviar mensaje** diálogo cuadro, escriba la organización principal, la organización del asociado, el código PIP, la versión PIP, el identificador de instancia PIP y la categoría del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-135">In the **Submit Message** dialog box, type the home organization, the partner organization, the PIP code, the PIP version, the PIP Instance ID, and the message category.</span></span>  
  
4.  <span data-ttu-id="ec8b6-136">Modificar el contenido del servicio según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-136">Modify the service content as needed.</span></span>  
  
5.  <span data-ttu-id="ec8b6-137">Haga clic en **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-137">Click **Submit**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec8b6-138">Notas</span><span class="sxs-lookup"><span data-stu-id="ec8b6-138">Remarks</span></span>  
 <span data-ttu-id="ec8b6-139">La utilidad de LOBWebApplication genera una instancia del mensaje a partir del PIP especificado y escribe el contenido del servicio de la instancia de mensaje generado en la página ASPX.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-139">The LOBWebApplication utility generates an instance of the message from the specified PIP, and enters service content from the generated message instance into the ASPX page.</span></span> <span data-ttu-id="ec8b6-140">Para ello, la utilidad utiliza la misma técnica que usa para generar una instancia de mensaje correcto directamente a partir de un PIP.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-140">To do this, the utility uses the same technique that it uses to generate a well-formed message instance directly from a PIP.</span></span> <span data-ttu-id="ec8b6-141">Para obtener más información, consulte [crear una instancia de mensaje bien formado a partir de un PIP](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md).</span><span class="sxs-lookup"><span data-stu-id="ec8b6-141">For more information, see [Creating a Well-Formed Message Instance from a PIP](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-well-formed-message-instance-from-a-pip.md).</span></span> <span data-ttu-id="ec8b6-142">Puede rellenar cualquier campo de contenido del servicio en la página ASPX con datos reales para generar una instancia real del mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-142">You can populate any field of the service content in the ASPX page with actual data to generate an actual message instance.</span></span>  
  
 <span data-ttu-id="ec8b6-143">Use la utilidad de LOBWebApplication para simular una aplicación Web de línea de negocio enviando un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-143">You use the LOBWebApplication utility to simulate a line-of-business Web application submitting a message.</span></span> <span data-ttu-id="ec8b6-144">Use la utilidad LOBApplication para simular una aplicación de escritorio de línea de negocio enviando un mensaje.</span><span class="sxs-lookup"><span data-stu-id="ec8b6-144">You use the LOBApplication utility to simulate a line-of-business desktop application submitting a message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec8b6-145">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec8b6-145">See Also</span></span>  
 <span data-ttu-id="ec8b6-146">[Utilidades](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span><span class="sxs-lookup"><span data-stu-id="ec8b6-146">[Utilities](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md) </span></span>  
 [<span data-ttu-id="ec8b6-147">LOBApplication</span><span class="sxs-lookup"><span data-stu-id="ec8b6-147">LOBApplication</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/lobapplication.md)
