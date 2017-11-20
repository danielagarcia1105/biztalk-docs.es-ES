---
title: "Cómo agregar un ámbito Shape5 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adding, Scope shapes
- Scope shape, adding
ms.assetid: 1e16eda1-c4bd-4428-a477-78c453aeb1aa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7bbe3f5fbb267fee618ac7f0b91c35ad33e1758
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="078b4-102">Cómo agregar una forma Ámbito</span><span class="sxs-lookup"><span data-stu-id="078b4-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="078b4-103">Siga estos pasos para agregar una **ámbito**forma.</span><span class="sxs-lookup"><span data-stu-id="078b4-103">Follow these steps to add a **Scope**shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="078b4-104">Procedimiento para agregar una forma Ámbito</span><span class="sxs-lookup"><span data-stu-id="078b4-104">To add a Scope shape</span></span>  
  
1.  <span data-ttu-id="078b4-105">Haga clic en la flecha situada bajo la **ReceiveFromIn** de puerto, seleccione **Insertar forma**y, a continuación, haga clic en **ámbito**.</span><span class="sxs-lookup"><span data-stu-id="078b4-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     <span data-ttu-id="078b4-106">En el **ámbito** forma, se establecen operaciones que podrían tener errores.</span><span class="sxs-lookup"><span data-stu-id="078b4-106">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="078b4-107">Por ejemplo, se agrega un puerto de envío y uno de recepción en una orquestación SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="078b4-107">For example, add a send, a receive and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="078b4-108">En este ejemplo, envía un mensaje a SERVER.</span><span class="sxs-lookup"><span data-stu-id="078b4-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="078b4-109">SERVER da una respuesta.</span><span class="sxs-lookup"><span data-stu-id="078b4-109">SERVER gives a response.</span></span> <span data-ttu-id="078b4-110">Ejecuta el resto de la orquestación y devuelve información al puerto OutFile.</span><span class="sxs-lookup"><span data-stu-id="078b4-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="078b4-111">En el **ámbito** forma, establezca el **tipo de transacción** a **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="078b4-111">In the **Scope** shape, set the **Transaction Type** to **None**.</span></span>  
  
3.  <span data-ttu-id="078b4-112">Pulse el botón derecho dentro de la **ámbito** forma y seleccione **nuevo controlador de excepción**.</span><span class="sxs-lookup"><span data-stu-id="078b4-112">Right-click inside the **Scope** shape and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="078b4-113">Esto crea el `Catch Exception`bloque.</span><span class="sxs-lookup"><span data-stu-id="078b4-113">This creates the `Catch Exception`block.</span></span> <span data-ttu-id="078b4-114">Si se produce una excepción desde el back-end, se detecta en el `Catch Exception`bloque.</span><span class="sxs-lookup"><span data-stu-id="078b4-114">If an exception occurs from the back-end, it is caught inside the `Catch Exception`block.</span></span>  
  
4.  <span data-ttu-id="078b4-115">En el bloque `Catch Exception`, debe agregar la lógica.</span><span class="sxs-lookup"><span data-stu-id="078b4-115">In the `Catch Exception` block, you must add the logic.</span></span>  
  
     <span data-ttu-id="078b4-116">La lógica más importante que debe establecer es el tipo de mensaje de error que espera recibir.</span><span class="sxs-lookup"><span data-stu-id="078b4-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="078b4-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="078b4-117">See Also</span></span>  
 [<span data-ttu-id="078b4-118">Uso de control de excepciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="078b4-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling5.md)