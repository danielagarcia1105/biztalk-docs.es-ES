---
title: Administración de Namespace | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4638c47c-3cdd-43af-aa00-da98e7293503
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa476034a578be24bf388c87f38f910565cd2548
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022474"
---
# <a name="namespace-management"></a><span data-ttu-id="6152f-102">Administrador de espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="6152f-102">Namespace Management</span></span>
<span data-ttu-id="6152f-103">El Editor de BizTalk proporciona compatibilidad para los espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="6152f-103">BizTalk Editor provides support for namespaces.</span></span> <span data-ttu-id="6152f-104">Un espacio de nombres XML es una colección de nombres que se puede usar como nombres de elemento o atributo en un mensaje XML.</span><span class="sxs-lookup"><span data-stu-id="6152f-104">An XML namespace is a collection of names that can be used as element or attribute names in an XML message.</span></span> <span data-ttu-id="6152f-105">El espacio de nombres califica los nombres de elemento y atributo para evitar conflictos entre los mismos nombres de elemento y atributo que se pueden definir en cualquier lugar dentro del mismo esquema.</span><span class="sxs-lookup"><span data-stu-id="6152f-105">The namespace qualifies element and attribute names to avoid conflicts between the same element and attribute names that might be defined elsewhere within the same schema.</span></span>  
  
 <span data-ttu-id="6152f-106">Los espacios de nombres se identifican con un Identificador de recursos universal (URI), bien como Localizador uniforme de recursos (URL) o como Nombre de recursos uniforme (URN).</span><span class="sxs-lookup"><span data-stu-id="6152f-106">Namespaces are identified by a Universal Resource Identifier (URI), either as a Uniform Resource Locator (URL) or a Uniform Resource Name (URN).</span></span> <span data-ttu-id="6152f-107">También reciben un alias de prefijo normalmente corto que lleva antepuesto dos puntos (:) al nombre del elemento o del atributo)</span><span class="sxs-lookup"><span data-stu-id="6152f-107">They are also given a typically short prefix alias that is prepended with a separating colon (:) from the element or attribute name itself.</span></span> <span data-ttu-id="6152f-108">Por ejemplo, es habitual ver la siguiente declaración de espacio de nombres dentro de la **esquema** elemento en la representación XSD del esquema.</span><span class="sxs-lookup"><span data-stu-id="6152f-108">For example, it is common to see the following namespace declaration within the **schema** element in the XSD representation of the schema.</span></span>  
  
```  
xmlns:xs="http://www.w3.org/2001/XMLSchema"  
  
```  
  
 <span data-ttu-id="6152f-109">El prefijo es xs, puede ver en la representación XSD, calificar elementos tales como el **elemento** (xs: element) y el **atributo** elemento (cualifica).</span><span class="sxs-lookup"><span data-stu-id="6152f-109">The prefix is xs, which you see throughout the XSD representation, qualifying such elements as the **element** element (xs:element) and the **attribute** element (xs:attribute).</span></span>  
  
 <span data-ttu-id="6152f-110">Cuando se crea un nuevo esquema, independientemente de si es un esquema de mensaje o un esquema de propiedad, es importante establecer el **Target Namespace** propiedad de la **esquema** nodo correctamente.</span><span class="sxs-lookup"><span data-stu-id="6152f-110">When you first create a new schema, regardless of whether it is a message schema or a property schema, it is important to set the **Target Namespace** property of the **Schema** node properly.</span></span> <span data-ttu-id="6152f-111">Debe establecer el espacio de nombres de destino antes de que otro esquema utilice el esquema con los mecanismos import, include y redefine, así como antes de que se defina cualquier promoción de propiedades.</span><span class="sxs-lookup"><span data-stu-id="6152f-111">You need to establish the target namespace before the schema is used by another schema with the import/include/redefine mechanisms, and before any property promotions are defined.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="6152f-112">Si va a utilizar dos espacios de nombres que varíen únicamente en las mayúsculas y minúsculas, la base de datos de BizTalk Server se debe instalar con una intercalación que distinga entre mayúsculas y minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6152f-112">If you will be using two namespaces that vary only by case, the BizTalk database must be installed with a case-sensitive collation.</span></span> <span data-ttu-id="6152f-113">Los ejemplos de intercalaciones que distinguen mayúsculas de minúsculas incluyen intercalaciones binarias y no binarias con la distinción de mayúsculas de minúsculas habilitada.</span><span class="sxs-lookup"><span data-stu-id="6152f-113">Examples of case-sensitive collations include binary and non-binary collations with case-sensitivity enabled.</span></span> <span data-ttu-id="6152f-114">De no hacerlo, se producirán errores en la resolución de esquemas, ya que XML distingue mayúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="6152f-114">If this is not done, schema resolution will fail because XML is case-sensitive.</span></span>  
  
 <span data-ttu-id="6152f-115">Los dos siguientes espacios de nombres se agregan automáticamente como declaraciones de espacios de nombres al elemento schema de la representación del esquema en el lenguaje de definición de esquemas XML (XSD):</span><span class="sxs-lookup"><span data-stu-id="6152f-115">The following two namespaces are automatically added as namespace declarations to the schema element in the XML Schema definition (XSD) language representation of the schema:</span></span>  
  
- <span data-ttu-id="6152f-116">xmlns: b = "<http://schemas.microsoft.com/BizTalk/2003>"</span><span class="sxs-lookup"><span data-stu-id="6152f-116">xmlns:b="<http://schemas.microsoft.com/BizTalk/2003>"</span></span>  
  
- <span data-ttu-id="6152f-117">xmlns: xs = "<http://www.w3.org/2001/XMLSchema>"</span><span class="sxs-lookup"><span data-stu-id="6152f-117">xmlns:xs="<http://www.w3.org/2001/XMLSchema>"</span></span>  
  
  <span data-ttu-id="6152f-118">Mientras use otros esquemas dentro del esquema que esté creando, se declararán otros espacios de nombres.</span><span class="sxs-lookup"><span data-stu-id="6152f-118">In the course of using other schemas within the schema you are creating, other namespaces will be declared.</span></span> <span data-ttu-id="6152f-119">Puede examinar estos espacios de nombres, así como los espacios de nombres incluidos automáticamente, en el **importaciones** cuadro de diálogo que puede tener acceso mediante el uso de la **importaciones** propiedad de la **esquema** nodo.</span><span class="sxs-lookup"><span data-stu-id="6152f-119">You can examine these namespaces, as well as the automatically included namespaces, in the **Imports** dialog box that you can access by using the **Imports** property of the **Schema** node.</span></span> <span data-ttu-id="6152f-120">Para obtener más información sobre el uso de otros tipos de datos declarados en otros esquemas dentro del esquema que está creando, consulte [esquemas que usan otros esquemas](../core/schemas-that-use-other-schemas.md) y [crear esquemas que usan otros esquemas](../core/how-to-create-schemas-that-use-other-schemas.md).</span><span class="sxs-lookup"><span data-stu-id="6152f-120">For more information about using other data types declared in other schemas within the schema you are creating, see [Schemas That Use Other Schemas](../core/schemas-that-use-other-schemas.md) and [Creating Schemas That Use Other Schemas](../core/how-to-create-schemas-that-use-other-schemas.md).</span></span>  
  
  <span data-ttu-id="6152f-121">Se pueden examinar los espacios de nombres asociados con esquemas de propiedades en el **promocionar propiedades** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="6152f-121">Namespaces associated with property schemas can be examined in the **Promote Properties** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6152f-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="6152f-122">See Also</span></span>  
 [<span data-ttu-id="6152f-123">Consideraciones al crear esquemas</span><span class="sxs-lookup"><span data-stu-id="6152f-123">Considerations When Creating Schemas</span></span>](../core/considerations-when-creating-schemas.md)