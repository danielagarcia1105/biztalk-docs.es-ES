---
title: Cómo agregar un ámbito forma1 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Scope shapes, adding
- Scope shapes, Catch Exception blocks
- Catch Exception blocks, Scope shapes
- adding, Scope shapes
ms.assetid: dfe039d1-4c4a-4e21-ae03-7ca534aafec3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 094f744f7d4d6d1c405ea50d222beb8c0a67920e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22247188"
---
# <a name="how-to-add-a-scope-shape"></a><span data-ttu-id="27741-102">Cómo agregar una forma Ámbito</span><span class="sxs-lookup"><span data-stu-id="27741-102">How to Add a Scope Shape</span></span>
<span data-ttu-id="27741-103">Para agregar una forma Ámbito, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="27741-103">Follow these steps to add a Scope shape.</span></span>  
  
### <a name="to-add-a-scope-shape"></a><span data-ttu-id="27741-104">Para agregar una forma Ámbito</span><span class="sxs-lookup"><span data-stu-id="27741-104">To add a Scope Shape</span></span>  
  
1.  <span data-ttu-id="27741-105">Haga clic en la flecha situada bajo la **ReceiveFromIn** de puerto, seleccione **Insertar forma**y, a continuación, haga clic en **ámbito**.</span><span class="sxs-lookup"><span data-stu-id="27741-105">Right-click the arrow below the **ReceiveFromIn** port, point to **Insert Shape**, and then click **Scope**.</span></span>  
  
     ![](../core/media/siebeladapter-18-exceptionhandling-insertscope.gif "SiebelAdapter_18_ExceptionHandling_InsertScope")  
  
     <span data-ttu-id="27741-106">En la forma Ámbito, se establecen operaciones que podrían tener errores.</span><span class="sxs-lookup"><span data-stu-id="27741-106">In the Scope shape, you set operations that might have a fault.</span></span>  
  
     <span data-ttu-id="27741-107">Por ejemplo, se agregan un puerto de envío y de recepción en una orquestación SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="27741-107">For example, add a send, a receive, and a send port in an SQLExecute orchestration.</span></span> <span data-ttu-id="27741-108">En este ejemplo se envía un mensaje a DB2.</span><span class="sxs-lookup"><span data-stu-id="27741-108">In this example, we are sending a message to DB2.</span></span> <span data-ttu-id="27741-109">DB2 da una respuesta.</span><span class="sxs-lookup"><span data-stu-id="27741-109">DB2 gives a response.</span></span> <span data-ttu-id="27741-110">Ejecuta el resto de la orquestación y devuelve información al puerto OutFile.</span><span class="sxs-lookup"><span data-stu-id="27741-110">It runs the rest of the orchestration and returns information back to the OutFile port.</span></span>  
  
2.  <span data-ttu-id="27741-111">En la forma ámbito, establezca el **transacciones** a **ninguno**.</span><span class="sxs-lookup"><span data-stu-id="27741-111">In the Scope shape, set the **Transaction** to **None**.</span></span>  
  
3.  <span data-ttu-id="27741-112">Pulse el botón derecho dentro de la forma ámbito y seleccione **nuevo controlador de excepción**.</span><span class="sxs-lookup"><span data-stu-id="27741-112">Right-click inside the Scope shape, and select **New Exception Handler**.</span></span>  
  
     ![](../core/media/siebeladapter-19-exceptionhandling-newexception.gif "SiebelAdapter_19_ExceptionHandling_NewException")  
  
     <span data-ttu-id="27741-113">Se creará el bloque Excepción de filtrado.</span><span class="sxs-lookup"><span data-stu-id="27741-113">This creates the Catch Exception block.</span></span> <span data-ttu-id="27741-114">Si se produce una excepción desde el back-end, ésta se captura dentro del bloque de excepción de filtrado.</span><span class="sxs-lookup"><span data-stu-id="27741-114">If an exception occurs from the back-end, it is caught inside the Catch Exception block.</span></span>  
  
4.  <span data-ttu-id="27741-115">En el bloque Excepción de filtrado, debe agregar la lógica.</span><span class="sxs-lookup"><span data-stu-id="27741-115">In the Catch Exception block, you must add the logic.</span></span>  
  
     <span data-ttu-id="27741-116">La lógica más importante que debe establecer es el tipo de mensaje de error que espera.</span><span class="sxs-lookup"><span data-stu-id="27741-116">The most important logic you must set is the type of error message you are expecting.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27741-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="27741-117">See Also</span></span>  
 [<span data-ttu-id="27741-118">Uso de control de excepciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="27741-118">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling2.md)