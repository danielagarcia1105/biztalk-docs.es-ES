---
title: Obtiene los metadatos para operaciones de Siebel en Visual Studio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: metadata, retrieving for Siebel operations in Visual Studio
ms.assetid: 63643942-6497-4891-ad7d-34b1df9acbc1
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30935631052adf4c455e730c476104b54a6a352b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="get-metadata-for-siebel-operations-in-visual-studio"></a><span data-ttu-id="e9914-102">Obtiene los metadatos para operaciones de Siebel en Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e9914-102">Get Metadata for Siebel Operations in Visual Studio</span></span>
<span data-ttu-id="e9914-103">El [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] proporciona dos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes que puede utilizar para ayudarle a desarrollar soluciones mediante el adaptador.</span><span class="sxs-lookup"><span data-stu-id="e9914-103">The [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] provides two [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components that you can use to help you develop solutions using the adapter.</span></span>  
  
-   <span data-ttu-id="e9914-104">La [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] está disponible en proyectos de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="e9914-104">The [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] is available in BizTalk Server projects.</span></span> <span data-ttu-id="e9914-105">Utiliza el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] para generar esquemas de mensaje (XSD) para las operaciones que desea tener como destino de la solución de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e9914-105">You use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] to generate message schemas (XSDs) for operations that you want to target in your BizTalk solution.</span></span> <span data-ttu-id="e9914-106">Para obtener más información sobre cómo desarrollar soluciones con BizTalk Server, vea [aplicaciones de BizTalk de desarrollar con el adaptador de Siebel](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="e9914-106">For more information about developing solutions with BizTalk Server, see [Develop BizTalk applications using the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/develop-biztalk-applications-using-the-siebel-adapter.md).</span></span>
  
-   <span data-ttu-id="e9914-107">La [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] está disponible en proyectos de programación no sean de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="e9914-107">The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] is available in non-BizTalk programming projects.</span></span> <span data-ttu-id="e9914-108">Utiliza el [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para generar una clase de cliente WCF o una interfaz de devolución de llamada de servicio WCF cuando se desarrollan soluciones mediante el modelo de servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="e9914-108">You use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] to generate a WCF client class or a WCF service callback interface when you develop solutions using the WCF service model.</span></span> <span data-ttu-id="e9914-109">Para obtener más información sobre cómo desarrollar soluciones con el modelo de servicio WCF, vea [aplicaciones Siebel desarrollar mediante el modelo de servicio de WCF](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).</span><span class="sxs-lookup"><span data-stu-id="e9914-109">For more information about developing solutions with the WCF service model, see [Develop Siebel applications using the WCF Service Model](../../adapters-and-accelerators/adapter-siebel/develop-siebel-applications-using-the-wcf-service-model.md).</span></span>  
  
 <span data-ttu-id="e9914-110">Ambos [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] componentes simplifican el desarrollo mediante:</span><span class="sxs-lookup"><span data-stu-id="e9914-110">Both of these [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] components simplify development by:</span></span>  
  
-   <span data-ttu-id="e9914-111">Proporcionar una interfaz de Microsoft Windows a través del cual se puede examinar y buscar para las operaciones que desea utilizar en la solución.</span><span class="sxs-lookup"><span data-stu-id="e9914-111">Providing a Microsoft Windows interface through which you can browse and search for operations that you want to use in your solution.</span></span>  
  
-   <span data-ttu-id="e9914-112">Al recuperar los metadatos expuestos por el adaptador para estas operaciones de destino.</span><span class="sxs-lookup"><span data-stu-id="e9914-112">Retrieving metadata exposed by the adapter for these target operations.</span></span>  
  
-   <span data-ttu-id="e9914-113">Convertir que los metadatos, que se expresa como un documento de lenguaje de descripción de servicios Web (WSDL) por el adaptador, en un formulario que puede usar en la solución (esquemas de mensaje XSD para los proyectos de BizTalk o una representación de objeto de .NET de un contrato de servicio de WCF modelo de servicio) y lo agrega al proyecto.</span><span class="sxs-lookup"><span data-stu-id="e9914-113">Converting that metadata, which is expressed as a Web Services Description Language (WSDL) document by the adapter, into a form that you can use in your solution (XSD message schemas for BizTalk projects or a .NET object representation of a service contract for the WCF service model) and adding it to your project.</span></span>  
  
 <span data-ttu-id="e9914-114">Esta sección proporciona instrucciones sobre cómo usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e9914-114">This section provides instructions about how to use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] and the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].</span></span>  
  

  
## <a name="see-also"></a><span data-ttu-id="e9914-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e9914-115">See Also</span></span>  
[<span data-ttu-id="e9914-116">Desarrollar las aplicaciones de Siebel</span><span class="sxs-lookup"><span data-stu-id="e9914-116">Develop your Siebel applications</span></span>](../../adapters-and-accelerators/adapter-siebel/develop-your-siebel-applications.md)