---
title: Crear segmentos de Z declarado | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Z objects, creating segments
- segments, creating Z segments [Z objects]
- Z segments, creating
- creating, Z segments [Z objects]
ms.assetid: afd1b7b7-089e-4c6a-a063-e708431bb888
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dae9148547f527d29238b6080cd499be8da7b7e6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-declared-z-segments"></a><span data-ttu-id="932af-102">Crear segmentos de Z declarado</span><span class="sxs-lookup"><span data-stu-id="932af-102">Creating Declared Z Segments</span></span>
<span data-ttu-id="932af-103">Puede crear segmentos de Z declarados en cualquier nivel de un esquema (a diferencia de los segmentos no declarados de Z, que debe ser la última parte de un mensaje de varias parte, después de la parte del cuerpo).</span><span class="sxs-lookup"><span data-stu-id="932af-103">You can create declared Z segments at any level of a schema (unlike undeclared Z segments, which must be the last part of a multi-party message, following the body part).</span></span>  
  
### <a name="to-create-a-z-segment-in-biztalk-editor"></a><span data-ttu-id="932af-104">Para crear un segmento de Z en el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="932af-104">To create a Z segment in BizTalk Editor</span></span>  
  
1.  <span data-ttu-id="932af-105">En el Explorador de soluciones de Visual Studio, haga clic en el esquema al que desea agregar un segmento de Z y, a continuación, haga clic en **abiertos**.</span><span class="sxs-lookup"><span data-stu-id="932af-105">In Solution Explorer of Visual Studio, right-click the schema to which you want to add a Z segment, and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="932af-106">En el Editor de BizTalk, haga clic en el nodo con el nombre del esquema, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario**.</span><span class="sxs-lookup"><span data-stu-id="932af-106">In BizTalk Editor, right-click the node with the name of the schema, point to **Insert Schema Node**, and then click **Child Record**.</span></span>  
  
3.  <span data-ttu-id="932af-107">Nombre del registro a partir del nombre de tres dígitos alfanuméricos, en mayúsculas, con el primer dígito que se va a "Z".</span><span class="sxs-lookup"><span data-stu-id="932af-107">Name the record starting the name with three alphanumeric digits, in capitals, with the first digit being "Z".</span></span> <span data-ttu-id="932af-108">(La etiqueta de segmento Z debe incluir tres caracteres). Insertar un carácter de subrayado (_) y, a continuación, agregue una descripción breve del segmento.</span><span class="sxs-lookup"><span data-stu-id="932af-108">(The Z segment tag must include three characters.) Insert an underscore (_), and then add a short description of the segment.</span></span> <span data-ttu-id="932af-109">La descripción debe contener uno o una serie de palabras, sin espacios en blanco, con la primera letra de cada palabra en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="932af-109">The description should be one or a series of words, without spaces, with the first letter of each word capitalized.</span></span> <span data-ttu-id="932af-110">La última palabra debe ser "Segmento".</span><span class="sxs-lookup"><span data-stu-id="932af-110">The last word should be "Segment".</span></span> <span data-ttu-id="932af-111">(Un ejemplo es "ZPP_PatientPreferencesSegment.) Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="932af-111">(An example is "ZPP_PatientPreferencesSegment.) Press **Enter**.</span></span>  
  
4.  <span data-ttu-id="932af-112">En el panel Propiedades, escriba las propiedades que desee para el segmento de Z, incluidos los **Data Structure Type** (nombre de esquema o xsd: anyType), **Max Occurs**, y **Min Occurs**.</span><span class="sxs-lookup"><span data-stu-id="932af-112">In the Properties pane, type the properties you want for the Z segment, including **Data Structure Type** (schema name or xsd:anyType), **Max Occurs**, and **Min Occurs**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="932af-113">Si especifica un tipo de estructura de datos para el registro, no podrá agregar un elemento de campo secundario.</span><span class="sxs-lookup"><span data-stu-id="932af-113">If you enter a data structure type for the record, you will not be able to add a child field element.</span></span>  
  
5.  <span data-ttu-id="932af-114">En el Editor de BizTalk, haga clic en el nombre del segmento de Z, seleccione **Insertar nodo de esquema**, a continuación, haga clic en **elemento de campo secundario**.</span><span class="sxs-lookup"><span data-stu-id="932af-114">In BizTalk Editor, right-click the name of the Z segment, point to **Insert Schema Node**, then click **Child Field Element**.</span></span>  
  
6.  <span data-ttu-id="932af-115">Escriba el nombre del campo, empezando el nombre con los tres primeros dígitos del nombre del segmento, seguido por un punto y el número del campo, seguido por un carácter de subrayado y, a continuación, una breve descripción del campo.</span><span class="sxs-lookup"><span data-stu-id="932af-115">Type the name of the field, starting the name with the first three digits of the segment name, followed by a period and the number of the field, followed by an underscore and then a short description of the field.</span></span> <span data-ttu-id="932af-116">La descripción debe contener uno o una serie de palabras, sin espacios en blanco, con la primera letra de cada palabra en mayúsculas.</span><span class="sxs-lookup"><span data-stu-id="932af-116">The description should be one or a series of words, without spaces, with the first letter of each word capitalized.</span></span> <span data-ttu-id="932af-117">Presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="932af-117">Press **Enter**.</span></span>  
  
7.  <span data-ttu-id="932af-118">En el panel Propiedades, escriba las propiedades que desee para el segmento de Z, incluidos los **tipo de datos**, **Nillable**, **Fixed**, **Max Occurs**, y **Min Occurs**.</span><span class="sxs-lookup"><span data-stu-id="932af-118">In the Properties pane, type the properties you want for the Z segment, including **Data Type**, **Nillable**, **Fixed**, **Max Occurs**, and **Min Occurs**.</span></span>  
  
8.  <span data-ttu-id="932af-119">Para crear un campo con los componentes, cree el campo como un registro y, a continuación, cree un elemento secundario de ese registro para cada componente.</span><span class="sxs-lookup"><span data-stu-id="932af-119">To create a field with components, create the field as a record, and then create a child element of that record for each component.</span></span> <span data-ttu-id="932af-120">Para crear un campo con subcomponentes, crear componentes como registros y el campo y los subcomponentes como elemento secundario elementos.</span><span class="sxs-lookup"><span data-stu-id="932af-120">To create a field with subcomponents, create the field and components as records, and the subcomponents as child elements.</span></span> <span data-ttu-id="932af-121">Tenga en cuenta que los subcomponentes no pueden ser tipos de datos compuestos.</span><span class="sxs-lookup"><span data-stu-id="932af-121">Note that subcomponents cannot be composite data types.</span></span> <span data-ttu-id="932af-122">Por ejemplo, para el segmento denominado ZPP_PatientPreferencesSegment, podría crear un campo de ZPP.1_Dietary y un componente de alergias PD.1 con un subcomponente de PD.1.1_FoodGroupAllergy.</span><span class="sxs-lookup"><span data-stu-id="932af-122">For example, for the segment named ZPP_PatientPreferencesSegment, you might create a ZPP.1_Dietary field and a PD.1 Allergies component with a PD.1.1_FoodGroupAllergy subcomponent.</span></span> <span data-ttu-id="932af-123">El subcomponente PD.1.1_FoodGroupAllergy tendría que ser un tipo de datos simple.</span><span class="sxs-lookup"><span data-stu-id="932af-123">The PD.1.1_FoodGroupAllergy subcomponent would have to be a simple data type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="932af-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="932af-124">See Also</span></span>  
 <span data-ttu-id="932af-125">[Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="932af-125">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="932af-126">[Crear tipos de datos personalizados en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="932af-126">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="932af-127">[Crear tablas personalizadas en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="932af-127">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 <span data-ttu-id="932af-128">[Extender las enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="932af-128">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="932af-129">Control de segmentos de Z no declarado</span><span class="sxs-lookup"><span data-stu-id="932af-129">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)