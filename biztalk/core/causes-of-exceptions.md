---
title: Causas de excepciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, errors
- errors, orchestrations
- errors, causes
ms.assetid: b0422382-d034-4c58-87c6-fc269dbbfe43
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9006234d71751078269e5a88559839fdadd91e91
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="causes-of-exceptions"></a><span data-ttu-id="2e661-102">Causas de excepciones</span><span class="sxs-lookup"><span data-stu-id="2e661-102">Causes of Exceptions</span></span>
<span data-ttu-id="2e661-103">Las excepciones se pueden generar en una orquestación de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="2e661-103">Exceptions can be generated within an orchestration in the following ways:</span></span>  
  
-   <span data-ttu-id="2e661-104">Por un **Iniciar excepción** forma, que produce una excepción inmediatamente y de forma incondicional.</span><span class="sxs-lookup"><span data-stu-id="2e661-104">By a **Throw Exception** shape, which throws an exception immediately and unconditionally.</span></span> <span data-ttu-id="2e661-105">El control se transfiere desde el **Iniciar excepción** forma directamente al controlador de excepciones adecuado.</span><span class="sxs-lookup"><span data-stu-id="2e661-105">Control passes from the **Throw Exception** shape directly to the appropriate exception handler.</span></span>  
  
-   <span data-ttu-id="2e661-106">Superación del tiempo de espera en una transacción que se ejecute durante mucho tiempo.</span><span class="sxs-lookup"><span data-stu-id="2e661-106">By a time-out expiring in a long-running transaction.</span></span> <span data-ttu-id="2e661-107">Una excepción predefinida del sistema:**Microsoft.XLANG.BaseTypes.TimeOutException**: se produce en este caso.</span><span class="sxs-lookup"><span data-stu-id="2e661-107">A predefined system exception—**Microsoft.XLANG.BaseTypes.TimeOutException**—is thrown in this case.</span></span>  
  
-   <span data-ttu-id="2e661-108">Otros errores de transacción.</span><span class="sxs-lookup"><span data-stu-id="2e661-108">By some other transaction failure.</span></span> <span data-ttu-id="2e661-109">El motor de tiempo de ejecución inicia un mensaje definido por el sistema, por ejemplo, Microsoft.XLANG.BaseTypes.PersistenceException, para estos errores.</span><span class="sxs-lookup"><span data-stu-id="2e661-109">The runtime engine throws a system-defined message such as Microsoft.XLANG.BaseTypes.PersistenceException for these failures.</span></span>  
  
-   <span data-ttu-id="2e661-110">Excepción de código de usuario.</span><span class="sxs-lookup"><span data-stu-id="2e661-110">By a user code exception.</span></span> <span data-ttu-id="2e661-111">Cuando se realizan llamadas a un código de usuario externo en una orquestación, las clases de Common language runtime a las que se llama pueden iniciar excepciones.</span><span class="sxs-lookup"><span data-stu-id="2e661-111">When calls to external user code are made within an orchestration, common language runtime classes that are called can throw exceptions.</span></span> <span data-ttu-id="2e661-112">Si estas excepciones no se controlan en el código de usuario, terminan propagándose en el ámbito en que se realiza la llamada al código de usuario.</span><span class="sxs-lookup"><span data-stu-id="2e661-112">If these exceptions are not handled in the user code, they eventually propagate up into the scope in which the call to the user code is made.</span></span>  
  
-   <span data-ttu-id="2e661-113">Otras excepciones del sistema (un error de persistencia, una excepción .NET o del sistema, como una excepción de cargador de tipo, o un error de conversión de datos).</span><span class="sxs-lookup"><span data-stu-id="2e661-113">By some other system exception (for example, a persistence failure, another .NET or system exception such as type loader exception, or a data conversion error).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2e661-114">Cuando se produce una excepción de cargador de tipo, no se puede detectar la excepción en el **excepción de filtrado** bloquear en el mismo **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="2e661-114">When a type loader exception is thrown, the exception may not be caught in the **Catch Exception** block in the same **Scope** shape.</span></span> <span data-ttu-id="2e661-115">Esto se debe a que la excepción es del cargador de tipo, no del proceso de orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2e661-115">This is because of that the exception is from the type loader, not from the BizTalk orchestration process.</span></span> <span data-ttu-id="2e661-116">Por tanto, no sigue las reglas de control de flujo de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="2e661-116">Therefore, it does not follow the BizTalk rules of control flow.</span></span>  
  
-   <span data-ttu-id="2e661-117">Rama hermana del ámbito circundante que detiene la ejecución.</span><span class="sxs-lookup"><span data-stu-id="2e661-117">By a sibling branch in a surrounding scope halting execution.</span></span> <span data-ttu-id="2e661-118">En este caso, se inicia la excepción Microsoft.XLANG.BaseTypes.ForcedTerminationException para cada rama, en cuyo caso puede que desee agregar un controlador de excepciones a cada una de ellas.</span><span class="sxs-lookup"><span data-stu-id="2e661-118">Microsoft.XLANG.BaseTypes.ForcedTerminationException is thrown to each branch in this case, and you might want to add an exception handler to each.</span></span> <span data-ttu-id="2e661-119">Un controlador de excepciones de este tipo no puede volver a iniciar la excepción ni debe intentar iniciar ningún otro tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="2e661-119">Such an exception handler cannot re-throw its exception, nor should it attempt to throw any other type of exception.</span></span>  
  
-   <span data-ttu-id="2e661-120">Recepción de un mensaje externo que indica un error.</span><span class="sxs-lookup"><span data-stu-id="2e661-120">By receipt of an external message that indicates a fault.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e661-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e661-121">See Also</span></span>  
 <span data-ttu-id="2e661-122">[Mensajes de error](../core/fault-messages.md) </span><span class="sxs-lookup"><span data-stu-id="2e661-122">[Fault Messages](../core/fault-messages.md) </span></span>  
 [<span data-ttu-id="2e661-123">Excepciones</span><span class="sxs-lookup"><span data-stu-id="2e661-123">Exceptions</span></span>](../core/exceptions.md)