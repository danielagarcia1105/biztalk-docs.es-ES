---
title: "Cómo se controlan las excepciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, handlers
- scopes, errors
- errors, scopes
- handlers [adapters], errors
ms.assetid: 30b88d8a-8737-4700-b856-1b49fdf6b6d0
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 004e4f29bcfc292edb33bae816a52b588a89771c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-exceptions-are-handled"></a><span data-ttu-id="991af-102">Cómo se controlan las excepciones</span><span class="sxs-lookup"><span data-stu-id="991af-102">How Exceptions Are Handled</span></span>
<span data-ttu-id="991af-103">Cuando se produce una excepción dentro de un ámbito, cada subproceso lógico de ejecución de éste se detiene.</span><span class="sxs-lookup"><span data-stu-id="991af-103">When an exception occurs within a scope, each logical thread of execution in the scope is stopped.</span></span> <span data-ttu-id="991af-104">El motor de tiempo de ejecución intenta encontrar un controlador de excepción para la correspondiente excepción.</span><span class="sxs-lookup"><span data-stu-id="991af-104">The runtime engine tries to find an exception handler for the appropriate exception.</span></span>  
  
 <span data-ttu-id="991af-105">Si se encuentra uno que coincida con el tipo específico o uno con sus tipos base, el control se transfiere a ese controlador y se ejecuta su código.</span><span class="sxs-lookup"><span data-stu-id="991af-105">If the exception handler is found that matches the specific type or one of its base types, control passes to that handler and its code runs.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="991af-106">El tipo de excepción debe derivarse de **System.Exception**.</span><span class="sxs-lookup"><span data-stu-id="991af-106">The exception type must be derived from **System.Exception**.</span></span>  
  
 <span data-ttu-id="991af-107">Los controladores de excepción son secuenciales; esto significa que se comprobarán en cada excepción concreta para ver si pueden controlarla.</span><span class="sxs-lookup"><span data-stu-id="991af-107">Exception handlers are sequential; that is, they will be checked in order to see if they can handle a particular exception.</span></span> <span data-ttu-id="991af-108">Para que funcionen correctamente, los controladores de excepción deben colocarse de modo que aquellos que controlen más tipos específicos aparezcan en primer lugar seguidos de los que controlan tipos más generales.</span><span class="sxs-lookup"><span data-stu-id="991af-108">To work properly, exception handlers must be placed so that those handling more specific types come first, followed by those handling more general types.</span></span> <span data-ttu-id="991af-109">De este modo, se asegura que una excepción de un tipo específico recibe el control por parte del controlador adecuado y no de uno diseñado para controlar un tipo base.</span><span class="sxs-lookup"><span data-stu-id="991af-109">This is so that you can ensure that an exception of a specific type is handled by the appropriate handler, rather than one designed to handle a base type.</span></span>  
  
 <span data-ttu-id="991af-110">Si el controlador de excepción se completa con normalidad, el control se transfiere al ámbito circundante.</span><span class="sxs-lookup"><span data-stu-id="991af-110">If the exception handler completes normally, control passes to the surrounding scope.</span></span> <span data-ttu-id="991af-111">Si no se ha producido una excepción en el ámbito circundante, la orquestación continúa su ejecución.</span><span class="sxs-lookup"><span data-stu-id="991af-111">If no exception has been thrown in the surrounding scope, the orchestration continues to run.</span></span> <span data-ttu-id="991af-112">Si el controlador de excepción finaliza con una instrucción de inicio, se vuelve a iniciar la excepción original para el ámbito circundante para actuar sobre ella, a menos que especifique una excepción diferente que desea que se inicie.</span><span class="sxs-lookup"><span data-stu-id="991af-112">If the exception handler ends with a throw statement, the original exception is thrown again for the surrounding scope to act upon, unless you specify a different exception that you want to be thrown.</span></span>  
  
 <span data-ttu-id="991af-113">Si no se consigue localizar ningún controlador de excepción, se ejecutará el controlador de excepción predeterminado.</span><span class="sxs-lookup"><span data-stu-id="991af-113">If no exception handler can be located, the default exception handler will run.</span></span> <span data-ttu-id="991af-114">El controlador de excepción predeterminado de un ámbito llamará a las compensaciones de las transacciones anidadas y, a continuación, volverá a iniciar la excepción.</span><span class="sxs-lookup"><span data-stu-id="991af-114">The default exception handler for a scope will call the compensations for any nested transactions, and then throw the exception again.</span></span> <span data-ttu-id="991af-115">Si escribe su propio controlador de excepción, puede decidir que la excepción no se propague.</span><span class="sxs-lookup"><span data-stu-id="991af-115">If you write your own exception handler, you can choose not to propagate the exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991af-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="991af-116">See Also</span></span>  
 [<span data-ttu-id="991af-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="991af-117">Exceptions</span></span>](../core/exceptions.md)