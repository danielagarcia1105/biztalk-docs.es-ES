---
title: El componente de distribuidor ESB | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 85655b5f-4717-42d1-b005-0a5592d5653b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe377221034637eab23b70c50ccf48a8454a23bf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294908"
---
# <a name="the-esb-dispatcher-component"></a><span data-ttu-id="74c37-102">El componente de distribuidor ESB</span><span class="sxs-lookup"><span data-stu-id="74c37-102">The ESB Dispatcher Component</span></span>
<span data-ttu-id="74c37-103">Basado en mensajería itinerarios servicios se ejecutan en el componente de distribuidor de ESB.</span><span class="sxs-lookup"><span data-stu-id="74c37-103">Messaging-based itinerary services are executed inside the ESB Dispatcher component.</span></span> <span data-ttu-id="74c37-104">El componente de distribuidor puede establecer propiedades de ubicación de punto de conexión para los mensajes salientes también dinámicamente y transformar mensajes de forma dinámica.</span><span class="sxs-lookup"><span data-stu-id="74c37-104">The Dispatcher component can also dynamically set endpoint location properties for outbound messages and dynamically transform messages.</span></span>  
  
## <a name="component-properties"></a><span data-ttu-id="74c37-105">Propiedades de componente</span><span class="sxs-lookup"><span data-stu-id="74c37-105">Component Properties</span></span>  
 <span data-ttu-id="74c37-106">El componente de distribuidor tiene seis propiedades:</span><span class="sxs-lookup"><span data-stu-id="74c37-106">The Dispatcher component has six properties:</span></span>  
  
-   <span data-ttu-id="74c37-107">**RoutingServiceName**.</span><span class="sxs-lookup"><span data-stu-id="74c37-107">**RoutingServiceName**.</span></span> <span data-ttu-id="74c37-108">Esta propiedad especifica el nombre registrado para el servicio de enrutamiento basado en mensajería.</span><span class="sxs-lookup"><span data-stu-id="74c37-108">This property specifies the registered name for the messaging-based routing service.</span></span> <span data-ttu-id="74c37-109">El valor predeterminado es **Microsoft.Practices.ESB.Services.Routing**.</span><span class="sxs-lookup"><span data-stu-id="74c37-109">The default value is **Microsoft.Practices.ESB.Services.Routing**.</span></span>  
  
-   <span data-ttu-id="74c37-110">**TransformServiceName**.</span><span class="sxs-lookup"><span data-stu-id="74c37-110">**TransformServiceName**.</span></span> <span data-ttu-id="74c37-111">Esta propiedad especifica el nombre registrado para el servicio de transformación basado en mensajería.</span><span class="sxs-lookup"><span data-stu-id="74c37-111">This property specifies the registered name for the messaging-based transform service.</span></span> <span data-ttu-id="74c37-112">El valor predeterminado es **Microsoft.Practices.ESB.Services.Transform**.</span><span class="sxs-lookup"><span data-stu-id="74c37-112">The default value is **Microsoft.Practices.ESB.Services.Transform**.</span></span>  
  
-   <span data-ttu-id="74c37-113">**Validar**.</span><span class="sxs-lookup"><span data-stu-id="74c37-113">**Validate**.</span></span> <span data-ttu-id="74c37-114">Esta propiedad especifica si es necesario validar un mensaje.</span><span class="sxs-lookup"><span data-stu-id="74c37-114">This property specifies whether a message needs to be validated.</span></span>  
  
-   <span data-ttu-id="74c37-115">**Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="74c37-115">**Enabled**.</span></span> <span data-ttu-id="74c37-116">Esta propiedad habilita o deshabilita el componente.</span><span class="sxs-lookup"><span data-stu-id="74c37-116">This property enables or disables the component.</span></span>  
  
-   <span data-ttu-id="74c37-117">**Punto de conexión**.</span><span class="sxs-lookup"><span data-stu-id="74c37-117">**Endpoint**.</span></span> <span data-ttu-id="74c37-118">Esta propiedad es una cadena de conexión de resolución en un formato registrado con el Kit de herramientas de BizTalk ESB.</span><span class="sxs-lookup"><span data-stu-id="74c37-118">This property is a resolver connection string in a format registered with BizTalk ESB Toolkit.</span></span>  
  
-   <span data-ttu-id="74c37-119">**Asignar nombre**.</span><span class="sxs-lookup"><span data-stu-id="74c37-119">**Map Name**.</span></span> <span data-ttu-id="74c37-120">Esta propiedad es el nombre completo de un mapa o un formato de cadena de conexión registrado en [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="74c37-120">This property is either the fully qualified name of a map or a connection string format registered with [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]:</span></span>  
  
    -   <span data-ttu-id="74c37-121">El siguiente es un ejemplo de un nombre de mapa:</span><span class="sxs-lookup"><span data-stu-id="74c37-121">The following is an example of a map name:</span></span>  
  
        ```  
        GlobalBank.ESB.DynamicResolution.Transforms.SubmitOrderRequestNA_To_SubmitOrderRequestCN, GlobalBank.ESB.DynamicResolution.Transforms, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c2c8b2b87f54180a  
        ```