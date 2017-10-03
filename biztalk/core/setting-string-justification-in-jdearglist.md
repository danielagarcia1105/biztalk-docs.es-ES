---
title: "Establecer la justificación de cadena en Jdearglist | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, setting string justification
- strings, configuring
- strings, right-justified
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daecf4101ebf5dc8964562dc7f385d41279a3401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="setting-string-justification-in-jdearglist"></a><span data-ttu-id="3983b-102">Configuración de la justificación de cadena en Jdearglist</span><span class="sxs-lookup"><span data-stu-id="3983b-102">Setting String Justification in Jdearglist</span></span>
<span data-ttu-id="3983b-103">Para configurar determinados argumentos de cadena como justificados a la derecha (y rellenos a la izquierda) en el archivo JD Edwards OneWorld jdearglist.txt, debe saber a qué función empresarial desea acceder y, específicamente, debe saber qué campos de la función empresarial desea llamar.</span><span class="sxs-lookup"><span data-stu-id="3983b-103">To configure certain string arguments as right-justified (and left padded) in the JD Edwards OneWorld jdearglist.txt file, you must know what business function you want to access; specifically, you must know which fields in the business function you want to call.</span></span>  
  
 <span data-ttu-id="3983b-104">Debe actualizar jdearglist.txt antes de generar los enlaces (esquemas) en la orquestación.</span><span class="sxs-lookup"><span data-stu-id="3983b-104">You must update the jdearglist.txt before you generate the bindings (schemas) in the orchestration.</span></span> <span data-ttu-id="3983b-105">Las instrucciones para actualizar el archivo jdearglist.txt se describen en [control de valores de cadena](../core/handling-string-values1.md).</span><span class="sxs-lookup"><span data-stu-id="3983b-105">The instructions for updating the jdearglist.txt file are outlined in [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
 <span data-ttu-id="3983b-106">Si recibe un mensaje de advertencia de jdearglist.txt en el registro de auditoría, le informará de que falta el archivo jdearglist.txt.</span><span class="sxs-lookup"><span data-stu-id="3983b-106">If you receive a jdearglist.txt warning message in the audit log, it informs you that the jdearglist.txt is missing.</span></span> <span data-ttu-id="3983b-107">Si ejecuta las funciones empresariales SalesOrder o PurchaseOrder, debe tener el archivo en su RUTA DE ACCESO para que funcione.</span><span class="sxs-lookup"><span data-stu-id="3983b-107">If you run the SalesOrder or PurchaseOrder business functions, you must have the file in your PATH, or it will not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3983b-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="3983b-108">See Also</span></span>  
 [<span data-ttu-id="3983b-109">Administración de BizTalk Adapter para JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="3983b-109">Administering BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/administering-biztalk-adapter-for-jd-edwards-oneworld.md)