---
title: Error - el Functoid No tiene entrada | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.functiodHasNoInput
ms.assetid: ea59b902-953d-4a5f-aa28-dbaa0a017dca
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97505d0c00e0cc9015dd17cb487bb5dbf6a50d90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error---functoid-has-no-input"></a><span data-ttu-id="f1ca0-102">Error - el Functoid No tiene entrada</span><span class="sxs-lookup"><span data-stu-id="f1ca0-102">Error - Functoid Has No Input</span></span>
<span data-ttu-id="f1ca0-103">**Código de error**</span><span class="sxs-lookup"><span data-stu-id="f1ca0-103">**Error Code**</span></span>  
  
 <span data-ttu-id="f1ca0-104">btm1012</span><span class="sxs-lookup"><span data-stu-id="f1ca0-104">btm1012</span></span>  
  
 <span data-ttu-id="f1ca0-105">**Explicación**</span><span class="sxs-lookup"><span data-stu-id="f1ca0-105">**Explanation**</span></span>  
  
 <span data-ttu-id="f1ca0-106">El functoid indicado necesita al menos un parámetro de entrada pero no se han especificado parámetros de entrada.</span><span class="sxs-lookup"><span data-stu-id="f1ca0-106">The indicated functoid requires at least one input parameter, but no input parameters have been specified.</span></span>  
  
 <span data-ttu-id="f1ca0-107">**Acción del usuario**</span><span class="sxs-lookup"><span data-stu-id="f1ca0-107">**User Action**</span></span>  
  
 <span data-ttu-id="f1ca0-108">Utilice uno o ambos de los métodos siguientes para proporcionar el número apropiado de parámetros de entrada al functoid indicado y preste especial atención al orden esperado de los parámetros de entrada:</span><span class="sxs-lookup"><span data-stu-id="f1ca0-108">Use one or both of the following methods to provide the appropriate number of input parameters to the indicated functoid, paying particular attention to the expected order of input parameters:</span></span>  
  
-   <span data-ttu-id="f1ca0-109">Arrastre para crear vínculos entre el functoid indicado y los nodos del esquema de origen o la salida de otros functoids situados a la izquierda del functoid indicado en una página de cuadrícula de asignación.</span><span class="sxs-lookup"><span data-stu-id="f1ca0-109">Drag to create links between the indicated functoid and either nodes in the source schema or the output of other functoids that are located to the left of the indicated functoid in a map grid page.</span></span>  
  
-   <span data-ttu-id="f1ca0-110">Seleccione el functoid indicado, haga clic en el botón de puntos suspensivos (**...** ) asociado a la **parámetros de entrada** propiedad de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades y, a continuación, configure y reorganice el orden de los parámetros de entrada en el **configurar \<Functoid > Functoid** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f1ca0-110">Select the indicated functoid, click the ellipsis (**...**) button associated with the **Input Parameters** property in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Properties window, and then configure and rearrange the order of the input parameters in the **Configure \<Functoid> Functoid** dialog box.</span></span> <span data-ttu-id="f1ca0-111">Se pueden crear parámetros de entrada, dados los valores, y se pueden poner en el orden correcto en relación con otros parámetros de entrada de este cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="f1ca0-111">Constant input parameters can be created, given values, and put in the proper order relative to the other input parameters in this dialog box.</span></span>