---
title: Cómo insertar un nodo cualquier elemento o cualquier atributo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cbfdc04-6c83-4639-82de-169b6f009a2e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bce55126fe800841aef325f22de0afe62e03cec
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021079"
---
# <a name="how-to-insert-an-any-element-or-any-attribute-node"></a><span data-ttu-id="dc7f6-102">Cómo insertar un nodo cualquier elemento o cualquier atributo</span><span class="sxs-lookup"><span data-stu-id="dc7f6-102">How to Insert an Any Element or Any Attribute Node</span></span>
<span data-ttu-id="dc7f6-103">El Editor de BizTalk admite dos tipos de nodos: **cualquier elemento** y **cualquier atributo**.</span><span class="sxs-lookup"><span data-stu-id="dc7f6-103">BizTalk Editor supports two types of any nodes: **Any Element** and **Any Attribute**.</span></span> <span data-ttu-id="dc7f6-104">Estos nodos le permiten crear ubicaciones dentro del esquema que se correspondan con ubicaciones de los mensajes de instancia pertinentes donde no conoce qué elementos o atributos aparecerán.</span><span class="sxs-lookup"><span data-stu-id="dc7f6-104">These nodes allow you to create locations within your schema that correspond to locations within the corresponding instance messages where you do not know what elements or attributes will appear.</span></span> <span data-ttu-id="dc7f6-105">Para obtener información acerca de cómo se interpretan estos nodos al procesar los mensajes de instancia, consulte directamente la información disponible sobre el lenguaje de definición de esquemas XML (XSD) en Internet.</span><span class="sxs-lookup"><span data-stu-id="dc7f6-105">For detailed information about how these nodes are interpreted when processing instance messages, refer directly to information about the XML Schema definition (XSD) language on the Web.</span></span> <span data-ttu-id="dc7f6-106">Para obtener vínculos a esta información, consulte [recursos XSD en Internet](../core/xsd-resources-on-the-web.md).</span><span class="sxs-lookup"><span data-stu-id="dc7f6-106">For links to this information, see [XSD Resources on the Web](../core/xsd-resources-on-the-web.md).</span></span>  

## <a name="insert-an-any-element-node-or-an-any-attribute-node"></a><span data-ttu-id="dc7f6-107">Insertar un nodo cualquier elemento o un nodo cualquier atributo</span><span class="sxs-lookup"><span data-stu-id="dc7f6-107">Insert an Any Element node or an Any Attribute node</span></span>  

1.  <span data-ttu-id="dc7f6-108">En la vista de árbol de esquema, seleccione el **registro** nodo en el que desea insertar el **cualquier elemento** nodo o la **cualquier atributo** nodo.</span><span class="sxs-lookup"><span data-stu-id="dc7f6-108">In the schema tree view, select the **Record** node into which you want to insert the **Any Element** node or the **Any Attribute** node.</span></span>  

2.  <span data-ttu-id="dc7f6-109">En el **BizTalk** menú, elija **Insertar nodo de esquema**y, a continuación, haga clic en **cualquier elemento** o **cualquier atributo**, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="dc7f6-109">On the **BizTalk** menu, point to **Insert Schema Node**, and then click **Any Element** or **Any Attribute**, as appropriate.</span></span>  

> [!IMPORTANT]
>  <span data-ttu-id="dc7f6-110">Establecer el **Process Contents** propiedad **Lax** para **cualquier elemento** o **cualquier atributo** nodos no funcionen correctamente.</span><span class="sxs-lookup"><span data-stu-id="dc7f6-110">Setting the **Process Contents** property to **Lax** for **Any Element** or **Any Attribute** nodes may not work correctly.</span></span> <span data-ttu-id="dc7f6-111">Para pasar la validación **cualquier elemento** o **cualquier atributo** nodos, establezca la propiedad en **Skip**.</span><span class="sxs-lookup"><span data-stu-id="dc7f6-111">To pass validation on **Any Element** or **Any Attribute** nodes, set the property to **Skip**.</span></span>  <span data-ttu-id="dc7f6-112">Obtener más detalles sobre esta propiedad [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span><span class="sxs-lookup"><span data-stu-id="dc7f6-112">More details on this property [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].</span></span>
> 
>  <span data-ttu-id="dc7f6-113">Para crear un mapa que contiene **cualquier elemento** o **cualquier atributo** nodos, se debe usar el [copia masiva](mass-copy-functoid.md) functoid o [Scripting](scripting-functoid.md) functoid (con Inline XSLT o plantilla de llamada de XSLT en línea) para realizar la asignación de dichos nodos, o simplemente no asignar esos nodos.</span><span class="sxs-lookup"><span data-stu-id="dc7f6-113">To create a map that contains **Any Element** or **Any Attribute** nodes, you must use either the [Mass Copy](mass-copy-functoid.md) functoid or the [Scripting](scripting-functoid.md) functoid (with Inline XSLT or Inline XSLT Call Template) to perform the mapping for such nodes, or simply not map those nodes.</span></span>  

## <a name="see-also"></a><span data-ttu-id="dc7f6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="dc7f6-114">See Also</span></span>  
- [<span data-ttu-id="dc7f6-115">Inserción de nodos en un esquema</span><span class="sxs-lookup"><span data-stu-id="dc7f6-115">Inserting Nodes into a Schema</span></span>](../core/inserting-nodes-into-a-schema.md)
- <span data-ttu-id="dc7f6-116">**Referencia de functoid** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="dc7f6-116">**Functoid Reference** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
