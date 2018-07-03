---
title: Limitaciones del adaptador de BizTalk para mySAP Business Suite | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapters, limitations of
- IDOC, sending an IDOC to an SAP system
ms.assetid: 1ca1e0cf-7ae7-4a8b-8363-e5f3746e8e26
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f289d1f70005e8b4caa0e7c739522cc5590bca58
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973718"
---
# <a name="limitations-of-biztalk-adapter-for-mysap-business-suite"></a><span data-ttu-id="b2f63-102">Limitaciones del adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="b2f63-102">Limitations of BizTalk Adapter for mySAP Business Suite</span></span>

## <a name="limitations-list"></a><span data-ttu-id="b2f63-103">Lista de limitaciones</span><span class="sxs-lookup"><span data-stu-id="b2f63-103">Limitations list</span></span>
<span data-ttu-id="b2f63-104">Lo siguiente es limitaciones conocida de la [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="b2f63-104">The following are known limitations of the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]:</span></span>  
  
- <span data-ttu-id="b2f63-105">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con el adaptador de Microsoft BizTalk para mySAP Business Suite, la versión anterior del adaptador.</span><span class="sxs-lookup"><span data-stu-id="b2f63-105">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] is not compatible with Microsoft BizTalk Adapter for mySAP Business Suite, the previous release of the adapter.</span></span> <span data-ttu-id="b2f63-106">No admite esta versión del adaptador de envío y recepción de mensajes con los esquemas generados con la versión anterior del adaptador.</span><span class="sxs-lookup"><span data-stu-id="b2f63-106">This release of the adapter does not support sending and receiving messages having schemas generated using the earlier version of the adapter.</span></span>  
  
- <span data-ttu-id="b2f63-107">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con RFC con tipos de parámetros complejos, incluidos los tipos de tabla (jerárquica) ITAB II.</span><span class="sxs-lookup"><span data-stu-id="b2f63-107">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs with complex parameter types, including ITAB II (hierarchical) table types.</span></span>  
  
- <span data-ttu-id="b2f63-108">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con RFC de tipos personalizados de ABAP.</span><span class="sxs-lookup"><span data-stu-id="b2f63-108">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support RFCs having custom ABAP types.</span></span>  
  
- <span data-ttu-id="b2f63-109">Debido a problemas con el control de tiempo de espera por la biblioteca de cliente subyacente, el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] no es compatible con el tiempo de espera de conexión y comando.</span><span class="sxs-lookup"><span data-stu-id="b2f63-109">Due to issues with timeout handling by the underlying client library, the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] does not support command and connection timeout.</span></span>  
  
- <span data-ttu-id="b2f63-110">Si cambia la hora del sistema del equipo que ejecuta el host de BizTalk Server, el tiempo no se actualiza automáticamente en el host de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b2f63-110">If you change the system time of the computer running the BizTalk Server host, the time is not updated automatically in the BizTalk Server host.</span></span> <span data-ttu-id="b2f63-111">Esto podría provocar un comportamiento incorrecto de las operaciones de entrada que usan el puerto de recepción de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="b2f63-111">This could lead to incorrect behavior of the inbound operations that use the receive port of BizTalk Server.</span></span> <span data-ttu-id="b2f63-112">Como alternativa, debe reiniciar la instancia de host que tiene un puerto de recepción después de haber cambiado la hora del sistema del equipo ejecuta.</span><span class="sxs-lookup"><span data-stu-id="b2f63-112">As a workaround, you must restart the host instance that has a receive port, after you have changed the system time of the computer running it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f63-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2f63-113">See Also</span></span>  
 [<span data-ttu-id="b2f63-114">Definición del adaptador de BizTalk para mySAP Business Suite</span><span class="sxs-lookup"><span data-stu-id="b2f63-114">Understand BizTalk Adapter for mySAP Business Suite</span></span>](../../adapters-and-accelerators/adapter-sap/understand-biztalk-adapter-for-mysap-business-suite.md)