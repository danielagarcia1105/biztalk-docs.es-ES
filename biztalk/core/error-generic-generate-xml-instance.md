---
title: Error - generar instancia XML | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericGenerateXmlInstance
ms.assetid: f2b42589-fd44-45d6-86e6-c2502820beee
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c859cfc775e74ab817e66dbb8b896f51458f0301
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---generic-generate-xml-instance"></a><span data-ttu-id="e24de-102">Error - generar instancia XML</span><span class="sxs-lookup"><span data-stu-id="e24de-102">Error - Generic Generate XML Instance</span></span>
<span data-ttu-id="e24de-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="e24de-103">**Error Code**</span></span>  
  
 <span data-ttu-id="e24de-104">btm1038</span><span class="sxs-lookup"><span data-stu-id="e24de-104">btm1038</span></span>  
  
 <span data-ttu-id="e24de-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="e24de-105">**Explanation**</span></span>  
  
 <span data-ttu-id="e24de-106">El Asignador de BizTalk no pudo generar un archivo de mensaje de instancia XML para el esquema de origen de la asignación,</span><span class="sxs-lookup"><span data-stu-id="e24de-106">BizTalk Mapper was not able to generate an XML instance message file for the source schema of the map.</span></span> <span data-ttu-id="e24de-107">lo cual sugiere que existe un problema con el esquema de origen asociado a la asignación.</span><span class="sxs-lookup"><span data-stu-id="e24de-107">This suggests that there is a problem with the source schema associated with the map.</span></span>  
  
 <span data-ttu-id="e24de-108">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="e24de-108">**User Action**</span></span>  
  
 <span data-ttu-id="e24de-109">Utilice el Editor de BizTalk para abrir el esquema de origen asociado a la asignación y empiece a investigar si existen problemas con el esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="e24de-109">Use BizTalk Editor to open the source schema associated with the map and begin investigating whether there are problems with the source schema.</span></span> <span data-ttu-id="e24de-110">Además, el **Validar esquema** y **generar instancia** comandos, que aparecen cuando hace clic en un esquema en el Explorador de soluciones, son útiles para encontrar errores de esquema.</span><span class="sxs-lookup"><span data-stu-id="e24de-110">Also, the **Validate Schema** and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, are useful for finding schema errors.</span></span>