---
title: Esquemas base y comunes | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- base schemas
- schemas, common schemas
- schemas, base schemas
- common schemas
ms.assetid: 60eb24f6-cc4f-4c6d-ab15-9e3a6b4ed376
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b7f8f86e4b74b84cef556ae95bc6255d8575237
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012573"
---
# <a name="base-and-common-schemas"></a><span data-ttu-id="4df86-102">Esquemas base y comunes</span><span class="sxs-lookup"><span data-stu-id="4df86-102">Base and Common Schemas</span></span>
<span data-ttu-id="4df86-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] ha implementado los registros y los elementos que componen los esquemas de mensaje individual en esquemas distintos.</span><span class="sxs-lookup"><span data-stu-id="4df86-103">Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] has implemented the records and elements that comprise individual message schemas in separate schemas.</span></span> <span data-ttu-id="4df86-104">Este enfoque proporciona una ubicación única para proporcionar actualizaciones para los campos y formatos, aislar el esquema de mensaje de dichos cambios.</span><span class="sxs-lookup"><span data-stu-id="4df86-104">This approach provides a single location to provide updates for fields and formats, insulating the message schema from such changes.</span></span>  
  
 <span data-ttu-id="4df86-105">El esquema de base (**Types.xsd Base SWIFT**) contiene las definiciones de registro y elemento comunes que hacen referencia a los esquemas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="4df86-105">The base schema (**SWIFT Base Types.xsd**) contains the common record and element definitions that the message schemas reference.</span></span> <span data-ttu-id="4df86-106">Las definiciones comunes de registro y elemento corresponden a los campos de mensaje de FIN de SWIFT.</span><span class="sxs-lookup"><span data-stu-id="4df86-106">The common record and element definitions correspond to the SWIFT FIN message fields.</span></span> <span data-ttu-id="4df86-107">Deberá agregar este esquema a cualquier proyecto que utiliza el esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="4df86-107">You need to add this schema to any project that uses the message schema.</span></span> <span data-ttu-id="4df86-108">El esquema de base trata las reglas y las funciones comunes y define los formatos de A4SWIFT para validar las instancias de mensaje adecuado.</span><span class="sxs-lookup"><span data-stu-id="4df86-108">The base schema covers the rules and common functions, and defines the formats that A4SWIFT uses to validate the appropriate message instances.</span></span> <span data-ttu-id="4df86-109">El esquema de SWIFT Base Types.xsd define XSD **simpleType** y elementos complejos para los campos SWIFT.</span><span class="sxs-lookup"><span data-stu-id="4df86-109">The SWIFT Base Types.xsd schema defines XSD **simpleType** and complex elements for SWIFT fields.</span></span> <span data-ttu-id="4df86-110">Ha definido SWIFT **simpleType** elementos para todos los campos de bases, como la cantidad, velocidad, precio etc., que usa SWIFT en muchos de los campos.</span><span class="sxs-lookup"><span data-stu-id="4df86-110">SWIFT has defined **simpleType** elements for all base fields, such as the Amount, Rate, Price, and so on, which SWIFT uses in many of the fields.</span></span> <span data-ttu-id="4df86-111">El esquema de SWIFT Base Types.xsd define también elementos complejos de XSD para los campos que se incluyen muchos de personalizado **simpleTypes** definido en el esquema.</span><span class="sxs-lookup"><span data-stu-id="4df86-111">The SWIFT Base Types.xsd schema also defines XSD complex elements for fields that include many of the custom **simpleTypes** defined in the schema.</span></span> <span data-ttu-id="4df86-112">Por ejemplo, el **BankIdentifierCode** elemento complejo que usa código del banco, código de país, código de área y código de la sucursal.</span><span class="sxs-lookup"><span data-stu-id="4df86-112">For example, the **BankIdentifierCode** complex element uses Bank Code, Country Code, Area Code, and Branch Code.</span></span> <span data-ttu-id="4df86-113">Los usuarios pueden agregar nuevos **simpleTypes** y elementos complejos que reflejen los campos SWIFT y pueden modificar los tipos existentes.</span><span class="sxs-lookup"><span data-stu-id="4df86-113">Users can add new **simpleTypes** and complex elements that mirror SWIFT fields and can modify existing types.</span></span> <span data-ttu-id="4df86-114">Debe procurar, sin embargo, al modificar tipos existentes, porque las características de validación de motor de reglas de negocios (BRE) y la validación de XML dependen de estos tipos definidos.</span><span class="sxs-lookup"><span data-stu-id="4df86-114">You should take care, however, when you modify existing types, because the Business Rule Engine (BRE) Validation and XML Validation features are dependent upon these defined types.</span></span>  
  
 <span data-ttu-id="4df86-115">El esquema común (**Types.xsd datos comunes de SWIFT**) define los juegos de caracteres apropiado para los campos en el esquema de base.</span><span class="sxs-lookup"><span data-stu-id="4df86-115">The common schema (**SWIFT Common Data Types.xsd**) defines the character sets appropriate to the fields in the base schema.</span></span> <span data-ttu-id="4df86-116">SWIFT define estos juegos de caracteres, como se hace referencia en el *manual del usuario de SWIFT*.</span><span class="sxs-lookup"><span data-stu-id="4df86-116">SWIFT defines these character sets, as referenced in the *SWIFT User Handbook*.</span></span> <span data-ttu-id="4df86-117">También deberá agregar el esquema común a los proyectos de esquema.</span><span class="sxs-lookup"><span data-stu-id="4df86-117">You also need to add the common schema to your schema projects.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4df86-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="4df86-118">See Also</span></span>  
 [<span data-ttu-id="4df86-119">Trabajar con esquemas</span><span class="sxs-lookup"><span data-stu-id="4df86-119">Working with Schemas</span></span>](../../adapters-and-accelerators/accelerator-swift/working-with-schemas.md)