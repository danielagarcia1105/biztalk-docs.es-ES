---
title: Administrar los mapas | Microsoft Docs
description: Vínculos a trabajar con mapas en BizTalk Server, incluida la visualización y eliminación de asignaciones
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e8e3057-5a9f-4b6b-b6ee-c71b7e6a51ac
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d6957a4f3d73c5f59df5cd36f70a7ed34631fa6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019834"
---
# <a name="manage-maps"></a><span data-ttu-id="939c5-103">Administrar asignaciones</span><span class="sxs-lookup"><span data-stu-id="939c5-103">Manage Maps</span></span>

## <a name="overview"></a><span data-ttu-id="939c5-104">Información general</span><span class="sxs-lookup"><span data-stu-id="939c5-104">Overview</span></span>
<span data-ttu-id="939c5-105">En esta sección, se proporcionan instrucciones acerca de la administración de asignaciones desde la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="939c5-105">This section provides instructions on managing maps by using the BizTalk Server Administration console.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="939c5-106"> usa las asignaciones para traducir los registros y campos de un esquema a los de otro.</span><span class="sxs-lookup"><span data-stu-id="939c5-106"> uses maps to translate the records and fields in one schema to the records and fields in another schema.</span></span> <span data-ttu-id="939c5-107">Las asignaciones pueden usarse en orquestaciones, puertos de envío y puertos de recepción.</span><span class="sxs-lookup"><span data-stu-id="939c5-107">Maps may be used by orchestrations, send ports, and receive ports.</span></span>  

## <a name="add-maps-to-an-application"></a><span data-ttu-id="939c5-108">Agregar mapas a una aplicación</span><span class="sxs-lookup"><span data-stu-id="939c5-108">Add maps to an application</span></span>  
 <span data-ttu-id="939c5-109">Se generan los mapas [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se compilan en ensamblados de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="939c5-109">Maps are built in [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] and compiled into BizTalk assemblies.</span></span> <span data-ttu-id="939c5-110">No es posible agregar una asignación a una aplicación de manera individual; una asignación se agrega a una aplicación del modo que se especifica a continuación:</span><span class="sxs-lookup"><span data-stu-id="939c5-110">You cannot add a map to an application individually; a map is added to an application as follows:</span></span>  
  
- <span data-ttu-id="939c5-111">Cuando agrega un ensamblado de BizTalk que contiene una asignación a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span><span class="sxs-lookup"><span data-stu-id="939c5-111">When you add a BizTalk assembly containing a map to the application, as described in [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
- <span data-ttu-id="939c5-112">Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene una asignación, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="939c5-112">When you import an .msi file into an application that includes a BizTalk assembly containing a map, as described in [How to Import a BizTalk Application](../core/how-to-import-a-biztalk-application.md).</span></span>  
  
- <span data-ttu-id="939c5-113">Cuando un programador implementa en una aplicación un ensamblado que contiene una asignación de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tal y como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span><span class="sxs-lookup"><span data-stu-id="939c5-113">When a developer deploys into an application an assembly containing a map from [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], as described in [Deploying BizTalk Assemblies from Visual Studio into a BizTalk Application](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).</span></span>  
  
  <span data-ttu-id="939c5-114">Para obtener información general acerca de las asignaciones, vea [asigna](../core/maps.md).</span><span class="sxs-lookup"><span data-stu-id="939c5-114">For background information about maps, see [Maps](../core/maps.md).</span></span> <span data-ttu-id="939c5-115">Para obtener información sobre la creación de mapas, vea [crear se asigna utilizando el asignador de BizTalk](../core/creating-maps-using-biztalk-mapper.md).</span><span class="sxs-lookup"><span data-stu-id="939c5-115">For information about creating maps, see [Creating Maps Using BizTalk Mapper](../core/creating-maps-using-biztalk-mapper.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="939c5-116">Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas.</span><span class="sxs-lookup"><span data-stu-id="939c5-116">You can use Microsoft Windows Management Instrumentation (WMI) Object Model to create and run scripts that automate administrative tasks.</span></span> <span data-ttu-id="939c5-117">Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="939c5-117">For information about using WMI, see the **WMI Class Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="939c5-118">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="939c5-118">Next steps</span></span> 
  
-   [<span data-ttu-id="939c5-119">Ver las asignaciones de una aplicación</span><span class="sxs-lookup"><span data-stu-id="939c5-119">View the Maps for an Application</span></span>](../core/how-to-view-the-maps-for-an-application.md)  
  
-   [<span data-ttu-id="939c5-120">Quitar una asignación de una aplicación</span><span class="sxs-lookup"><span data-stu-id="939c5-120">Remove a Map from an Application</span></span>](../core/how-to-remove-a-map-from-an-application.md)