---
title: Características en el adaptador de Siebel clave | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- features, performance-related
- adapter features, new
- features, technology-related
- features, metadata-related
- adapter features, operations-related
- adapter features, performance-related
- features, new
- features, operations-related
- adapter features, metadata-related
ms.assetid: 4612c9ab-810e-4c69-9168-a25c58682e71
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 295ff8b13358109a5d4737fb5f9325b3c9caa0f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222132"
---
# <a name="key-features-in-the-siebel-adapter"></a><span data-ttu-id="d54ed-102">Características clave en el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="d54ed-102">Key features in the Siebel Adapter</span></span>
<span data-ttu-id="d54ed-103">Esta sección enumeran las nuevas características de [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d54ed-103">This section lists the new features in [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d54ed-104">En este tema se ha utilizado desde la versión anterior de [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] ayuda.</span><span class="sxs-lookup"><span data-stu-id="d54ed-104">This topic has been used from the previous version of [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] Help.</span></span>  
  
## <a name="new-features-in-the-siebel-adapter"></a><span data-ttu-id="d54ed-105">Nuevas características en el adaptador de Siebel</span><span class="sxs-lookup"><span data-stu-id="d54ed-105">New Features in the Siebel Adapter</span></span>  
 <span data-ttu-id="d54ed-106">Los siguientes son las nuevas características introducidas en esta versión de la [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d54ed-106">The following are the new features introduced in this release of the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
### <a name="technology-related-features"></a><span data-ttu-id="d54ed-107">Características relacionadas con la tecnología</span><span class="sxs-lookup"><span data-stu-id="d54ed-107">Technology-Related Features</span></span>  
  
|<span data-ttu-id="d54ed-108">Característica</span><span class="sxs-lookup"><span data-stu-id="d54ed-108">Feature</span></span>|<span data-ttu-id="d54ed-109">Comentario</span><span class="sxs-lookup"><span data-stu-id="d54ed-109">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="d54ed-110">Compatibilidad para usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] con Microsoft Office SharePoint Server (MOSS)</span><span class="sxs-lookup"><span data-stu-id="d54ed-110">Support for using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] with Microsoft Office SharePoint Server (MOSS)</span></span>|<span data-ttu-id="d54ed-111">Puede utilizar los adaptadores para presentar los datos en el sistema Siebel en un portal MOSS.</span><span class="sxs-lookup"><span data-stu-id="d54ed-111">You can use the adapters to present data from the Siebel system onto a MOSS portal.</span></span> <span data-ttu-id="d54ed-112">Para obtener más información, consulte [usa el adaptador de Siebel con Microsoft Office SharePoint Server](https://msdn.microsoft.com/library/dd788017.aspx).</span><span class="sxs-lookup"><span data-stu-id="d54ed-112">For more information, see [Using the Siebel Adapter with Microsoft Office SharePoint Server](https://msdn.microsoft.com/library/dd788017.aspx).</span></span>|  
  
### <a name="operations-related-features"></a><span data-ttu-id="d54ed-113">Características relacionadas con las operaciones</span><span class="sxs-lookup"><span data-stu-id="d54ed-113">Operations-Related Features</span></span>  
  
|<span data-ttu-id="d54ed-114">Característica</span><span class="sxs-lookup"><span data-stu-id="d54ed-114">Feature</span></span>|<span data-ttu-id="d54ed-115">Comentario</span><span class="sxs-lookup"><span data-stu-id="d54ed-115">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="d54ed-116">Soporte para la operación de asociación en componentes empresariales</span><span class="sxs-lookup"><span data-stu-id="d54ed-116">Support for ASSOCIATE operation on business components</span></span>|<span data-ttu-id="d54ed-117">Los clientes de adaptador pueden asociar registros especificando expresiones de búsqueda primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="d54ed-117">Adapter clients can associate records by specifying search expressions for parent and child records.</span></span> <span data-ttu-id="d54ed-118">Esto es aplicable sólo para los componentes empresariales con campos de grupo con varios valores (MVG).</span><span class="sxs-lookup"><span data-stu-id="d54ed-118">This is applicable only for business components with multivalued group (MVG) fields.</span></span> <span data-ttu-id="d54ed-119">Tenga en cuenta que las expresiones de búsqueda deben utilizar un filtro exactamente un registro para el elemento primario y el secundario componentes empresariales.</span><span class="sxs-lookup"><span data-stu-id="d54ed-119">Note that the search expressions should filter exactly one record for both the parent and child business components.</span></span>|  
|<span data-ttu-id="d54ed-120">Soporte para la operación de DESASOCIAR en componentes empresariales</span><span class="sxs-lookup"><span data-stu-id="d54ed-120">Support for DISASSOCIATE operation on business components</span></span>|<span data-ttu-id="d54ed-121">Los clientes de adaptador pueden anular la asociación de registros mediante la especificación de expresiones de búsqueda primarios y secundarios.</span><span class="sxs-lookup"><span data-stu-id="d54ed-121">Adapter clients can dissociate records by specifying search expressions for parent and child records.</span></span> <span data-ttu-id="d54ed-122">Esto es aplicable sólo para los componentes empresariales con campos de grupo con varios valores (MVG).</span><span class="sxs-lookup"><span data-stu-id="d54ed-122">This is applicable only for business components with multivalued group (MVG) fields.</span></span> <span data-ttu-id="d54ed-123">Tenga en cuenta que las expresiones de búsqueda deben filtrar exactamente un registro para el elemento primario y el secundario componentes empresariales.</span><span class="sxs-lookup"><span data-stu-id="d54ed-123">Note that the search expressions must filter exactly one record for both the parent and child business components.</span></span>|  
|<span data-ttu-id="d54ed-124">Compatibilidad con las consultas de vínculo con varios valores</span><span class="sxs-lookup"><span data-stu-id="d54ed-124">Support for multivalue link queries</span></span>|<span data-ttu-id="d54ed-125">Los clientes de adaptador pueden consultar los registros secundarios asociados a un registro primario especificando el registro primario y el nombre del campo con varios valores.</span><span class="sxs-lookup"><span data-stu-id="d54ed-125">Adapter clients can query the child records associated with a parent record by specifying the parent record and the multivalued field name.</span></span> <span data-ttu-id="d54ed-126">Esto es aplicable sólo para los componentes empresariales con campos de grupo con varios valores (MVG).</span><span class="sxs-lookup"><span data-stu-id="d54ed-126">This is applicable only for business components with multivalued group (MVG) fields.</span></span>|  
  
### <a name="other-features"></a><span data-ttu-id="d54ed-127">Otras características</span><span class="sxs-lookup"><span data-stu-id="d54ed-127">Other Features</span></span>  
  
|<span data-ttu-id="d54ed-128">Característica</span><span class="sxs-lookup"><span data-stu-id="d54ed-128">Feature</span></span>|<span data-ttu-id="d54ed-129">Comentario</span><span class="sxs-lookup"><span data-stu-id="d54ed-129">Comment</span></span>|  
|-------------|-------------|  
|<span data-ttu-id="d54ed-130">Nueva forma de utilizar el adaptador en[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d54ed-130">New way of using the adapter in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]</span></span>|<span data-ttu-id="d54ed-131">La [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] puede usarse como un puerto de WCF-Custom o WCF-Siebel en BizTalk.</span><span class="sxs-lookup"><span data-stu-id="d54ed-131">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] can be used in BizTalk either as a WCF-Custom port or a WCF-Siebel port.</span></span> <span data-ttu-id="d54ed-132">Si desea utilizar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto personalizado de WCF, no es necesario agregar el puerto personalizado de WCF para la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración porque el puerto WCF personalizado se agrega a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d54ed-132">If you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Custom port, you do not need to add the WCF-Custom port to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console because the WCF-Custom port is added to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console by default.</span></span> <span data-ttu-id="d54ed-133">Sin embargo, si desea usar el [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] a través de un puerto de WCF-Siebel, primero debe agregar el adaptador de WCF-Siebel a la [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="d54ed-133">However, if you want to use the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] through a WCF-Siebel port, you must first add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="d54ed-134">Para obtener más información, consulte [agregar el adaptador de Siebel a la consola de administración de BizTalk Server](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span><span class="sxs-lookup"><span data-stu-id="d54ed-134">For more information, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d54ed-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="d54ed-135">See Also</span></span>  
 [<span data-ttu-id="d54ed-136">Comprender el adaptador de BizTalk para Siebel eBusiness Applications</span><span class="sxs-lookup"><span data-stu-id="d54ed-136">Understand BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/understand-biztalk-adapter-for-siebel-ebusiness-applications.md)