---
title: Importar aplicaciones PeopleSoft | Microsoft Docs
description: Usar un archivo de enlace XML para importar las aplicaciones del adaptador de PeopleSoft en BizTalk Server y las limitaciones de lectura al importar
ms.custom: ''
ms.date: 10/19/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f53d1b4-e1df-41ff-b554-1bb1d20b9111
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7ca4d0ecbfdb23e35797eb2ba3a704fe19f4cec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972717"
---
# <a name="deploy-biztalk-adapter-for-peoplesoft-enterprise"></a><span data-ttu-id="01e17-103">Implementar el adaptador de BizTalk para PeopleSoft Enterprise</span><span class="sxs-lookup"><span data-stu-id="01e17-103">Deploy BizTalk Adapter for PeopleSoft Enterprise</span></span>
<span data-ttu-id="01e17-104">Esta sección proporciona información acerca de la implementación del adaptador de BizTalk para PeopleSoft Enterprise.</span><span class="sxs-lookup"><span data-stu-id="01e17-104">This section provides information about deploying BizTalk Adapter for PeopleSoft Enterprise.</span></span>  

## <a name="overview"></a><span data-ttu-id="01e17-105">Información general</span><span class="sxs-lookup"><span data-stu-id="01e17-105">Overview</span></span>
<span data-ttu-id="01e17-106">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede duplicar puertos y ensamblados en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="01e17-106">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="01e17-107"> exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="01e17-107"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="01e17-108">Utilice [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar las siguiente tareas:</span><span class="sxs-lookup"><span data-stu-id="01e17-108">You use the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to perform these tasks:</span></span>  
  
- <span data-ttu-id="01e17-109">Implementar o quitar los ensamblados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una base de datos de configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="01e17-109">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
- <span data-ttu-id="01e17-110">Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="01e17-110">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
- <span data-ttu-id="01e17-111">Importar o exportar información de enlace de ensamblado de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde archivos de enlace o a archivos de enlace.</span><span class="sxs-lookup"><span data-stu-id="01e17-111">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files.</span></span>  
  
<span data-ttu-id="01e17-112">Para usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="01e17-112">To use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01e17-113">El adaptador de Microsoft BizTalk para PeopleSoft Enterprise solo necesita que tenga Visual Studio en un equipo de origen (desarrollo).</span><span class="sxs-lookup"><span data-stu-id="01e17-113">The Microsoft BizTalk Adapter for PeopleSoft Enterprise only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="01e17-114">Visual Studio no es necesario en el equipo de producción.</span><span class="sxs-lookup"><span data-stu-id="01e17-114">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="01e17-115">Confirme la configuración</span><span class="sxs-lookup"><span data-stu-id="01e17-115">Confirm your setup</span></span>
<span data-ttu-id="01e17-116">Antes de usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para importar un archivo de enlace, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="01e17-116">Before you use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="01e17-117">CLASSPATH apunta a una ubicación concreta para los archivos específicos de PeopleSoft.</span><span class="sxs-lookup"><span data-stu-id="01e17-117">The CLASSPATH is pointing to a specific location for the PeopleSoft-specific files.</span></span> <span data-ttu-id="01e17-118">Compruebe que la ubicación de estos archivos es el mismo en el equipo nuevo, o editar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="01e17-118">Verify that the location of these files is the same on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="01e17-119">Las carpetas para las respuestas deben existir y ser idénticas en el equipo nuevo, o editar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="01e17-119">The folders for the responses must exist and be identical on the new computer—or edit the binding file.</span></span>  
  
-   <span data-ttu-id="01e17-120">Las contraseñas del sistema PeopleSoft Enterprise, si están presentes en la configuración, se guardan como \*\*\*\*\* en el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="01e17-120">PeopleSoft Enterprise system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="01e17-121">Consulte **limitaciones** en este tema.</span><span class="sxs-lookup"><span data-stu-id="01e17-121">See **Limitations** in this topic.</span></span>

> [!NOTE]
>  <span data-ttu-id="01e17-122">La implementación sobrescribe la configuración de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="01e17-122">Deployment overwrites receive location configuration.</span></span> <span data-ttu-id="01e17-123">Al implementar un archivo de enlace y un ensamblado en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="01e17-123">When you deploy a binding file and assembly on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
 <span data-ttu-id="01e17-124">Para obtener instrucciones paso a paso sobre cómo importar archivos de enlace, consulte [cómo importar enlaces a un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md).</span><span class="sxs-lookup"><span data-stu-id="01e17-124">For step-by-step directions about importing binding files, see [How to Import Bindings into a BizTalk Group](../core/how-to-import-bindings-into-a-biztalk-group.md).</span></span> 
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="01e17-125">Limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="01e17-125">Clean the target computer</span></span>
<span data-ttu-id="01e17-126">Para limpiar el equipo de destino para la implementación de la nueva aplicación, quite los puertos de envío y ubicaciones de recepción enlazada a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="01e17-126">To clean the target computer for deploying the new application, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="01e17-127">Si Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] no está instalado en el equipo de destino, puede ejecutar estos scripts para quitar los puertos:</span><span class="sxs-lookup"><span data-stu-id="01e17-127">If you do not have Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] installed on the target computer, you may remove the ports by running these scripts:</span></span>  
  
<span data-ttu-id="01e17-128">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove enviar Port\VBScript\RemoveSendPort.vbs**</span><span class="sxs-lookup"><span data-stu-id="01e17-128">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs**</span></span>  
  
<span data-ttu-id="01e17-129">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove recibir Port\VBScript\RemoveReceivePort.vbs**</span><span class="sxs-lookup"><span data-stu-id="01e17-129">**\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs**</span></span>  
  
<span data-ttu-id="01e17-130">Por ejemplo, en un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="01e17-130">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a><span data-ttu-id="01e17-131">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="01e17-131">Limitations</span></span>
<span data-ttu-id="01e17-132">La contraseña del adaptador de transporte se almacena como asteriscos (\*) en el archivo de enlace exportado por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y pasa al componente de administración en el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="01e17-132">The Transport Adapter password is stored as asterisks (******) in the binding file that is exported by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span>  
  
 <span data-ttu-id="01e17-133">Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="01e17-133">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="01e17-134">De este modo, se evita que la información de contraseña aparezca en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="01e17-134">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="01e17-135">La próxima vez que utilice el archivo para importar la información de enlace, debe escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="01e17-135">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="01e17-136">También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo.</span><span class="sxs-lookup"><span data-stu-id="01e17-136">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="01e17-137">En ese caso, debe eliminar las contraseñas del archivo de enlace antes de que finalice la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="01e17-137">In this case, you must delete the passwords from the binding file after the import operation finishes.</span></span>  
  

### <a name="work-around-the-password-limitation"></a><span data-ttu-id="01e17-138">Evitar la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="01e17-138">Work around the password limitation</span></span>  

<span data-ttu-id="01e17-139">**Opción 1**</span><span class="sxs-lookup"><span data-stu-id="01e17-139">**Option 1**</span></span>   
  
- <span data-ttu-id="01e17-140">Antes de importar, actualice el archivo de enlace al reemplazar los asteriscos por texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="01e17-140">Before you import, update the binding file by replacing the asterisks with plain text.</span></span>  
  
  > [!CAUTION]
  >  <span data-ttu-id="01e17-141">Esta práctica no se recomienda por motivos de seguridad.</span><span class="sxs-lookup"><span data-stu-id="01e17-141">This practice is not recommended for security reasons.</span></span>  
  
- <span data-ttu-id="01e17-142">Antes de importar, actualice el fileby enlace reemplace los asteriscos por un valor aleatorio (es decir, no la contraseña correcta).</span><span class="sxs-lookup"><span data-stu-id="01e17-142">Before you import, update the binding fileby replacing the asterisks with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="01e17-143">Después de importar, escriba la contraseña correcta en el **propiedades de transporte** en administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="01e17-143">After you import, enter the correct password in the **Transport Properties** in BizTalk Server Administration.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="01e17-144">Esta solución solo puede utilizarse si Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] se encuentra instalado en el equipo de destino o si se desarrolla una herramienta personalizada.</span><span class="sxs-lookup"><span data-stu-id="01e17-144">This work-around can be used only if Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] is installed on the target computer, or if you develop a custom tool.</span></span>  
  
<span data-ttu-id="01e17-145">**Opción 2**</span><span class="sxs-lookup"><span data-stu-id="01e17-145">**Option 2**</span></span>  
  
-   <span data-ttu-id="01e17-146">Use el inicio de sesión único (SSO) empresarial en lugar de utilizar contraseñas.</span><span class="sxs-lookup"><span data-stu-id="01e17-146">Use Enterprise Single Sign-On (SSO) instead of using passwords.</span></span> <span data-ttu-id="01e17-147">El uso de la opción SSO requiere una importación del archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="01e17-147">Using the SSO option requires an import of the binding file.</span></span>  
  
- <span data-ttu-id="01e17-148">Compruebe el sistema lógico y la transmisión y recepción de servicios.</span><span class="sxs-lookup"><span data-stu-id="01e17-148">Verify the logical system and the Transmit and Receive services.</span></span> 
  
## <a name="next-steps"></a><span data-ttu-id="01e17-149">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="01e17-149">Next steps</span></span>
[<span data-ttu-id="01e17-150">Usar el control de excepciones de BizTalk Server en la orquestación</span><span class="sxs-lookup"><span data-stu-id="01e17-150">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling2.md)