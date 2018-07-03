---
title: Se produjo una excepción de seguridad al reflejar el ensamblado de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 301b85c7-8e67-482e-8666-67a91ca5c73d
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d07b1e5788ae696e94a3bbe326f2cfe79d1b76f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979933"
---
# <a name="a-security-exception-occurred-while-reflecting-a-biztalk-assembly"></a><span data-ttu-id="b45e2-102">Excepción de seguridad al reflejar el ensamblado de BizTalk</span><span class="sxs-lookup"><span data-stu-id="b45e2-102">A security exception occurred while reflecting a BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="b45e2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="b45e2-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b45e2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="b45e2-104">Product Name</span></span>   |                                                                                                                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                                                                                                 |
| <span data-ttu-id="b45e2-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="b45e2-105">Product Version</span></span> |                                                                                                                                             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                                                                                                             |
|    <span data-ttu-id="b45e2-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="b45e2-106">Event ID</span></span>     |                                                                                                                                                                         <span data-ttu-id="b45e2-107">0</span><span class="sxs-lookup"><span data-stu-id="b45e2-107">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="b45e2-108">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="b45e2-108">Event Source</span></span>   |                                                                                                                                                                         <span data-ttu-id="b45e2-109">0</span><span class="sxs-lookup"><span data-stu-id="b45e2-109">0</span></span>                                                                                                                                                                          |
|    <span data-ttu-id="b45e2-110">Componente</span><span class="sxs-lookup"><span data-stu-id="b45e2-110">Component</span></span>    |                                                                                                                                                                         <span data-ttu-id="b45e2-111">0</span><span class="sxs-lookup"><span data-stu-id="b45e2-111">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="b45e2-112">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="b45e2-112">Symbolic Name</span></span>  |                                                                                                                                                                         <span data-ttu-id="b45e2-113">0</span><span class="sxs-lookup"><span data-stu-id="b45e2-113">0</span></span>                                                                                                                                                                          |
|  <span data-ttu-id="b45e2-114">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="b45e2-114">Message Text</span></span>   | <span data-ttu-id="b45e2-115">Se produjo una excepción de seguridad al reflejar el ensamblado de BizTalk "{0}".</span><span class="sxs-lookup"><span data-stu-id="b45e2-115">A security exception occurred while reflecting BizTalk assembly "{0}".</span></span> <span data-ttu-id="b45e2-116">El problema surge si el ensamblado está ubicado en una carpeta de red compartida.</span><span class="sxs-lookup"><span data-stu-id="b45e2-116">This problem may occur if the assembly is located in a shared network folder.</span></span> <span data-ttu-id="b45e2-117">Para corregir este problema, pruebe uno de los siguientes: 1.</span><span class="sxs-lookup"><span data-stu-id="b45e2-117">To correct this problem, try one of the following: 1.</span></span> <span data-ttu-id="b45e2-118">Copie el ensamblado y sus dependencias en el equipo local.</span><span class="sxs-lookup"><span data-stu-id="b45e2-118">Copy the assembly and its dependencies to the local machine.</span></span> <span data-ttu-id="b45e2-119">2.</span><span class="sxs-lookup"><span data-stu-id="b45e2-119">2.</span></span> <span data-ttu-id="b45e2-120">Ajuste la directiva de seguridad en tiempo de ejecución de la configuración .NET para permitir el acceso.</span><span class="sxs-lookup"><span data-stu-id="b45e2-120">Adjust the .NET Configuration Runtime Security policy to permit access.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b45e2-121">Explicación</span><span class="sxs-lookup"><span data-stu-id="b45e2-121">Explanation</span></span>  
 <span data-ttu-id="b45e2-122">Este error se producirá al intentar publicar un ensamblado de BizTalk que está en una red compartida sin la directiva .NET correcta.</span><span class="sxs-lookup"><span data-stu-id="b45e2-122">This error will occur when trying to publish a BizTalk assembly that is on a network share without the right .NET policy.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b45e2-123">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="b45e2-123">User Action</span></span>  
 <span data-ttu-id="b45e2-124">Además de seguir los pasos específicos indicados en el mensaje de error, copie el ensamblado localmente.</span><span class="sxs-lookup"><span data-stu-id="b45e2-124">In addition to taking the specific steps outlined in the error message, copy the assembly locally.</span></span> <span data-ttu-id="b45e2-125">O bien, edite la directiva para conceder total confianza a la intranet local.</span><span class="sxs-lookup"><span data-stu-id="b45e2-125">Or edit the policy to grant full trust to the local intranet.</span></span>  
  
 <span data-ttu-id="b45e2-126">**Uso de la herramienta Directiva de seguridad de acceso a código (Caspol.exe)**</span><span class="sxs-lookup"><span data-stu-id="b45e2-126">**Using the Code Access Security Policy Tool (Caspol.exe)**</span></span>  
  
 <span data-ttu-id="b45e2-127">Puede conceder confianza a una carpeta del equipo local en el nivel de usuario con permisos de usuario normales.</span><span class="sxs-lookup"><span data-stu-id="b45e2-127">You can grant trust to a folder on your local computer at the User level with normal user permissions.</span></span> <span data-ttu-id="b45e2-128">Para conceder confianza a una ubicación de red, debe disponer de privilegios de administrador y cambiar la directiva de seguridad en el nivel de equipo.</span><span class="sxs-lookup"><span data-stu-id="b45e2-128">To grant trust to a network location, you must have administrator privileges and change the security policy at the Machine level.</span></span> <span data-ttu-id="b45e2-129">El nivel de directiva de equipo actúa independientemente del nivel de directiva de usuario, y el nivel de directiva de equipo no concede total confianza a la zona de intranet aunque la directiva de usuario lo haga.</span><span class="sxs-lookup"><span data-stu-id="b45e2-129">The Machine policy level acts independently of the User policy level, and the machine policy level does not grant full trust to the Intranet zone even if the User policy does.</span></span> <span data-ttu-id="b45e2-130">Los niveles de directiva deben coincidir.</span><span class="sxs-lookup"><span data-stu-id="b45e2-130">The policy levels must agree.</span></span>  
  
 <span data-ttu-id="b45e2-131">**Para conceder total confianza a una carpeta local**</span><span class="sxs-lookup"><span data-stu-id="b45e2-131">**To grant full trust to a local folder**</span></span>  
  
-   <span data-ttu-id="b45e2-132">Escriba el comando siguiente en el símbolo del sistema de Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="b45e2-132">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -u -ag All_Code -url   
C:\<FolderName>\<FolderName>\* FullTrust -n "<Name>" -d  
"<Description>"  
```  
  
 <span data-ttu-id="b45e2-133">**Para conceder plena confianza a una carpeta de red**</span><span class="sxs-lookup"><span data-stu-id="b45e2-133">**To grant full trust to a network folder**</span></span>  
  
-   <span data-ttu-id="b45e2-134">Escriba el comando siguiente en el símbolo del sistema de Visual Studio:</span><span class="sxs-lookup"><span data-stu-id="b45e2-134">Type the following command in the Visual Studio Command Prompt:</span></span>  
  
```  
caspol -m -ag LocalIntranet_Zone -url   
\\<ServerName>\<FolderName>\* FullTrust -n "<Name>" -d   
"<Description>"  
```