---
title: Crear tipos de datos personalizados en esquemas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, creating Z data types [Z objects]
- data types, creating [Z objects]
- Z objects, creating Z data types
ms.assetid: e545c849-d414-4d5d-bb56-d3f9d5238c70
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09b07843a6e010021b00a1ffa7c3010977d1d3c7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="creating-custom-data-types-in-schemas"></a><span data-ttu-id="891fe-102">Crear tipos de datos personalizados en esquemas</span><span class="sxs-lookup"><span data-stu-id="891fe-102">Creating Custom Data Types in Schemas</span></span>
<span data-ttu-id="891fe-103">Puede crear un tipo de datos personalizados en el datatypes_\<*versión*> esquema común de XSD.</span><span class="sxs-lookup"><span data-stu-id="891fe-103">You can create a custom data type in the datatypes_\<*version*>.xsd common schema.</span></span> <span data-ttu-id="891fe-104">Puede basar un tipo de datos personalizado en un tipo de datos existente, un tipo de base de datos, o en una enumeración definidos en una tabla.</span><span class="sxs-lookup"><span data-stu-id="891fe-104">You can base a custom data type on an existing data type, a base data type, or on an enumeration defined in a table.</span></span>  
  
### <a name="to-create-a-z-data-type"></a><span data-ttu-id="891fe-105">Para crear un tipo de datos de Z</span><span class="sxs-lookup"><span data-stu-id="891fe-105">To create a Z data type</span></span>  
  
1.  <span data-ttu-id="891fe-106">En el Explorador de soluciones de Visual Studio, abra el archivo de esquema de tipo de datos comunes (**datatypes_\<*versión*> .xsd **) y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="891fe-106">In Solution Explorer of Visual Studio, open the common data-type schema file (**datatypes_\<*version*>.xsd**), and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="891fe-107">En el Editor de BizTalk, haga clic en **HL7DefinedDataTypes**, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **registro secundario** para crear un tipo de datos de componentes, o haga clic en  **Elemento secundario** para crear un tipo de datos simple.</span><span class="sxs-lookup"><span data-stu-id="891fe-107">In BizTalk Editor, right-click **HL7DefinedDataTypes**, point to **Insert Schema Node**, and then click **Child Record** to create a component data type, or click **Child Element** to create a simple data type.</span></span>  
  
3.  <span data-ttu-id="891fe-108">Nombre para el tipo de datos con una etiqueta de tres caracteres a partir de "Z".</span><span class="sxs-lookup"><span data-stu-id="891fe-108">Name the data type with a three-character tag starting with "Z".</span></span>  
  
4.  <span data-ttu-id="891fe-109">En el panel Propiedades, escriba los valores que desee para **Base Data Type**, **tipo de datos**y otras propiedades, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="891fe-109">In the Properties pane, type the values you want for **Base Data Type**, **Data Type**, and other properties, as needed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="891fe-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="891fe-110">See Also</span></span>  
 <span data-ttu-id="891fe-111">[Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="891fe-111">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="891fe-112">[Crear segmentos de Z declarado](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="891fe-112">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="891fe-113">[Crear tablas personalizadas en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="891fe-113">[Creating Custom Tables in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-tables-in-schemas.md) </span></span>  
 <span data-ttu-id="891fe-114">[Extender las enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="891fe-114">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="891fe-115">Control de segmentos de Z no declarado</span><span class="sxs-lookup"><span data-stu-id="891fe-115">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)