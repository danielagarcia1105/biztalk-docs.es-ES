---
title: Extender la resolución y el marco de proveedores de adaptador | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d5e6f2-b3bc-46e2-b8f7-d7e271d4a8c0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6ab5caf03d113e313e00a74c11641058e86b886
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294084"
---
# <a name="extending-the-resolver-and-adapter-provider-framework"></a><span data-ttu-id="16ce6-102">Extender la resolución y el marco de proveedores de adaptador</span><span class="sxs-lookup"><span data-stu-id="16ce6-102">Extending the Resolver and Adapter Provider Framework</span></span>
<span data-ttu-id="16ce6-103">La resolución y el marco de proveedores de adaptador proporciona compatibilidad para el punto de conexión y la resolución de transformación y del enrutamiento, y también puede proporcionar metadatos personalizados para los servicios.</span><span class="sxs-lookup"><span data-stu-id="16ce6-103">The Resolver and Adapter Provider Framework provides support for endpoint and transformation resolution and routing, and it can also provide custom metadata for services.</span></span> <span data-ttu-id="16ce6-104">El marco de trabajo puede resolver los puntos de conexión y establecer las propiedades de salida del adaptador dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="16ce6-104">The framework can dynamically resolve endpoints and set outbound adapter properties.</span></span> <span data-ttu-id="16ce6-105">Después de la resolución de una componente resuelve un punto de conexión (por ejemplo, con Universal Description, Discovery e integración [UDDI] para buscar una dirección URL saliente), un componente de proveedor de adaptador establece propiedades específicas de los adaptadores de Microsoft BizTalk Server registrados.</span><span class="sxs-lookup"><span data-stu-id="16ce6-105">After a resolver component resolves an endpoint (for example, using Universal Description, Discovery, and Integration [UDDI] to look up an outbound URL), an adapter provider component sets specific properties of registered Microsoft BizTalk Server adapters.</span></span>  
  
 <span data-ttu-id="16ce6-106">Hay tres áreas principales donde puede ampliar la resolución y el marco de proveedores de adaptador:</span><span class="sxs-lookup"><span data-stu-id="16ce6-106">There are three main areas where you can extend the Resolver and Adapter Provider Framework:</span></span>  
  
-   [<span data-ttu-id="16ce6-107">Crear a una resolución personalizada</span><span class="sxs-lookup"><span data-stu-id="16ce6-107">Creating a Custom Resolver</span></span>](../esb-toolkit/creating-a-custom-resolver.md)  
  
-   [<span data-ttu-id="16ce6-108">Crear a una resolución personalizada con un contenedor de Unity</span><span class="sxs-lookup"><span data-stu-id="16ce6-108">Creating a Custom Resolver with a Unity Container</span></span>](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)  
  
-   [<span data-ttu-id="16ce6-109">Crear un proveedor de adaptador personalizado</span><span class="sxs-lookup"><span data-stu-id="16ce6-109">Creating a Custom Adapter Provider</span></span>](../esb-toolkit/creating-a-custom-adapter-provider.md)