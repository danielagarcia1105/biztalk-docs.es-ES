---
title: Persistencia en orquestaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, persistence
- persistence
- BizTalk Server Orchestration Engine
ms.assetid: 2f79d294-f7df-4d84-ba76-50618506b6c6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af73db551ced1206ac316f0ba15b8c90a7d5053f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="persistence-in-orchestrations"></a><span data-ttu-id="07e91-102">Persistencia en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="07e91-102">Persistence in Orchestrations</span></span>
<span data-ttu-id="07e91-103">El motor de orquestaciones guarda toda la información de estado de una instancia de orquestación en varios puntos de persistencia para permitir la rehidratación de la instancia de orquestación.</span><span class="sxs-lookup"><span data-stu-id="07e91-103">The orchestration engine saves the entire state of an orchestration instance at various persistence points to allow rehydration of the orchestration instance.</span></span> <span data-ttu-id="07e91-104">El estado incluye los componentes basados en .NET que se pueden usar en la orquestación, así como los mensajes y variables.</span><span class="sxs-lookup"><span data-stu-id="07e91-104">The state includes any .NET-based components that may be used in the orchestration, in addition to messages and variables.</span></span> <span data-ttu-id="07e91-105">El motor almacena la información de estado en los siguientes puntos de persistencia:</span><span class="sxs-lookup"><span data-stu-id="07e91-105">The engine stores state at the following persistence points:</span></span>  
  
-   <span data-ttu-id="07e91-106">Final de un ámbito transaccional (atómico o de larga ejecución).</span><span class="sxs-lookup"><span data-stu-id="07e91-106">End of a transactional scope (atomic or long running)</span></span>  
  
-   <span data-ttu-id="07e91-107">En los puntos de interrupción de depuración.</span><span class="sxs-lookup"><span data-stu-id="07e91-107">At debugging breakpoints</span></span>  
  
-   <span data-ttu-id="07e91-108">En la ejecución de otras orquestaciones a través de la forma Iniciar orquestación.</span><span class="sxs-lookup"><span data-stu-id="07e91-108">At the execution of other orchestrations through the Start Orchestration shape</span></span>  
  
-   <span data-ttu-id="07e91-109">En la forma Envío (excepto en una transacción atómica).</span><span class="sxs-lookup"><span data-stu-id="07e91-109">At the Send shape (except in an atomic transaction)</span></span>  
  
-   <span data-ttu-id="07e91-110">Cuando una instancia de orquestación se suspende.</span><span class="sxs-lookup"><span data-stu-id="07e91-110">When an Orchestration Instance is suspended</span></span>  
  
-   <span data-ttu-id="07e91-111">Cuando se apaga el sistema de forma controlada.</span><span class="sxs-lookup"><span data-stu-id="07e91-111">When the system shutdowns in a controlled manner</span></span>  
  
-   <span data-ttu-id="07e91-112">Cuando el motor determina que quiere deshidratar.</span><span class="sxs-lookup"><span data-stu-id="07e91-112">When the engine determines it wants to dehydrate</span></span>  
  
-   <span data-ttu-id="07e91-113">Cuando una instancia de orquestación ha finalizado.</span><span class="sxs-lookup"><span data-stu-id="07e91-113">When an orchestration instance is finished</span></span>  
  
 <span data-ttu-id="07e91-114">El motor optimiza el número de puntos de persistencia dado que son caros, en especial cuando se trata de mensajes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="07e91-114">The engine optimizes the number of persistence points as they are expensive, especially when dealing with large message sizes.</span></span> <span data-ttu-id="07e91-115">Como se muestra en las dos instancias de orquestación a continuación, en la orquestación con las formas Envío en un ámbito atómico, el motor determina un único punto de persistencia entre el final del ámbito transaccional y el final de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="07e91-115">As shown in the two orchestration instances below, in the orchestration with the Send Shapes in an atomic scope, the engine determines a single persistence point between the end of the transaction scope and the end of the orchestration.</span></span> <span data-ttu-id="07e91-116">En la otra orquestación, habrá dos puntos de persistencia, uno para la primera forma Envío y el segundo para la forma Envío más el final de la orquestación.</span><span class="sxs-lookup"><span data-stu-id="07e91-116">In the other orchestration, there will be two persistence points, one for the first Send shape and the second for the Send shape plus end of the orchestration.</span></span>  
  
 <span data-ttu-id="07e91-117">**Persistencia de orquestación**</span><span class="sxs-lookup"><span data-stu-id="07e91-117">**Orchestration persistence**</span></span>  
  
 <span data-ttu-id="07e91-118">![Persistencia de orquestación](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")</span><span class="sxs-lookup"><span data-stu-id="07e91-118">![Orchestration persistence](../core/media/bts-trans-orch-fig2.gif "BTS_Trans_Orch_Fig2")</span></span>  
  
 <span data-ttu-id="07e91-119">Los objetos basados en .NET que use en las orquestaciones, sea de forma directa o indirecta, deben estar marcados como serializables a menos que se invoquen en ámbitos atómicos o si los objetos no tienen información de estado y se invocan únicamente a través de métodos estáticos.</span><span class="sxs-lookup"><span data-stu-id="07e91-119">Any .NET-based objects you use in orchestrations, either directly or indirectly, must be marked as serializable unless they are invoked in atomic scopes, or if the objects are stateless and are invoked only through static methods.</span></span> <span data-ttu-id="07e91-120">**System.Xml.XmlDocument** es un caso especial y no deben marcarse como serializables, independientemente de la propiedad de transacción para un ámbito.</span><span class="sxs-lookup"><span data-stu-id="07e91-120">**System.Xml.XmlDocument** is a special case and does not need to be marked as serializable regardless of the transaction property for a scope.</span></span>  
  
 <span data-ttu-id="07e91-121">¿Cómo el control especial **System.Xml.XmlDocument** de trabajo:</span><span class="sxs-lookup"><span data-stu-id="07e91-121">How does the special handling for **System.Xml.XmlDocument** work:</span></span>  
  
 <span data-ttu-id="07e91-122">Cuando el usuario define una variable **X** de tipo **T**, donde **T** es **System.Xml.XmlDocument** o una clase derivada de  **System.Xml.XmlDocument** , a continuación, el compilador tratará **X** como un objeto serializable.</span><span class="sxs-lookup"><span data-stu-id="07e91-122">When the user defines a variable **X** of type **T**, where **T** is **System.Xml.XmlDocument** or a class derived from **System.Xml.XmlDocument** then the compiler will treat **X** as a serializable object.</span></span>  
  
 <span data-ttu-id="07e91-123">Al serializar **X**, el tiempo de ejecución mantendrá la siguiente información: (a) el tipo real **Tr** del objeto **X** hace referencia a (b) el  **OuterXml** cadena del documento.</span><span class="sxs-lookup"><span data-stu-id="07e91-123">When serializing **X**, the runtime will keep the following pieces of information: (a) the actual type **Tr** of the object **X** is referring to (b) the **OuterXml** string of the document.</span></span>  
  
 <span data-ttu-id="07e91-124">Al deserializar **X**, el tiempo de ejecución creará una instancia de **Tr** (Esto supone un constructor que no tome ningún parámetro) y llamará a **LoadXml** proporcionando el instancia con el guardado **OuterXml.  X** , a continuación, se establecerá para que apunte a la instancia recién creada de **Tr**.</span><span class="sxs-lookup"><span data-stu-id="07e91-124">When de-serializing **X**, the runtime will create an instance of **Tr** (this assumes a constructor that does not take any parameters) and will call **LoadXml** providing the instance with the saved **OuterXml.  X** will then be set to point to the newly created instance of **Tr**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07e91-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="07e91-125">See Also</span></span>  
 [<span data-ttu-id="07e91-126">Transacciones</span><span class="sxs-lookup"><span data-stu-id="07e91-126">Transactions</span></span>](../core/transactions.md)