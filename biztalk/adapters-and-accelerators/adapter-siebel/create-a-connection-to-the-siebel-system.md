---
title: "Crear una conexión con el sistema Siebel | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: connecting, to the Siebel system
ms.assetid: 5810eeb1-6e26-4620-a731-fb352eebea2e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a108335263e85db832f4db144d27b64b92429683
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="create-a-connection-to-the-siebel-system"></a><span data-ttu-id="82540-102">Crear una conexión con el sistema Siebel</span><span class="sxs-lookup"><span data-stu-id="82540-102">Create a connection to the Siebel system</span></span>
<span data-ttu-id="82540-103">El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="82540-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="82540-104">Por lo tanto, habilita la comunicación con un sistema Siebel a través de una dirección de extremo WCF.</span><span class="sxs-lookup"><span data-stu-id="82540-104">As such, it enables communication to a Siebel system through a WCF endpoint address.</span></span> <span data-ttu-id="82540-105">En WCF, la dirección del extremo identifica la ubicación de un servicio de red y normalmente se expresa como un identificador uniforme de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="82540-105">In WCF the endpoint address identifies the network location of a service and is typically expressed as a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="82540-106">El [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] se utiliza para establecer una conexión con el sistema Siebel.</span><span class="sxs-lookup"><span data-stu-id="82540-106">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] uses to establish a connection to the Siebel system.</span></span> <span data-ttu-id="82540-107">Debe especificar un URI de conexión al que:</span><span class="sxs-lookup"><span data-stu-id="82540-107">You must specify a connection URI when you:</span></span>  
  
-   <span data-ttu-id="82540-108">Crear un generador de canales o un agente de escucha del canal mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] canal modelo o crear un host de servicio o cliente WCF con el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="82540-108">Create a channel factory or a channel listener using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel model, or create a WCF client or service host using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model.</span></span>  
  
-   <span data-ttu-id="82540-109">Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="82540-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
-   <span data-ttu-id="82540-110">Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF, o interfaz de servicio WCF para una [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] solución de modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="82540-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class, or WCF service interface for a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model solution.</span></span>  
  
-   <span data-ttu-id="82540-111">Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar los esquemas de mensaje desde el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="82540-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] for a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
-   <span data-ttu-id="82540-112">Usar la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="82540-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class, or WCF service interface for a WCF service model solution.</span></span>  
  
 <span data-ttu-id="82540-113">Los temas de esta sección describen cómo establecer una conexión entre el [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] y el sistema Siebel proporcionando con:</span><span class="sxs-lookup"><span data-stu-id="82540-113">The topics in this section describe how to establish a connection between the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] and the Siebel system by providing you with:</span></span>  
  
-   <span data-ttu-id="82540-114">Información sobre las propiedades de conexión y la estructura del URI de conexión de Siebel.</span><span class="sxs-lookup"><span data-stu-id="82540-114">Information about the connection properties and the structure of the Siebel connection URI.</span></span>  
  
-   <span data-ttu-id="82540-115">Vínculos a temas que muestran cómo establecer una conexión con el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="82540-115">Links to topics that show how to establish a connection by using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="82540-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="82540-116">See Also</span></span>  
[<span data-ttu-id="82540-117">Desarrollar las aplicaciones de Siebel</span><span class="sxs-lookup"><span data-stu-id="82540-117">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)