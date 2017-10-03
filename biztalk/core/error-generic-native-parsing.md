---
title: "Error: análisis nativo genérico | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.genericNativeParsing
ms.assetid: a28a4c0f-b69b-448b-b305-3b06b4f061e4
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 383c3198af290552715d51812f22c82760cb445f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---generic-native-parsing"></a><span data-ttu-id="08746-102">Error: análisis nativo genérico</span><span class="sxs-lookup"><span data-stu-id="08746-102">Error - Generic Native Parsing</span></span>
<span data-ttu-id="08746-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="08746-103">**Error Code**</span></span>  
  
 <span data-ttu-id="08746-104">btm1042</span><span class="sxs-lookup"><span data-stu-id="08746-104">btm1042</span></span>  
  
 <span data-ttu-id="08746-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="08746-105">**Explanation**</span></span>  
  
 <span data-ttu-id="08746-106">No se pudo analizar el archivo de mensaje de instancia de entrada nativo especificado para la operación Comprobar asignación y se produjo un error grave de análisis genérico.</span><span class="sxs-lookup"><span data-stu-id="08746-106">The native input instance message file specified for the Test Map operation could not be parsed, and generated a generic fatal parsing error.</span></span>  
  
 <span data-ttu-id="08746-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="08746-107">**User Action**</span></span>  
  
 <span data-ttu-id="08746-108">Según resulte necesario, corrija el esquema de origen asociado a la asignación o el mensaje de instancia de entrada nativo del archivo especificado, o ambos.</span><span class="sxs-lookup"><span data-stu-id="08746-108">As appropriate, correct either the source schema associated with the map or the native input instance message in the specified file, or both.</span></span> <span data-ttu-id="08746-109">Considere trabajar en el Editor de BizTalk para aislar el problema.</span><span class="sxs-lookup"><span data-stu-id="08746-109">Consider working within BizTalk Editor to isolate the problem.</span></span> <span data-ttu-id="08746-110">El **Validar esquema** y **generar instancia** comandos, que aparecen cuando hace clic en un esquema en el Explorador de soluciones, son útiles para encontrar errores de esquema.</span><span class="sxs-lookup"><span data-stu-id="08746-110">The **Validate Schema** and **Generate Instance** commands, available when you right-click a schema in Solution Explorer, are useful for finding schema errors.</span></span>