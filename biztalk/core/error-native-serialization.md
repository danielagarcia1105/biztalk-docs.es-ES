---
title: 'Error: serialización nativa | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.nativeSerialize
ms.assetid: 48f8d460-83a0-44ce-af9b-086fcad36cb8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c0d4a842a3f9a10703fb47bf21edb01ab92bd93c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---native-serialization"></a><span data-ttu-id="39ebc-102">Error: serialización nativa</span><span class="sxs-lookup"><span data-stu-id="39ebc-102">Error - Native Serialization</span></span>
<span data-ttu-id="39ebc-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="39ebc-103">**Error Code**</span></span>  
  
 <span data-ttu-id="39ebc-104">btm1048</span><span class="sxs-lookup"><span data-stu-id="39ebc-104">btm1048</span></span>  
  
 <span data-ttu-id="39ebc-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="39ebc-105">**Explanation**</span></span>  
  
 <span data-ttu-id="39ebc-106">Se detectó el error de serialización indicado al intentar convertir el mensaje de instancia de salida XML que produjo la asignación en el formato nativo especificado por el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="39ebc-106">The indicated serialization error was encountered when attempting to convert the XML output instance message produced by the map into the native format specified by the destination schema.</span></span>  
  
 <span data-ttu-id="39ebc-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="39ebc-107">**User Action**</span></span>  
  
 <span data-ttu-id="39ebc-108">En función del error de serialización indicado, haga las correcciones necesarias en las transformaciones especificadas en la asignación, en el esquema de destino o en ambos.</span><span class="sxs-lookup"><span data-stu-id="39ebc-108">Based on the indicated serialization error, make the appropriate corrections to either the transformations specified in the map, or to the destination schema, or to both.</span></span> <span data-ttu-id="39ebc-109">Puede resultar útil abrir el esquema de destino en el Editor de BizTalk y utilice la **Validar esquema**, **Validar instancia**, y **generar instancia** comandos disponibles cuando Haga un esquema en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="39ebc-109">It may be helpful to open the destination schema in BizTalk Editor and use the **Validate Schema**, **Validate Instance**, and **Generate Instance** commands available when you right-click a schema in Solution Explorer.</span></span>