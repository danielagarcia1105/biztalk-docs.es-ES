---
title: "Compensación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- compensations, errors
- compensations
- errors, compensations
- compensations, about compensations
- compensations, atomic transactions
- atomic transactions, compensations
- transactions, compensations
ms.assetid: 0a80dd16-fd35-4f45-95b7-52bb9df80cbb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c572638ea6212c3fb79e6b239aa8ffbe713c3c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="compensation"></a><span data-ttu-id="f708f-102">Compensación</span><span class="sxs-lookup"><span data-stu-id="f708f-102">Compensation</span></span>
<span data-ttu-id="f708f-103">Si se produce un error y tiene que deshacer o invertir los efectos de una transacción confirmada correctamente, puede hacerlo agregando código de compensación a la orquestación.</span><span class="sxs-lookup"><span data-stu-id="f708f-103">If an error occurs and you need to undo or reverse the effects of a successfully committed transaction, you can do so by adding compensation code to your orchestration.</span></span>  
  
 <span data-ttu-id="f708f-104">solo puede invocarse la compensación después de que la transacción haya completado correctamente sus acciones.</span><span class="sxs-lookup"><span data-stu-id="f708f-104">The compensation can be invoked after the transaction has completed its actions successfully.</span></span> <span data-ttu-id="f708f-105">En ese punto, se conoce el estado de la orquestación y la información de estado está disponible para el código de la compensación, con lo que ya es posible escribir código que actúe debidamente en función del estado de la orquestación cuando se confirme la transacción.</span><span class="sxs-lookup"><span data-stu-id="f708f-105">At that point, the state of the orchestration is known, and state information is available to the code in the compensation, which means that you can write code to act appropriately depending on the state of the orchestration when the transaction commits.</span></span>  
  
 <span data-ttu-id="f708f-106">También se pueden realizar compensaciones para las transacciones atómicas.</span><span class="sxs-lookup"><span data-stu-id="f708f-106">Compensations can also be provided on atomic transactions.</span></span> <span data-ttu-id="f708f-107">solo se puede llamar a estas compensaciones después de que se confirme la transacción atómica.</span><span class="sxs-lookup"><span data-stu-id="f708f-107">These compensations can only be called after the atomic transaction commits.</span></span> <span data-ttu-id="f708f-108">Es preciso escribir código en la compensación que deshaga o invierta la ruta de ejecución normal.</span><span class="sxs-lookup"><span data-stu-id="f708f-108">You need to write code to undo or reverse the path of the normal execution in the compensation.</span></span>  
  
 <span data-ttu-id="f708f-109">El bloque de compensación es flexible; puede contener cualquier otra forma, incluso otro ámbito de transacción.</span><span class="sxs-lookup"><span data-stu-id="f708f-109">The compensation block is flexible; it can contain any other shape, including another transaction scope.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f708f-110">Únicamente se puede realizar una compensación para cada ámbito determinado.</span><span class="sxs-lookup"><span data-stu-id="f708f-110">You can do a compensation only once on a given scope.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f708f-111">En esta sección</span><span class="sxs-lookup"><span data-stu-id="f708f-111">In This Section</span></span>  
  
-   [<span data-ttu-id="f708f-112">Cómo configurar la forma compensar</span><span class="sxs-lookup"><span data-stu-id="f708f-112">How to Configure the Compensate Shape</span></span>](../core/how-to-configure-the-compensate-shape.md)  
  
-   [<span data-ttu-id="f708f-113">Cómo agregar la compensación personalizada a una orquestación</span><span class="sxs-lookup"><span data-stu-id="f708f-113">How to Add Custom Compensation to an Orchestration</span></span>](../core/how-to-add-custom-compensation-to-an-orchestration.md)  
  
-   [<span data-ttu-id="f708f-114">Cómo agregar un bloque de compensación</span><span class="sxs-lookup"><span data-stu-id="f708f-114">How to Add a Compensation Block</span></span>](../core/how-to-add-a-compensation-block.md)