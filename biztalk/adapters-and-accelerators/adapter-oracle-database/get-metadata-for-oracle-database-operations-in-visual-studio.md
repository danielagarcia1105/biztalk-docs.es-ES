---
title: Obtener los metadatos de las operaciones de base de datos de Oracle en Visual Studio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- metadata, retrieving in Visual Studio
- metadata
ms.assetid: d903b408-1144-4625-909d-710826e37769
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9fdf1d1943c471591e35f1efb6ca6e08f36948fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214332"
---
# <a name="get-metadata-for-oracle-database-operations-in-visual-studio"></a><span data-ttu-id="c87d4-102">Obtener los metadatos de las operaciones de base de datos de Oracle en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c87d4-102">Get metadata for Oracle Database operations in Visual Studio</span></span>
<span data-ttu-id="c87d4-103">El [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] proporciona tres [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes que puede utilizar para ayudarle a desarrollar soluciones mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="c87d4-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] provides three [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter.</span></span>  
  
-   <span data-ttu-id="c87d4-104">El [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] y [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] están disponibles en proyectos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="c87d4-104">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] and the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] are available in BizTalk Server projects.</span></span> <span data-ttu-id="c87d4-105">Usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c87d4-105">You use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] and the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)] to generate message schemas (XSDs) for operations that you want to target in your BizTalk solution.</span></span> <span data-ttu-id="c87d4-106">Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, vea [aplicaciones de BizTalk de desarrollar con el adaptador de la base de datos de Oracle](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)</span><span class="sxs-lookup"><span data-stu-id="c87d4-106">For more information about developing solutions with BizTalk Server, see [Develop BizTalk applications using the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)</span></span>  
  
-   <span data-ttu-id="c87d4-107">La [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] está disponible en proyectos de programación no sean de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="c87d4-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] is available in non-BizTalk programming projects.</span></span> <span data-ttu-id="c87d4-108">Utiliza el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="c87d4-108">You use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client class or a WCF service callback interface when you develop solutions using the WCF service model.</span></span> <span data-ttu-id="c87d4-109">Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [desarrollar aplicaciones de base de datos de Oracle mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="c87d4-109">For more information about developing solutions with the WCF service model, see [Develop Oracle Database Applications using the WCF Service Model](../../adapters-and-accelerators/adapter-oracle-database/develop-oracle-database-applications-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="c87d4-110">Todos estos tres [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes simplifican el desarrollo mediante:</span><span class="sxs-lookup"><span data-stu-id="c87d4-110">All these three [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
-   <span data-ttu-id="c87d4-111">Proporcionar una interfaz de Microsoft Windows a través del cual se puede examinar y buscar para las operaciones que desea utilizar en la solución.</span><span class="sxs-lookup"><span data-stu-id="c87d4-111">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
-   <span data-ttu-id="c87d4-112">Al recuperar los metadatos expuestos por el adaptador para estas operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="c87d4-112">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
-   <span data-ttu-id="c87d4-113">Convertir que los metadatos, que se expresa como un documento de lenguaje de descripción de servicios Web (WSDL) por el adaptador, en un formulario que puede usar en la solución (esquemas de mensaje XSD para los proyectos de BizTalk o una representación de objeto de .NET de un contrato de servicio de WCF modelo de servicio) y lo agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="c87d4-113">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
 <span data-ttu-id="c87d4-114">Esta sección proporciona instrucciones sobre cómo usar [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c87d4-114">This section provides instructions about how to use [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)], and [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c87d4-115">En esta sección</span><span class="sxs-lookup"><span data-stu-id="c87d4-115">In This Section</span></span>  
  
-   [<span data-ttu-id="c87d4-116">Conectarse a la base de datos de Oracle en Visual Studio mediante el servicio de adaptador</span><span class="sxs-lookup"><span data-stu-id="c87d4-116">Connect to the Oracle Database in Visual Studio using the Consume Adapter Service</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-oracle-database-in-visual-studio-using-the-consume-adapter-service.md) 
  
-   [<span data-ttu-id="c87d4-117">Examinar, buscar y obtener los metadatos de las operaciones de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="c87d4-117">Browse, search, and get metadata for Oracle Database operations</span></span>](../../adapters-and-accelerators/adapter-oracle-database/browse-search-and-get-metadata-for-oracle-database-operations.md)  
  
## <a name="see-also"></a><span data-ttu-id="c87d4-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c87d4-118">See Also</span></span>  
[<span data-ttu-id="c87d4-119">Desarrollar las aplicaciones de base de datos de Oracle</span><span class="sxs-lookup"><span data-stu-id="c87d4-119">Develop your Oracle Database applications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)