---
title: "Cómo configurar la forma compensar | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Compensate shape [Orchestration Designer], about Compensate shape
- Compensate shape [Orchestration Designer]
- compensations, Compensate shape [Orchestration Designer]
- configuring [Orchestration Designer], Compensate shape
- Compensate shape [Orchestration Designer], configuring
ms.assetid: 9f06289e-4d11-4864-9851-c210276865a7
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 059ac58d95d33234737033c00c4a6a2a36e256f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-compensate-shape"></a><span data-ttu-id="4d4e2-102">Cómo configurar la forma Compensar</span><span class="sxs-lookup"><span data-stu-id="4d4e2-102">How to Configure the Compensate Shape</span></span>
<span data-ttu-id="4d4e2-103">Si está utilizando transacciones anidadas en la orquestación, puede agregar un **compensar** forma en el bloque de compensación o un bloque de excepción de la transacción.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-103">If you are using nested transactions in your orchestration, you can add a **Compensate** shape in the compensation block or an exception block of a transaction scope.</span></span> <span data-ttu-id="4d4e2-104">Esto permite que la orquestación lleve a cabo explícitamente compensaciones en una transacción anidada.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-104">This enables your orchestration to explicitly perform compensation on a nested transaction.</span></span> <span data-ttu-id="4d4e2-105">Especifica qué transacciones quiere que se compensen en el **compensar** forma como cualquier otro código de compensación de la transacción anidada se ejecutará, siempre que ésta se llevó a cabo correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-105">You specify which transaction you would like to be compensated in the **Compensate** shape, and any compensation code in the nested transaction will be run, provided the transaction committed successfully.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d4e2-106">El **compensación** propiedad hace referencia al identificador único del ámbito de transacción, no hace referencia al nombre del ámbito.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-106">The **Compensation** property refers to the unique identifier of the transaction scope; it does not refer to the name of the scope.</span></span>  
  
 <span data-ttu-id="4d4e2-107">Si desea compensar más de una transacción anidada, agregar otro **compensar** forma por cada transacción.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-107">If you want to compensate more than one nested transaction, you add an additional **Compensate** shape for each transaction.</span></span>  
  
 <span data-ttu-id="4d4e2-108">Ya no **compensar** forma es necesaria si no hay ningún otro código de compensación en una transacción externa; se ejecutará automáticamente el código de compensación de las transacciones anidadas.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-108">No **Compensate** shape is necessary if there is no other compensation code in an outer transaction; the compensation code of any nested transactions will be run automatically.</span></span> <span data-ttu-id="4d4e2-109">El **compensar** forma le proporciona control sobre el proceso de por lo que le permite decidir si desea o no se compensen las transacciones anidadas.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-109">The **Compensate** shape gives you control over the process by allowing you to decide whether or not you want a nested transaction to be compensated.</span></span>  
  
### <a name="to-configure-a-compensate-shape"></a><span data-ttu-id="4d4e2-110">Para configurar una forma Compensar</span><span class="sxs-lookup"><span data-stu-id="4d4e2-110">To configure a Compensate shape</span></span>  
  
-   <span data-ttu-id="4d4e2-111">En la ventana Propiedades, seleccione el bloque de compensación para llamar desde el **compensación** lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-111">In the Properties window, select the compensation block to call from the **Compensation** drop-down list.</span></span>  
  
     <span data-ttu-id="4d4e2-112">La lista desplegable mostrará todas las transacciones que pueden compensarse, lo que incluye la transacción actual y todas las transacciones secundarias inmediatas respecto de la actual.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-112">The drop-down list will display all of the transactions which can be compensated, which includes the current transaction and any immediate child transactions of the current transaction.</span></span> <span data-ttu-id="4d4e2-113">Si no puede ver una transacción que esperaba, podría deberse a la relación de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-113">If you cannot see a transaction that you expect, it might be due to the relationship of the transactions.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4d4e2-114">No es posible compensar la transacción actual desde dentro del cuerpo de la transacción.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-114">You cannot compensate the current transaction from within the body of the transaction.</span></span>  <span data-ttu-id="4d4e2-115">Puede compensarla desde el bloque de compensación o desde un bloque de excepción de la transacción.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-115">You can compensate it from the compensation block or an exception block of the transaction.</span></span>  
  
     <span data-ttu-id="4d4e2-116">Si opta por compensar la transacción actual, se invocará el controlador predeterminado y no un bloque de compensación explícito (si hubiera uno).</span><span class="sxs-lookup"><span data-stu-id="4d4e2-116">If you choose to compensate the current transaction, that means that the default handler will be invoked, and not an explicit compensation block (if there is one).</span></span> <span data-ttu-id="4d4e2-117">Se trata de un mecanismo para compensar automáticamente las transacciones anidadas de forma directa que se han completado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d4e2-117">This is a mechanism for automatically compensating directly nested transactions that have completed successfully.</span></span>