---
title: "Vínculos en asignaciones | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- functoid types, Looping
- Looping functoids
- maps, links
- BizTalk Mapper, links
ms.assetid: 3db77b8d-7b86-4c00-99a0-0513aff9b56b
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a32d2a9ef07cf2d79037d7983e49b26c6cfe5e81
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="links-in-maps"></a><span data-ttu-id="861ea-102">Vínculos en asignaciones</span><span class="sxs-lookup"><span data-stu-id="861ea-102">Links in Maps</span></span>
<span data-ttu-id="861ea-103">Los vínculos especifican la función básica de copiar datos de un elemento o atributo de un mensaje de instancia de entrada en un elemento o atributo de una instancia de salida.</span><span class="sxs-lookup"><span data-stu-id="861ea-103">Links specify the basic function of copying data from an element or attribute in an input instance message to an element or attribute in an output instance.</span></span> <span data-ttu-id="861ea-104">Los vínculos entre registros y campos en los esquemas de origen y de destino se crean en tiempo de diseño.</span><span class="sxs-lookup"><span data-stu-id="861ea-104">You create links between records and fields in the source and destination schemas at design time.</span></span> <span data-ttu-id="861ea-105">De esta forma, se impulsa la creación, en tiempo de ejecución, de un mensaje de instancia de salida que se ajusta al esquema de destino desde un mensaje de instancia de entrada que se ajusta al esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="861ea-105">This drives the creation, at run time, of an output instance message conforming to the destination schema from an input instance message conforming to the source schema.</span></span>  
  
 <span data-ttu-id="861ea-106">El Asignador de BizTalk admite vínculos de uno a uno y de uno a muchos.</span><span class="sxs-lookup"><span data-stu-id="861ea-106">BizTalk Mapper supports one-to-one links and one-to-many links.</span></span> <span data-ttu-id="861ea-107">Por ejemplo, un vínculo puede conectar un registro o campo único del esquema de origen con un registro o campo único del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="861ea-107">For example, a link can connect a single record or field from the source schema to a single record or field in the destination schema.</span></span> <span data-ttu-id="861ea-108">Un vínculo también puede conectar un registro o campo único del esquema de origen con múltiples registros o campos del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="861ea-108">A link can also connect a single record or field from the source schema to multiple records or fields in the destination schema.</span></span>  
  
 <span data-ttu-id="861ea-109">Los vínculos también pueden conectar varios registros o campos del esquema de origen con un functoid que, a continuación, se conecta con uno o varios registros o campos únicos del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="861ea-109">Links can also connect multiple records or fields from the source schema to a functoid, which then connects to a single (or multiple) record(s) and/or field(s) in the destination schema.</span></span> <span data-ttu-id="861ea-110">En general, los vínculos directos desde varios registros o campos de origen hasta un registro o campo de destino único no son válidos y generan una advertencia.</span><span class="sxs-lookup"><span data-stu-id="861ea-110">In general, direct links from multiple source records or fields to a single destination record or field are not valid and produce a warning.</span></span> <span data-ttu-id="861ea-111">Una excepción a esto es el **bucle** functoid.</span><span class="sxs-lookup"><span data-stu-id="861ea-111">One exception to this is the **Looping** functoid.</span></span> <span data-ttu-id="861ea-112">Para obtener más información sobre la **bucle** functoid, consulte [Functoid de bucle de](../core/looping-functoid.md).</span><span class="sxs-lookup"><span data-stu-id="861ea-112">For more information about the **Looping** functoid, see [Looping Functoid](../core/looping-functoid.md).</span></span>  
  
 <span data-ttu-id="861ea-113">En los temas de esta sección se describen conceptos relativos a la creación y el trabajo con vínculos en el Asignador de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="861ea-113">The topics in this section describe concepts related to creating and working with links in BizTalk Mapper.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="861ea-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="861ea-114">In This Section</span></span>  
  
-   [<span data-ttu-id="861ea-115">Tipos de vínculos</span><span class="sxs-lookup"><span data-stu-id="861ea-115">Types of Links</span></span>](../core/types-of-links.md)  
  
-   [<span data-ttu-id="861ea-116">Crear vínculos</span><span class="sxs-lookup"><span data-stu-id="861ea-116">Creating Links</span></span>](../core/creating-links.md)  
  
-   [<span data-ttu-id="861ea-117">Configuración de vínculos</span><span class="sxs-lookup"><span data-stu-id="861ea-117">Configuring Links</span></span>](../core/configuring-links.md)  
  
-   [<span data-ttu-id="861ea-118">Vinculación de registro a registro</span><span class="sxs-lookup"><span data-stu-id="861ea-118">Record-to-Record Linking</span></span>](../core/record-to-record-linking.md)  
  
-   [<span data-ttu-id="861ea-119">Vínculos a y desde el elemento Any y anyAttribute nodos</span><span class="sxs-lookup"><span data-stu-id="861ea-119">Links To and From the Any Element and anyAttribute Nodes</span></span>](../core/links-to-and-from-the-any-element-and-anyattribute-nodes.md)  
  
-   [<span data-ttu-id="861ea-120">Vínculos y directivas de compilador</span><span class="sxs-lookup"><span data-stu-id="861ea-120">Compiler Directives and Links</span></span>](../core/compiler-directives-and-links.md)