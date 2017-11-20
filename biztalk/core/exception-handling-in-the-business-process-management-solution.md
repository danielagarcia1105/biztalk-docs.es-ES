---
title: "Control de excepciones en la solución de administración de procesos empresariales | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- errors, tutorials
- process management solution tutorial, errors
ms.assetid: ac9fcb33-7dac-448e-88b8-04d4d439ea6a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1cd3134b8ed4e2fc6fd4a50d9b64397692ea32b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="exception-handling-in-the-business-process-management-solution"></a><span data-ttu-id="734d3-102">Control de excepciones en la solución de administración de procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="734d3-102">Exception Handling in the Business Process Management Solution</span></span>
<span data-ttu-id="734d3-103">La solución Administración de procesos empresariales utiliza una orquestación de control de excepciones especial, así como el control de excepciones estándar de BizTalk Server. Además, para los errores de adaptadores, canalizaciones, asignaciones y enrutamiento, usa la nueva característica de informes de errores.</span><span class="sxs-lookup"><span data-stu-id="734d3-103">The business process management solution uses a special exception handling orchestration, as well as the standard BizTalk Server exception handling, and for adapter, pipeline, mapping, and routing failures, the new error reporting feature.</span></span> <span data-ttu-id="734d3-104">Este sistema personalizado se basa en el **ExceptionHandler** orquestación.</span><span class="sxs-lookup"><span data-stu-id="734d3-104">This customized system is built around the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="734d3-105">La solución utiliza la **ExceptionHandler** orquestación para volver a intentar una operación o volver a intentar una llamada que podría realizarse correctamente después de un problema transitorio.</span><span class="sxs-lookup"><span data-stu-id="734d3-105">The solution uses the **ExceptionHandler** orchestration to retry an operation or to retry a call that might succeed after a transient problem.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="734d3-106">Se puede reutilizar el código de orquestaciones, como **activar**, que utilizan el **ExceptionHandler** orquestación.</span><span class="sxs-lookup"><span data-stu-id="734d3-106">You can re-use code from orchestrations, such as **Activate**, that use the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="734d3-107">Todas estas orquestaciones incluyen un ámbito denominado **CallingCode** con un **excepción** bloque.</span><span class="sxs-lookup"><span data-stu-id="734d3-107">All of these orchestrations include a scope titled **CallingCode** with an attached **Exception** block.</span></span> <span data-ttu-id="734d3-108">Reemplace el código de la **CallingCode** ámbito con el código.</span><span class="sxs-lookup"><span data-stu-id="734d3-108">Replace the code in the **CallingCode** scope with your code.</span></span> <span data-ttu-id="734d3-109">El **excepción** bloque define todas las variables necesarias para llamar a la **ExceptionHandler** orquestación.</span><span class="sxs-lookup"><span data-stu-id="734d3-109">The **Exception** block defines all of the variables need to call the **ExceptionHandler** orchestration.</span></span> <span data-ttu-id="734d3-110">Edite los valores asignados a las variables.</span><span class="sxs-lookup"><span data-stu-id="734d3-110">Edit the values assigned to the variables.</span></span>  
  
 <span data-ttu-id="734d3-111">La solución utiliza excepciones personalizadas y un par de excepciones de BizTalk predefinidas para los casos de errores irrecuperables, como un mensaje de pedido incorrecto.</span><span class="sxs-lookup"><span data-stu-id="734d3-111">The solution uses custom exceptions, and a couple pre-defined BizTalk exceptions, for cases where the error is unrecoverable such as a malformed order message.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="734d3-112">La solución usa un adaptador personalizado para el control de errores en algunos puertos.</span><span class="sxs-lookup"><span data-stu-id="734d3-112">The solution uses a custom adapter for handling failures on some ports.</span></span> <span data-ttu-id="734d3-113">Para obtener más información acerca del adaptador, vea [el adaptador Ops](../core/the-ops-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="734d3-113">For more information about the adapter, see [The Ops Adapter](../core/the-ops-adapter.md).</span></span>  
  
 <span data-ttu-id="734d3-114">Esta sección se describe la **ExceptionHandler** orquestación y las excepciones personalizadas.</span><span class="sxs-lookup"><span data-stu-id="734d3-114">This section describes the **ExceptionHandler** orchestration and the custom exceptions.</span></span> <span data-ttu-id="734d3-115">También se ofrece una breve descripción acerca de cómo la solución utiliza la característica del producto de informes de errores.</span><span class="sxs-lookup"><span data-stu-id="734d3-115">It also discusses, briefly, how the solution employs the error reporting product feature.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="734d3-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="734d3-116">In This Section</span></span>  
  
-   [<span data-ttu-id="734d3-117">La orquestación de ExceptionHandler</span><span class="sxs-lookup"><span data-stu-id="734d3-117">The ExceptionHandler Orchestration</span></span>](../core/the-exceptionhandler-orchestration.md)  
  
-   [<span data-ttu-id="734d3-118">Excepciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="734d3-118">Custom Exceptions</span></span>](../core/custom-exceptions.md)