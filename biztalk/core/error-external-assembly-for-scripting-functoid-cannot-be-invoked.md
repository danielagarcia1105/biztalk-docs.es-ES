---
title: 'Error: ensamblado externo para el Functoid de secuencias de comandos no se puede invocar | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.cannotInvokeExternalAssembly
ms.assetid: 30d97b05-2cbf-44a5-b219-3a5ae17fc597
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37f6df36a955f2f40da35368fd72fd2d1fcbb7b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---external-assembly-for-scripting-functoid-cannot-be-invoked"></a><span data-ttu-id="31c04-102">No se puede invocar el error: ensamblado externo para el Functoid de secuencias de comandos</span><span class="sxs-lookup"><span data-stu-id="31c04-102">Error - External Assembly for Scripting Functoid Cannot Be Invoked</span></span>
<span data-ttu-id="31c04-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="31c04-103">**Error Code**</span></span>  
  
 <span data-ttu-id="31c04-104">btm1067</span><span class="sxs-lookup"><span data-stu-id="31c04-104">btm1067</span></span>  
  
 <span data-ttu-id="31c04-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="31c04-105">**Explanation**</span></span>  
  
 <span data-ttu-id="31c04-106">El método de ensamblado externo que está asociado con la correspondiente **secuencias de comandos** no se puede invocar el functoid.</span><span class="sxs-lookup"><span data-stu-id="31c04-106">The external assembly method that is associated with the relevant **Scripting** functoid cannot be invoked.</span></span> <span data-ttu-id="31c04-107">Aunque no son necesarios para la compilación de la asignación, la operación Comprobar asignación necesita que dichos ensambladores externos estén presentes en la caché de ensamblados global (GAC).</span><span class="sxs-lookup"><span data-stu-id="31c04-107">Although not required for map compilation, the Test Map operation requires that such external assemblies be present in the global assembly cache (GAC).</span></span> <span data-ttu-id="31c04-108">La operación en tiempo de ejecución normal también necesita que estos ensambladores externos estén presentes en la caché de ensamblado global (GAC).</span><span class="sxs-lookup"><span data-stu-id="31c04-108">Normal, run time operation also requires that external assemblies be present in the GAC.</span></span>  
  
 <span data-ttu-id="31c04-109">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="31c04-109">**User Action**</span></span>  
  
 <span data-ttu-id="31c04-110">Asegúrese de que el ensamblado externo al que hace referencia la correspondiente **secuencias de comandos** functoid está en la GAC.</span><span class="sxs-lookup"><span data-stu-id="31c04-110">Ensure that the external assembly referenced by the relevant **Scripting** functoid is in the GAC.</span></span>