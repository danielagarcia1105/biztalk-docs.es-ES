---
title: Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bf3374a2-2fca-4df4-a1b1-d11cdc05d393
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d201987490d9395b07d043c67fa50a31400fe7cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-biztalk-applications-using-the-oracle-e-business-suite-adapter"></a><span data-ttu-id="73dc6-102">Desarrollar aplicaciones de BizTalk con el adaptador de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="73dc6-102">Develop BizTalk applications using the Oracle E-Business Suite adapter</span></span>
<span data-ttu-id="73dc6-103">Desarrollo de aplicaciones de BizTalk implica la creación de un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]y el uso de la  **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]**  o  **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]**  para generar el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="73dc6-103">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], and using the **[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]** or **[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]** to generate XML schema.</span></span> <span data-ttu-id="73dc6-104">Una vez que haya generado el esquema, puede usar enrutamiento por contenidos (CBR) o crear orquestaciones de BizTalk para enviar y recibir mensajes que cumplen el esquema generado.</span><span class="sxs-lookup"><span data-stu-id="73dc6-104">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to your generated schema.</span></span>  
  
 <span data-ttu-id="73dc6-105">CBR puede utilizarse en escenarios donde los mensajes se envíen a Oracle E-Business Suite no requieren ningún procesamiento intensivo.</span><span class="sxs-lookup"><span data-stu-id="73dc6-105">CBR can be used in scenarios where the messages being sent to Oracle E-Business Suite do not require any intensive processing.</span></span> <span data-ttu-id="73dc6-106">Por ejemplo, si sabe que los mensajes de recepción del puerto de recepción solo de un tipo determinado, se puede agregar un filtro al puerto de envío para enrutar los mensajes que coinciden con la expresión de filtro para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="73dc6-106">For example, if you know that the receive port receive messages only of a certain type, you can add a filter to the send port to route messages that match the filter expression to the send port.</span></span>  

## <a name="use-orchestration"></a><span data-ttu-id="73dc6-107">Orquestación de uso</span><span class="sxs-lookup"><span data-stu-id="73dc6-107">Use orchestration</span></span>  
 <span data-ttu-id="73dc6-108">En las orquestaciones de BizTalk, creará el envío y puertos de recepción para enviar y recibir mensajes desde y hacia el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que a su vez envía los mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73dc6-108">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> 
 
 <span data-ttu-id="73dc6-109">Esta sección proporciona información sobre el uso de las orquestaciones de BizTalk para realizar tareas y operaciones sobre el uso de Oracle E-Business Suite el [!INCLUDE[adapteroraclebusinessshort_md](../../includes/adapteroraclebusinessshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="73dc6-109">This section provides information about using BizTalk orchestrations to perform tasks and operations on Oracle E-Business Suite using the [!INCLUDE[adapteroraclebusinessshort_md](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="73dc6-110">El [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] a su vez usa la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que puede interactuar con un enlace de WCF.</span><span class="sxs-lookup"><span data-stu-id="73dc6-110">The [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which can interact with a WCF binding.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="73dc6-111">Para usar el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], siempre se debe establecer el **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**.</span><span class="sxs-lookup"><span data-stu-id="73dc6-111">To use the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], you must always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="73dc6-112">Para conocer los pasos, consulte [configurar las propiedades de enlace de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span><span class="sxs-lookup"><span data-stu-id="73dc6-112">For the steps, see [Configure the binding properties for Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md).</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="73dc6-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="73dc6-113">See Also</span></span>  
[<span data-ttu-id="73dc6-114">Desarrollar las aplicaciones de Oracle E-Business Suite</span><span class="sxs-lookup"><span data-stu-id="73dc6-114">Develop your Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/develop-your-oracle-e-business-suite-applications.md)