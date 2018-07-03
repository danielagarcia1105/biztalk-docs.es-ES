---
title: Directivas de compilador y los vínculos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compilier directives
- maps, compiling
- BizTalk Mapper, compiler directives
- links [maps], compiling
ms.assetid: 1655e10c-af98-4100-849d-b8214f93cfe9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 38e00b7d20e6fd0aff4f6af72377e301a812b8fd
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992005"
---
# <a name="compiler-directives-and-links"></a><span data-ttu-id="c75f7-102">Vínculos y directivas de compilador</span><span class="sxs-lookup"><span data-stu-id="c75f7-102">Compiler Directives and Links</span></span>
<span data-ttu-id="c75f7-103">Puede configurar las dos siguientes directivas de compilador vínculo por vínculo:</span><span class="sxs-lookup"><span data-stu-id="c75f7-103">You can configure the following two compiler directives on a link-by-link basis:</span></span>  
  
- <span data-ttu-id="c75f7-104">Qué datos del mensaje de instancia de entrada se recuperan y copian como valor de elemento o atributo correspondiente en el mensaje de instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="c75f7-104">What data from the input instance message is retrieved and copied as the relevant element or attribute value in the output instance message.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="c75f7-105">Estos datos incluyen la opción de copiar el propio nombre del elemento o atributo, en vez de cualquier valor asociado con ellos.</span><span class="sxs-lookup"><span data-stu-id="c75f7-105">Data here includes the option to copy the name of the element or attribute itself, rather than any value associated with the element or attribute.</span></span> <span data-ttu-id="c75f7-106">Generalmente, los nombres de elemento o atributo no se consideran como una parte de los datos transmitidos en un mensaje de instancia XML.</span><span class="sxs-lookup"><span data-stu-id="c75f7-106">Element and attribute names are not normally thought of as part of the data carried in an XML instance message.</span></span>  
  
- <span data-ttu-id="c75f7-107">Cómo llevar a cabo la coincidencia de nodos entre los esquemas de origen y de destino.</span><span class="sxs-lookup"><span data-stu-id="c75f7-107">How node-matching is performed between the source and destination schemas.</span></span>  
  
  <span data-ttu-id="c75f7-108">En esta sección se proporciona un explicación detallada de las opciones disponibles para estas directivas.</span><span class="sxs-lookup"><span data-stu-id="c75f7-108">This section provides a detailed explanation of these options available for these directives.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c75f7-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c75f7-109">In This Section</span></span>  
  
-   [<span data-ttu-id="c75f7-110">Configuración de transformación de datos</span><span class="sxs-lookup"><span data-stu-id="c75f7-110">Data Transformation Configuration</span></span>](../core/data-transformation-configuration.md)  
  
-   [<span data-ttu-id="c75f7-111">Coincidencia del nivel jerárquico de nodos</span><span class="sxs-lookup"><span data-stu-id="c75f7-111">Node-Hierarchy Level Matching</span></span>](../core/node-hierarchy-level-matching.md)