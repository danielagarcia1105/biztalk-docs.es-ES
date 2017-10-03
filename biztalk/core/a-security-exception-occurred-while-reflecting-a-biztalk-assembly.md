---
title: "Se produjo una excepción de seguridad al reflejar el ensamblado de BizTalk | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 301b85c7-8e67-482e-8666-67a91ca5c73d
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cca28c534b910479be3ae6ad26bd1e0a27a1637d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="a-security-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="47b74-102">Excepción de seguridad al reflejar el ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="47b74-102">A security exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="47b74-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="47b74-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="47b74-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="47b74-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="47b74-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="47b74-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="47b74-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="47b74-106">Event ID</span></span>|<span data-ttu-id="47b74-107">0</span><span class="sxs-lookup"><span data-stu-id="47b74-107">0</span></span>|  
|<span data-ttu-id="47b74-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="47b74-108">Event Source</span></span>|<span data-ttu-id="47b74-109">0</span><span class="sxs-lookup"><span data-stu-id="47b74-109">0</span></span>|  
|<span data-ttu-id="47b74-110">Componente</span><span class="sxs-lookup"><span data-stu-id="47b74-110">Component</span></span>|<span data-ttu-id="47b74-111">0</span><span class="sxs-lookup"><span data-stu-id="47b74-111">0</span></span>|  
|<span data-ttu-id="47b74-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="47b74-112">Symbolic Name</span></span>|<span data-ttu-id="47b74-113">0</span><span class="sxs-lookup"><span data-stu-id="47b74-113">0</span></span>|  
|<span data-ttu-id="47b74-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="47b74-114">Message Text</span></span>|<span data-ttu-id="47b74-115">Excepción de seguridad al reflejar el ensamblado de BizTalk "{0}".</span><span class="sxs-lookup"><span data-stu-id="47b74-115">A security exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="47b74-116">El problema surge si el ensamblado está ubicado en una carpeta de red compartida.</span><span class="sxs-lookup"><span data-stu-id="47b74-116">This problem may occur if the assembly is located in a shared network folder.</span></span> <span data-ttu-id="47b74-117">Para corregir este problema, pruebe una de las siguientes acciones: 1.</span><span class="sxs-lookup"><span data-stu-id="47b74-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="47b74-118">Copie el ensamblado y sus dependencias en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="47b74-118">Copy the assembly and its dependencies to the local machine.</span></span> <span data-ttu-id="47b74-119">2.</span><span class="sxs-lookup"><span data-stu-id="47b74-119">2.</span></span> <span data-ttu-id="47b74-120">Ajuste la directiva de seguridad en tiempo de ejecución de la configuración .NET para permitir el acceso.</span><span class="sxs-lookup"><span data-stu-id="47b74-120">Adjust the .NET Configuration Runtime Security policy to permit access.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="47b74-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="47b74-121">Explanation</span></span>  
 <span data-ttu-id="47b74-122">Este error se producirá al intentar publicar un ensamblado de BizTalk que está en una red compartida sin la directiva .NET correcta.</span><span class="sxs-lookup"><span data-stu-id="47b74-122">This error will occur when trying to publish a BizTalk assembly that is on a network share without the right .NET policy.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="47b74-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="47b74-123">User Action</span></span>  
 <span data-ttu-id="47b74-124">Además de seguir los pasos específicos indicados en el mensaje de error, copie el ensamblado localmente.</span><span class="sxs-lookup"><span data-stu-id="47b74-124">In addition to taking the specific steps outlined in the error message, copy the assembly locally.</span></span> <span data-ttu-id="47b74-125">O bien, edite la directiva para conceder total confianza a la intranet local.</span><span class="sxs-lookup"><span data-stu-id="47b74-125">Or edit the policy to grant full trust to the local intranet.</span></span>  
  
 <span data-ttu-id="47b74-126">**Usar la herramienta Directiva de seguridad de acceso a código (Caspol.exe)**</span><span class="sxs-lookup"><span data-stu-id="47b74-126">**Using the Code Access Security Policy Tool (Caspol.exe)**</span></span>  
  
 <span data-ttu-id="47b74-127">Puede conceder confianza a una carpeta del equipo local en el nivel de usuario con permisos de usuario normales.</span><span class="sxs-lookup"><span data-stu-id="47b74-127">You can grant trust to a folder on your local computer at the User level with normal user permissions.</span></span> <span data-ttu-id="47b74-128">Para conceder confianza a una ubicación de red, debe disponer de privilegios de administrador y cambiar la directiva de seguridad en el nivel de equipo.</span><span class="sxs-lookup"><span data-stu-id="47b74-128">To grant trust to a network location, you must have administrator privileges and change the security policy at the Machine level.</span></span> <span data-ttu-id="47b74-129">El nivel de directiva de equipo actúa independientemente del nivel de directiva de usuario, y el nivel de directiva de equipo no concede total confianza a la zona de intranet aunque la directiva de usuario lo haga.</span><span class="sxs-lookup"><span data-stu-id="47b74-129">The Machine policy level acts independently of the User policy level, and the machine policy level does not grant full trust to the Intranet zone even if the User policy does.</span></span> <span data-ttu-id="47b74-130">Los niveles de directiva deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="47b74-130">The policy levels must agree.</span></span>  
  
 <span data-ttu-id="47b74-131">**Para otorgar plena confianza a una carpeta local**</span><span class="sxs-lookup"><span data-stu-id="47b74-131">**To grant full trust to a local folder**</span></span>  
  
-   <span data-ttu-id="47b74-132">Escriba el comando siguiente en el símbolo del sistema de Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="47b74-132">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -u -ag All_Code -url   
C:\<FolderName>\<FolderName>\* FullTrust -n "<Name>" -d  
"<Description>"  
```  
  
 <span data-ttu-id="47b74-133">**Para otorgar plena confianza a una carpeta de red**</span><span class="sxs-lookup"><span data-stu-id="47b74-133">**To grant full trust to a network folder**</span></span>  
  
-   <span data-ttu-id="47b74-134">Escriba el comando siguiente en el símbolo del sistema de Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="47b74-134">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -m -ag LocalIntranet_Zone -url   
\\<ServerName>\<FolderName>\* FullTrust -n "<Name>" -d   
"<Description>"  
```