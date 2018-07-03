---
title: Crear una conexión al sistema SAP | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SAP system, connecting to
- connection URI
- URI
- Uniform Resource Identifier
ms.assetid: 25d1eaa7-d02a-4fd0-8adf-83505cdb1ab8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef25dddf3d30f584b30aa0f35b8b1c4140d285e2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36965813"
---
# <a name="create-a-connection-to-the-sap-system"></a><span data-ttu-id="d5dd7-102">Crear una conexión con el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="d5dd7-102">Create a connection to the SAP system</span></span>
<span data-ttu-id="d5dd7-103">El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="d5dd7-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="d5dd7-104">Por lo tanto, permite la comunicación a un sistema SAP a través de una dirección de extremo WCF.</span><span class="sxs-lookup"><span data-stu-id="d5dd7-104">As such, it enables communication to an SAP system through a WCF endpoint address.</span></span> <span data-ttu-id="d5dd7-105">En WCF, la dirección de punto de conexión identifica la ubicación de red de un servicio y normalmente se expresa como un identificador uniforme de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="d5dd7-105">In WCF the endpoint address identifies the network location of a service and is typically expressed as a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="d5dd7-106">El [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] usa para establecer una conexión con el sistema SAP.</span><span class="sxs-lookup"><span data-stu-id="d5dd7-106">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses to establish a connection to the SAP system.</span></span> <span data-ttu-id="d5dd7-107">Debe especificar un URI de conexión cuando le:</span><span class="sxs-lookup"><span data-stu-id="d5dd7-107">You must specify a connection URI when you:</span></span>  
  
- <span data-ttu-id="d5dd7-108">Cuando se crea un generador de canales o un agente de escucha del canal mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo del canal o al crear un host de servicio o cliente WCF mediante el [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="d5dd7-108">When you create a channel factory or a channel listener using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel model or when you create a WCF client or service host using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model.</span></span>  
  
- <span data-ttu-id="d5dd7-109">Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="d5dd7-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="d5dd7-110">Use la [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o una interfaz de servicio WCF para un [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] solución de modelo de servicio.</span><span class="sxs-lookup"><span data-stu-id="d5dd7-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class or WCF service interface for a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model solution.</span></span>  
  
- <span data-ttu-id="d5dd7-111">Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar esquemas de mensaje desde el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] para un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="d5dd7-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] for a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="d5dd7-112">Utilice la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="d5dd7-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
  <span data-ttu-id="d5dd7-113">Los temas de esta sección describen cómo establecer una conexión entre el [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] y el sistema SAP, ya que con:</span><span class="sxs-lookup"><span data-stu-id="d5dd7-113">The topics in this section describe how to establish a connection between the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] and the SAP system by providing you with:</span></span>  
  
- <span data-ttu-id="d5dd7-114">Información sobre las propiedades de conexión y la estructura de lo URI de conexión de SAP.</span><span class="sxs-lookup"><span data-stu-id="d5dd7-114">Information about the connection properties and the structure of the SAP connection URI.</span></span>  
  
- <span data-ttu-id="d5dd7-115">Vínculos a temas que muestran cómo establecer una conexión con el [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5dd7-115">Links to topics that show how to establish a connection by using the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d5dd7-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="d5dd7-116">In This Section</span></span>  
  
-   [<span data-ttu-id="d5dd7-117">Crear el URI de conexión del sistema SAP</span><span class="sxs-lookup"><span data-stu-id="d5dd7-117">Create the SAP system connection URI</span></span>](../../adapters-and-accelerators/adapter-sap/create-the-sap-system-connection-uri.md)