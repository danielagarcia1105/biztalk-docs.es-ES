---
title: Importar aplicaciones de JD Edwards EnterpriseOne | Documentos de Microsoft
description: "Confirmar la instalación, importe el archivo de enlace de la aplicación y revisar las limitaciones del adaptador de JD Edwards EnterpriseOne en BizTalk"
ms.custom: 
ms.date: 10/18/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 852f948b-48ba-4ae2-b1eb-7c88c1542a52
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 55374c87192c993e26cc11cb496d89074d527868
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="import-the-jd-edwards-enterpriseone-application"></a><span data-ttu-id="4ba19-103">Importar la aplicación JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="4ba19-103">Import the JD Edwards EnterpriseOne application</span></span>
  
## <a name="overview"></a><span data-ttu-id="4ba19-104">Información general</span><span class="sxs-lookup"><span data-stu-id="4ba19-104">Overview</span></span>
<span data-ttu-id="4ba19-105">Con [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], puede duplicar puertos y ensamblados en un equipo de destino.</span><span class="sxs-lookup"><span data-stu-id="4ba19-105">With [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you can duplicate ports and assemblies on a target computer.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="4ba19-106"> exporta la configuración de ubicación de recepción/puertos de envío en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="4ba19-106"> exports the send ports/receive location configuration into an XML file.</span></span>  
  
 <span data-ttu-id="4ba19-107">Puede usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="4ba19-107">You can use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to do the following tasks:</span></span>  
  
-   <span data-ttu-id="4ba19-108">Implementar o quitar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ensamblados en una base de datos de configuración de BizTalk</span><span class="sxs-lookup"><span data-stu-id="4ba19-108">Deploy or remove [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assemblies in a BizTalk Configuration database</span></span>  
  
-   <span data-ttu-id="4ba19-109">Instalar o desinstalar los ensamblados en la caché de ensamblados global (GAC)</span><span class="sxs-lookup"><span data-stu-id="4ba19-109">Install or uninstall the assemblies in the global assembly cache (GAC)</span></span>  
  
-   <span data-ttu-id="4ba19-110">Importar o exportar información de vínculos de ensamblados de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde y a archivos de vínculos</span><span class="sxs-lookup"><span data-stu-id="4ba19-110">Import or export [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] assembly binding information to and from binding files</span></span>  
  
<span data-ttu-id="4ba19-111">Usar [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para implementar puertos y ensamblados, consulte [cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="4ba19-111">To use [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to deploy ports and assemblies, see [How to Export Bindings for a BizTalk Application](../core/how-to-export-bindings-for-a-biztalk-application.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ba19-112">El adaptador de Microsoft BizTalk para JD Edwards EnterpriseOne solo necesita que tenga Visual Studio en un equipo de origen (desarrollo).</span><span class="sxs-lookup"><span data-stu-id="4ba19-112">The Microsoft BizTalk Adapter for JD Edwards EnterpriseOne only requires that you have Visual Studio on a source (development) computer.</span></span> <span data-ttu-id="4ba19-113">Visual Studio no es necesario en el equipo de producción.</span><span class="sxs-lookup"><span data-stu-id="4ba19-113">Visual Studio is not required on the production computer.</span></span>  

## <a name="confirm-your-setup"></a><span data-ttu-id="4ba19-114">Confirme la configuración</span><span class="sxs-lookup"><span data-stu-id="4ba19-114">Confirm your setup</span></span>
<span data-ttu-id="4ba19-115">Antes de usar BizTalk Server para importar un archivo de enlace, debe comprobar lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4ba19-115">Before you use the BizTalk Server to import a binding file, you must verify the following:</span></span>  
  
-   <span data-ttu-id="4ba19-116">CLASSPATH apunta a una ubicación concreta para los archivos específicos de JD Edwards EnterpriseOne.</span><span class="sxs-lookup"><span data-stu-id="4ba19-116">The CLASSPATH is pointing to a specific location for the JD Edwards EnterpriseOne-specific files.</span></span> <span data-ttu-id="4ba19-117">Verifique si la ubicación de estos archivos es la misma en el equipo nuevo, o edite el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="4ba19-117">Verify that the location of these files is the same on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="4ba19-118">Las carpetas para las respuestas existen y son idénticas en el equipo nuevo, o bien edite el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="4ba19-118">The folders for the responses exist and are identical on the new computer, or edit the binding file.</span></span>  
  
-   <span data-ttu-id="4ba19-119">Las contraseñas del sistema JD Edwards EnterpriseOne, si están presentes en la configuración, se guardan como ***** en el archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="4ba19-119">JD Edwards EnterpriseOne system passwords, if present in the configuration, are saved as ***** in the binding file.</span></span> <span data-ttu-id="4ba19-120">Para obtener más información, consulte **limitaciones** en este tema.</span><span class="sxs-lookup"><span data-stu-id="4ba19-120">For more information, see **Limitations** in this topic.</span></span>

## <a name="clean-the-target-computer"></a><span data-ttu-id="4ba19-121">Limpiar el equipo de destino</span><span class="sxs-lookup"><span data-stu-id="4ba19-121">Clean the target computer</span></span>
<span data-ttu-id="4ba19-122">Al volver a implementar un archivo de enlace (y un ensamblado) en un equipo de destino, los puertos de envío y las ubicaciones de recepción se sustituyen por los del archivo de enlace XML cuando se vuelven a importar.</span><span class="sxs-lookup"><span data-stu-id="4ba19-122">When you redeploy a binding file (and assembly) on a target computer, the send ports and receive locations are replaced with those in the XML binding file when they are reimported.</span></span>  
  
<span data-ttu-id="4ba19-123">Antes de importar, quite los puertos de envío y ubicaciones de recepción vinculadas a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="4ba19-123">Before you import, remove Send ports and Receive locations bound to the orchestration.</span></span> <span data-ttu-id="4ba19-124">Si Visual Studio no está instalado en el equipo de destino, puede quitar los puertos ejecutando estos scripts:</span><span class="sxs-lookup"><span data-stu-id="4ba19-124">If you do not have Visual Studio installed on the target computer, you can remove the ports by running the scripts:</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="4ba19-125">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span><span class="sxs-lookup"><span data-stu-id="4ba19-125">SDK\Samples\Admin\WMI\Remove Send Port\VBScript\RemoveSendPort.vbs</span></span>  
  
- [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]<span data-ttu-id="4ba19-126">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span><span class="sxs-lookup"><span data-stu-id="4ba19-126">SDK\Samples\Admin\WMI\Remove Receive Port\VBScript\RemoveReceivePort.vbs</span></span>  

<span data-ttu-id="4ba19-127">Por ejemplo, desde un símbolo del sistema, ejecute:</span><span class="sxs-lookup"><span data-stu-id="4ba19-127">For example, from a command prompt run:</span></span>  
  
```
cscript RemoveSendPort.vbs \<Send port name\>
```
## <a name="limitations"></a><span data-ttu-id="4ba19-128">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="4ba19-128">Limitations</span></span>
<span data-ttu-id="4ba19-129">La contraseña del adaptador de transporte se almacena como estrellas (*) en el archivo de enlace exportado por el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], y pasa al componente de administración en el mismo formato.</span><span class="sxs-lookup"><span data-stu-id="4ba19-129">The Transport Adapter password is stored as stars (******) in the binding file that is exported by the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], and it passes to the management component in the same format.</span></span> <span data-ttu-id="4ba19-130">Edite el archivo de enlace antes de la importación al reemplazar los asteriscos por un valor aleatorio (es decir, una contraseña que no sea correcta).</span><span class="sxs-lookup"><span data-stu-id="4ba19-130">Edit the binding file before importing by replacing the stars with some junk value (that is, not the correct password).</span></span>  
  
 <span data-ttu-id="4ba19-131">Al exportar la información de enlace, el archivo de enlace resultante no contiene ninguna de las contraseñas usadas por los adaptadores de transporte en los puertos de envío o las ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="4ba19-131">When you export binding information, the resultant binding file does not contain any of the passwords that were used by transport adapters in receive locations/send ports.</span></span> <span data-ttu-id="4ba19-132">De este modo, se evita que la información de contraseña aparezca en texto no cifrado.</span><span class="sxs-lookup"><span data-stu-id="4ba19-132">This prevents password information from appearing in clear text.</span></span> <span data-ttu-id="4ba19-133">La próxima vez que use el archivo para importar la información de enlace, deberá escribir las contraseñas a través de la interfaz de usuario de las páginas de propiedades de transporte.</span><span class="sxs-lookup"><span data-stu-id="4ba19-133">The next time you use the file to import the binding information, you must enter the passwords by using transport property pages user interface.</span></span>  
  
 <span data-ttu-id="4ba19-134">También puede modificar temporalmente el archivo de enlace antes de la importación si especifica las contraseñas en este archivo.</span><span class="sxs-lookup"><span data-stu-id="4ba19-134">Alternatively, you can temporarily modify the binding file before importing by typing the passwords into it.</span></span> <span data-ttu-id="4ba19-135">En ese caso, debe eliminar las contraseñas del archivo de enlace una vez que finalice correctamente la operación de importación.</span><span class="sxs-lookup"><span data-stu-id="4ba19-135">In this case, you must delete the passwords from the binding file after the import operation successfully completes.</span></span>  
  
### <a name="work-around-the-password-limitation"></a><span data-ttu-id="4ba19-136">Evitar la limitación de contraseña</span><span class="sxs-lookup"><span data-stu-id="4ba19-136">Work around the password limitation</span></span>  
  
1.  <span data-ttu-id="4ba19-137">Use el inicio de sesión único empresarial en lugar de contraseñas.</span><span class="sxs-lookup"><span data-stu-id="4ba19-137">Use Enterprise Single Sign-On instead of using passwords.</span></span> <span data-ttu-id="4ba19-138">El uso de la opción SSO no requiere trabajo adicional; solo requiere una importación del archivo de enlace.</span><span class="sxs-lookup"><span data-stu-id="4ba19-138">Using the SSO option requires no extra work; only an import of the binding file.</span></span>  
  
2.  <span data-ttu-id="4ba19-139">Compruebe el sistema lógico y los servicios de transmisión y recepción.</span><span class="sxs-lookup"><span data-stu-id="4ba19-139">Verify the Logical system and the Transmit and Receive services.</span></span>  


## <a name="next-steps"></a><span data-ttu-id="4ba19-140">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="4ba19-140">Next steps</span></span>
[<span data-ttu-id="4ba19-141">Usar el control de excepciones de BizTalk Server en la orquestación</span><span class="sxs-lookup"><span data-stu-id="4ba19-141">Use BizTalk Server Exception Handling in your orchestration</span></span>](../core/using-biztalk-server-exception-handling3.md)