---
title: Desarrollar aplicaciones de BizTalk con el adaptador de Siebel | Documentos de Microsoft
ms.custom: ''
ms.date: 08/02/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk applications, developing
- developing, BizTalk applications
- CBR
- Content-Based Routing
ms.assetid: 1a2a9765-305c-44b2-aed7-5437725e4c19
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c8267c07027d9994b0115ebaf49fde96e76f2716
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221932"
---
# <a name="develop-biztalk-applications-using-the-siebel-adapter"></a><span data-ttu-id="d9f3d-102">Desarrollar aplicaciones de BizTalk con el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="d9f3d-102">Develop BizTalk applications using the Siebel adapter</span></span>

## <a name="overview"></a><span data-ttu-id="d9f3d-103">Información general</span><span class="sxs-lookup"><span data-stu-id="d9f3d-103">Overview</span></span>
<span data-ttu-id="d9f3d-104">Desarrollo de aplicaciones de BizTalk implica la creación de un proyecto de BizTalk en [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] y el uso de la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar el esquema XML.</span><span class="sxs-lookup"><span data-stu-id="d9f3d-104">Developing BizTalk applications involves creating a BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] and using the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate XML schema.</span></span> <span data-ttu-id="d9f3d-105">Una vez que haya generado el esquema, puede usar enrutamiento por contenidos (CBR) o crear orquestaciones de BizTalk para enviar y recibir mensajes que cumplen el esquema generado.</span><span class="sxs-lookup"><span data-stu-id="d9f3d-105">Once you have generated the schema, you can either use Content-Based Routing (CBR) or create BizTalk orchestrations to send and receive messages that conform to the generated schema.</span></span>  
  
 <span data-ttu-id="d9f3d-106">CBR puede utilizarse en escenarios donde los mensajes se envíen a un sistema Siebel no requieren ningún procesamiento intensivo.</span><span class="sxs-lookup"><span data-stu-id="d9f3d-106">CBR can be used in scenarios where the messages being sent to a Siebel system do not require any intensive processing.</span></span> <span data-ttu-id="d9f3d-107">Por ejemplo, si sabe que el puerto de recepción va a recibir mensajes sólo de un tipo determinado, puede agregar un filtro al puerto de envío para enrutar los mensajes que coinciden con la expresión de filtro para el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="d9f3d-107">For example, if you know that the receive port will be receiving messages only of a certain type, you can add a filter to the send port to route the messages matching the filter expression to the send port.</span></span>  
  
 <span data-ttu-id="d9f3d-108">En las orquestaciones de BizTalk, creará el envío y puertos de recepción para enviar y recibir mensajes desde y hacia el [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], que a su vez envía los mensajes a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9f3d-108">In BizTalk orchestrations, you create send and receive ports to send and receive messages to and from the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)], which in turn sends the messages to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="d9f3d-109">Esta sección proporciona información sobre el uso de las orquestaciones de BizTalk para realizar operaciones en un sistema Siebel mediante el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9f3d-109">This section provides information about using BizTalk orchestrations to perform operations on a Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="d9f3d-110">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a su vez usa la [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] que puede interactuar con un enlace de WCF.</span><span class="sxs-lookup"><span data-stu-id="d9f3d-110">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in turn uses the [!INCLUDE[wcfadapter_short](../../includes/wcfadapter-short-md.md)] that can interact with a WCF binding.</span></span>  

## <a name="before-you-begin"></a><span data-ttu-id="d9f3d-111">Antes de empezar</span><span class="sxs-lookup"><span data-stu-id="d9f3d-111">Before you begin</span></span>  

* <span data-ttu-id="d9f3d-112">Para usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], establezca siempre la **EnableBizTalkCompatibilityMode** enlazar la propiedad a **True**.</span><span class="sxs-lookup"><span data-stu-id="d9f3d-112">To use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)], always set the **EnableBizTalkCompatibilityMode** binding property to **True**.</span></span> <span data-ttu-id="d9f3d-113">Para conocer los pasos, consulte [configurar las propiedades de enlace de Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md).</span><span class="sxs-lookup"><span data-stu-id="d9f3d-113">For the steps, see [Configure the binding properties for Siebel](../../adapters-and-accelerators/adapter-siebel/configure-the-binding-properties-for-siebel.md).</span></span>
  
* <span data-ttu-id="d9f3d-114">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] acompaña [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] no se mostrará automáticamente en la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="d9f3d-114">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] shipped with [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] is not automatically listed in the BizTalk Server Administration console.</span></span> <span data-ttu-id="d9f3d-115">Esto es porque el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] es un enlace personalizado de WCF.</span><span class="sxs-lookup"><span data-stu-id="d9f3d-115">This is because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] is a WCF custom binding.</span></span> 

* <span data-ttu-id="d9f3d-116">Para generar los metadatos, use el [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9f3d-116">To generate metadata, use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)].</span></span> <span data-ttu-id="d9f3d-117">No use el [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d9f3d-117">Do not use the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="d9f3d-118">Para obtener instrucciones sobre cómo utilizar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], consulte [obtener metadatos para operaciones de Siebel en Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="d9f3d-118">For instructions on using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], see [Get Metadata for Siebel Operations in Visual Studio](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md).</span></span>   

  
## <a name="see-also"></a><span data-ttu-id="d9f3d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9f3d-119">See Also</span></span>  
[<span data-ttu-id="d9f3d-120">Desarrollar las aplicaciones de Siebel</span><span class="sxs-lookup"><span data-stu-id="d9f3d-120">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)