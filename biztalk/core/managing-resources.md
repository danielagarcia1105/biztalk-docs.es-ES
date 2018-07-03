---
title: Administración de recursos | Microsoft Docs
description: Usar btstask o administración de BizTalk para trabajar con ensamblados, secuencias de comandos, certificados, los archivos de enlace y otra información en el servidor BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b478ef2e-1363-4c2c-a4b7-6a582a6b33a5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9aad282dfb444c2947afca3cefc0a96cd806826
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015117"
---
# <a name="manage-resources"></a><span data-ttu-id="85d53-103">Administración de recursos</span><span class="sxs-lookup"><span data-stu-id="85d53-103">Manage Resources</span></span>

## <a name="overview"></a><span data-ttu-id="85d53-104">Información general</span><span class="sxs-lookup"><span data-stu-id="85d53-104">Overview</span></span>
<span data-ttu-id="85d53-105">Los temas de esta sección proporcionan instrucciones sobre cómo utilizar la consola de administración de BizTalk Server o la herramienta de la línea de comandos BTSTask para administrar recursos de BizTalk Server una vez que se han implementado en un grupo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="85d53-105">The topics in this section provide instructions on how to use the BizTalk Server Administration console or the BTSTask command-line tool to manage BizTalk Server resources after they have been deployed into a BizTalk group.</span></span> <span data-ttu-id="85d53-106">Los recursos incluyen los siguientes tipos de artefactos:</span><span class="sxs-lookup"><span data-stu-id="85d53-106">Resources include the following types of artifacts:</span></span>  
  
-   <span data-ttu-id="85d53-107">Ensamblados de BizTalk</span><span class="sxs-lookup"><span data-stu-id="85d53-107">BizTalk Assemblies</span></span>  
  
-   <span data-ttu-id="85d53-108">Secuencias de comandos previas y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="85d53-108">Pre- and post-processing scripts</span></span>  
  
-   <span data-ttu-id="85d53-109">Ensamblados .NET</span><span class="sxs-lookup"><span data-stu-id="85d53-109">.NET assemblies</span></span>  
  
-   <span data-ttu-id="85d53-110">Componentes COM</span><span class="sxs-lookup"><span data-stu-id="85d53-110">COM components</span></span>  
  
-   <span data-ttu-id="85d53-111">Certificados</span><span class="sxs-lookup"><span data-stu-id="85d53-111">Certificates</span></span>  
  
-   <span data-ttu-id="85d53-112">Archivos ad hoc</span><span class="sxs-lookup"><span data-stu-id="85d53-112">Ad hoc files</span></span>  
  
-   <span data-ttu-id="85d53-113">Definiciones de BAM</span><span class="sxs-lookup"><span data-stu-id="85d53-113">BAM definitions</span></span>  
  
-   <span data-ttu-id="85d53-114">Archivos de enlace</span><span class="sxs-lookup"><span data-stu-id="85d53-114">Binding files</span></span>  
  
-   <span data-ttu-id="85d53-115">Directorios virtuales</span><span class="sxs-lookup"><span data-stu-id="85d53-115">Virtual directories</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="85d53-116">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="85d53-116">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="85d53-117">Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="85d53-117">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
> 
> [!NOTE]
>  <span data-ttu-id="85d53-118">No agregue varios recursos con el mismo nombre, independientemente del caso, a un grupo de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="85d53-118">Do not add multiple resources with the same name, regardless of case, to a BizTalk Server group.</span></span> <span data-ttu-id="85d53-119">No se admite la agregación de varios recursos con el mismo nombre a un grupo de BizTalk Server, incluso cuando la base de datos de administración de BizTalk Server esté alojada en un servidor SQL Server que se haya configurado para utilizar la intercalación binaria y distinga entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="85d53-119">Adding multiple resources with the same name to a BizTalk Server group is not supported, even when the BizTalk Server management database is housed on a SQL Server that is configured to use binary collation and supports case sensitivity.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="85d53-120">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="85d53-120">Next steps</span></span>
  
-   [<span data-ttu-id="85d53-121">Administración de ensamblados de BizTalk</span><span class="sxs-lookup"><span data-stu-id="85d53-121">Managing BizTalk Assemblies</span></span>](../core/managing-biztalk-assemblies.md)  
  
-   [<span data-ttu-id="85d53-122">Administración de scripts previos y posteriores al procesamiento</span><span class="sxs-lookup"><span data-stu-id="85d53-122">Managing Pre- and Post-processing Scripts</span></span>](../core/managing-pre-and-post-processing-scripts.md)  
  
-   [<span data-ttu-id="85d53-123">Administración de ensamblados .NET, certificados y otros recursos</span><span class="sxs-lookup"><span data-stu-id="85d53-123">Managing .NET Assemblies, Certificates, and Other Resources</span></span>](../core/managing-net-assemblies-certificates-and-other-resources.md)  
  
-   [<span data-ttu-id="85d53-124">Actualizar un recurso</span><span class="sxs-lookup"><span data-stu-id="85d53-124">Refresh a Resource</span></span>](../core/how-to-refresh-a-resource.md)