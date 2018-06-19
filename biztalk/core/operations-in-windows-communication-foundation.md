---
title: Operaciones de Windows Communication Foundation | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a1728d2f-ac74-446e-a36f-4b645a6e042a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c6b5344b8fb2c5a5ba7a68b112adb50133198c3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263772"
---
# <a name="operations-in-windows-communication-foundation"></a><span data-ttu-id="8083c-102">Operaciones en Windows Communication Foundation</span><span class="sxs-lookup"><span data-stu-id="8083c-102">Operations in Windows Communication Foundation</span></span>
<span data-ttu-id="8083c-103">Esta sección contiene las operaciones personalizadas que admite el interceptor de WCF de BAM.</span><span class="sxs-lookup"><span data-stu-id="8083c-103">This section contains the custom operations supported by the BAM WCF interceptor.</span></span>  
  
 <span data-ttu-id="8083c-104">Si un elemento de nombre de operación contiene un atributo Acción, tenga en cuenta que:</span><span class="sxs-lookup"><span data-stu-id="8083c-104">Note that if an operation name element contains an Action attribute:</span></span>  
  
1.  <span data-ttu-id="8083c-105">El nombre de la operación es el identificado mediante el atributo de nombre para el cliente y el servidor.</span><span class="sxs-lookup"><span data-stu-id="8083c-105">The operation name is the one identified by the name attribute for both the client and the server,</span></span>  
  
2.  <span data-ttu-id="8083c-106">En el caso de rutas de respuesta (respuesta de devolución), respuesta del cliente y del servicio, el nombre de la operación se identifica mediante el atributo del nombre.</span><span class="sxs-lookup"><span data-stu-id="8083c-106">For reply paths (callback reply), client reply and service rely, the operation name is identified by the name attribute.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8083c-107">El nombre del nodo de los mensajes de respuesta se asignará anexando la palabra "Resultado" al nombre especificado por el atributo de nombre.</span><span class="sxs-lookup"><span data-stu-id="8083c-107">Reply messages will have a node that is named by appending the word "Result" to the name specified by the name attribute.</span></span> <span data-ttu-id="8083c-108">Debe asegurarse de que los XPaths reflejen esta convención de nomenclatura.</span><span class="sxs-lookup"><span data-stu-id="8083c-108">You must ensure that the XPaths reflect this naming convention.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8083c-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="8083c-109">In This Section</span></span>  
  
-   [<span data-ttu-id="8083c-110">Autogeneratecorrelationtoken (operación)</span><span class="sxs-lookup"><span data-stu-id="8083c-110">AutoGenerateCorrelationToken</span></span>](../core/autogeneratecorrelationtoken.md)  
  
-   [<span data-ttu-id="8083c-111">Getcontextproperty (operación)</span><span class="sxs-lookup"><span data-stu-id="8083c-111">GetContextProperty</span></span>](../core/getcontextproperty1.md)  
  
-   [<span data-ttu-id="8083c-112">GetEndpointName</span><span class="sxs-lookup"><span data-stu-id="8083c-112">GetEndpointName</span></span>](../core/getendpointname.md)  
  
-   [<span data-ttu-id="8083c-113">Getoperationname (operación)</span><span class="sxs-lookup"><span data-stu-id="8083c-113">GetOperationName</span></span>](../core/getoperationname.md)  
  
-   [<span data-ttu-id="8083c-114">Getservicecontractcallpoint (operación)</span><span class="sxs-lookup"><span data-stu-id="8083c-114">GetServiceContractCallPoint</span></span>](../core/getservicecontractcallpoint.md)  
  
-   [<span data-ttu-id="8083c-115">XPath</span><span class="sxs-lookup"><span data-stu-id="8083c-115">XPath</span></span>](../core/xpath.md)