---
title: Esquemas de sobres | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: af296c30-95dc-4fef-9aa3-bea2f2cd8caf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03c44f1a5d9797ec09cc164789148287c98b4399
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="envelope-schemas"></a><span data-ttu-id="6960a-102">Esquemas de sobres</span><span class="sxs-lookup"><span data-stu-id="6960a-102">Envelope Schemas</span></span>

## <a name="overview"></a><span data-ttu-id="6960a-103">Información general</span><span class="sxs-lookup"><span data-stu-id="6960a-103">Overview</span></span>
<span data-ttu-id="6960a-104">Puede crear un esquema de sobre de las mismas maneras con las que crea un esquema XML de un documento empresarial.</span><span class="sxs-lookup"><span data-stu-id="6960a-104">You can create an envelope schema in all of the same ways that you can create an XML schema for a business document.</span></span> <span data-ttu-id="6960a-105">Puede crear un esquema a partir de un mensaje de instancia de sobre XML bien estructurado o a partir de representaciones DTD (definición de tipo de documento) o XDR (datos reducidos XML) del esquema de sobre.</span><span class="sxs-lookup"><span data-stu-id="6960a-105">You can create a schema from a well-formed XML envelope instance message, or from Document Type Definition (DTD) or XML-Data reduced (XDR) representations of the envelope schema.</span></span> <span data-ttu-id="6960a-106">Asimismo, puede crear un nuevo esquema, bien junto con otros esquemas o bien de forma aislada.</span><span class="sxs-lookup"><span data-stu-id="6960a-106">Or, you can create a new schema, either in conjunction with other schemas or not.</span></span> <span data-ttu-id="6960a-107">Como los esquemas de sobre son normalmente más pequeños y menos complicados que la mayoría de los esquemas de documentos empresariales, la creación de un esquema de sobre nuevo es normalmente una alternativa viable.</span><span class="sxs-lookup"><span data-stu-id="6960a-107">Because envelope schemas are generally much smaller and less complicated than most business document schemas, creating new envelope schemas is usually a viable alternative.</span></span>  
  
 <span data-ttu-id="6960a-108">Para definir un esquema como esquema de sobres, debe establecer el **sobres** propiedad de la **esquema** nodo en el valor **Sí**.</span><span class="sxs-lookup"><span data-stu-id="6960a-108">To define a schema as an envelope schema, you need to set the **Envelope** property of the **Schema** node to the value **Yes**.</span></span> <span data-ttu-id="6960a-109">Cuando se define un esquema de sobre, debe señalar la envoltura **XPath de cuerpo** para el nodo primario que contiene únicamente el \<cualquier > elemento secundario.</span><span class="sxs-lookup"><span data-stu-id="6960a-109">When you define an envelope schema, you should point the envelope's **Body XPath** to the parent node that contains only the \<any> child element.</span></span> <span data-ttu-id="6960a-110">Para que el ensamblador XML pueda usar el sobre, el nodo primario no debe contener ningún otro elemento.</span><span class="sxs-lookup"><span data-stu-id="6960a-110">In order for the XML assembler to use the envelope, the parent node must not contain any other elements.</span></span>  
  
 <span data-ttu-id="6960a-111">Al establecer **sobres** propiedad **Sí**, significa que el contenido real del mensaje del mensaje de instancia XML (denominado cuerpo del mensaje) está presente en algún lugar dentro de la raíz **registro**  nodo del esquema, según lo especificado por el **XPath de cuerpo** propiedad de ese nodo.</span><span class="sxs-lookup"><span data-stu-id="6960a-111">When you set **Envelope** property to **Yes**, it means that the actual message content of the XML instance message (called the body of the message) is present somewhere inside the root **Record** node of this schema, as specified by the **Body XPath** property of that node.</span></span> <span data-ttu-id="6960a-112">Por tanto, también debe establecer propiedades adicionales según algunas circunstancias:</span><span class="sxs-lookup"><span data-stu-id="6960a-112">Therefore, you must also set additional properties based on a variety of conditions:</span></span>  
  
-   <span data-ttu-id="6960a-113">Si un esquema de sobre tiene una única raíz, debe establecer el **XPath de cuerpo** propiedad para ese nodo raíz.</span><span class="sxs-lookup"><span data-stu-id="6960a-113">If an envelope schema has a single root, you must set the **Body XPath** property for that root.</span></span>  
  
-   <span data-ttu-id="6960a-114">Si un esquema de sobre tiene varias raíces y la **referencia raíz** no está establecida la propiedad, debe establecer el **XPath de cuerpo** propiedad para todas las raíces.</span><span class="sxs-lookup"><span data-stu-id="6960a-114">If an envelope schema has multiple roots and the **Root Reference** property is not set, you must set the **Body XPath** property for all roots.</span></span>  
  
-   <span data-ttu-id="6960a-115">Si un esquema de sobre tiene varias raíces y la **referencia raíz** propiedad está establecida, se debe establecer el **XPath de cuerpo** propiedad de la raíz correspondiente **registro** nodo.</span><span class="sxs-lookup"><span data-stu-id="6960a-115">If an envelope schema has multiple roots and the **Root Reference** property is set, you must set the **Body XPath** property of the corresponding root **Record** node.</span></span> <span data-ttu-id="6960a-116">Opcionalmente, puede establecer la **XPath de cuerpo** propiedad para el resto de las raíces.</span><span class="sxs-lookup"><span data-stu-id="6960a-116">You can optionally set the **Body XPath** property for the remaining roots.</span></span>  
  
-   <span data-ttu-id="6960a-117">Independientemente de si un esquema de sobre tiene una o varias raíces, establecer el **[referencia raíz** propiedad no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="6960a-117">Regardless of whether an envelope schema has a single root or multiple roots, setting the **[Root Reference** property is not required.</span></span>  

<span data-ttu-id="6960a-118">Para obtener más información acerca de estas propiedades [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="6960a-118">More details on these properties [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6960a-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="6960a-119">See Also</span></span>  
 <span data-ttu-id="6960a-120">[Diferentes tipos de esquemas de BizTalk](../core/different-types-of-biztalk-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="6960a-120">[Different Types of BizTalk Schemas](../core/different-types-of-biztalk-schemas.md) </span></span>  
 [<span data-ttu-id="6960a-121">Cómo crear esquemas de sobres</span><span class="sxs-lookup"><span data-stu-id="6960a-121">How to Create Schemas for Envelopes</span></span>](../core/how-to-create-schemas-for-envelopes.md)