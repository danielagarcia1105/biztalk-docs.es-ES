---
title: Escriba reutilización y derivaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 240145ea-be41-40ce-8edd-3d4d00e2baec
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2982fdf5e46f813669ff74b513615637aa699bd4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286620"
---
# <a name="type-reuse-and-derivations"></a><span data-ttu-id="adc59-102">Reutilización y derivaciones de tipos</span><span class="sxs-lookup"><span data-stu-id="adc59-102">Type Reuse and Derivations</span></span>
<span data-ttu-id="adc59-103">Dentro del lenguaje de definición de esquemas XML (XSD), los tipos globales complejos proporcionan un mecanismo para definir un tipo de datos estructurado que se puede reutilizar y potencialmente redefinir en varias ubicaciones del esquema.</span><span class="sxs-lookup"><span data-stu-id="adc59-103">Within XML Schema definition (XSD) language, complex global types provide a mechanism for defining a structured data type that can be reused, and potentially redefined, at various locations within your schema.</span></span> <span data-ttu-id="adc59-104">Tal vez el ejemplo más clásico sea la estructura de una dirección, que incluye un nombre, la calle, la ciudad, el estado, etc.</span><span class="sxs-lookup"><span data-stu-id="adc59-104">Perhaps the most classic example is an address structure that includes a name, street, city, state, and so on.</span></span> <span data-ttu-id="adc59-105">Asimismo, el propio nombre puede ser una estructura que incluya cadenas de nombre, segundo nombre y apellidos.</span><span class="sxs-lookup"><span data-stu-id="adc59-105">Further, the name itself might be a structure that includes first, middle, and last name strings.</span></span> <span data-ttu-id="adc59-106">Si esta estructura compleja está definida de forma global, se podrá utilizar en varias ubicaciones dentro del esquema, como una dirección de envío y una dirección de facturación.</span><span class="sxs-lookup"><span data-stu-id="adc59-106">If this complex structure is defined globally, you can use it in multiple locations within your schema, such as for both a shipping address and a billing address.</span></span>  
  
 <span data-ttu-id="adc59-107">XSD también proporciona mecanismos para derivar un tipo a partir de otro.</span><span class="sxs-lookup"><span data-stu-id="adc59-107">XSD also provides mechanisms for deriving one type from another.</span></span> <span data-ttu-id="adc59-108">Esto incluye tanto tipos de contenido simple como tipos de contenido complejo.</span><span class="sxs-lookup"><span data-stu-id="adc59-108">This includes both simple content types and complex content types.</span></span> <span data-ttu-id="adc59-109">Por ejemplo, se puede derivar un tipo nuevo a partir de un tipo de cadena simple (como xs:string) de modo que el tipo nuevo admita únicamente un número reducido de cadenas concretas como valores permitidos.</span><span class="sxs-lookup"><span data-stu-id="adc59-109">For example, a new type can be derived from a simple string type (such as, xs:string) such that the new type allows only a few particular strings as legal values.</span></span> <span data-ttu-id="adc59-110">Este tipo de derivación se conoce en XSD como derivación por restricción, ya que los valores permitidos por el tipo derivado son más restrictivos que los que admite el tipo base.</span><span class="sxs-lookup"><span data-stu-id="adc59-110">This type of derivation is known within XSD as derivation by restriction because the values allowed by the derived type are more restrictive than the values allowed by the base type.</span></span>  
  
 <span data-ttu-id="adc59-111">Un ejemplo de derivación con un tipo complejo puede ser el tipo de dirección que se ha indicado antes.</span><span class="sxs-lookup"><span data-stu-id="adc59-111">An example of a derivation involving a complex type can be seen in the address type previously suggested.</span></span> <span data-ttu-id="adc59-112">Supongamos que el tipo de dirección se ha diseñado para las direcciones de un país y una región concretas, donde el propio valor de país o región se considera parte de la dirección.</span><span class="sxs-lookup"><span data-stu-id="adc59-112">Suppose that the address type is designed to accommodate the addresses within a particular country/region, where the country/region itself is assumed in the address.</span></span> <span data-ttu-id="adc59-113">Para ampliar ese tipo de dirección de modo que abarque direcciones internacionales, puede derivar un tipo nuevo a partir del tipo de dirección original y, a continuación, incluir información adicional en el tipo derivado, como el país y la región.</span><span class="sxs-lookup"><span data-stu-id="adc59-113">To extend such an address type to handle international addresses, you can derive a new type from the original address type and then include additional information in the derived type, such as the country/region.</span></span> <span data-ttu-id="adc59-114">Este tipo de derivación se conoce en XSD como derivación por extensión, ya que el tipo derivado ha extendido el tipo base.</span><span class="sxs-lookup"><span data-stu-id="adc59-114">This type of derivation is known within XSD as derivation by extension because the derived type has extended the base type.</span></span>  
  
 <span data-ttu-id="adc59-115">Esta sección describe la reutilización de tipos y las formas en las que se puede usar la derivación para redefinir tipos reutilizados.</span><span class="sxs-lookup"><span data-stu-id="adc59-115">This section describes type reuse and the ways in which you can use derivation to redefine types as they are reused.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="adc59-116">En esta sección</span><span class="sxs-lookup"><span data-stu-id="adc59-116">In This Section</span></span>  
  
-   [<span data-ttu-id="adc59-117">Definición de tipo Global complejo y nomenclatura</span><span class="sxs-lookup"><span data-stu-id="adc59-117">Complex Global Type Definition and Naming</span></span>](../core/complex-global-type-definition-and-naming.md)  
  
-   [<span data-ttu-id="adc59-118">Formas de utilizar los tipos globales complejos</span><span class="sxs-lookup"><span data-stu-id="adc59-118">Ways to Use Complex Global Types</span></span>](../core/ways-to-use-complex-global-types.md)  
  
-   [<span data-ttu-id="adc59-119">Derivación de tipo simple</span><span class="sxs-lookup"><span data-stu-id="adc59-119">Simple Type Derivation</span></span>](../core/simple-type-derivation.md)