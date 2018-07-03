---
title: Importar el adaptador de BizTalk para JD Edwards OneWorld | Microsoft Docs
description: Importe el archivo de enlace de la aplicación y revisar las limitaciones del adaptador de JD Edwards OneWorld en BizTalk
ms.custom: ''
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f308d2fe-39dd-4008-94ed-292c4c26fe06
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ca65c71e14d488b264d861616fe170220ac249b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999221"
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a><span data-ttu-id="47460-103">Importar la aplicación JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="47460-103">Import the JD Edwards EnterpriseOne application</span></span>
  
## <a name="overview"></a><span data-ttu-id="47460-104">Información general</span><span class="sxs-lookup"><span data-stu-id="47460-104">Overview</span></span>
<span data-ttu-id="47460-105">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] puede duplicar puertos y ensamblados en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="47460-105">Using [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> <span data-ttu-id="47460-106">BizTalk Server exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="47460-106">BizTalk Server exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="47460-107">Puede usar BizTalk Server para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="47460-107">You can use BizTalk Server to do the following tasks:</span></span>  
  
-   <span data-ttu-id="47460-108">Implementar o quitar los ensamblados de BizTalk Server en una base de datos de configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="47460-108">Deploy or remove BizTalk Server assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="47460-109">Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="47460-109">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="47460-110">Importar o exportar información de enlace de ensamblado de BizTalk Server desde archivos de enlace o a archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="47460-110">Import or export BizTalk Server assembly binding information to and from binding files</span></span>  

<span data-ttu-id="47460-111">Para usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="47460-111">To use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47460-112">El adaptador de Microsoft BizTalk para JD Edwards OneWorld solo necesita que tenga Visual Studio en un equipo de origen (desarrollo).</span><span class="sxs-lookup"><span data-stu-id="47460-112">The Microsoft BizTalk Adapter for JD Edwards OneWorld only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="47460-113">Visual Studio no es necesario en el equipo de producción.</span><span class="sxs-lookup"><span data-stu-id="47460-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="47460-114">Confirme la configuración</span><span class="sxs-lookup"><span data-stu-id="47460-114">Confirm your setup</span></span>
<span data-ttu-id="47460-115">Antes de usar el servidor BizTalk Server para importar un archivo de enlace, compruebe lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="47460-115">Before you use the BizTalk Server to import a binding file, verify the following:</span></span>  
  
-   <span data-ttu-id="47460-116">CLASSPATH apunta a una ubicación específica para los archivos específicos de JD Edwards.</span><span class="sxs-lookup"><span data-stu-id="47460-116">The CLASSPATH is pointing to a specific location for the JD Edwards-specific files.</span></span> <span data-ttu-id="47460-117">Verifique si la ubicación de estos archivos es la misma en el equipo nuevo, o edite el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="47460-117">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="47460-118">Las carpetas para las respuestas existen y son idénticas en el equipo nuevo, o bien edite el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="47460-118">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="47460-119">Las contraseñas del sistema de JD Edwards, si hay en la configuración se guardan como \*\*\*\*\* en el archivo de enlaces.</span><span class="sxs-lookup"><span data-stu-id="47460-119">JD Edwards system passwords, if present in the configuration, are saved as \*\*\*\*\* in the binding file.</span></span> <span data-ttu-id="47460-120">Consulte **limitaciones** en este tema.</span><span class="sxs-lookup"><span data-stu-id="47460-120">See **Limitations** in this topic.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="47460-121">La implementación sobrescribe la configuración de ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="47460-121">Deployment overwrites Receive Location configuration.</span></span> <span data-ttu-id="47460-122">Al implementar un archivo de enlace (y un ensamblado) en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="47460-122">When deploying a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
  
## <a name="clean-the-target-computer"></a><span data-ttu-id="47460-123">Limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="47460-123">Clean the target computer</span></span>
<span data-ttu-id="47460-124">Implementación sobrescribe la configuración de la ubicación de recepción.</span><span class="sxs-lookup"><span data-stu-id="47460-124">Deployment overwrites the receive location configuration.</span></span> <span data-ttu-id="47460-125">Al implementar un archivo de enlace (y el ensamblado) en un equipo de destino, los puertos de envío y ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se importan.</span><span class="sxs-lookup"><span data-stu-id="47460-125">When you deploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are imported.</span></span>  
  
<span data-ttu-id="47460-126">Antes de importar, quite los puertos de envío y enlazadas a la orquestación de las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="47460-126">Before you import, remove send ports and receive locations bound to the orchestration.</span></span>  
  
<span data-ttu-id="47460-127">Si no tiene Microsoft Visual Studio instalada en el equipo de destino, puede quitar los puertos ejecutando estas secuencias de comandos:</span><span class="sxs-lookup"><span data-stu-id="47460-127">If you do not have Microsoft Visual Studio installed on the target computer, you can remove the ports by running these scripts:</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="47460-128">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="47460-128">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="47460-129">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="47460-129">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  
  
<span data-ttu-id="47460-130">Por ejemplo, en un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="47460-130">For example, at a command prompt, run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
  
## <a name="limitations"></a><span data-ttu-id="47460-131">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="47460-131">Limitations</span></span>
<span data-ttu-id="47460-132">La contraseña del adaptador de transporte se almacena como asteriscos (\*\*\*\*\*\*) en el archivo de enlace exportado por el Asistente para la implementación de BizTalk, y se pasa a la administración componente en el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="47460-132">The Transport Adapter password is stored as asterisks (\*\*\*\*\*\*) in the binding file that is exported by BizTalk Deployment Wizard, and is passed to the management component in the same format.</span></span> <span data-ttu-id="47460-133">Edite el archivo de enlace antes de la importación. Para ello, reemplace los asteriscos por valores alfanuméricos aleatorios (es decir, una contraseña que no sea la correcta).</span><span class="sxs-lookup"><span data-stu-id="47460-133">Edit the binding file before importing by replacing the asterisks with random alphanumeric values (that is, not the correct password).</span></span> <span data-ttu-id="47460-134">A continuación, escriba la contraseña correcta mediante la **propiedades de transporte** página después de importar el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="47460-134">Then enter the correct password using the **Transport Properties** page after importing the binding file.</span></span>  
  
 <span data-ttu-id="47460-135">Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="47460-135">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="47460-136">De este modo, se evita que la información de contraseña aparezca en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="47460-136">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="47460-137">La próxima vez que use el archivo para importar la información de enlace, deberá escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="47460-137">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span> <span data-ttu-id="47460-138">También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo.</span><span class="sxs-lookup"><span data-stu-id="47460-138">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="47460-139">En ese caso, debe eliminar las contraseñas del archivo de enlace una vez que finalice correctamente la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="47460-139">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="47460-140">Al importar un archivo .msi en una aplicación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] que contiene información de enlace para cualquiera de los adaptadores empresariales, es posible que aparezca un mensaje de error de importación.</span><span class="sxs-lookup"><span data-stu-id="47460-140">When importing an .msi file into a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] application containing binding information for any of the Enterprise adapters, you may receive an import error message.</span></span> <span data-ttu-id="47460-141">Está disponible en Microsoft, junto con una descripción completa del error en una revisión compatible [ http://support.microsoft.com/kb/923733/en-us ](http://support.microsoft.com/kb/923733/en-us).</span><span class="sxs-lookup"><span data-stu-id="47460-141">A supported hotfix is available from Microsoft along with a full description of the error at [http://support.microsoft.com/kb/923733/en-us](http://support.microsoft.com/kb/923733/en-us).</span></span>  
  
### <a name="work-around-the-password-limitation"></a><span data-ttu-id="47460-142">Evitar la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="47460-142">Work around the password limitation</span></span>  

<span data-ttu-id="47460-143">**Opción 1**</span><span class="sxs-lookup"><span data-stu-id="47460-143">**Option 1**</span></span>  

- <span data-ttu-id="47460-144">Antes de importar, actualice el archivo de enlace al reemplazar los asteriscos por texto sin formato.</span><span class="sxs-lookup"><span data-stu-id="47460-144">Before you import, update the binding file by replacing the asterisks with plain text.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="47460-145">Por motivos de seguridad, esta práctica no es recomendable.</span><span class="sxs-lookup"><span data-stu-id="47460-145">This is not recommended for security reasons.</span></span>  
  
- <span data-ttu-id="47460-146">Antes de importar, actualice el archivo de enlace al reemplazar los asteriscos por un valor aleatorio (es decir, no la contraseña correcta).</span><span class="sxs-lookup"><span data-stu-id="47460-146">Before you import, update the binding file by replacing the asterisks with some junk value (that is, not the correct password).</span></span> <span data-ttu-id="47460-147">Después de importar, escriba la contraseña correcta mediante la **propiedades de transporte**.</span><span class="sxs-lookup"><span data-stu-id="47460-147">After you import, enter the correct password using the **Transport Properties**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="47460-148">Esta solución solo puede usarse si Microsoft Visual Studio se encuentra instalado en el equipo de destino o si se desarrolla una herramienta personalizada.</span><span class="sxs-lookup"><span data-stu-id="47460-148">This work-around can be used only if Microsoft Visual Studio is installed on the target computer or by developing a custom tool.</span></span>  
  
<span data-ttu-id="47460-149">**Opción 2**</span><span class="sxs-lookup"><span data-stu-id="47460-149">**Option 2**</span></span>  
  
1.  <span data-ttu-id="47460-150">Use el inicio de sesión único empresarial en lugar de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="47460-150">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="47460-151">El uso de la opción SSO no requiere trabajo adicional; solo requiere una importación del archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="47460-151">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="47460-152">Compruebe el sistema lógico y los servicios de transmisión y recepción.</span><span class="sxs-lookup"><span data-stu-id="47460-152">Verify the Logical system and the Transmit and Receive services.</span></span>  

## <a name="next-steps"></a><span data-ttu-id="47460-153">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="47460-153">Next steps</span></span>
[<span data-ttu-id="47460-154">Usar el control de excepciones de BizTalk Server en la orquestación</span><span class="sxs-lookup"><span data-stu-id="47460-154">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling1.md)