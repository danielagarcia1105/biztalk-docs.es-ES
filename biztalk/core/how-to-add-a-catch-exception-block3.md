---
title: Cómo agregar un Block3 de excepción Catch | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shape [Orchestration Designer], Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer]
- Catch Exception block [Orchestration Designer], creating
- Catch Exception block [Orchestration Designer], exception handler
- Catch Exception block [Orchestration Designer], about Catch Exception blocks
- Orchestration Designer, errors
ms.assetid: 63ca4a60-b657-452a-86fd-78968ccf2933
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1040a27a5e1273d2ad80a722deb421878de36c12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247060"
---
# <a name="how-to-add-a-catch-exception-block"></a><span data-ttu-id="313cd-102">Cómo agregar un bloque Excepción de filtrado</span><span class="sxs-lookup"><span data-stu-id="313cd-102">How to Add a Catch Exception Block</span></span>
<span data-ttu-id="313cd-103">El **excepción de filtrado** de bloqueo representa un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="313cd-103">The **Catch Exception** block represents an exception handler.</span></span> <span data-ttu-id="313cd-104">**Detectar excepciones** bloques se adjuntan al final de un **ámbito** forma en el Diseñador de orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="313cd-104">**Catch Exception** blocks are attached to the end of a **Scope** shape in Orchestration Designer.</span></span> <span data-ttu-id="313cd-105">Puede adjuntar tantos **excepción de filtrado** bloquea según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="313cd-105">You can attach as many **Catch Exception** blocks as you need.</span></span>  
  
 <span data-ttu-id="313cd-106">Puede configurar controladores de excepción para controlar los distintos tipos de excepciones.</span><span class="sxs-lookup"><span data-stu-id="313cd-106">You can set up exception handlers to handle different kinds of exceptions.</span></span> <span data-ttu-id="313cd-107">En cada controlador de excepción, especifique un tipo de excepción, que debe ser un mensaje de error o un objeto derivado de la clase **System.Exception**.</span><span class="sxs-lookup"><span data-stu-id="313cd-107">On each exception handler, you specify an exception type, which must be either a fault message or an object derived from the class **System.Exception**.</span></span> <span data-ttu-id="313cd-108">Si no especifica un tipo de excepción, el bloque de excepción se tratará como un controlador de excepción general y puede detectar las excepciones que no se derivan de **System.Exception**.</span><span class="sxs-lookup"><span data-stu-id="313cd-108">If you do not specify an exception type, the exception block will be treated as a general exception handler, and can catch exceptions that do not derive from **System.Exception**.</span></span>  
  
 <span data-ttu-id="313cd-109">Si se origina una excepción que coincida con el tipo especificado en un controlador de excepción, se llamará a dicho controlador.</span><span class="sxs-lookup"><span data-stu-id="313cd-109">If an exception is thrown that matches the specified type in an exception handler, that exception handler will be called.</span></span> <span data-ttu-id="313cd-110">Si se origina otra excepción, la controlará el controlador de excepción predeterminado.</span><span class="sxs-lookup"><span data-stu-id="313cd-110">If some other exception is thrown, it will be handled by the default exception handler.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="313cd-111">Para agregar una **excepción de filtrado** bloquear a un **ámbito** forma, el **tipo de transacción** propiedad de la **ámbito** forma debe establecerse en **Ninguno** o **de larga ejecución**.</span><span class="sxs-lookup"><span data-stu-id="313cd-111">To add a **Catch Exception** block to a **Scope** shape, the **Transaction Type** property of the **Scope** shape must be set to **None** or **Long Running**.</span></span>  
  
### <a name="to-add-a-catch-exception-block"></a><span data-ttu-id="313cd-112">Para agregar un bloque Excepción de filtrado</span><span class="sxs-lookup"><span data-stu-id="313cd-112">To add a Catch Exception block</span></span>  
  
1.  <span data-ttu-id="313cd-113">Haga clic en el **ámbito** forma a la que desea agregar un **excepción de filtrado** bloquear y, a continuación, haga clic en **nuevo controlador de excepción**.</span><span class="sxs-lookup"><span data-stu-id="313cd-113">Right-click the **Scope** shape to which you want to add a **Catch Exception** block, and then click **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="313cd-114">A **excepción de filtrado** bloque se agrega a la orquestación inmediatamente después asociado **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="313cd-114">A **Catch Exception** block is added to the orchestration immediately following the associated **Scope** shape.</span></span>  
  
2.  <span data-ttu-id="313cd-115">En la ventana Propiedades, especifique las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="313cd-115">In the Properties window, specify the following properties:</span></span>  
  
    |<span data-ttu-id="313cd-116">Propiedad</span><span class="sxs-lookup"><span data-stu-id="313cd-116">Property</span></span>|<span data-ttu-id="313cd-117">Description</span><span class="sxs-lookup"><span data-stu-id="313cd-117">Description</span></span>|  
    |--------------|-----------------|  
    |<span data-ttu-id="313cd-118">Nombre de objeto de excepción</span><span class="sxs-lookup"><span data-stu-id="313cd-118">Exception Object Name</span></span>|<span data-ttu-id="313cd-119">Asigna un nombre al objeto de excepción filtrado por el controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="313cd-119">Assigns a name to the exception object caught by the exception handler.</span></span>|  
    |<span data-ttu-id="313cd-120">Tipo de objeto de excepción</span><span class="sxs-lookup"><span data-stu-id="313cd-120">Exception Object Type</span></span>|<span data-ttu-id="313cd-121">Determina el tipo de objeto (procedente de System.Exception) que filtrará este controlador de excepción.</span><span class="sxs-lookup"><span data-stu-id="313cd-121">Determines the object type (derived from System.Exception) that this exception handler will catch.</span></span>|  
  
3.  <span data-ttu-id="313cd-122">Dentro de la **excepción de filtrado** bloquear, agregue formas a fin de crear el proceso para controlar la excepción.</span><span class="sxs-lookup"><span data-stu-id="313cd-122">Inside the **Catch Exception** block, add shapes to create the process for handling the exception.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="313cd-123">Si especifica una excepción General como el **excepción** tipo de objeto, el **excepción de filtrado** bloque interceptará todas las excepciones, las que no se deriva de incluidas **System.Exception** .</span><span class="sxs-lookup"><span data-stu-id="313cd-123">If you specify General Exception as the **Exception** object type, the **Catch Exception** block will intercept any exception, including those that are not derived from **System.Exception**.</span></span> <span data-ttu-id="313cd-124">En tal caso, no dispondrá de acceso a un objeto de excepción.</span><span class="sxs-lookup"><span data-stu-id="313cd-124">In such a case, you will not have access to an exception object.</span></span> <span data-ttu-id="313cd-125">Dentro de este bloque, si utiliza un **Iniciar excepción** forma con el tipo de excepción General, se estará volviendo a la excepción detectada.</span><span class="sxs-lookup"><span data-stu-id="313cd-125">Within this block, if you use a **Throw Exception** shape with the General Exception type, you will be effectively rethrowing the caught exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313cd-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="313cd-126">See Also</span></span>  
 [<span data-ttu-id="313cd-127">Excepciones</span><span class="sxs-lookup"><span data-stu-id="313cd-127">Exceptions</span></span>](../core/exceptions.md)