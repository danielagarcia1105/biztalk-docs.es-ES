---
title: Consideraciones importantes para actualizar aplicaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- updating, applications
- applications, planning
- applications, updating
- planning, applications
- planning, updating
- updating, planning
ms.assetid: e7690bdf-943d-4bb6-b8cd-a6841b722d40
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c24528dcce390376b7ac2e47199aa5ae06d412a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="important-considerations-for-updating-applications"></a><span data-ttu-id="105e3-102">Consideraciones importantes para actualizar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="105e3-102">Important Considerations for Updating Applications</span></span>
<span data-ttu-id="105e3-103">A continuación se indican problemas importantes que deben considerarse antes de actualizar una aplicación, especialmente si la misma se ejecuta en un entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="105e3-103">The following are important issues to consider before updating an application, especially one that is running in a production environment.</span></span>  
  
## <a name="general-considerations"></a><span data-ttu-id="105e3-104">Consideraciones generales</span><span class="sxs-lookup"><span data-stu-id="105e3-104">General considerations</span></span>  
  
-   <span data-ttu-id="105e3-105">Las entidades y reglas están visibles en un ámbito de grupo, por lo que agregar entidades y reglas adicionales puede afectar a otras aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="105e3-105">Parties and rules are visible at a group scope, so adding additional parties and rules could disrupt other applications.</span></span>  
  
-   <span data-ttu-id="105e3-106">Para anular la implementación de un artefacto del que depende otro, primero se debe anular la implementación del artefacto dependiente.</span><span class="sxs-lookup"><span data-stu-id="105e3-106">If you are undeploying an artifact on which another artifact depends, the dependent artifact must be undeployed first.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="105e3-107">La consola de administración de BizTalk Server mostrará una advertencia e impedirá anular la implementación de artefactos si se intenta realizar en un orden incorrecto.</span><span class="sxs-lookup"><span data-stu-id="105e3-107">The BizTalk Server Administration console will display a warning and prevent you from undeploying artifacts in the incorrect order.</span></span>  
  
-   <span data-ttu-id="105e3-108">Si se actualiza un ensamblado de BizTalk en una aplicación existente, debe reiniciar instancias de host para que los cambios surtan efecto.</span><span class="sxs-lookup"><span data-stu-id="105e3-108">If a BizTalk assembly in an existing application is updated, you may need to restart host instances for the changes to take effect.</span></span> <span data-ttu-id="105e3-109">Al reiniciar una instancia de host detiene todas las demás aplicaciones que se ejecutan en la instancia de host.</span><span class="sxs-lookup"><span data-stu-id="105e3-109">Restarting a host instance stops all other applications that are running on the host instance.</span></span>  
  
-   <span data-ttu-id="105e3-110">Si se usa Visual Studio para implementar una aplicación en un entorno de producción (no se recomienda en absoluto) y la opción Reiniciar instancias de host está establecida como True en las propiedades del proyecto, se reiniciarán todas las instancias de host al implementar la aplicación, incluidas las que no estén asociadas a esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="105e3-110">If you use Visual Studio to deploy an application into a production environment (which we strongly recommend against doing) and the Restart Host Instances option is set to True in project properties, all host instances will restart when you deploy the application, including those that are not associated with this application.</span></span> <span data-ttu-id="105e3-111">Esto detendrá todas las demás aplicaciones que estén en ejecución en cualquier instancia de host del equipo local.</span><span class="sxs-lookup"><span data-stu-id="105e3-111">This will stop all other applications that are running on any host instance on the local computer.</span></span>  
  
-   <span data-ttu-id="105e3-112">Si desea actualizar un ensamblado de BizTalk Server (que contiene una orquestación, un esquema o una asignación) que se implementa como una aplicación de BizTalk, puede realizar cualquiera de las acciones siguientes:</span><span class="sxs-lookup"><span data-stu-id="105e3-112">If you want to update a BizTalk Server assembly (containing an orchestration, schema, or map) which is deployed as a BizTalk application, you can do any of the following:</span></span>  
  
    -   <span data-ttu-id="105e3-113">Efectúe una implementación en paralelo.</span><span class="sxs-lookup"><span data-stu-id="105e3-113">Perform a side-by-side deployment.</span></span> <span data-ttu-id="105e3-114">Puede modificar de forma apropiada el ensamblado más reciente, generalmente incrementando la versión.</span><span class="sxs-lookup"><span data-stu-id="105e3-114">You can appropriately modify the newer assembly typically by incrementing the version.</span></span> <span data-ttu-id="105e3-115">Esto hace que ambos ensamblados tengan un nombre completo de ensamblado distinto.</span><span class="sxs-lookup"><span data-stu-id="105e3-115">This makes both the assemblies have a distinct fully qualified assembly name.</span></span> <span data-ttu-id="105e3-116">Para obtener más información, consulte [cómo implementar una nueva versión de una aplicación en ejecución Side-by-side con una versión existente](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md).</span><span class="sxs-lookup"><span data-stu-id="105e3-116">For more information, see [How to Deploy a New Version of an Application to Run Side-by-side with an Existing Version](../core/deploy-new-application-version-to-run-side-by-side-with-existing-version.md).</span></span>  
  
    -   <span data-ttu-id="105e3-117">Sustituya el ensamblado de BizTalk Server existente por un nuevo ensamblado.</span><span class="sxs-lookup"><span data-stu-id="105e3-117">Replace the existing BizTalk Server assembly with a new assembly.</span></span> <span data-ttu-id="105e3-118">Debe detener todas las instancias de host que tengan la posibilidad de cargar el ensamblado obsoleto, sustituir el ensamblado obsoleto en la GAC y reiniciar las instancias de host.</span><span class="sxs-lookup"><span data-stu-id="105e3-118">You must stop all host instances that can possibly load the out-dated assembly, replace the out-dated assembly in the GAC, and then restart the host instances.</span></span>  
  
-   <span data-ttu-id="105e3-119">Si se implementa una aplicación completamente nueva para reemplazar una existente, se debe corregir cualquier referencia existente entre otras aplicaciones y la aplicación que se está reemplazando.</span><span class="sxs-lookup"><span data-stu-id="105e3-119">If you deploy an entirely new application to replace an existing application, you must correct any references between other applications and the application that you are replacing.</span></span>  
  
## <a name="considerations-for-updating-schemas"></a><span data-ttu-id="105e3-120">Consideraciones para actualizar esquemas</span><span class="sxs-lookup"><span data-stu-id="105e3-120">Considerations for updating schemas</span></span>  
  
-   <span data-ttu-id="105e3-121">Si agrega un ensamblado a una aplicación que incluye un nuevo esquema con el mismo tipo de mensaje como un esquema existente en el grupo de BizTalk, se usará el esquema con el mayor número de versión cuando la resolución de esquemas se produce en las canalizaciones.</span><span class="sxs-lookup"><span data-stu-id="105e3-121">If you add an assembly to an application that includes a new schema with the same message type as an existing schema in the BizTalk group, the schema with the highest version number will be used when schema resolution occurs in pipelines.</span></span> <span data-ttu-id="105e3-122">Además, si un tipo de mensaje hace referencia a más de un tipo. NET, esta ambigüedad puede provocar errores de ejecución de canalización.</span><span class="sxs-lookup"><span data-stu-id="105e3-122">In addition, if one message type refers to more than one .NET type, this ambiguity may cause pipeline execution failure.</span></span> <span data-ttu-id="105e3-123">Esto se debe a que la búsqueda de esquemas usa el tipo de mensaje, el espacio de nombres de destino y el nombre de raíz de la instancia.</span><span class="sxs-lookup"><span data-stu-id="105e3-123">This is because schema lookup uses message type, the target namespace, and root name of the instance.</span></span> <span data-ttu-id="105e3-124">Esta situación puede ocurrir con las canalizaciones de aplicaciones que usen un esquema con el mismo tipo de mensaje que el nuevo esquema.</span><span class="sxs-lookup"><span data-stu-id="105e3-124">This can occur for pipelines in any application that uses a schema with the same message type as the new schema.</span></span> <span data-ttu-id="105e3-125">Para obtener más información acerca de la resolución de esquemas, vea [resolución de esquemas en componentes de canalización](../core/schema-resolution-in-pipeline-components.md).</span><span class="sxs-lookup"><span data-stu-id="105e3-125">For more information about schema resolution, see [Schema Resolution in Pipeline Components](../core/schema-resolution-in-pipeline-components.md).</span></span>  
  
-   <span data-ttu-id="105e3-126">Al actualizar un esquema, también se deben actualizar las asignaciones que hacen referencia al mismo (o crear nuevas asignaciones) y cualquier otra orquestación basada en él.</span><span class="sxs-lookup"><span data-stu-id="105e3-126">When you update a schema, you must also update the maps that reference the schema (or create new maps) as well as any orchestrations that rely on the schema.</span></span>  
  
-   <span data-ttu-id="105e3-127">Si se incrementa la versión de un esquema, se debe actualizar la referencia al esquema para cualquier instancia y componente de canalización que lo use.</span><span class="sxs-lookup"><span data-stu-id="105e3-127">If you increment a schema version, you should update the reference to the schema for any pipeline instances and pipeline components that use it.</span></span>  
  
-   <span data-ttu-id="105e3-128">Al anular la implementación de un esquema, se activa la versión anterior del esquema, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="105e3-128">Undeploying a schema causes the previous version of the schema, if available, to become active.</span></span>  
  
## <a name="considerations-for-updating-policies"></a><span data-ttu-id="105e3-129">Consideraciones para actualizar directivas</span><span class="sxs-lookup"><span data-stu-id="105e3-129">Considerations for updating policies</span></span>  
  
-   <span data-ttu-id="105e3-130">El tiempo de ejecución de BizTalk Server usa la versión más alta de una directiva con estado implementado.</span><span class="sxs-lookup"><span data-stu-id="105e3-130">The highest version of a policy that is in a deployed state is used by the BizTalk Server runtime.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="105e3-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="105e3-131">See Also</span></span>  
 [<span data-ttu-id="105e3-132">Actualizar aplicaciones de BizTalk</span><span class="sxs-lookup"><span data-stu-id="105e3-132">Updating BizTalk Applications</span></span>](../core/updating-biztalk-applications.md)