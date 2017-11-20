---
title: Extender HL7 2.X esquemas con objetos de Z | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, Z objects
- Z objects, extending 2.X schemas
ms.assetid: 0980d919-eb81-4c65-b0f7-f17f7cfef6b3
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a27ef2bea3e13904f04449a5b77d05672c2b2d94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="extending-hl7-2x-schemas-with-z-objects"></a><span data-ttu-id="ea5a7-102">Extender HL7 2.X esquemas con objetos de Z</span><span class="sxs-lookup"><span data-stu-id="ea5a7-102">Extending HL7 2.X Schemas with Z Objects</span></span>
<span data-ttu-id="ea5a7-103">La organización de HL7 define HL7 2.X esquemas y se espera que todos los remitentes y receptores reconocer y utilizar estos esquemas, tal y como define la organización.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-103">The HL7 organization defines HL7 2.X schemas, and expects all senders and receivers to recognize and use these schemas as the organization defines them.</span></span> <span data-ttu-id="ea5a7-104">Conforme a los esquemas garantiza para la interoperabilidad.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-104">Conforming to the schemas ensures for interoperability.</span></span> <span data-ttu-id="ea5a7-105">Sin embargo, el estándar HL7 le permite personalizar HL7 existente 2.X esquemas para sus fines locales específicos.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-105">However, the HL7 standard enables you to customize existing HL7 2.X schemas for your specific local purposes.</span></span> <span data-ttu-id="ea5a7-106">También puede definir objetos y esquemas completamente nuevos.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-106">You can also define entirely new schemas and objects.</span></span> <span data-ttu-id="ea5a7-107">Para ello, con qué las HL7 estándares llamadas a objetos de Z.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-107">You do so with what the HL7 standard calls Z objects.</span></span>  
  
 <span data-ttu-id="ea5a7-108">El estándar HL7 no define el valor de los objetos de Z.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-108">The HL7 standard does not define the value of Z objects.</span></span> <span data-ttu-id="ea5a7-109">Los esquemas de HL7 publicados no incluirlos.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-109">The published HL7 schemas do not include them.</span></span> <span data-ttu-id="ea5a7-110">Definirlos localmente y usarlos de acuerdo con todas las partes locales.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-110">You define them locally, and use them by agreement with all local parties.</span></span> <span data-ttu-id="ea5a7-111">La organización de HL7 reserva todos los tipo de mensaje, evento de desencadenador, segmento, tipo de datos y los nombres de tabla que empiezan por "Z" para este uso local.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-111">The HL7 organization reserves all message type, trigger event, segment, data type, and table names beginning with "Z" for this local use.</span></span> <span data-ttu-id="ea5a7-112">Por el prefijo, el estándar HL7 llama a estos objetos de objetos definidos por el sitio Z.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-112">Because of the prefix, the HL7 standard calls these site-defined objects Z objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea5a7-113">Cuando se agrega un objeto de Z en un esquema definido de HL7 existente, puede acabar con varias versiones de ese esquema.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-113">When you add a Z object to an existing HL7-defined schema, you may end up with multiple versions of that schema.</span></span> <span data-ttu-id="ea5a7-114">La mejor manera de controlar estos varias versiones consiste en utilizar la característica de Namespace en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ea5a7-114">The best way to handle these multiple versions is to use the Namespace feature in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].</span></span> <span data-ttu-id="ea5a7-115">Puede encontrar esta característica en el **validación** ficha [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración (en el nivel de entidad).</span><span class="sxs-lookup"><span data-stu-id="ea5a7-115">You can find this feature on the **Validation** tab in [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer (at the party level).</span></span> <span data-ttu-id="ea5a7-116">También necesitará cambiar la propiedad de espacio de nombres del esquema que se implementan para ese proyecto.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-116">You will also need to change the namespace property within the schema that you deploy for that project.</span></span>  
  
 <span data-ttu-id="ea5a7-117">Al crear o procesar Z objetos, debe seguir las reglas que haya establecido la organización HL7 para objetos de Z...</span><span class="sxs-lookup"><span data-stu-id="ea5a7-117">In creating or processing Z objects, you should follow the rules that the HL7 organization has established for Z objects..</span></span>  
  
 <span data-ttu-id="ea5a7-118">Al agregar un objeto de Z en un esquema existente o crear un nuevo esquema de mensaje de Z, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] usará el esquema con los objetos de Z para procesar el mensaje con codificación HL7.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-118">When you add a Z object to an existing schema or create a new Z message schema, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] will use the schema with the Z object(s) to process the HL7-encoded message.</span></span> <span data-ttu-id="ea5a7-119">Este tipo de objeto de Z es un objeto declarado de Z.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-119">This type of Z object is a declared Z object.</span></span> <span data-ttu-id="ea5a7-120">También puede usar un segmento de Z no declarado, que el motor de integración no se procesará según el esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="ea5a7-120">You can also use an undeclared Z segment, which the integration engine will not process according to the message schema.</span></span> <span data-ttu-id="ea5a7-121">Para obtener más información acerca de este tipo de segmento de Z, consulte [control no declarado Z segmentos](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md).</span><span class="sxs-lookup"><span data-stu-id="ea5a7-121">For more information about this type of Z segment, see [Handling Undeclared Z Segments](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ea5a7-122">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ea5a7-122">In This Section</span></span>  
  
-   [<span data-ttu-id="ea5a7-123">Crear segmentos de Z declarado</span><span class="sxs-lookup"><span data-stu-id="ea5a7-123">Creating Declared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md)  
  
-   [<span data-ttu-id="ea5a7-124">Crear tipos de datos personalizados en esquemas</span><span class="sxs-lookup"><span data-stu-id="ea5a7-124">Creating Custom Data Types in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md)  
  
-   [<span data-ttu-id="ea5a7-125">Crear tablas personalizadas en esquemas</span><span class="sxs-lookup"><span data-stu-id="ea5a7-125">Creating Custom Tables in Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md)  
  
-   [<span data-ttu-id="ea5a7-126">Extender las enumeraciones</span><span class="sxs-lookup"><span data-stu-id="ea5a7-126">Extending Enumerations</span></span>](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md)  
  
-   [<span data-ttu-id="ea5a7-127">Personalización de mensajes a través de objetos de Z</span><span class="sxs-lookup"><span data-stu-id="ea5a7-127">Customizing Messages through Z Objects</span></span>](../../adapters-and-accelerators/accelerator-hl7/customizing-messages-through-z-objects.md)