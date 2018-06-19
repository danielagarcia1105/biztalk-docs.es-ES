---
title: Cómo agregar un ámbito forma3 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
ms.assetid: 8068ce97-4409-4c88-89e8-6505b56cefc5
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8231dfed1ea84ba5c11e0352f789b92cc38d0f83
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248068"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="bcde9-102">Cómo agregar una forma Ámbito</span><span class="sxs-lookup"><span data-stu-id="bcde9-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="bcde9-103">Use el procedimiento siguiente para agregar una forma Ámbito</span><span class="sxs-lookup"><span data-stu-id="bcde9-103">Use the following procedure to add a Scope shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="bcde9-104">Para agregar una forma Ámbito</span><span class="sxs-lookup"><span data-stu-id="bcde9-104">To add a Scope Shape</span></span>  
  
1.  <span data-ttu-id="bcde9-105">Haga clic en la flecha situada bajo la **recepción** de puerto, seleccione **Insertar forma**y, a continuación, seleccione **ámbito**.</span><span class="sxs-lookup"><span data-stu-id="bcde9-105">Right-click the arrow below the **Receive** port, point to **Insert Shape**, and then select **Scope**.</span></span>  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     <span data-ttu-id="bcde9-106">En el **ámbito** forma, se establecen operaciones que podrían tener errores.</span><span class="sxs-lookup"><span data-stu-id="bcde9-106">In the **Scope** shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="bcde9-107">Por ejemplo, se agregan un puerto de envío y de recepción en una orquestación SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="bcde9-107">For example, add a send, a receive, and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="bcde9-108">En este ejemplo, envía un mensaje a SERVER.</span><span class="sxs-lookup"><span data-stu-id="bcde9-108">In this example, you send a message to SERVER.</span></span> <span data-ttu-id="bcde9-109">SERVER da una respuesta.</span><span class="sxs-lookup"><span data-stu-id="bcde9-109">SERVER gives a response.</span></span> <span data-ttu-id="bcde9-110">Ejecuta el resto de la orquestación y devuelve información al puerto outFile.</span><span class="sxs-lookup"><span data-stu-id="bcde9-110">It runs the rest of the orchestration and returns information back to the outFile port.</span></span>  
  
2.  <span data-ttu-id="bcde9-111">En el **ámbito** forma, establezca el **transacciones** a **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="bcde9-111">In the **Scope** shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="bcde9-112">Pulse el botón derecho dentro de la **ámbito** forma y seleccione **nuevo controlador de excepción**.</span><span class="sxs-lookup"><span data-stu-id="bcde9-112">Right-click inside the **Scope** shape, and select **New Exception Handler**.</span></span>  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     <span data-ttu-id="bcde9-113">Esto crea la **excepción de filtrado** bloque.</span><span class="sxs-lookup"><span data-stu-id="bcde9-113">This creates the **Catch Exception** block.</span></span> <span data-ttu-id="bcde9-114">Si se produce una excepción desde el sistema back-end, se detecta en el **excepción de filtrado** bloque.</span><span class="sxs-lookup"><span data-stu-id="bcde9-114">If an exception occurs from the back-end system, it is caught inside the **Catch Exception** block.</span></span>  
  
4.  <span data-ttu-id="bcde9-115">En el **excepción de filtrado** bloque, debe agregar la lógica.</span><span class="sxs-lookup"><span data-stu-id="bcde9-115">In the **Catch Exception** block, you must add the logic.</span></span>  
  
     <span data-ttu-id="bcde9-116">La lógica más importante que debe establecer es el tipo de mensaje de error que espera recibir.</span><span class="sxs-lookup"><span data-stu-id="bcde9-116">The most important logic that you must set is the type of error message that you expect to receive.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bcde9-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcde9-117">See Also</span></span>  
 [<span data-ttu-id="bcde9-118">Uso de control de excepciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="bcde9-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)