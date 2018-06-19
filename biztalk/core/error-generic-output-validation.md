---
title: 'Error: validación de salida genérica | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.genericOutputValidation
ms.assetid: 27fb2233-3add-42f8-a96b-872e2e38f797
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c1bac5235788f6e369cc316ed1236357a51c004
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239876"
---
# <a name="error---generic-output-validation"></a><span data-ttu-id="f131d-102">Error: validación de salida genérica</span><span class="sxs-lookup"><span data-stu-id="f131d-102">Error - Generic Output Validation</span></span>
<span data-ttu-id="f131d-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="f131d-103">**Error Code**</span></span>  
  
 <span data-ttu-id="f131d-104">btm1047</span><span class="sxs-lookup"><span data-stu-id="f131d-104">btm1047</span></span>  
  
 <span data-ttu-id="f131d-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="f131d-105">**Explanation**</span></span>  
  
 <span data-ttu-id="f131d-106">El archivo de mensaje de instancia de salida que creó la operación Comprobar asignación no se pudo validar con respecto al esquema de destino debido a una razón no especificada.</span><span class="sxs-lookup"><span data-stu-id="f131d-106">The output instance message file created by the Test Map operation could not be validated against the destination schema for an unspecified reason.</span></span>  
  
 <span data-ttu-id="f131d-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="f131d-107">**User Action**</span></span>  
  
 <span data-ttu-id="f131d-108">Abra el esquema de destino en el Editor de BizTalk y utilice la **Validar esquema**, **Validar instancia**, y **generar instancia** comandos, que aparecen cuando hace clic en un esquema en el Explorador de soluciones, para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="f131d-108">Open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, to isolate the problem.</span></span>