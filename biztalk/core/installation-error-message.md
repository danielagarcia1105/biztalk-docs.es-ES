---
title: Mensaje de Error de instalación | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installation, error message
- error messages, installation
ms.assetid: 593b033f-03da-43ae-a948-f87aa5e4bccd
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1fe3b422c860b4b697b259dc731f5484fac87455
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001813"
---
# <a name="installation-error-message"></a><span data-ttu-id="1c7e9-102">Mensaje de error de instalación</span><span class="sxs-lookup"><span data-stu-id="1c7e9-102">Installation Error Message</span></span>
<span data-ttu-id="1c7e9-103">Tras instalar el adaptador de Microsoft BizTalk para TIBCO Enterprise Message Service, definir una ubicación de recepción o de envío puede dar lugar al siguiente error:</span><span class="sxs-lookup"><span data-stu-id="1c7e9-103">After you install Microsoft BizTalk Adapter for TIBCO Enterprise Message Service, defining a send or receive location for it might result in the following error:</span></span>  
  
 <span data-ttu-id="1c7e9-104">El motor de mensajería no se pudo agregar una dirección URL de recepción "\< dirección URL de ubicación de envío/recepción\>" al adaptador "TIBCO EMS".</span><span class="sxs-lookup"><span data-stu-id="1c7e9-104">The Messaging Engine failed to add a receive URL "\< send/receive location URL\>" to the adapter "TIBCO EMS".</span></span> <span data-ttu-id="1c7e9-105">Motivo: "archivo o ensamblado nombre TIBCO. EMS o una de sus dependencias, no se encontró."</span><span class="sxs-lookup"><span data-stu-id="1c7e9-105">Reason: "File or assembly name TIBCO.EMS, or one of its dependencies, was not found."</span></span>  
  
## <a name="possible-causes"></a><span data-ttu-id="1c7e9-106">Posibles causas</span><span class="sxs-lookup"><span data-stu-id="1c7e9-106">Possible Causes</span></span>  
 <span data-ttu-id="1c7e9-107">Este error se suele producir por una de las siguientes causas.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-107">This error usually has one of the following causes.</span></span>  
  
### <a name="assembly-not-in-gac"></a><span data-ttu-id="1c7e9-108">Ensamblado no en la GAC</span><span class="sxs-lookup"><span data-stu-id="1c7e9-108">Assembly Not in GAC</span></span>  
 <span data-ttu-id="1c7e9-109">El adaptador de BizTalk para TIBCO EMS es una aplicación .NET Framework y utiliza el ensamblado de .NET Framework, TIBCO.EMS.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-109">BizTalk Adapter for TIBCO EMS is a .NET Framework application, and uses the .NET Framework assembly, TIBCO.EMS.</span></span> <span data-ttu-id="1c7e9-110">Este ensamblado debe estar presente en la caché de ensamblados global (GAC) de .NET Framework para que .NET Framework lo busque en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-110">This assembly must be present in the .NET Framework global assembly cache (GAC) for the .NET Framework to find it at run time.</span></span>  
  
#### <a name="solution"></a><span data-ttu-id="1c7e9-111">Solución</span><span class="sxs-lookup"><span data-stu-id="1c7e9-111">Solution</span></span>  
 <span data-ttu-id="1c7e9-112">Para determinar si el ensamblado está presente en la GAC, abra un símbolo del sistema y escriba el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1c7e9-112">To determine if the assembly is present in the GAC, open a command prompt and type the following command:</span></span>  
  
 `GACUTIL /L TIBCO.EMS`  
  
 <span data-ttu-id="1c7e9-113">Si el resultado no muestra ningún elemento, debe agregar el ensamblado a la GAC.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-113">If the result shows zero items, you must add the assembly to the GAC.</span></span> <span data-ttu-id="1c7e9-114">Para ello, abra un símbolo del sistema, cambie los directorios al directorio de instalación TIBCO EMS clients\cs (la ubicación de instalación predeterminada es C:\TIBCO\EMS\Clients\CS) y ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1c7e9-114">To do this, open a command prompt, change directories to your TIBCO EMS installation clients\cs directory (the default installation location is C:\TIBCO\EMS\Clients\CS), and run the following command:</span></span>  
  
 `GACUTIL /i TIBCO.EMS.DLL`  
  
### <a name="different-version-of-assembly-in-gac"></a><span data-ttu-id="1c7e9-115">Versión distinta de ensamblado en la GAC</span><span class="sxs-lookup"><span data-stu-id="1c7e9-115">Different Version of Assembly in GAC</span></span>  
 <span data-ttu-id="1c7e9-116">El ensamblado TIBCO.EMS.dll está en la GAC, pero es una versión distinta de la que se usa para crear el adaptador de BizTalk para TIBCO EMS.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-116">The TIBCO.EMS.dll assembly is in the GAC, but it is a different version from the one used to build BizTalk Adapter for TIBCO EMS.</span></span> <span data-ttu-id="1c7e9-117">Si TIBCO.EMS.dll que se ha instalado en el equipo es de una versión del producto 4.2 o superior, debe ser compatible con la versión utilizada para crear el adaptador (puede verificar dicha información con TIBCO).</span><span class="sxs-lookup"><span data-stu-id="1c7e9-117">If the TIBCO.EMS.dll that is installed on the computer is from a product version 4.2 or above, it should be compatible with the version used to build the adapter (you can verify that information with TIBCO).</span></span>  
  
#### <a name="solution"></a><span data-ttu-id="1c7e9-118">Solución</span><span class="sxs-lookup"><span data-stu-id="1c7e9-118">Solution</span></span>  
 <span data-ttu-id="1c7e9-119">.NET Framework proporciona una forma para solucionar este problema.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-119">The .NET Framework provides a way to work around this problem.</span></span> <span data-ttu-id="1c7e9-120">Se llama *redirección de enlace*, que utiliza un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-120">It is called *binding redirection*, which uses a configuration file.</span></span>  
  
 <span data-ttu-id="1c7e9-121">Siga estos pasos para eliminar el mensaje de error:</span><span class="sxs-lookup"><span data-stu-id="1c7e9-121">Follow these steps to eliminate the error message:</span></span>  
  
1. <span data-ttu-id="1c7e9-122">Con un editor de texto, abra el archivo BTSNTSVC.exe.config.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-122">With any text editor, open the file BTSNTSVC.exe.config.</span></span>  
  
    <span data-ttu-id="1c7e9-123">El archivo se encuentra en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directorio (la ubicación de instalación predeterminada es: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="1c7e9-123">The file is located in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] directory (the default installation location is: [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]).</span></span>  
  
2. <span data-ttu-id="1c7e9-124">Agregue la siguiente entrada al archivo BTSNTSVC.exe.config, como un elemento secundario de la \<assemblyBinding\> elemento:</span><span class="sxs-lookup"><span data-stu-id="1c7e9-124">Add the following entry to the BTSNTSVC.exe.config file, as a child of the \<assemblyBinding\> element:</span></span>  
  
```  
<dependentAssembly>  
    <assemblyIdentity name='TIBCO.EMS'  
        publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
    <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
        newVersion='1.0.0.0' />  
</dependentAssembly>  
```  
  
 <span data-ttu-id="1c7e9-125">Si el archivo BTSNTSVC.exe.config no se ha modificado anteriormente, el \<assemblyBinding\> elemento no tendría el aspecto siguiente:</span><span class="sxs-lookup"><span data-stu-id="1c7e9-125">If the BTSNTSVC.exe.config file has not been previously modified, the \<assemblyBinding\> element would not look like this:</span></span>  
  
```  
<assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
    <probing privatePath="BizTalk Assemblies;Developer  
        Tools;Tracking;Tracking\interop" />  
    <dependentAssembly>  
        <assemblyIdentity name='TIBCO.EMS'  
            publicKeyToken='5b83db8ff05c64ba ' culture='neutral' />  
        <bindingRedirect oldVersion='1.0.0.0-65535.65535.65535.65535'  
            newVersion='1.0.0.0' />  
    </dependentAssembly>  
</assemblyBinding>  
```  
  
1. <span data-ttu-id="1c7e9-126">En un símbolo del sistema, escriba el comando: `GACUTIL /L TIBCO.EMS`.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-126">In a command prompt, type the command: `GACUTIL /L TIBCO.EMS`.</span></span>  
  
2. <span data-ttu-id="1c7e9-127">Copie el número de versión del ensamblado TIBCO.EMS desde la salida.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-127">Copy the TIBCO.EMS assembly version number from the output.</span></span>  
  
   > [!CAUTION]
   >  <span data-ttu-id="1c7e9-128">Aparecen dos números de versión: uno es el número de versión de la utilidad gacutil.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-128">Two version numbers appear: one is the version number of the gacutil utility.</span></span> <span data-ttu-id="1c7e9-129">Desea que el segundo número de versión, que aparece justo después **versión =**.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-129">You want the second version number, which appears just after **Version=**.</span></span>  
  
3. <span data-ttu-id="1c7e9-130">Pegue el número de versión en el archivo BTSNTSVC.exe.config, entre las comillas, justo después de **newVersion =** (caracteres en negrita en el ejemplo XML anterior).</span><span class="sxs-lookup"><span data-stu-id="1c7e9-130">Paste the version number in the BTSNTSVC.exe.config file, between the quotation marks, right after **newVersion=** (bold characters in the previous XML example).</span></span>  
  
4. <span data-ttu-id="1c7e9-131">Guarde el archivo BTSNTSVC.exe.config modificado.</span><span class="sxs-lookup"><span data-stu-id="1c7e9-131">Save the modified BTSNTSVC.exe.config file.</span></span>  
  
5. <span data-ttu-id="1c7e9-132">Reinicie el host [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1c7e9-132">Restart the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] host.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c7e9-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="1c7e9-133">See Also</span></span>  
 [<span data-ttu-id="1c7e9-134">Solución de problemas de TIBCO Enterprise Message Service</span><span class="sxs-lookup"><span data-stu-id="1c7e9-134">Troubleshooting TIBCO Enterprise Message Service</span></span>](../core/troubleshooting-tibco-enterprise-message-service.md)