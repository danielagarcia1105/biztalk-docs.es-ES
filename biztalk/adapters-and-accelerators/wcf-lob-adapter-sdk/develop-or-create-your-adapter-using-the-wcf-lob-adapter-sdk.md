---
title: Desarrollar o crear el adaptador mediante el SDK de adaptador LOB de WCF | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2ca8c03a-1e4a-4077-b4cb-4e184b520bbb
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e7e4c76add25b53a8b3e32707c6a09b92636559
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="develop-or-create-your-adapter-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="09217-102">Desarrollar o crear el adaptador mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="09217-102">Develop or create your adapter using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="09217-103">Esta sección contiene información para programadores que crean adaptadores que usan el [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="09217-103">This section contains information for developers who are creating adapters using the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)].</span></span> <span data-ttu-id="09217-104">Una vez que el adaptador se ha desarrollado, normalmente se consume en .NET o [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] a los desarrolladores una manera de tener acceso a las operaciones y datos en un sistema de línea de negocio de destino deseado.</span><span class="sxs-lookup"><span data-stu-id="09217-104">Once the adapter has been developed, it is usually consumed by either .NET or [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] developers as a way to access operations and data in a desired target line-of-business system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="09217-105">En esta sección</span><span class="sxs-lookup"><span data-stu-id="09217-105">In This Section</span></span>  
  
-   [<span data-ttu-id="09217-106">Prácticas recomendadas de desarrollo mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="09217-106">Development Best Practices using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/development-best-practices-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="09217-107">Usar espacios de nombres con el Proxy de WSDL en el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="09217-107">Use namespaces with the WSDL-Proxy in the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/use-namespaces-with-the-wsdl-proxy-in-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="09217-108">Describe el esquema de documentación de WSDL PortType con el SDK del adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="09217-108">Describe the WSDL PortType Documentation Schema with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/describe-the-wsdl-porttype-documentation-schema-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="09217-109">Administrar el control de versiones de adaptador con el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="09217-109">Manage adapter versioning with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/manage-adapter-versioning-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="09217-110">Utilizar un comportamiento de servicio para especificar las credenciales con el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="09217-110">Use a Service Behavior to enter credentials with the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/use-a-service-behavior-to-enter-credentials-with-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="09217-111">Exponer la configuración del adaptador como propiedad de enlace mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="09217-111">Expose adapter settings as binding property using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/expose-adapter-settings-as-a-binding-property-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="09217-112">Examinar y buscar los metadatos mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="09217-112">Browse and Search Metadata using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/browse-and-search-metadata-using-the-wcf-lob-adapter-sdk.md)  
  
-   [<span data-ttu-id="09217-113">Compatibilidad con transacciones</span><span class="sxs-lookup"><span data-stu-id="09217-113">Transaction Support</span></span>](../../core/transaction-support.md)  
  
-   [<span data-ttu-id="09217-114">Hospedar un adaptador en IIS mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="09217-114">Host an adapter in IIS using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/host-an-adapter-in-iis-using-the-wcf-lob-adapter-sdk.md) 
  
-   [<span data-ttu-id="09217-115">Utilizar un adaptador creado mediante el SDK de adaptador LOB de WCF</span><span class="sxs-lookup"><span data-stu-id="09217-115">Consume an Adapter created using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/consume-an-adapter-created-using-the-wcf-lob-adapter-sdk.md)  
  
## <a name="see-also"></a><span data-ttu-id="09217-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="09217-116">See Also</span></span>  
 <span data-ttu-id="09217-117">[Empezar a trabajar con el SDK de adaptador LOB de WCF](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md) </span><span class="sxs-lookup"><span data-stu-id="09217-117">[Get started with the WCF LOB Adapter SDK](../../adapters-and-accelerators/wcf-lob-adapter-sdk/get-started-with-the-with-the-wcf-lob-adapter-sdk.md) </span></span>  
 [<span data-ttu-id="09217-118">Solución de problemas de los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="09217-118">Troubleshooting the WCF Adapters</span></span>](../../core/troubleshooting-the-wcf-adapters.md)