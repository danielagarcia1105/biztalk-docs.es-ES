---
title: "Cómo agregar un ámbito Shape2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- adding, Scope shapes
ms.assetid: 9449210f-1f29-4b86-a14b-148caa06ac6b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef67618c553702ae32cd0a88f6d2f77eb1ff053
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="46e2a-102">Cómo agregar una forma Ámbito</span><span class="sxs-lookup"><span data-stu-id="46e2a-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="46e2a-103">Utilice el procedimiento siguiente para agregar una **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="46e2a-103">Use the following procedure to add a **Scope** shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="46e2a-104">Para agregar una forma ámbito</span><span class="sxs-lookup"><span data-stu-id="46e2a-104">To add a scope shape</span></span>  
  
1.  <span data-ttu-id="46e2a-105">Haga clic en la flecha situada bajo la **ReceiveFromIn** de puerto, seleccione **Insertar forma**y seleccione **ámbito**.</span><span class="sxs-lookup"><span data-stu-id="46e2a-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and select **Scope**.</span></span>  
  
     <span data-ttu-id="46e2a-106">En el **ámbito** forma, se establecen operaciones que podrían tener errores.</span><span class="sxs-lookup"><span data-stu-id="46e2a-106">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="46e2a-107">Por ejemplo, se agrega un puerto de envío y uno de recepción en una orquestación SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="46e2a-107">For example, add a send, a receive and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="46e2a-108">En este ejemplo, envía un mensaje a SERVER.</span><span class="sxs-lookup"><span data-stu-id="46e2a-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="46e2a-109">SERVER da una respuesta.</span><span class="sxs-lookup"><span data-stu-id="46e2a-109">SERVER gives a response.</span></span> <span data-ttu-id="46e2a-110">Ejecuta el resto de la orquestación y devuelve información al puerto OutFile.</span><span class="sxs-lookup"><span data-stu-id="46e2a-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="46e2a-111">En el **ámbito** forma, establezca el **tipo de transacción** a **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="46e2a-111">In the **Scope** shape, set the **Transaction Type** to **None**.</span></span>  
  
3.  <span data-ttu-id="46e2a-112">Pulse el botón derecho dentro de la **ámbito** forma y seleccione **nuevo controlador de excepción**.</span><span class="sxs-lookup"><span data-stu-id="46e2a-112">Right-click inside the **Scope** shape and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="46e2a-113">Esto crea la **excepción de filtrado** bloque.</span><span class="sxs-lookup"><span data-stu-id="46e2a-113">This creates the **Catch Exception** block.</span></span> <span data-ttu-id="46e2a-114">Si se produce una excepción desde el sistema back-end, se detecta en el **excepción de filtrado** bloque.</span><span class="sxs-lookup"><span data-stu-id="46e2a-114">If an exception occurs from the back-end system, it is caught inside the **Catch Exception** block.</span></span>  
  
4.  <span data-ttu-id="46e2a-115">En el **excepción de filtrado** bloque, debe agregar la lógica.</span><span class="sxs-lookup"><span data-stu-id="46e2a-115">In the **Catch Exception** block, you must add the logic.</span></span>  
  
     <span data-ttu-id="46e2a-116">La lógica más importante que debe establecer es el tipo de mensaje de error que espera recibir.</span><span class="sxs-lookup"><span data-stu-id="46e2a-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46e2a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="46e2a-117">See Also</span></span>  
 [<span data-ttu-id="46e2a-118">Uso de control de excepciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="46e2a-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)