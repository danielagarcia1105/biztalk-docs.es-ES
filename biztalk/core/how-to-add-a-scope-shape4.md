---
title: "Cómo agregar un ámbito forma4 | Documentos de Microsoft"
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
ms.assetid: 4ed56ada-a656-40b1-b34a-0c0803c01216
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a81bb85412784616d185b64ee39f1e777d19fea3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="7b0c3-102">Cómo agregar una forma Ámbito</span><span class="sxs-lookup"><span data-stu-id="7b0c3-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="7b0c3-103">Siga estos pasos para agregar una **ámbito** forma.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-103">Follow these steps to add a **Scope** shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="7b0c3-104">Para agregar una forma ámbito</span><span class="sxs-lookup"><span data-stu-id="7b0c3-104">To add a scope shape</span></span>  
  
1.  <span data-ttu-id="7b0c3-105">Haga clic en la flecha situada bajo la **ReceiveFromIn** de puerto, seleccione **Insertar forma**y, a continuación, haga clic en **ámbito**.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     <span data-ttu-id="7b0c3-106">En la forma Ámbito, se establecen operaciones que podrían tener errores.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-106">In the Scope shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="7b0c3-107">Por ejemplo, se agrega un puerto de envío y uno de recepción en una orquestación SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-107">For example, add a send, a receive and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="7b0c3-108">En este ejemplo, envía un mensaje a SERVER.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="7b0c3-109">SERVER da una respuesta.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-109">SERVER gives a response.</span></span> <span data-ttu-id="7b0c3-110">Ejecuta el resto de la orquestación y devuelve información al puerto OutFile.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="7b0c3-111">En la forma ámbito, establezca el **transacciones** a **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-111">In the Scope shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="7b0c3-112">Pulse el botón derecho dentro de la forma ámbito y seleccione **nuevo controlador de excepción**.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-112">Right-click inside the Scope shape and select **New Exception Handler**.</span></span>  
  
     <span data-ttu-id="7b0c3-113">Esto crea la **excepción de filtrado** bloque.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-113">This creates the **Catch Exception** block.</span></span> <span data-ttu-id="7b0c3-114">Si se produce una excepción desde el back-end, se detecta en el **excepción de filtrado** bloque.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-114">If an exception occurs from the back-end, it is caught inside the **Catch Exception** block.</span></span>  
  
4.  <span data-ttu-id="7b0c3-115">En el **excepción de filtrado** bloque, debe agregar la lógica.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-115">In the **Catch Exception** block, you must add the logic.</span></span>  
    <span data-ttu-id="7b0c3-116">La lógica más importante que debe establecer es el tipo de mensaje de error que espera recibir.</span><span class="sxs-lookup"><span data-stu-id="7b0c3-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b0c3-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7b0c3-117">See Also</span></span>  
 [<span data-ttu-id="7b0c3-118">Uso de control de excepciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="7b0c3-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling4.md)