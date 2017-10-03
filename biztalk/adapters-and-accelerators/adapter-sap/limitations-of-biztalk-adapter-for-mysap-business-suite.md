---
title: Limitaciones del adaptador de BizTalk para mySAP Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, limitations of
- IDOC, sending an IDOC to an SAP system
ms.assetid: 1ca1e0cf-7ae7-4a8b-8363-e5f3746e8e26
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d392178cd49918151f0ad86c73a5fcba712d6b7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="9de9e-102">Limitaciones del adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="9de9e-102">Limitations of BizTalk Adapter for mySAP Business Suite</span></span>

## <a name="limitations-list"></a><span data-ttu-id="9de9e-103">Lista de limitaciones</span><span class="sxs-lookup"><span data-stu-id="9de9e-103">Limitations list</span></span>
<span data-ttu-id="9de9e-104">Los siguientes se conocen las limitaciones de la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="9de9e-104">The following are known limitations of the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span></span>  
  
-   <span data-ttu-id="9de9e-105">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con el adaptador de Microsoft BizTalk para mySAP Business Suite, la versión anterior del adaptador.</span><span class="sxs-lookup"><span data-stu-id="9de9e-105">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is not compatible with Microsoft BizTalk Adapter for mySAP Business Suite, the previous release of the adapter.</span></span> <span data-ttu-id="9de9e-106">Esta versión del adaptador no admite enviar y recibir mensajes con esquemas generados utilizando la versión anterior del adaptador.</span><span class="sxs-lookup"><span data-stu-id="9de9e-106">This release of the adapter does not support sending and receiving messages having schemas generated using the earlier version of the adapter.</span></span>  
  
-   <span data-ttu-id="9de9e-107">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con RFC con tipos de parámetros complejos, incluidos los tipos de tabla (jerárquicos) ITAB II.</span><span class="sxs-lookup"><span data-stu-id="9de9e-107">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs with complex parameter types, including ITAB II (hierarchical) table types.</span></span>  
  
-   <span data-ttu-id="9de9e-108">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con RFC tener tipos ABAP personalizados.</span><span class="sxs-lookup"><span data-stu-id="9de9e-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs having custom ABAP types.</span></span>  
  
-   <span data-ttu-id="9de9e-109">Debido a problemas con el control de tiempo de espera por la biblioteca de cliente subyacente, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con el tiempo de espera de conexión y comando.</span><span class="sxs-lookup"><span data-stu-id="9de9e-109">Due to issues with timeout handling by the underlying client library, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support command and connection timeout.</span></span>  
  
-   <span data-ttu-id="9de9e-110">Si cambia la hora del sistema del equipo que ejecuta el host de BizTalk Server, el tiempo no se actualiza automáticamente en el host de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9de9e-110">If you change the system time of the computer running the BizTalk Server host, the time is not updated automatically in the BizTalk Server host.</span></span> <span data-ttu-id="9de9e-111">Esto podría provocar un comportamiento incorrecto de las operaciones de entrada que utilizan el puerto de recepción de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="9de9e-111">This could lead to incorrect behavior of the inbound operations that use the receive port of BizTalk Server.</span></span> <span data-ttu-id="9de9e-112">Como alternativa, debe reiniciar la instancia de host que tiene un puerto de recepción, después de haber cambiado la hora del sistema del equipo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="9de9e-112">As a workaround, you must restart the host instance that has a receive port, after you have changed the system time of the computer running it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de9e-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="9de9e-113">See Also</span></span>  
 [<span data-ttu-id="9de9e-114">Comprender el adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="9de9e-114">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)