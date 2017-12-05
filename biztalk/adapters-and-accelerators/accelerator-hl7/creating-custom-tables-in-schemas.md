---
title: Crear tablas personalizadas en esquemas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, Z tables [Z objects]
- Z objects, creating Z tables
- 2.X schemas, creating Z tables
ms.assetid: d6ab8ac9-a835-4ec0-9ddd-76ff267a3cbd
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a663dd593123e647f2f466b6d472d60bb32be1be
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="creating-custom-tables-in-schemas"></a><span data-ttu-id="3054a-102">Crear tablas personalizadas en esquemas</span><span class="sxs-lookup"><span data-stu-id="3054a-102">Creating Custom Tables in Schemas</span></span>
<span data-ttu-id="3054a-103">Puede crear una tabla personalizada en el tablevalues_\<*versión*\>esquema común de XSD.</span><span class="sxs-lookup"><span data-stu-id="3054a-103">You can create a custom table in the tablevalues_\<*version*\>.xsd common schema.</span></span> <span data-ttu-id="3054a-104">Puede basar una tabla personalizada en un tipo de datos existente, un tipo de base de datos, o en una enumeración definidos en una tabla.</span><span class="sxs-lookup"><span data-stu-id="3054a-104">You can base a custom table on an existing data type, a base data type, or on an enumeration defined in a table.</span></span>  
  
### <a name="to-create-a-z-table"></a><span data-ttu-id="3054a-105">Para crear una tabla de Z</span><span class="sxs-lookup"><span data-stu-id="3054a-105">To create a Z table</span></span>  
  
1.  <span data-ttu-id="3054a-106">En el Explorador de soluciones, abra el archivo de esquema de tipo de datos común  **tablevalues_\<*versión*\>.xsd ** y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="3054a-106">In Solution Explorer, open the common data-type schema file **tablevalues_\<*version*\>.xsd**, and then click **Open**.</span></span>  
  
2.  <span data-ttu-id="3054a-107">En el Editor de BizTalk, haga clic en **HL7DefinedTables**, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **elemento de campo secundario**.</span><span class="sxs-lookup"><span data-stu-id="3054a-107">In BizTalk Editor, right-click **HL7DefinedTables**, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  
  
3.  <span data-ttu-id="3054a-108">Nombre de la tabla con una etiqueta que empieza por la letra "Z".</span><span class="sxs-lookup"><span data-stu-id="3054a-108">Name the table with a tag starting with the letter "Z".</span></span>  
  
4.  <span data-ttu-id="3054a-109">En el panel Propiedades, escriba los valores que desee para determinadas propiedades, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="3054a-109">In the Properties pane, type the values you want for specific properties, as needed.</span></span>  
  
5.  <span data-ttu-id="3054a-110">Para asociar una enumeración con la tabla, en el panel Propiedades, establezca **Derived By** a **restricción**, haga clic en **enumeración**, haga clic en el botón de puntos suspensivos (...) para  **Enumeración**y, a continuación, escriba los valores que desea que la enumeración para que contenga en el Editor de enumeración.</span><span class="sxs-lookup"><span data-stu-id="3054a-110">To associate an enumeration with the table, in the Properties pane, set **Derived By** to **Restriction**, click **Enumeration**, click the ellipsis (…) button for **Enumeration**, and then type the values that you want the enumeration to contain in the Enumeration Editor.</span></span> <span data-ttu-id="3054a-111">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="3054a-111">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3054a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3054a-112">See Also</span></span>  
 <span data-ttu-id="3054a-113">[Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span><span class="sxs-lookup"><span data-stu-id="3054a-113">[Extending HL7 2.X Schemas with Z Objects](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md) </span></span>  
 <span data-ttu-id="3054a-114">[Crear segmentos de Z declarado](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span><span class="sxs-lookup"><span data-stu-id="3054a-114">[Creating Declared Z Segments](../../adapters-and-accelerators/accelerator-hl7/creating-declared-z-segments.md) </span></span>  
 <span data-ttu-id="3054a-115">[Crear tipos de datos personalizados en esquemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="3054a-115">[Creating Custom Data Types in Schemas](../../adapters-and-accelerators/accelerator-hl7/creating-custom-data-types-in-schemas.md) </span></span>  
 <span data-ttu-id="3054a-116">[Extender las enumeraciones](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span><span class="sxs-lookup"><span data-stu-id="3054a-116">[Extending Enumerations](../../adapters-and-accelerators/accelerator-hl7/extending-enumerations.md) </span></span>  
 [<span data-ttu-id="3054a-117">Control de segmentos de Z no declarados</span><span class="sxs-lookup"><span data-stu-id="3054a-117">Handling Undeclared Z Segments</span></span>](../../adapters-and-accelerators/accelerator-hl7/handling-undeclared-z-segments.md)