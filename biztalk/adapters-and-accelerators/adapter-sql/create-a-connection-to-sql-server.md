---
title: Crear una conexión a SQL Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 44a03b2c-55b5-49a0-92cc-6f017720d34a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b7c5f186a28f068f3ffc217ce5f252a1512f03a0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978013"
---
# <a name="create-a-connection-to-sql-server"></a><span data-ttu-id="67dc5-102">Crear una conexión a SQL Server</span><span class="sxs-lookup"><span data-stu-id="67dc5-102">Create a connection to SQL Server</span></span>
<span data-ttu-id="67dc5-103">El [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] es un [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] enlace personalizado.</span><span class="sxs-lookup"><span data-stu-id="67dc5-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="67dc5-104">Por lo tanto, permite la comunicación a una base de datos de SQL Server a través de una dirección de extremo WCF.</span><span class="sxs-lookup"><span data-stu-id="67dc5-104">As such, it enables communication to a SQL Server database through a WCF endpoint address.</span></span> <span data-ttu-id="67dc5-105">En WCF, la dirección del punto de conexión identifica la ubicación de un servicio de red y normalmente se expresa como un identificador uniforme de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="67dc5-105">In WCF, the endpoint address identifies the network location of a service and is typically expressed as a Uniform Resource Identifier (URI).</span></span> <span data-ttu-id="67dc5-106">El [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expresa esta ubicación como un URI, que contiene las propiedades de conexión que el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] utiliza para establecer una conexión a la base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="67dc5-106">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses to establish a connection to the SQL Server database.</span></span> <span data-ttu-id="67dc5-107">Debe especificar un URI de conexión cuando le:</span><span class="sxs-lookup"><span data-stu-id="67dc5-107">You must specify a connection URI when you:</span></span>  
  
- <span data-ttu-id="67dc5-108">Crear un generador de canales o un agente de escucha del canal mediante el modelo de canal WCF o al crear un host de servicio o cliente WCF mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="67dc5-108">Create a channel factory or a channel listener using the WCF channel model or when you create a WCF client or service host using the WCF service model.</span></span>  
  
- <span data-ttu-id="67dc5-109">Crear un enlace de puerto físico en un [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solución.</span><span class="sxs-lookup"><span data-stu-id="67dc5-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="67dc5-110">Use el [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="67dc5-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
- <span data-ttu-id="67dc5-111">Use la [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para recuperar esquemas de mensaje desde el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] para una solución de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="67dc5-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] for a BizTalk Server solution.</span></span>  
  
- <span data-ttu-id="67dc5-112">Utilice la herramienta de utilidad de metadatos de ServiceModel (svcutil.exe) para generar una clase de cliente WCF o una interfaz de servicio WCF para una solución de modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="67dc5-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
  <span data-ttu-id="67dc5-113">Los temas de esta sección describen cómo establecer una conexión entre el [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] y la base de datos de SQL Server al proporcionarle con:</span><span class="sxs-lookup"><span data-stu-id="67dc5-113">The topics in this section describe how to establish a connection between the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] and the SQL Server database by providing you with:</span></span>  
  
- <span data-ttu-id="67dc5-114">Información sobre las propiedades de conexión y la estructura de lo URI de conexión de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="67dc5-114">Information about the connection properties and the structure of the SQL Server connection URI.</span></span>  
  
- <span data-ttu-id="67dc5-115">Vínculos a temas que muestran cómo especificar un URI de conexión mediante el [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="67dc5-115">Links to topics that show how to specify a connection URI by using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
- <span data-ttu-id="67dc5-116">Información sobre cómo conectarse a SQL Server mediante autenticación de Windows.</span><span class="sxs-lookup"><span data-stu-id="67dc5-116">Information about connecting to SQL Server using Windows Authentication.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="67dc5-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="67dc5-117">See Also</span></span>  
[<span data-ttu-id="67dc5-118">Desarrollar las aplicaciones SQL</span><span class="sxs-lookup"><span data-stu-id="67dc5-118">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)