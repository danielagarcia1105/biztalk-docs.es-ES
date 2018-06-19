---
title: Uso de transacciones y controlar las excepciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- transactions, orchestrations
- orchestrations, transactions
- orchestrations, errors
- transactions
- errors, orchestrations
- transactions, BizTalk Server Orchestration Engine
- errors, Scope shape [Orchestration Designer]
- Scope shape [Orchestration Designer], errors
- Scope shape [Orchestration Designer], transactions
ms.assetid: bb38f5eb-6641-4e7c-8e2a-c474fc739999
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab32729aa6b4f12aada623587f52728c6bd23240
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22288436"
---
# <a name="using-transactions-and-handling-exceptions"></a><span data-ttu-id="e8858-102">Uso de transacciones y control de excepciones</span><span class="sxs-lookup"><span data-stu-id="e8858-102">Using Transactions and Handling Exceptions</span></span>
<span data-ttu-id="e8858-103">Cuando designe una orquestación, debe considerar detenidamente dónde pueden producirse problemas y cuál es la mejor forma de procesarlos.</span><span class="sxs-lookup"><span data-stu-id="e8858-103">When you design an orchestration, you should consider carefully where problems might occur and how best to deal with them.</span></span> <span data-ttu-id="e8858-104">Numerosas orquestaciones tienen varios puntos posibles de error.</span><span class="sxs-lookup"><span data-stu-id="e8858-104">Many orchestrations have several potential points of failure.</span></span> <span data-ttu-id="e8858-105">Los problemas pueden surgir por cualquier motivo; por ejemplo, puede que se desconecte el servidor o que el mensaje se formatee de forma incorrecta.</span><span class="sxs-lookup"><span data-stu-id="e8858-105">Problems can arise for any number of other reasons; for example, a server might go down or a message might be badly formatted.</span></span>  
  
 <span data-ttu-id="e8858-106">Es muy importante para una orquestación compleja o de larga ejecución realizar el seguimiento de su estado e informar de los errores en el momento en que se produzcan, para que los problemas se puedan solucionar con mayor precisión y un esfuerzo mínimo.</span><span class="sxs-lookup"><span data-stu-id="e8858-106">It is especially important for a long-running or complex orchestration to keep track of its state and to report errors as they occur, so that you can resolve problems accurately and with a minimum of effort.</span></span> <span data-ttu-id="e8858-107">Es de igual importancia para una orquestación mantener la integridad de un conjunto de acciones muy relacionadas, de modo que si parte de la transacción tiene lugar pero otra no, toda la transacción se puede deshacer como si nunca hubiese sucedido.</span><span class="sxs-lookup"><span data-stu-id="e8858-107">It is equally important for an orchestration to maintain the integrity of a set of closely related actions, so that if part of a transaction takes place but another does not, the entire transaction can be rolled back as though it never occurred.</span></span>  
  
 <span data-ttu-id="e8858-108">La orquestación de BizTalk permite garantizar la atomicidad del trabajo, es decir, la integridad de acciones relacionadas, incluso cuando los sistemas externos participan en transacciones.</span><span class="sxs-lookup"><span data-stu-id="e8858-108">BizTalk Orchestration enables you to guarantee the atomicity of work, that is, the integrity of related actions, even when external systems are participating in transactions.</span></span> <span data-ttu-id="e8858-109">Proporcionan herramientas para controlar los errores, mantener el estado de una orquestación y solucionar problemas cuando se producen a través de transacciones, compensación y control de excepciones.</span><span class="sxs-lookup"><span data-stu-id="e8858-109">It gives you tools to handle errors, to maintain the state of an orchestration, and to fix problems as they occur through transactions, compensation, and exception handling.</span></span>  
  
 <span data-ttu-id="e8858-110">Un marco de trabajo para las transacciones y control de excepciones, el Diseñador de orquestaciones proporciona la **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="e8858-110">As a framework for transactions and exception handling, Orchestration Designer provides the **Scope** shape.</span></span> <span data-ttu-id="e8858-111">Un ámbito puede tener un tipo de transacción, una compensación y cualquier número de controladores de excepción.</span><span class="sxs-lookup"><span data-stu-id="e8858-111">A scope can have a transaction type, a compensation, and any number of exception handlers.</span></span>  
  
 <span data-ttu-id="e8858-112">Los pasos para configurar una transacción y el control de excepciones son:</span><span class="sxs-lookup"><span data-stu-id="e8858-112">The steps for setting up a transaction and exception handling are:</span></span>  
  
-   <span data-ttu-id="e8858-113">Crear un ámbito.</span><span class="sxs-lookup"><span data-stu-id="e8858-113">Create a scope.</span></span>  
  
-   <span data-ttu-id="e8858-114">Identificar el tipo de transacción necesario.</span><span class="sxs-lookup"><span data-stu-id="e8858-114">Identify the kind of transaction you need.</span></span>  
  
-   <span data-ttu-id="e8858-115">Determinar lo que será necesario compensar.</span><span class="sxs-lookup"><span data-stu-id="e8858-115">Determine what will need to be compensated.</span></span>  
  
-   <span data-ttu-id="e8858-116">Identificar posibles errores.</span><span class="sxs-lookup"><span data-stu-id="e8858-116">Identify potential errors.</span></span>  
  
-   <span data-ttu-id="e8858-117">Agregar controladores de excepción y el código de compensación adecuados.</span><span class="sxs-lookup"><span data-stu-id="e8858-117">Add appropriate exception handlers and compensation code.</span></span>  
  
## <a name="examples-of-using-transactions-exception-handlings-and-compensations"></a><span data-ttu-id="e8858-118">Ejemplos de uso de transacciones, controladores de excepciones y compensaciones</span><span class="sxs-lookup"><span data-stu-id="e8858-118">Examples of Using Transactions, Exception Handlings, and Compensations</span></span>  
  
-   [<span data-ttu-id="e8858-119">Error de control (carpeta de ejemplos de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="e8858-119">Error Handling (BizTalk Server Samples Folder)</span></span>](../core/error-handling-biztalk-server-samples-folder.md)  
  
-   [<span data-ttu-id="e8858-120">Compensación (ejemplo de BizTalk Server)</span><span class="sxs-lookup"><span data-stu-id="e8858-120">Compensation (BizTalk Server Sample)</span></span>](../core/compensation-biztalk-server-sample.md)  
  
-   <span data-ttu-id="e8858-121">Descargue el ejemplo SDK "Atomic Transactions con COM + realizando tareas de mantenimiento componentes in Orchestrations" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="e8858-121">Download the SDK sample "Atomic Transactions with COM+ Serviced Components in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="e8858-122">Descargue el ejemplo SDK "Utilizando el SQL adaptador con Atomic Transactions in Orchestrations" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="e8858-122">Download the SDK sample "Using the SQL Adapter with Atomic Transactions in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="e8858-123">Descargue el ejemplo SDK "Using Long-Running Transactions in Orchestrations" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="e8858-123">Download the SDK sample "Using Long-Running Transactions in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
-   <span data-ttu-id="e8858-124">Descargue el ejemplo SDK "Exception Handling in Orchestrations" de [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="e8858-124">Download the SDK sample "Exception Handling in Orchestrations" from [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e8858-125">En esta sección</span><span class="sxs-lookup"><span data-stu-id="e8858-125">In This Section</span></span>  
  
-   [<span data-ttu-id="e8858-126">Ámbitos</span><span class="sxs-lookup"><span data-stu-id="e8858-126">Scopes</span></span>](../core/scopes.md)  
  
-   [<span data-ttu-id="e8858-127">Cómo configurar la forma ámbito</span><span class="sxs-lookup"><span data-stu-id="e8858-127">How to Configure the Scope Shape</span></span>](../core/how-to-configure-the-scope-shape.md)  
  
-   [<span data-ttu-id="e8858-128">Realizar orquestaciones transaccionales</span><span class="sxs-lookup"><span data-stu-id="e8858-128">Making Orchestrations Transactional</span></span>](../core/making-orchestrations-transactional.md)  
  
-   [<span data-ttu-id="e8858-129">Excepciones</span><span class="sxs-lookup"><span data-stu-id="e8858-129">Exceptions</span></span>](../core/exceptions.md)  
  
-   [<span data-ttu-id="e8858-130">Compensación</span><span class="sxs-lookup"><span data-stu-id="e8858-130">Compensation</span></span>](../core/compensation.md)  
  
## <a name="see-also"></a><span data-ttu-id="e8858-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8858-131">See Also</span></span>  
 [<span data-ttu-id="e8858-132">Usar el motor de mensajería de BizTalk</span><span class="sxs-lookup"><span data-stu-id="e8858-132">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)