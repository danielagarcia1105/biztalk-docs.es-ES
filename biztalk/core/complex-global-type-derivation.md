---
title: Derivación de tipo Global complejo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbf429d0-64f4-4c43-a5f7-e8af050803b9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee4e6235af62b2c08c08382b897632d15e34e0cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22231676"
---
# <a name="complex-global-type-derivation"></a><span data-ttu-id="41610-102">Derivación de tipo global complejo</span><span class="sxs-lookup"><span data-stu-id="41610-102">Complex Global Type Derivation</span></span>
<span data-ttu-id="41610-103">Hay dos tipos de herencia en XSD: extensión y restricción.</span><span class="sxs-lookup"><span data-stu-id="41610-103">There are two types of inheritance in XSD: extension and restriction.</span></span> <span data-ttu-id="41610-104">El Editor de BizTalk proporciona acceso a esta funcionalidad XSD mediante los dos siguientes **registro** propiedades de nodo:</span><span class="sxs-lookup"><span data-stu-id="41610-104">BizTalk Editor provides access to this XSD functionality by using the following two **Record** node properties:</span></span>  
  
-   <span data-ttu-id="41610-105">**Tipo de datos base**.</span><span class="sxs-lookup"><span data-stu-id="41610-105">**Base Data Type**.</span></span> <span data-ttu-id="41610-106">esta propiedad proporciona la lista de todos los tipos simples y complejos globales disponibles para usarlos como tipos de datos base.</span><span class="sxs-lookup"><span data-stu-id="41610-106">This property provides the list of all global complex types and simple types available for use as a base data type.</span></span> <span data-ttu-id="41610-107">Los tipos globales complejos puede estar en el mismo esquema o en cualquier esquema importado.</span><span class="sxs-lookup"><span data-stu-id="41610-107">The complex global types can be in the same schema or in any imported schema.</span></span>  
  
-   <span data-ttu-id="41610-108">**Derivada por**.</span><span class="sxs-lookup"><span data-stu-id="41610-108">**Derived By**.</span></span> <span data-ttu-id="41610-109">esta propiedad sirve para elegir entre la derivación por extensión o por restricción.</span><span class="sxs-lookup"><span data-stu-id="41610-109">This property is used to choose between deriving by extension or by restriction.</span></span> <span data-ttu-id="41610-110">Esta propiedad se establece automáticamente en **extensión** al establecer el **Base Data Type** propiedad a cualquier tipo de la lista.</span><span class="sxs-lookup"><span data-stu-id="41610-110">This property is automatically set to **Extension** when you set the **Base Data Type** property to any type in the list.</span></span> <span data-ttu-id="41610-111">Si establece esta propiedad en **(predeterminado)**, cualquier tipo en el **Base Data Type** propiedad se quita, se deshabilita la herencia para el nodo.</span><span class="sxs-lookup"><span data-stu-id="41610-111">If you set this property to **(Default)**, any type in the **Base Data Type** property is removed, disabling inheritance for the node.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="41610-112">El **tipo de contenido** propiedad también se establece automáticamente en **ComplexContent** cuando se utiliza la derivación por extensión o restricción.</span><span class="sxs-lookup"><span data-stu-id="41610-112">The **Content Type** property is also set automatically to **ComplexContent** when derivation by extension or restriction is being used.</span></span>  
  
 <span data-ttu-id="41610-113">En esta sección se explica con mayor detalle la derivación de tipo complejo mediante los mecanismos de extensión y restricción.</span><span class="sxs-lookup"><span data-stu-id="41610-113">This section explains complex type derivation by using the extension and restriction mechanisms in greater detail.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="41610-114">En esta sección</span><span class="sxs-lookup"><span data-stu-id="41610-114">In This Section</span></span>  
  
-   [<span data-ttu-id="41610-115">Derivación de tipo complejo mediante el mecanismo de extensión</span><span class="sxs-lookup"><span data-stu-id="41610-115">Complex Type Derivation Using the Extension Mechanism</span></span>](../core/complex-type-derivation-using-the-extension-mechanism.md)  
  
-   [<span data-ttu-id="41610-116">Derivación de tipo complejo mediante el mecanismo de restricción</span><span class="sxs-lookup"><span data-stu-id="41610-116">Complex Type Derivation Using the Restriction Mechanism</span></span>](../core/complex-type-derivation-using-the-restriction-mechanism.md)