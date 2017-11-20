---
title: "Derivación de tipo simple | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d43932a0-039c-4211-82c0-087bae186145
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fcc74796de8543f1e0f895d0b3dff705aeb2930e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="simple-type-derivation"></a><span data-ttu-id="b7487-102">Derivación de tipo simple</span><span class="sxs-lookup"><span data-stu-id="b7487-102">Simple Type Derivation</span></span>
<span data-ttu-id="b7487-103">El lenguaje de definición de esquemas XML (XSD) proporciona varios mecanismos para definir las variaciones de tipos simples según las derivaciones de tipos simples existentes, como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="b7487-103">XML Schema definition (XSD) language provides several mechanisms for defining variations of simple types, based on derivations of existing simple types, as follows:</span></span>  
  
-   <span data-ttu-id="b7487-104">**Restricción**.</span><span class="sxs-lookup"><span data-stu-id="b7487-104">**Restriction**.</span></span> <span data-ttu-id="b7487-105">la derivación de tipo simple mediante el mecanismo de restricción conlleva la implementación de restricciones en los valores posibles de dicho tipo.</span><span class="sxs-lookup"><span data-stu-id="b7487-105">Simple type derivation by using the restriction mechanism involves the introduction of restrictions to the possible values for that type.</span></span> <span data-ttu-id="b7487-106">Entre los ejemplos se incluyen los valores mínimos y máximos de tipos numéricos, o la longitud mínima y máxima de los tipos de cadena.</span><span class="sxs-lookup"><span data-stu-id="b7487-106">Examples are minimum and/or maximum values for numeric types, or a minimum and maximum length for string types.</span></span>  
  
-   <span data-ttu-id="b7487-107">**Lista**.</span><span class="sxs-lookup"><span data-stu-id="b7487-107">**List**.</span></span> <span data-ttu-id="b7487-108">la derivación de tipo simple mediante el mecanismo de lista permite la definición de un valor de atributo o elemento de un mensaje de instancia como una lista de valores de un tipo específico separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="b7487-108">Simple type derivation by using the list mechanism allows a single attribute or element value in an instance message to be defined as consisting of a list of space-separated values of a particular type.</span></span>  
  
-   <span data-ttu-id="b7487-109">**Unión**.</span><span class="sxs-lookup"><span data-stu-id="b7487-109">**Union**.</span></span> <span data-ttu-id="b7487-110">la derivación de tipo simple mediante el mecanismo de unión permite la definición de un valor de atributo o elemento de un mensaje de instancia como un valor individual de uno de varios tipos especificados</span><span class="sxs-lookup"><span data-stu-id="b7487-110">Simple type derivation by using the union mechanism allows a single attribute or element value in an instance message to be defined as a single value of one of several specified types.</span></span>  
  
 <span data-ttu-id="b7487-111">En esta sección se describen estas derivaciones de tipo simple en mayor profundidad, incluida información sobre cómo definir estas derivaciones mediante el establecimiento de las propiedades de nodo correspondientes en la ventana Propiedades, así como el modo en que se construye el XSD correspondiente.</span><span class="sxs-lookup"><span data-stu-id="b7487-111">This section describes these simple type derivations in more detail, including how to define these derivations by setting the appropriate node properties in the Properties window, as well as how the corresponding XSD is constructed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b7487-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b7487-112">In This Section</span></span>  
  
-   [<span data-ttu-id="b7487-113">Derivación de tipo simple mediante el mecanismo de restricción</span><span class="sxs-lookup"><span data-stu-id="b7487-113">Simple Type Derivation Using the Restriction Mechanism</span></span>](../core/simple-type-derivation-using-the-restriction-mechanism.md)  
  
-   [<span data-ttu-id="b7487-114">Derivación de tipo simple mediante el mecanismo de lista</span><span class="sxs-lookup"><span data-stu-id="b7487-114">Simple Type Derivation Using the List Mechanism</span></span>](../core/simple-type-derivation-using-the-list-mechanism.md)  
  
-   [<span data-ttu-id="b7487-115">Derivación de tipo simple mediante el mecanismo de unión</span><span class="sxs-lookup"><span data-stu-id="b7487-115">Simple Type Derivation Using the Union Mechanism</span></span>](../core/simple-type-derivation-using-the-union-mechanism.md)