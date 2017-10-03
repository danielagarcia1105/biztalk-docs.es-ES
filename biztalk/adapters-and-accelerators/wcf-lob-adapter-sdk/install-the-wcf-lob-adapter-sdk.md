---
title: Instalar el SDK del adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 41b9b34b-3fbb-480f-a335-a218eab33693
caps.latest.revision: "40"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa2124425fa97729b1bec692fc1a88e301434c0b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="install-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="48321-102">Instalar el SDK del adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="48321-102">Install the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="48321-103">Instalar y configurar el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48321-103">Install and configure the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> 
  
## <a name="requirements"></a><span data-ttu-id="48321-104">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48321-104">Requirements</span></span> 
<span data-ttu-id="48321-105">Instalar el siguiente componentes en el sistema donde se instala el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48321-105">Install following components on the system where you install the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> 

> [!NOTE]
> <span data-ttu-id="48321-106">**Para obtener una lista de las versiones admitidas**, consulte:</span><span class="sxs-lookup"><span data-stu-id="48321-106">**For a list of the supported versions**, see:</span></span> 
> 
> <span data-ttu-id="48321-107">[Hardware and Software Requirements for BizTalk Server 2016](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md) (Requisitos de hardware y software de BizTalk Server 2016)</span><span class="sxs-lookup"><span data-stu-id="48321-107">[Hardware and Software Requirements for BizTalk Server 2016](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)</span></span>  
> [<span data-ttu-id="48321-108">Requisitos de hardware y Software para BizTalk Server 2013 y 2013 R2</span><span class="sxs-lookup"><span data-stu-id="48321-108">Hardware and Software Requirements for BizTalk Server 2013 and 2013 R2</span></span>](../../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2013-and-2013-r2.md)
 
 | | | 
 | --- | --- |
 | <span data-ttu-id="48321-109">Windows</span><span class="sxs-lookup"><span data-stu-id="48321-109">Windows</span></span> | <span data-ttu-id="48321-110">x86 o x x64</span><span class="sxs-lookup"><span data-stu-id="48321-110">x86 or x64</span></span> <br/><br/><span data-ttu-id="48321-111">Recursos de sistema operativo necesarios son:</span><span class="sxs-lookup"><span data-stu-id="48321-111">Required OS resources include:</span></span><br/> <ul><li><span data-ttu-id="48321-112">Microsoft Distributed Transaction Coordinator (MSDTC): Debe para admitir las transacciones de OleTx</span><span class="sxs-lookup"><span data-stu-id="48321-112">Microsoft Distributed Transaction Coordinator (MSDTC) : Required to support OleTx transactions</span></span></li><li><span data-ttu-id="48321-113">Message Queue Server (MSMQ): Debe para admitir la mensajería de confianza</span><span class="sxs-lookup"><span data-stu-id="48321-113">Message Queuing (MSMQ) : Required to support reliable messaging</span></span></li><li><span data-ttu-id="48321-114">Internet Information Services (IIS): Necesario si desea hospedar su aplicación en IIS</span><span class="sxs-lookup"><span data-stu-id="48321-114">Internet Information Services (IIS) : Required if you want to host your application in IIS</span></span></li><li><span data-ttu-id="48321-115">Windows Process Activation Service (WAS): Necesario si desea hospedar su aplicación en WAS</span><span class="sxs-lookup"><span data-stu-id="48321-115">Windows Process Activation Service (WAS) : Required if you want to host your application in WAS</span></span></li></ul> |
 |<span data-ttu-id="48321-116">Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="48321-116">Windows Communication Foundation</span></span>| | 
 | [!INCLUDE[btsDotNetFramework_md](../../includes/btsdotnetframework-md.md)] | | 
 | [!INCLUDE[btsVStudioNoVersion_md](../../includes/btsvstudionoversion-md.md)] | <span data-ttu-id="48321-117">Necesario si va a crear adaptadores personalizados, o bien desarrollar soluciones que usan los adaptadores integrados con el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48321-117">Required if you are building custom adapters, or developing solutions that use the adapters built with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> |
| [!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)] | <span data-ttu-id="48321-118">Obligatorio si usa los adaptadores con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="48321-118">Required if you use the adapters with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span>  |


  
## <a name="install"></a><span data-ttu-id="48321-119">Install</span><span class="sxs-lookup"><span data-stu-id="48321-119">Install</span></span>

> [!IMPORTANT]
> * <span data-ttu-id="48321-120">Cierre todas las instancias de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="48321-120">Close all instances of Visual Studio</span></span>
> * <span data-ttu-id="48321-121">Para realizar una **completar** el programa de instalación, confirme que BizTalk Server está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="48321-121">To do a **Complete** setup, confirm that BizTalk Server is installed on the computer.</span></span>  
  
1.  <span data-ttu-id="48321-122">Ejecute el [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe** como administrador.</span><span class="sxs-lookup"><span data-stu-id="48321-122">Run the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] **Setup.exe** as Administrator.</span></span>
  
2.  <span data-ttu-id="48321-123">Seleccione **instalar Microsoft BizTalk Adapters**y, a continuación, seleccione **instalar el SDK de Microsoft WCF LOB adaptador**.</span><span class="sxs-lookup"><span data-stu-id="48321-123">Select **Install Microsoft BizTalk Adapters**, and then select **Install Microsoft WCF LOB Adapter SDK**.</span></span>  
  
3.  <span data-ttu-id="48321-124">En el **bienvenida** pantalla, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="48321-124">On the **Welcome** screen, select **Next**.</span></span>  
  
4.  <span data-ttu-id="48321-125">Acepte el contrato de licencia y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="48321-125">Accept the license agreement, and select **Next**.</span></span>  
  
5.  <span data-ttu-id="48321-126">En **Elegir tipo de instalación**, seleccione el tipo de instalación:</span><span class="sxs-lookup"><span data-stu-id="48321-126">In **Choose Setup Type**, select the type of installation:</span></span>  
  
    -   <span data-ttu-id="48321-127">Para instalar las herramientas y el tiempo de ejecución comunes, seleccione **típica**.</span><span class="sxs-lookup"><span data-stu-id="48321-127">To install the common run time and tools, select **Typical**.</span></span>  
  
    -   <span data-ttu-id="48321-128">Para seleccionar las características que desea instalar y la ubicación de instalación, seleccione **personalizada**y, a continuación, seleccione las características que desea instalar.</span><span class="sxs-lookup"><span data-stu-id="48321-128">To select the features that you want to install and the installation location, select **Custom**, and then select the features you want to install.</span></span>  
  
    -   <span data-ttu-id="48321-129">Para instalar todas las características, seleccione **completar**.</span><span class="sxs-lookup"><span data-stu-id="48321-129">To install all the features, select **Complete**.</span></span>  
  
6.  <span data-ttu-id="48321-130">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="48321-130">Select **Install**.</span></span>  
  
## <a name="update-or-remove"></a><span data-ttu-id="48321-131">Quitar o actualizar</span><span class="sxs-lookup"><span data-stu-id="48321-131">Update or remove</span></span>
  
1.  <span data-ttu-id="48321-132">Abra **programas y características**.</span><span class="sxs-lookup"><span data-stu-id="48321-132">Open **Programs and Feature**.</span></span> 
  
2.  <span data-ttu-id="48321-133">En la lista, seleccione **SDK de adaptador LOB de Windows Communication Foundation**y, a continuación, seleccione **cambio**.</span><span class="sxs-lookup"><span data-stu-id="48321-133">In the list, select **Windows Communication Foundation LOB Adapter SDK**, and then select **Change**.</span></span>  
  
3.  <span data-ttu-id="48321-134">En el **bienvenida** pantalla, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="48321-134">On the **Welcome** screen, select **Next**.</span></span>  
  
4.  <span data-ttu-id="48321-135">Realice una de las siguientes operaciones:</span><span class="sxs-lookup"><span data-stu-id="48321-135">Do one of the following:</span></span>  
  
    -   <span data-ttu-id="48321-136">Para seleccionar los componentes que desea instalar, seleccione **cambio**.</span><span class="sxs-lookup"><span data-stu-id="48321-136">To select the components that you want to install, select **Change**.</span></span>  
  
    -   <span data-ttu-id="48321-137">Para reparar los errores en la instalación más reciente, seleccione **reparar**.</span><span class="sxs-lookup"><span data-stu-id="48321-137">To repair errors in the most recent installation, select **Repair**.</span></span>  
  
    -   <span data-ttu-id="48321-138">Para quitar el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en el equipo, seleccione **quitar**.</span><span class="sxs-lookup"><span data-stu-id="48321-138">To remove the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] from the computer, select **Remove**.</span></span>  
  
5.  <span data-ttu-id="48321-139">Si decide modificar la instalación:</span><span class="sxs-lookup"><span data-stu-id="48321-139">If you choose to modify the installation:</span></span>  
  
    1.  <span data-ttu-id="48321-140">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="48321-140">Select **Next**.</span></span>  
  
    2.  <span data-ttu-id="48321-141">Seleccione **cambio**y, a continuación, seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="48321-141">Select **Change**, and then select **Finish**.</span></span>  
  
6.  <span data-ttu-id="48321-142">Si elige reparar la instalación, en la **preparado para reparar el SDK de adaptador LOB de WCF** cuadro de diálogo, seleccione **reparar**y, a continuación, seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="48321-142">If you choose to repair the installation, in the **Ready to repair WCF LOB Adapter SDK** dialog box, select **Repair**, and then select **Finish**.</span></span>  
  
7.  <span data-ttu-id="48321-143">Si decide quitar los adaptadores, en el **listo para quitar el SDK de adaptador LOB de WCF** cuadro de diálogo, seleccione **quitar**y, a continuación, seleccione **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="48321-143">If you choose to remove the adapters, in the **Ready to remove WCF LOB Adapter SDK** dialog box, select **Remove**, and then select **Finish**.</span></span>  
  
  
#### <a name="remove-custom-adapters-after-uninstalling-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="48321-144">Quitar adaptadores personalizados después de desinstalar el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="48321-144">Remove custom adapters after uninstalling the WCF LOB Adapter SDK</span></span>  

 <span data-ttu-id="48321-145">Si ha desarrollado los adaptadores personalizados mediante el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]y estos adaptadores se han registrado en el equipo, también debe completar el procedimiento siguiente.</span><span class="sxs-lookup"><span data-stu-id="48321-145">If you have developed any custom adapters using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], and you have registered these adapters on your computer, you must also complete the following procedure.</span></span>  
  
1.  <span data-ttu-id="48321-146">Quite el adaptador personalizado de la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="48321-146">Remove the custom adapter from the global assembly cache (GAC).</span></span>  
  
    1.  <span data-ttu-id="48321-147">Abra un **símbolo del sistema de Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="48321-147">Open a **Visual Studio command prompt**.</span></span>  
  
    2.  <span data-ttu-id="48321-148">Quitar personalizado **adaptador .dll** desde la GAC mediante **comando gacutil /u**.</span><span class="sxs-lookup"><span data-stu-id="48321-148">Remove the custom **adapter .dll** from the GAC using **command gacutil /u**.</span></span>  
  
2.  <span data-ttu-id="48321-149">Quite las referencias para el enlace de adaptador personalizado de machine.config.</span><span class="sxs-lookup"><span data-stu-id="48321-149">Remove the references to the custom adapter binding from machine.config</span></span>  
  
    1.  <span data-ttu-id="48321-150">Vaya al archivo machine.config en \< *unidad del sistema*>: \WINDOWS\Microsoft.NET\Framework\\< versión\>\CONFIG.</span><span class="sxs-lookup"><span data-stu-id="48321-150">Go to the machine.config file under \<*system drive*>:\WINDOWS\Microsoft.NET\Framework\\<version\>\CONFIG.</span></span>  
  
    2.  <span data-ttu-id="48321-151">Abra el archivo con un editor de texto.</span><span class="sxs-lookup"><span data-stu-id="48321-151">Open the file by using a text editor.</span></span>  
  
    3.  <span data-ttu-id="48321-152">Busque el elemento bindingExtensions, cliente y bindingElementExtensions en system.serviceModel\extensions.</span><span class="sxs-lookup"><span data-stu-id="48321-152">Search for the element bindingExtensions, client and bindingElementExtensions under system.serviceModel\extensions.</span></span>  
  
    4.  <span data-ttu-id="48321-153">Quite el enlace de WCF que pertenece a un adaptador personalizado.</span><span class="sxs-lookup"><span data-stu-id="48321-153">Remove the WCF binding that pertains to your custom adapter.</span></span>  
  
## <a name="do-a-silent-installation"></a><span data-ttu-id="48321-154">Realizar una instalación silenciosa</span><span class="sxs-lookup"><span data-stu-id="48321-154">Do a silent installation</span></span>  
 <span data-ttu-id="48321-155">Una instalación silenciosa es ideal para escenarios de prueba o como parte de una implementación empresarial a gran escala.</span><span class="sxs-lookup"><span data-stu-id="48321-155">A silent installation is ideal for test scenarios or as part of a large-scale enterprise deployment.</span></span> [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]<span data-ttu-id="48321-156">Proporciona los parámetros de línea de comandos que puede usar con AdapterFramework.msi para realizar una instalación silenciosa.</span><span class="sxs-lookup"><span data-stu-id="48321-156"> provides command line parameters that you can use with AdapterFramework.msi to perform a silent installation.</span></span>  
 
> [!NOTE]
>  <span data-ttu-id="48321-157">Para llevar a cabo una instalación silenciosa, debe ser un administrador en el equipo.</span><span class="sxs-lookup"><span data-stu-id="48321-157">To perform silent installation, you should be an Administrator on the computer.</span></span> 

  
1.  <span data-ttu-id="48321-158">Abra un símbolo del sistema como administrador.</span><span class="sxs-lookup"><span data-stu-id="48321-158">Open a command prompt as administrator.</span></span>  
  
2.  <span data-ttu-id="48321-159">Escriba lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="48321-159">Type the following:</span></span>
  
    ```  
    AdapterFramework.msi /quiet MUOPTIN=”Yes”  
    ```  
  
    <span data-ttu-id="48321-160">Utilice las siguientes opciones de línea de comandos junto con AdapterFramework.msi:</span><span class="sxs-lookup"><span data-stu-id="48321-160">Use the following command line options in conjunction with AdapterFramework.msi:</span></span>  
  
    * <span data-ttu-id="48321-161">Use `/quiet` instalar [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] en modo silencioso.</span><span class="sxs-lookup"><span data-stu-id="48321-161">Use `/quiet` to install [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] silently.</span></span>  
  
    * <span data-ttu-id="48321-162">Usar MUOPTIN = "Yes" &#124; " No"para indicar si el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] debe buscar actualizaciones con Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="48321-162">Use MUOPTIN=”Yes”&#124;”No” to indicate if the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] should check for updates with Microsoft Update.</span></span>  
    
        <span data-ttu-id="48321-163">Cuando se establece en Sí, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] comprueba si hay actualizaciones a través de Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="48321-163">When set to Yes, [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] checks for updates through Microsoft Update.</span></span> <span data-ttu-id="48321-164">Cuando se establece en no [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] no buscar actualizaciones con Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="48321-164">When set to no [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)] does not check for updates with Microsoft Update.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48321-165">Para mostrar las opciones adicionales para la instalación de línea de comandos, escriba `AdapterFramework.msi /?`en el símbolo del sistema.</span><span class="sxs-lookup"><span data-stu-id="48321-165">To display additional options for command line installation, type `AdapterFramework.msi /?`at the command prompt.</span></span>  
  
