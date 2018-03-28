---
title: Importar enlaces para TIBCO EMS | Documentos de Microsoft
description: Implementar el adaptador de BizTalk para aplicaciones de TIBCO Enterprise Message Service con la característica Importar enlaces en BizTalk Server
ms.custom: ''
ms.date: 10/23/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 69dae448-4ec6-4a56-a628-bb447bc21b62
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79f7f3ec0478746b8c2c6762fe212229f9c7b11d
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-tibco-ems-ports-and-assemblies"></a><span data-ttu-id="fe49a-103">Implementar ensamblados y puertos de TIBCO EMS</span><span class="sxs-lookup"><span data-stu-id="fe49a-103">Deploy TIBCO EMS ports and assemblies</span></span>

## <a name="overview"></a><span data-ttu-id="fe49a-104">Información general</span><span class="sxs-lookup"><span data-stu-id="fe49a-104">Overview</span></span>
<span data-ttu-id="fe49a-105">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede duplicar puertos y ensamblados en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="fe49a-105">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fe49a-106"> configuración de la ubicación de recepción/puertos de envío de exportaciones en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="fe49a-106"> exports send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="fe49a-107">Puede usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="fe49a-107">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
-   <span data-ttu-id="fe49a-108">Implementar o quitar los ensamblados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en una base de datos de configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="fe49a-108">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database.</span></span>  
  
-   <span data-ttu-id="fe49a-109">Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="fe49a-109">Install or uninstall the assemblies in the global assembly cache (GAC).</span></span>  
  
-   <span data-ttu-id="fe49a-110">Importar información de enlace de ensamblado de BizTalk a archivos de enlace o exportarla a ellos.</span><span class="sxs-lookup"><span data-stu-id="fe49a-110">Import or export BizTalk assembly binding information to and from binding files.</span></span>  
  
 <span data-ttu-id="fe49a-111">Para obtener información sobre cómo usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="fe49a-111">For information about how to use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fe49a-112">Microsoft BizTalk Adapter para TIBCO Enterprise Message Service solo necesita que disponga de Visual Studio en un equipo de origen (desarrollo).</span><span class="sxs-lookup"><span data-stu-id="fe49a-112">Microsoft BizTalk Adapter for TIBCO Enterprise Message Service only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="fe49a-113">Visual Studio no es necesario en el equipo de producción.</span><span class="sxs-lookup"><span data-stu-id="fe49a-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="fe49a-114">Confirme la configuración</span><span class="sxs-lookup"><span data-stu-id="fe49a-114">Confirm your setup</span></span>
<span data-ttu-id="fe49a-115">Antes de usar BizTalk Server para importar un archivo de enlace, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fe49a-115">Before you use BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="fe49a-116">Deben existir las carpetas para las respuestas y ser idénticas en el equipo nuevo, o bien debe editar el archivo.</span><span class="sxs-lookup"><span data-stu-id="fe49a-116">The folders for the responses must exist and be identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="fe49a-117">Las contraseñas del sistema TIBCO Enterprise Message Service, si están presentes en la configuración, se guardan como \*\*\*\*\* en el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="fe49a-117">TIBCO Enterprise Message Service system passwords, if present in the configuration, must be saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="fe49a-118">Vea **limitaciones** en este tema.</span><span class="sxs-lookup"><span data-stu-id="fe49a-118">See **Limitations** in this topic.</span></span>


## <a name="clean-the-target-computer"></a><span data-ttu-id="fe49a-119">Limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="fe49a-119">Clean the target computer</span></span>
<span data-ttu-id="fe49a-120">Implementación sobrescribe la configuración de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="fe49a-120">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="fe49a-121">Al implementar un archivo de enlace (y el ensamblado) en un equipo de destino, los puertos de envío y ubicaciones de recepción se sustituyen por los en el archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="fe49a-121">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  

<span data-ttu-id="fe49a-122">Antes de importar, quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="fe49a-122">Before you import, remove any send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="fe49a-123">Si no tiene Microsoft Visual Studio instalada en el equipo de destino, puede quitar los puertos ejecutando estas secuencias de comandos:</span><span class="sxs-lookup"><span data-stu-id="fe49a-123">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs`  
  
`\<Microsoft BizTalk Server\>\SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs`
  

<span data-ttu-id="fe49a-124">Por ejemplo, en un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="fe49a-124">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```

## <a name="limitations"></a><span data-ttu-id="fe49a-125">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="fe49a-125">Limitations</span></span>
<span data-ttu-id="fe49a-126">La contraseña del adaptador de transporte se almacena como estrellas (\*\*\*\*\*\*) en el archivo de enlace que se ha exportado por BizTalk Server y pasa al componente de administración en el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="fe49a-126">The Transport Adapter password is stored as stars (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Server, and it passes to the management component in the same format.</span></span> <span data-ttu-id="fe49a-127">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).</span><span class="sxs-lookup"><span data-stu-id="fe49a-127">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="fe49a-128">Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="fe49a-128">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
 <span data-ttu-id="fe49a-129">Se trata de una limitación conocida.</span><span class="sxs-lookup"><span data-stu-id="fe49a-129">This is a known limitation.</span></span> <span data-ttu-id="fe49a-130">Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="fe49a-130">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="fe49a-131">De este modo, se evita que la información de contraseña aparezca en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="fe49a-131">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="fe49a-132">La próxima vez que utilice el archivo para importar la información de enlace, debe escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="fe49a-132">The next time that you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="fe49a-133">También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo.</span><span class="sxs-lookup"><span data-stu-id="fe49a-133">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="fe49a-134">En ese caso, debe eliminar las contraseñas del archivo de enlace antes de que finalice la operación de importación correctamente.</span><span class="sxs-lookup"><span data-stu-id="fe49a-134">In this case, you must delete the passwords from the binding file after the import operation successfully finishes.</span></span>  
  
 
### <a name="password-limitation-workaround"></a><span data-ttu-id="fe49a-135">Solución para la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="fe49a-135">Password Limitation Workaround</span></span>  
 <span data-ttu-id="fe49a-136">Para solucionar esta limitación de contraseña, puede usar uno de los siguientes métodos:</span><span class="sxs-lookup"><span data-stu-id="fe49a-136">To work around this password limitation, you can use one of the following methods:</span></span>  
  
-   <span data-ttu-id="fe49a-137">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="fe49a-137">Edit the binding file before importing by replacing the stars with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="fe49a-138">Por motivos de seguridad, esta práctica no es recomendable.</span><span class="sxs-lookup"><span data-stu-id="fe49a-138">This is not recommended for security reasons.</span></span>  
  
-   <span data-ttu-id="fe49a-139">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).</span><span class="sxs-lookup"><span data-stu-id="fe49a-139">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="fe49a-140">Escriba la contraseña correcta mediante la **propiedades de transporte** página en la consola de administración de BizTalk Server después de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="fe49a-140">Enter the correct password using the **Transport Properties** page in the BizTalk Server Administration Console after importing the binding file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="fe49a-141">Esta solución solo se puede usar si Visual Studio está instalado en el equipo de destino, o si desarrolla una herramienta personalizada.</span><span class="sxs-lookup"><span data-stu-id="fe49a-141">This work-around can be used only if Visual Studio is installed on the target computer, or if you develop a custom tool.</span></span>  
  
-   <span data-ttu-id="fe49a-142">Compruebe el sistema lógico y los servicios de transmisión y recepción.</span><span class="sxs-lookup"><span data-stu-id="fe49a-142">Verify the Logical system and the Transmit and Receive services.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="fe49a-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fe49a-143">Next steps</span></span>
[<span data-ttu-id="fe49a-144">Usar el control de excepciones de BizTalk Server en la orquestación</span><span class="sxs-lookup"><span data-stu-id="fe49a-144">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling5.md)