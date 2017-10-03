---
title: "Ámbitos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scopes, exception handling
- Scope shape [Orchestration Designer], nesting
- scopes, variables
- scopes, Scope shape [Orchestration Designer]
- Scope shape [Orchestration Designer], exception handling
- scopes, transactions
- scopes, synchronization
- scopes, nesting
- Scope shape [Orchestration Designer], transactions
ms.assetid: 51d81ce4-0034-4415-b6ab-4c952737c1bd
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2bc4d1b5d926540477293591ade8123126be1b84
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="scopes"></a><span data-ttu-id="30691-102">Ámbitos</span><span class="sxs-lookup"><span data-stu-id="30691-102">Scopes</span></span>
<span data-ttu-id="30691-103">Un ámbito es un marco de trabajo para agrupar acciones.</span><span class="sxs-lookup"><span data-stu-id="30691-103">A scope is a framework for grouping actions.</span></span> <span data-ttu-id="30691-104">Se utiliza principalmente para la ejecución de transacciones y el control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="30691-104">It is primarily used for transactional execution and exception handling.</span></span>  
  
 <span data-ttu-id="30691-105">Un ámbito contiene uno o más bloques.</span><span class="sxs-lookup"><span data-stu-id="30691-105">A scope contains one or more blocks.</span></span> <span data-ttu-id="30691-106">Tiene un cuerpo y, de forma opcional, puede tener anexado cualquier número de bloques de control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="30691-106">It has a body and can optionally have appended to it any number of exception-handling blocks.</span></span> <span data-ttu-id="30691-107">También puede incluir un bloque de compensación opcional, según sea la naturaleza del ámbito.</span><span class="sxs-lookup"><span data-stu-id="30691-107">It may have an optional compensation block as well, depending on the nature of the scope.</span></span> <span data-ttu-id="30691-108">Algunos ámbitos estarán destinados únicamente al control de excepciones y no necesitarán compensación.</span><span class="sxs-lookup"><span data-stu-id="30691-108">Some scopes will be purely for exception handling, and will not require compensation.</span></span> <span data-ttu-id="30691-109">Sin embargo, otros serán explícitamente transaccionales y siempre contarán con un controlador de compensación predeterminado junto con uno opcional que cree para ellos.</span><span class="sxs-lookup"><span data-stu-id="30691-109">Other scopes will be explicitly transactional, and will always have a default compensation handler, along with an optional compensation handler that you create for it.</span></span> <span data-ttu-id="30691-110">Un ámbito transaccional también incluirá un controlador de excepción predeterminado y un número indefinido de controladores de excepción adicionales que cree para él.</span><span class="sxs-lookup"><span data-stu-id="30691-110">A transactional scope will also have a default exception handler and any number of additional exception handlers that you create for it.</span></span>  
  
## <a name="synchronized-scopes"></a><span data-ttu-id="30691-111">Ámbitos sincronizados</span><span class="sxs-lookup"><span data-stu-id="30691-111">Synchronized scopes</span></span>  
 <span data-ttu-id="30691-112">Puede especificar que los ámbitos estén sincronizados o no.</span><span class="sxs-lookup"><span data-stu-id="30691-112">You can specify that scopes are synchronized or not synchronized.</span></span> <span data-ttu-id="30691-113">Al sincronizar un ámbito, se asegura de que una o varias acciones paralelas de la orquestación no escriban los datos compartidos a los que se tenga acceso dentro del ámbito, ni tampoco mientras otra acción los lee.</span><span class="sxs-lookup"><span data-stu-id="30691-113">By synchronizing a scope, you ensure that any shared data that is accessed within it will not be written to by one or more parallel actions in your orchestration, nor will it be written to while another action is reading it.</span></span>  
  
 <span data-ttu-id="30691-114">Los ámbitos de transacciones atómicas siempre están sincronizados.</span><span class="sxs-lookup"><span data-stu-id="30691-114">Atomic transaction scopes are always synchronized.</span></span> <span data-ttu-id="30691-115">Todas las acciones dentro de un ámbito sincronizado se consideran sincronizadas, así como todas las acciones incluidas en cualquiera de sus controladores de excepción.</span><span class="sxs-lookup"><span data-stu-id="30691-115">All actions within a synchronized scope are considered synchronized, as are all actions in any of its exception handlers.</span></span> <span data-ttu-id="30691-116">Las acciones del controlador de compensación de un ámbito transaccional no están sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="30691-116">Actions in the compensation handler for a transactional scope are not synchronized.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="30691-117">Tenga en cuenta que, si no diseña los procesos con cuidado, todavía puede encontrarse con una condición de interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="30691-117">Note that you can still run into a deadlock condition if you do not design your processes carefully.</span></span> <span data-ttu-id="30691-118">Por ejemplo, dos ramas de una paralela en la orquestación A tienen acceso al mismo mensaje, una para enviarlo y otra para recibirlo, por lo que ambas deben tener un ámbito sincronizado.</span><span class="sxs-lookup"><span data-stu-id="30691-118">For example: two branches of a parallel in orchestration A access the same message, one to send it and one to receive it, so both must have a synchronized scope.</span></span> <span data-ttu-id="30691-119">Una segunda orquestación recibe el mensaje y lo vuelve a enviar.</span><span class="sxs-lookup"><span data-stu-id="30691-119">A second orchestration receives the message and sends it back.</span></span> <span data-ttu-id="30691-120">Es posible que la rama de envío de la orquestación A reciba sus bloqueos antes que la rama de recepción, y terminará encontrándose con un interbloqueo.</span><span class="sxs-lookup"><span data-stu-id="30691-120">It is possible that the sending branch in orchestration A will receive its locks before the receiving branch, and you will end up with a deadlock.</span></span>  
  
## <a name="nesting-of-scopes"></a><span data-ttu-id="30691-121">Anidación de ámbitos</span><span class="sxs-lookup"><span data-stu-id="30691-121">Nesting of scopes</span></span>  
 <span data-ttu-id="30691-122">Puede anidar **ámbito** formas dentro de otras **ámbito** formas.</span><span class="sxs-lookup"><span data-stu-id="30691-122">You can nest **Scope** shapes inside other **Scope** shapes.</span></span> <span data-ttu-id="30691-123">Las reglas para anidar ámbitos son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="30691-123">The rules for nesting scopes are as follows:</span></span>  
  
-   <span data-ttu-id="30691-124">Los ámbitos transaccionales o sincronizados no pueden anidarse en ámbitos sincronizados, incluidos los controladores de excepción de ámbitos sincronizados.</span><span class="sxs-lookup"><span data-stu-id="30691-124">Transactional and/or synchronized scopes cannot be nested inside synchronized scopes, including the exception handlers of synchronized scopes.</span></span>  
  
-   <span data-ttu-id="30691-125">Los ámbitos de transacciones atómicas no pueden tener otros ámbitos transaccionales anidados en ellos.</span><span class="sxs-lookup"><span data-stu-id="30691-125">Atomic transaction scopes cannot have any other transactional scopes nested inside them.</span></span>  
  
-   <span data-ttu-id="30691-126">Los ámbitos transaccionales no pueden anidarse en ámbitos no transaccionales ni en orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="30691-126">Transactional scopes cannot be nested inside nontransactional scopes or orchestrations.</span></span>  
  
-   <span data-ttu-id="30691-127">Puede anidar ámbitos con una profundidad máxima de 21 niveles.</span><span class="sxs-lookup"><span data-stu-id="30691-127">You can nest scopes up to 21 levels deep.</span></span>  
  
-   <span data-ttu-id="30691-128">**Orquestación de llamada** formas pueden incluirse dentro de los ámbitos, pero las orquestaciones llamadas se tratan igual que cualquier otra transacción anidada y se aplican las mismas reglas.</span><span class="sxs-lookup"><span data-stu-id="30691-128">**Call Orchestration** shapes can be included inside scopes, but the called orchestrations are treated the same as any other nested transaction, and the same rules apply.</span></span>  
  
-   <span data-ttu-id="30691-129">**Iniciar orquestación** formas pueden incluirse dentro de los ámbitos.</span><span class="sxs-lookup"><span data-stu-id="30691-129">**Start Orchestration** shapes can be included inside scopes.</span></span> <span data-ttu-id="30691-130">Las limitaciones de anidación no se aplican a las orquestaciones iniciadas.</span><span class="sxs-lookup"><span data-stu-id="30691-130">Nesting limitations do not apply to started orchestrations.</span></span>  
  
## <a name="scope-variables"></a><span data-ttu-id="30691-131">Variables de ámbito</span><span class="sxs-lookup"><span data-stu-id="30691-131">Scope variables</span></span>  
 <span data-ttu-id="30691-132">Puede declarar variables como mensajes y conjuntos de correlaciones en el nivel de ámbito.</span><span class="sxs-lookup"><span data-stu-id="30691-132">You can declare variables such as messages and correlation sets at the scope level.</span></span> <span data-ttu-id="30691-133">Sin embargo, no puede utilizar el mismo nombre para una variable de ámbito y para una variable de orquestación; la ocultación de nombres no está permitida.</span><span class="sxs-lookup"><span data-stu-id="30691-133">You cannot use the same name for a scope variable as for an orchestration variable, however; name hiding is not allowed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30691-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="30691-134">See Also</span></span>  
 <span data-ttu-id="30691-135">[Uso de transacciones y control de excepciones](../core/using-transactions-and-handling-exceptions.md) </span><span class="sxs-lookup"><span data-stu-id="30691-135">[Using Transactions and Handling Exceptions](../core/using-transactions-and-handling-exceptions.md) </span></span>  
 [<span data-ttu-id="30691-136">Transacciones atómicas</span><span class="sxs-lookup"><span data-stu-id="30691-136">Atomic Transactions</span></span>](../core/atomic-transactions.md)