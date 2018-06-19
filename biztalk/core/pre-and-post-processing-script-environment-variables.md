---
title: Las Variables de entorno de secuencia de comandos previas y posteriores al procesamiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, post-processing
- scripts, pre-processing
- scripts, variables
ms.assetid: 4185fb68-b00d-4875-82fd-a040905f84e7
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dab1086a30ce670524a095f30c0bd6c1910365b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264508"
---
# <a name="pre--and-post-processing-script-environment-variables"></a><span data-ttu-id="a90d8-102">Variables de entorno de secuencias de comandos previas y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="a90d8-102">Pre- and Post-processing Script Environment Variables</span></span>
<span data-ttu-id="a90d8-103">En los temas de esta sección se describen las variables de entorno a las que pueden tener acceso las secuencias de comandos previas y posteriores al procesamiento.</span><span class="sxs-lookup"><span data-stu-id="a90d8-103">The topics in this section describe the environment variables that pre- and post-processing scripts can access.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a90d8-104">Según el estándar de Windows, el nombre de la variable de entorno no distingue entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a90d8-104">Per Windows standards, the name of the environment variable is not case-sensitive.</span></span> <span data-ttu-id="a90d8-105">Sin embargo, los valores de las variables sí distinguen entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="a90d8-105">Variable values, however, are case-sensitive.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a90d8-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a90d8-106">In This Section</span></span>  
  
-   [<span data-ttu-id="a90d8-107">BTAD_ChangeRequestAction</span><span class="sxs-lookup"><span data-stu-id="a90d8-107">BTAD_ChangeRequestAction</span></span>](../core/btad-changerequestaction.md)  
  
-   [<span data-ttu-id="a90d8-108">BTAD_HostClass</span><span class="sxs-lookup"><span data-stu-id="a90d8-108">BTAD_HostClass</span></span>](../core/btad-hostclass.md)  
  
-   [<span data-ttu-id="a90d8-109">BTAD_InstallMode</span><span class="sxs-lookup"><span data-stu-id="a90d8-109">BTAD_InstallMode</span></span>](../core/btad-installmode.md)  
  
-   [<span data-ttu-id="a90d8-110">BTAD_InstallDir</span><span class="sxs-lookup"><span data-stu-id="a90d8-110">BTAD_InstallDir</span></span>](../core/btad-installdir.md)  
  
-   [<span data-ttu-id="a90d8-111">BTAD_ApplicationName</span><span class="sxs-lookup"><span data-stu-id="a90d8-111">BTAD_ApplicationName</span></span>](../core/btad-applicationname.md)  
  
-   [<span data-ttu-id="a90d8-112">BTAD_SilentMode</span><span class="sxs-lookup"><span data-stu-id="a90d8-112">BTAD_SilentMode</span></span>](../core/btad-silentmode.md)  
  
-   [<span data-ttu-id="a90d8-113">BTAD_Server</span><span class="sxs-lookup"><span data-stu-id="a90d8-113">BTAD_Server</span></span>](../core/btad-server.md)  
  
-   [<span data-ttu-id="a90d8-114">BTAD_Database</span><span class="sxs-lookup"><span data-stu-id="a90d8-114">BTAD_Database</span></span>](../core/btad-database.md)