---
title: Elemento bamactivity de intercepción | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dee61b4-83cd-4a22-b8a6-1c1a7ea3648b
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd43869922e46187c8b2e06155d525e428edd905
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257068"
---
# <a name="interceptor-bamactivity-element"></a><span data-ttu-id="98311-102">Elemento BamActivity de intercepción</span><span class="sxs-lookup"><span data-stu-id="98311-102">Interceptor BamActivity Element</span></span>
<span data-ttu-id="98311-103">El **BamActivity** elemento define una sola actividad BAM.</span><span class="sxs-lookup"><span data-stu-id="98311-103">The **BamActivity** element defines a single BAM activity.</span></span>  
  
## <a name="format"></a><span data-ttu-id="98311-104">Formato</span><span class="sxs-lookup"><span data-stu-id="98311-104">Format</span></span>  
 <span data-ttu-id="98311-105">El `BamActivity` elemento incluye un **nombre** de atributo y contiene uno o varios `OnEvent` elementos.</span><span class="sxs-lookup"><span data-stu-id="98311-105">The `BamActivity` element includes a **Name** attribute and contains one or more `OnEvent` elements.</span></span>  
  
```  
<ic:BamActivity Name="PurchaseOrder">  
  <!-- One or more OnEvent elements -->  
</ic:BamActivity>   
```  
  
### <a name="attributes"></a><span data-ttu-id="98311-106">Atributos</span><span class="sxs-lookup"><span data-stu-id="98311-106">Attributes</span></span>  
  
|<span data-ttu-id="98311-107">Nombre del atributo</span><span class="sxs-lookup"><span data-stu-id="98311-107">Attribute name</span></span>|<span data-ttu-id="98311-108">Description</span><span class="sxs-lookup"><span data-stu-id="98311-108">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="98311-109">Nombre</span><span class="sxs-lookup"><span data-stu-id="98311-109">Name</span></span>|<span data-ttu-id="98311-110">Nombre de la actividad de BAM definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="98311-110">User-defined name of the BAM activity.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="98311-111">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98311-111">Example</span></span>  
 <span data-ttu-id="98311-112">El siguiente ejemplo contiene una muestra de BamActivity para "MyOrderWorkflow" con un único elemento OnEvent.</span><span class="sxs-lookup"><span data-stu-id="98311-112">The following example contains a sample BamActivity for "MyOrderWorkflow" with a single OnEvent.</span></span>  
  
```  
<ic:BamActivity Name="MyOrderWorkflow">  
  <ic:OnEvent Name="MyActivityEvent"  Source="OrderWorkflow">  
    …  
  </ic:OnEvent>  
</ic:BamActivity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="98311-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="98311-113">See Also</span></span>  
 <span data-ttu-id="98311-114">[Elemento EventSource del interceptor](../core/interceptor-eventsource-element.md) </span><span class="sxs-lookup"><span data-stu-id="98311-114">[Interceptor EventSource Element](../core/interceptor-eventsource-element.md) </span></span>  
 [<span data-ttu-id="98311-115">Elemento OnEvent del interceptor</span><span class="sxs-lookup"><span data-stu-id="98311-115">Interceptor OnEvent Element</span></span>](../core/interceptor-onevent-element.md)