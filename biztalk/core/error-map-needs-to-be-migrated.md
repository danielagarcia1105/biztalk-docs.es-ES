---
title: 'Error: asignación debe migrar | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.mapNeedsMigrating
ms.assetid: f10af4a4-6e40-4eec-a2fd-e526821aebe6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9f49ef4aae0db47216f6117f1053185df6fae0a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240556"
---
# <a name="error---map-needs-to-be-migrated"></a><span data-ttu-id="e6855-102">Error: asignación debe migrar</span><span class="sxs-lookup"><span data-stu-id="e6855-102">Error - Map Needs to be Migrated</span></span>
<span data-ttu-id="e6855-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="e6855-103">**Error Code**</span></span>  
  
 <span data-ttu-id="e6855-104">btm1064</span><span class="sxs-lookup"><span data-stu-id="e6855-104">btm1064</span></span>  
  
 <span data-ttu-id="e6855-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="e6855-105">**Explanation**</span></span>  
  
 <span data-ttu-id="e6855-106">No se puede compilar la asignación porque se creó mediante una versión anterior del Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e6855-106">The map cannot be compiled because it was created using a previous version of BizTalk Mapper.</span></span> <span data-ttu-id="e6855-107">Debe migrar las asignaciones de este tipo a esta versión del Asignador de BizTalk para poder compilarlas.</span><span class="sxs-lookup"><span data-stu-id="e6855-107">You must migrate such maps to this version of BizTalk Mapper before they can be compiled.</span></span>  
  
 <span data-ttu-id="e6855-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="e6855-108">**User Action**</span></span>  
  
 <span data-ttu-id="e6855-109">Para migrar la asignación a la versión actual del Asignador de BizTalk, cambie su extensión de archivo de "xml" a "btm", y agréguela al proyecto de Microsoft BizTalk Server correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e6855-109">Migrate the map to the current version of BizTalk Mapper by changing its file extension from "xml" to "btm", adding it to the relevant Microsoft BizTalk Server project.</span></span> <span data-ttu-id="e6855-110">Use la **Agregar elemento existente** comandos disponibles en la **archivo** menú en el menú contextual de BizTalk del proyecto en el Explorador de soluciones y, a continuación, abra la asignación haciendo doble clic en él en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="e6855-110">Use the **Add Existing Item** command available on the **File** menu and on the shortcut menu for the BizTalk project in Solution Explorer, and then open the map by double-clicking it in Solution Explorer.</span></span> <span data-ttu-id="e6855-111">Puesto que ha llegado a este tema, probablemente ya haya llevado a cabo los dos primeros pasos.</span><span class="sxs-lookup"><span data-stu-id="e6855-111">Because you have reached this topic, you have probably already performed the first two steps.</span></span> <span data-ttu-id="e6855-112">Con tan solo abrir la asignación de la versión actual del Asignador de BizTalk se realizará una migración dinámica de la asignación.</span><span class="sxs-lookup"><span data-stu-id="e6855-112">Simply opening the map in the current version of BizTalk Mapper will perform an on-the-fly migration of the map.</span></span>