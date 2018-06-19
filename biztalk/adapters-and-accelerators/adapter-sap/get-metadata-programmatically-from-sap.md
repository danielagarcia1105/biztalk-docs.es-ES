---
title: Obtener metadatos mediante programación desde SAP | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IMetadataRetrievalContract endpoint
- metadata, retrieving programmatically
- WS-Metadata Exchange (MEX) endpoint
ms.assetid: 8d75332e-c103-4bd5-a9a2-56d21747a04e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c856b3629d7d7dcd3f9aa5431c0406f6c822e54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216836"
---
# <a name="get-metadata-programmatically-from-sap"></a><span data-ttu-id="a55f9-102">Obtener metadatos mediante programación desde SAP</span><span class="sxs-lookup"><span data-stu-id="a55f9-102">Get Metadata Programmatically from SAP</span></span>
<span data-ttu-id="a55f9-103">El [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] es un enlace personalizado de WCF que expone un sistema SAP como un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="a55f9-103">The [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] is a custom WCF binding that exposes an SAP system as a WCF service.</span></span> <span data-ttu-id="a55f9-104">El adaptador expone el sistema SAP como servicio autodescriptivo; es decir, un servicio que es capaz de publicación de metadatos acerca de las operaciones que admite.</span><span class="sxs-lookup"><span data-stu-id="a55f9-104">The adapter exposes the SAP system as a self-describing service; that is, a service that is capable of publishing metadata about the operations that it supports.</span></span> <span data-ttu-id="a55f9-105">Los metadatos describen la interfaz lógica a un servicio WCF; es decir, el contrato de servicio, mensajes y los esquemas de mensaje que se deben usar para interactuar con el servicio.</span><span class="sxs-lookup"><span data-stu-id="a55f9-105">Metadata describes the logical interface to a WCF service; that is, the service contract, messages, and message schemas that must be used to interact with the service.</span></span>  
  
 <span data-ttu-id="a55f9-106">Estos metadatos se utilizan con herramientas como:</span><span class="sxs-lookup"><span data-stu-id="a55f9-106">This metadata is used by tools such as:</span></span>  
  
-   <span data-ttu-id="a55f9-107">El [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] para generar representaciones de código administrado del contrato de servicio, y</span><span class="sxs-lookup"><span data-stu-id="a55f9-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate managed code representations of the service contract, and</span></span>  
  
-   <span data-ttu-id="a55f9-108">El [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] para generar esquemas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a55f9-108">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to generate message schemas.</span></span>  
  
 <span data-ttu-id="a55f9-109">Sin embargo, también puede recuperar metadatos mediante programación desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="a55f9-109">However, you can also retrieve metadata programmatically from the adapter.</span></span> <span data-ttu-id="a55f9-110">Por ejemplo, puede realizar esta operación para crear una herramienta de recuperación de metadatos personalizados para utilizar en una aplicación existente.</span><span class="sxs-lookup"><span data-stu-id="a55f9-110">For example, you might want to do this to create a custom metadata retrieval tool to use in an existing application.</span></span>  
  
 <span data-ttu-id="a55f9-111">El adaptador publica los metadatos a través de dos puntos de conexión:</span><span class="sxs-lookup"><span data-stu-id="a55f9-111">The adapter publishes metadata through two endpoints:</span></span>  
  
-   <span data-ttu-id="a55f9-112">Un extremo de WS-Metadata Exchange (MEX).</span><span class="sxs-lookup"><span data-stu-id="a55f9-112">A WS-Metadata Exchange (MEX) endpoint.</span></span> <span data-ttu-id="a55f9-113">WCF proporciona automáticamente un extremo MEX para todos los enlaces de WCF.</span><span class="sxs-lookup"><span data-stu-id="a55f9-113">WCF automatically provides a MEX endpoint for all WCF bindings.</span></span> <span data-ttu-id="a55f9-114">Puede usar el intercambio de metadatos para recuperar metadatos para operaciones admitidas por el adaptador en el sistema SAP subyacente.</span><span class="sxs-lookup"><span data-stu-id="a55f9-114">You can use metadata exchange to retrieve metadata for operations supported by the adapter on the underlying SAP system.</span></span>  
  
-   <span data-ttu-id="a55f9-115">Un **IMetadataRetrievalContract** punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="a55f9-115">An **IMetadataRetrievalContract** endpoint.</span></span> <span data-ttu-id="a55f9-116">El **IMetadataRetrievalContract** interfaz se implementa mediante el [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a55f9-116">The **IMetadataRetrievalContract** interface is implemented by the [!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)].</span></span> <span data-ttu-id="a55f9-117">Clasifica los artefactos del sistema SAP en varios niveles lógicos y los presenta como un árbol de nodos de metadatos.</span><span class="sxs-lookup"><span data-stu-id="a55f9-117">It categorizes SAP system artifacts at multiple logical levels and presents them as a tree of metadata nodes.</span></span> <span data-ttu-id="a55f9-118">Puede usar los métodos expuestos por el **IMetadataRetrievalContract** interfaz para examinar y buscar los nodos de este árbol y para devolver los metadatos para las operaciones en el que esté interesado.</span><span class="sxs-lookup"><span data-stu-id="a55f9-118">You can use methods exposed by the **IMetadataRetrievalContract** interface to browse and search the nodes of this tree and to return metadata for operations in which you are interested.</span></span>  
  
 <span data-ttu-id="a55f9-119">Los temas de esta sección describen cómo utilizar MEX y **IMetadataRetrievalContract** puntos de conexión para recuperar metadatos mediante programación desde el adaptador.</span><span class="sxs-lookup"><span data-stu-id="a55f9-119">The topics in this section describe how to use MEX and **IMetadataRetrievalContract** endpoints to retrieve metadata programmatically from the adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a55f9-120">En esta sección</span><span class="sxs-lookup"><span data-stu-id="a55f9-120">In This Section</span></span>  
  
-   [<span data-ttu-id="a55f9-121">Recuperar metadatos mediante WS-Metadata Exchange en SAP</span><span class="sxs-lookup"><span data-stu-id="a55f9-121">Retrieving Metadata Using WS-Metadata Exchange in SAP</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-using-ws-metadata-exchange-in-sap.md)  
  
-   [<span data-ttu-id="a55f9-122">Al recuperar los metadatos de SAP mediante IMetadataRetrievalContract</span><span class="sxs-lookup"><span data-stu-id="a55f9-122">Retrieving Metadata in SAP Using IMetadataRetrievalContract</span></span>](../../adapters-and-accelerators/adapter-sap/get-metadata-in-sap-using-imetadataretrievalcontract.md)  
  
## <a name="see-also"></a><span data-ttu-id="a55f9-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="a55f9-123">See Also</span></span>  
[<span data-ttu-id="a55f9-124">Desarrollar las aplicaciones de SAP</span><span class="sxs-lookup"><span data-stu-id="a55f9-124">Develop your SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/develop-your-sap-applications.md)