---
title: Funciones de Control del motor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Business Rules Engine, functions
ms.assetid: a7900e59-c52c-4a6d-9ca3-ee4ec659f9b5
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 033a4213a6552319f44a98e23562d7e8703fdd42
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="engine-control-functions"></a><span data-ttu-id="d3d9c-102">Funciones de control del motor</span><span class="sxs-lookup"><span data-stu-id="d3d9c-102">Engine Control Functions</span></span>
<span data-ttu-id="d3d9c-103">En esta sección se explican los comportamientos asociados con varias funciones de control del motor de reglas de negocios que permiten a una aplicación o a una directiva controlar los datos de la memoria de trabajo del motor de reglas.</span><span class="sxs-lookup"><span data-stu-id="d3d9c-103">This section explains the behaviors associated with several Business Rule engine control functions that allow an application or policy to control the facts in the rule engine's working memory.</span></span> <span data-ttu-id="d3d9c-104">La presencia de datos en la memoria de trabajo determina las condiciones que se evalúan y las acciones que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="d3d9c-104">The presence of facts in the working memory drives the conditions that are evaluated and the actions that are executed.</span></span>  
  
 <span data-ttu-id="d3d9c-105">Esta sección se examina la **Assert**, **Retract**, **RetractByType**, **imponer**, y **actualización** funciones de hechos diferentes: objetos. NET, **TypedXmlDocument**, **DataConnection**, y **TypedDataTable**.</span><span class="sxs-lookup"><span data-stu-id="d3d9c-105">This section examines the **Assert**, **Retract**, **RetractByType**, **Reassert**, and **Update** functions for different facts: .NET objects, **TypedXmlDocument**, **DataConnection**, and **TypedDataTable**.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d3d9c-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d3d9c-106">In This Section</span></span>  
  
-   [<span data-ttu-id="d3d9c-107">Assert</span><span class="sxs-lookup"><span data-stu-id="d3d9c-107">Assert</span></span>](../core/assert.md)  
  
-   [<span data-ttu-id="d3d9c-108">Retirar</span><span class="sxs-lookup"><span data-stu-id="d3d9c-108">Retract</span></span>](../core/retract.md)  
  
-   [<span data-ttu-id="d3d9c-109">RetractByType</span><span class="sxs-lookup"><span data-stu-id="d3d9c-109">RetractByType</span></span>](../core/retractbytype.md)  
  
-   [<span data-ttu-id="d3d9c-110">Volver a imponer</span><span class="sxs-lookup"><span data-stu-id="d3d9c-110">Reassert</span></span>](../core/reassert.md)  
  
-   [<span data-ttu-id="d3d9c-111">Update</span><span class="sxs-lookup"><span data-stu-id="d3d9c-111">Update</span></span>](../core/update1.md)  
  
-   [<span data-ttu-id="d3d9c-112">Detener</span><span class="sxs-lookup"><span data-stu-id="d3d9c-112">Halt</span></span>](../core/halt.md)