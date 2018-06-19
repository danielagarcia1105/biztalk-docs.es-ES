---
title: Establecer justificación de cadena en el adaptador de JD Edwards OneWorld | Documentos de Microsoft
description: Actualizar archivo jdearglist para utilizar el adaptador de JD Edwards OneWorld en una orquestación de BizTalk Server
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70b32d0106d95a1970b480e32dfa47a81ebf98ca
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013003"
---
# <a name="set-string-justification-in-jdearglist"></a><span data-ttu-id="6a507-103">Establezca la justificación de cadena en Jdearglist</span><span class="sxs-lookup"><span data-stu-id="6a507-103">Set string Justification in Jdearglist</span></span>

## <a name="overview"></a><span data-ttu-id="6a507-104">Información general</span><span class="sxs-lookup"><span data-stu-id="6a507-104">Overview</span></span>
<span data-ttu-id="6a507-105">Para configurar determinados argumentos de cadena como justificados a la derecha (y rellenos a la izquierda) en el archivo JD Edwards OneWorld jdearglist.txt, debe saber a qué función empresarial desea acceder y, específicamente, debe saber qué campos de la función empresarial desea llamar.</span><span class="sxs-lookup"><span data-stu-id="6a507-105">To configure certain string arguments as right-justified (and left padded) in the JD Edwards OneWorld jdearglist.txt file, you must know what business function you want to access; specifically, you must know which fields in the business function you want to call.</span></span>  
  
 <span data-ttu-id="6a507-106">Debe actualizar jdearglist.txt antes de generar los enlaces (esquemas) en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="6a507-106">You must update the jdearglist.txt before you generate the bindings (schemas) in the orchestration.</span></span> <span data-ttu-id="6a507-107">Las instrucciones para actualizar el archivo jdearglist.txt se describen en [control de valores de cadena](../core/handling-string-values1.md).</span><span class="sxs-lookup"><span data-stu-id="6a507-107">The instructions for updating the jdearglist.txt file are outlined in [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
 <span data-ttu-id="6a507-108">Si recibe un mensaje de advertencia de jdearglist.txt en el registro de auditoría, le informará de que falta el archivo jdearglist.txt.</span><span class="sxs-lookup"><span data-stu-id="6a507-108">If you receive a jdearglist.txt warning message in the audit log, it informs you that the jdearglist.txt is missing.</span></span> <span data-ttu-id="6a507-109">Si ejecuta las funciones empresariales SalesOrder o PurchaseOrder, debe tener el archivo en su RUTA DE ACCESO para que funcione.</span><span class="sxs-lookup"><span data-stu-id="6a507-109">If you run the SalesOrder or PurchaseOrder business functions, you must have the file in your PATH, or it will not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a507-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a507-110">See Also</span></span>  
[<span data-ttu-id="6a507-111">Uso del control de excepciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="6a507-111">Use BizTalk Server Exception Handling</span></span>](using-biztalk-server-exception-handling1.md)