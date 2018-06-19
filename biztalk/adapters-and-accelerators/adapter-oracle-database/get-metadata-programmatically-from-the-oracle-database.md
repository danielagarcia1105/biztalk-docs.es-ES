---
title: Obtener metadatos mediante programación de la base de datos de Oracle | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving programmatically from the Oracle database
ms.assetid: 28a55935-6078-41d0-abfa-ac86e9ca8471
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c36fcd6a791f1d960a4dd4dfd78ca199d2e49cb5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214276"
---
# <a name="get-metadata-programmatically-from-the-oracle-database"></a><span data-ttu-id="b431d-102">Obtener metadatos mediante programación de la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="b431d-102">Get Metadata Programmatically from the Oracle Database</span></span>
<span data-ttu-id="b431d-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] es un enlace personalizado de WCF que expone una base de datos de Oracle como un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="b431d-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] is a custom WCF binding that exposes an Oracle database as a WCF service.</span></span> <span data-ttu-id="b431d-104">El adaptador expone la base de datos de Oracle como un servicio autodescriptivo; es decir, un servicio que es capaz de publicación de metadatos acerca de las operaciones que admite.</span><span class="sxs-lookup"><span data-stu-id="b431d-104">The adapter exposes the Oracle database as a self-describing service; that is, a service that is capable of publishing metadata about the operations that it supports.</span></span> <span data-ttu-id="b431d-105">Los metadatos describen la interfaz lógica a un servicio WCF; es decir, el contrato de servicio, mensajes y los esquemas de mensaje que se deben usar para interactuar con el servicio.</span><span class="sxs-lookup"><span data-stu-id="b431d-105">Metadata describes the logical interface to a WCF service; that is, the service contract, messages, and message schemas that must be used to interact with the service.</span></span>  
  
 <span data-ttu-id="b431d-106">Estos metadatos se utilizan con herramientas como:</span><span class="sxs-lookup"><span data-stu-id="b431d-106">This metadata is used by tools such as:</span></span>  
  
-   <span data-ttu-id="b431d-107">El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar representaciones de código administrado del contrato de servicio, y</span><span class="sxs-lookup"><span data-stu-id="b431d-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate managed code representations of the service contract, and</span></span>  
  
-   <span data-ttu-id="b431d-108">El [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar esquemas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="b431d-108">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate message schemas.</span></span>  
  
 <span data-ttu-id="b431d-109">Sin embargo, también puede recuperar metadatos mediante programación desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="b431d-109">However, you can also retrieve metadata programmatically from the adapter.</span></span> <span data-ttu-id="b431d-110">Por ejemplo, puede realizar esta operación para crear una herramienta de recuperación de metadatos personalizados para utilizar en una aplicación existente.</span><span class="sxs-lookup"><span data-stu-id="b431d-110">For example, you might want to do this to create a custom metadata retrieval tool to use in an existing application.</span></span>  
  
 <span data-ttu-id="b431d-111">El adaptador publica los metadatos a través de dos puntos de conexión:</span><span class="sxs-lookup"><span data-stu-id="b431d-111">The adapter publishes metadata through two endpoints:</span></span>  
  
-   <span data-ttu-id="b431d-112">Un extremo de WS-Metadata Exchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="b431d-112">A WS-Metadata Exchange (MEX) endpoint.</span></span> <span data-ttu-id="b431d-113">WCF proporciona automáticamente un extremo MEX para todos los enlaces de WCF.</span><span class="sxs-lookup"><span data-stu-id="b431d-113">WCF automatically provides a MEX endpoint for all WCF bindings.</span></span> <span data-ttu-id="b431d-114">Puede usar el intercambio de metadatos para recuperar metadatos para operaciones admitidas por el adaptador en la base de datos de Oracle subyacente.</span><span class="sxs-lookup"><span data-stu-id="b431d-114">You can use metadata exchange to retrieve metadata for operations supported by the adapter on the underlying Oracle database.</span></span>  
  
-   <span data-ttu-id="b431d-115">Un **IMetadataRetrievalContract** punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="b431d-115">An **IMetadataRetrievalContract** endpoint.</span></span> <span data-ttu-id="b431d-116">El **IMetadataRetrievalContract** interfaz se implementa mediante el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b431d-116">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="b431d-117">Clasifica los artefactos de la base de datos de Oracle en varios niveles lógicos y los presenta como un árbol de nodos de metadatos.</span><span class="sxs-lookup"><span data-stu-id="b431d-117">It categorizes Oracle database artifacts at multiple logical levels and presents them as a tree of metadata nodes.</span></span> <span data-ttu-id="b431d-118">Puede usar los métodos expuestos por el **IMetadataRetrievalContract** interfaz para examinar y buscar los nodos de este árbol y para devolver los metadatos para las operaciones en el que esté interesado.</span><span class="sxs-lookup"><span data-stu-id="b431d-118">You can use methods exposed by the **IMetadataRetrievalContract** interface to browse and search the nodes of this tree and to return metadata for operations in which you are interested.</span></span>  
  
 <span data-ttu-id="b431d-119">Los temas de esta sección describen cómo utilizar MEX y **IMetadataRetrievalContract** puntos de conexión para recuperar metadatos mediante programación desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="b431d-119">The topics in this section describe how to use MEX and **IMetadataRetrievalContract** endpoints to retrieve metadata programmatically from the adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b431d-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b431d-120">In This Section</span></span>  
  
-   [<span data-ttu-id="b431d-121">Obtener metadatos con WS-Metadata Exchange en la base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="b431d-121">Get Metadata Using WS-Metadata Exchange in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-using-ws-metadata-exchange-in-oracle-database.md)  
  
-   [<span data-ttu-id="b431d-122">Obtener metadatos de base de datos de Oracle mediante IMetadataRetrievalContract</span><span class="sxs-lookup"><span data-stu-id="b431d-122">Get Metadata in Oracle Database Using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-in-oracle-database-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a><span data-ttu-id="b431d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b431d-123">See Also</span></span>  
[<span data-ttu-id="b431d-124">Desarrollar las aplicaciones de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="b431d-124">Develop your Oracle Database applications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)