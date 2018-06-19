---
title: Cómo agregar un bloque de compensación | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- compensations, compensation blocks
- compensation blocks, adding
ms.assetid: 1bdeed92-3144-44ef-ad0d-1c6976f46a36
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dec4f4dd01c2bbf522dfff44ec8aaf0c2f5e89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246540"
---
# <a name="how-to-add-a-compensation-block"></a><span data-ttu-id="21fd9-102">Cómo agregar un bloque de compensación</span><span class="sxs-lookup"><span data-stu-id="21fd9-102">How to Add a Compensation Block</span></span>
<span data-ttu-id="21fd9-103">Si no agrega su propia compensación, el motor de tiempo de ejecución llevará a cabo una compensación predeterminada que invoca las compensaciones de las transacciones anidadas contenidas en la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="21fd9-103">If you do not add your own compensation, the runtime engine performs a default compensation that invokes the compensations of any nested transactions within the current transaction.</span></span> <span data-ttu-id="21fd9-104">En primer lugar, invoca la compensación de la transacción completada más recientemente y va retrocediendo hasta que se han compensado todas las transacciones anidadas.</span><span class="sxs-lookup"><span data-stu-id="21fd9-104">It first invokes the compensation of the most recently completed transaction, and works backward until all nested transactions have been compensated.</span></span>  
  
 <span data-ttu-id="21fd9-105">Esto es cierto incluso cuando la compensación tenga lugar dentro de una forma bucle: las compensaciones se ejecutarán en orden inverso.</span><span class="sxs-lookup"><span data-stu-id="21fd9-105">This holds true even when your compensation takes place inside a Loop shape: the compensations will be run in reverse order.</span></span> <span data-ttu-id="21fd9-106">En primer lugar, se invocará la compensación de la última iteración del bucle, luego la de la iteración anterior, y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="21fd9-106">First, the compensation for the last iteration of the loop will be invoked, then the compensation for the previous iteration, and so on.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="21fd9-107">Dado que los datos persisten en la memoria física para que la compensación funcione, el uso de compensaciones dentro de un bucle puede afectar al rendimiento, lo que podría convertirse en un problema si el número de iteraciones es elevado.</span><span class="sxs-lookup"><span data-stu-id="21fd9-107">Because data is persisted to physical memory for compensation to work, using compensations inside a loop might affect performance, which might be an issue given a large number of iterations.</span></span>  
  
 <span data-ttu-id="21fd9-108">Si el orden predeterminado no se ajusta a los requisitos, puede escribir su propio controlador de compensación para llamar explícitamente a los controladores de compensación de los ámbitos anidados en el orden que desee especificar.</span><span class="sxs-lookup"><span data-stu-id="21fd9-108">If the default ordering does not fit your requirements, you can write your own compensation handler to explicitly call the compensation handlers of the nested scopes in the order you specify.</span></span>  
  
### <a name="to-add-a-compensation-block"></a><span data-ttu-id="21fd9-109">Para agregar un bloque de compensación</span><span class="sxs-lookup"><span data-stu-id="21fd9-109">To add a Compensation Block</span></span>  
  
1.  <span data-ttu-id="21fd9-110">Haga clic en el **ámbito** forma para la transacción a la que desea agregar un **bloque de compensación**y, a continuación, haga clic en **nuevo bloque de compensación**.</span><span class="sxs-lookup"><span data-stu-id="21fd9-110">Right-click the **Scope** shape for the transaction to which you want to add a **Compensation Block**, and then click **New Compensation Block**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="21fd9-111">Para agregar una **bloque de compensación** a una **ámbito** forma, el **tipo de transacción** propiedad de la **ámbito** forma debe establecerse en **Atómica** o **de larga ejecución**.</span><span class="sxs-lookup"><span data-stu-id="21fd9-111">To add a **Compensation Block** to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **Atomic** or **Long Running**.</span></span>  
  
     <span data-ttu-id="21fd9-112">A **bloque de compensación** se agrega a la orquestación inmediatamente después asociado **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="21fd9-112">A **Compensation Block** is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="21fd9-113">Dentro de la **bloque de compensación** forma, agregue formas a fin de crear el proceso para deshacer una transacción confirmada.</span><span class="sxs-lookup"><span data-stu-id="21fd9-113">Inside the **Compensation Block** shape, add shapes to create the process for undoing a committed transaction.</span></span>