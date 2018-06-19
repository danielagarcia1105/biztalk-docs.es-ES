---
title: Cómo configurar la forma Finalizar | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Terminate shape [Orchestration Designer], about Terminate shape
- Terminate shape [Orchestration Designer], literal strings
- configuring [Orchestration Designer], Terminate shapes
- Terminate shape [Orchestration Designer], configuring
- Terminate shape [Orchestration Designer]
ms.assetid: 2c4f2c94-2bab-4af3-8954-7275696ca147
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a5eb4867970c6acafc8903eb474b67541d22764
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247932"
---
# <a name="how-to-configure-the-terminate-shape"></a><span data-ttu-id="9ce14-102">Cómo configurar la forma Finalizar</span><span class="sxs-lookup"><span data-stu-id="9ce14-102">How to Configure the Terminate Shape</span></span>
![](../core/media/ebiz-orch-terminate.gif "ebiz_orch_terminate")  
<span data-ttu-id="9ce14-103">Forma Finalizar</span><span class="sxs-lookup"><span data-stu-id="9ce14-103">Terminate shape</span></span>  
  
 <span data-ttu-id="9ce14-104">La forma Finalizar se usa para terminar una instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="9ce14-104">The Terminate shape is used to end an orchestration instance.</span></span> <span data-ttu-id="9ce14-105">Puede especificar una cadena de mensaje para acompañar la forma cuando se visualice en los resultados de la página Concentrador de grupo.</span><span class="sxs-lookup"><span data-stu-id="9ce14-105">You can specify a message string to accompany the shape when viewed in the output from the Group Hub page.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="9ce14-106">Si coloca un **Terminate** forma dentro de un **acciones paralelas** forma así como la rama con la **Terminate** en que se ejecuta, la instancia se completa inmediatamente, sin tener en cuenta Si el resto de bifurcaciones ha terminado de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="9ce14-106">If you place a **Terminate** shape inside a **Parallel Actions** shape, and the branch with the **Terminate** on it is run, the instance completes immediately, regardless of whether other branches have finished running.</span></span> <span data-ttu-id="9ce14-107">Según su diseño, los resultados podrían ser imprevisibles en este caso.</span><span class="sxs-lookup"><span data-stu-id="9ce14-107">Depending on your design, results might be unpredictable in this case.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="9ce14-108">Si un **Terminate** forma se encuentra en una orquestación que se ha llamado de forma sincrónica (igual que con la **llamar a** forma) por otra orquestación, la instancia anidada y todas las orquestación envolvente puede finalizar instancias.</span><span class="sxs-lookup"><span data-stu-id="9ce14-108">If a **Terminate** shape is encountered in an orchestration that has been called synchronously (as with the **Call** shape) by another orchestration, the nested instance and all enclosing orchestration instances will be terminated.</span></span>  
  
### <a name="to-configure-a-terminate-shape"></a><span data-ttu-id="9ce14-109">Para configurar una forma Finalizar:</span><span class="sxs-lookup"><span data-stu-id="9ce14-109">To configure a Terminate shape</span></span>  
  
-   <span data-ttu-id="9ce14-110">Puede usar el **mensaje de Error** propiedad para especificar el texto que desea asociar a la forma cuando se ve en el resultado de la consulta en la página concentrador de grupo.</span><span class="sxs-lookup"><span data-stu-id="9ce14-110">You can use the **Error Message** property to specify text that you want to associate with the shape when viewed in the query output on the Group Hub page.</span></span> <span data-ttu-id="9ce14-111">Este texto puede ser una cadena literal o una expresión que se evalúa como un **System.String**.</span><span class="sxs-lookup"><span data-stu-id="9ce14-111">This text may be a literal string, or an expression that evaluates to a **System.String**.</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="9ce14-112">Si escribe una cadena literal, ésta debe ir entre comillas.</span><span class="sxs-lookup"><span data-stu-id="9ce14-112">If you enter a literal string, you must enclose it in quotation marks.</span></span>