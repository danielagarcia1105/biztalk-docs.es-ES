---
title: Los esquemas comunes de los valores de tabla | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, table values
- common schemas
ms.assetid: 2421e150-1bae-43bd-aba3-6322c679b22b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b93434c57988b8ef0cdb068ffb960e6fb342edc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="table-values-common-schemas"></a><span data-ttu-id="a8083-102">Valores de tabla de esquemas comunes</span><span class="sxs-lookup"><span data-stu-id="a8083-102">Table Values Common Schemas</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="a8083-103">Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) genera el  **tablevalues_*\<versión >*.xsd ** de archivos para cada versión de HL7 y busca el archivo en la raíz de la HL7 carpeta específica de la versión.</span><span class="sxs-lookup"><span data-stu-id="a8083-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) generates the **tablevalues_*\<version>*.xsd** file for each HL7 version, and locates the file at the root of the HL7 version-specific folder.</span></span> <span data-ttu-id="a8083-104">El archivo de esquema común de tipos de datos hace referencia el archivo de esquema común de valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="a8083-104">The data type common schema file references the table values common schema file.</span></span>  
  
 <span data-ttu-id="a8083-105">Valores de estas tablas están en el formulario de enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="a8083-105">Values in these tables are in the form of enumerations.</span></span> <span data-ttu-id="a8083-106">Cada enumeración define los valores que son aceptables en los campos de uno o varios de los esquemas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a8083-106">Each enumeration defines the values that are acceptable within one or more fields of the message schemas.</span></span> <span data-ttu-id="a8083-107">Puede ver qué tabla se aplica a un nodo de un esquema de mensaje abrir el esquema en el Editor de BizTalk, haga clic en un nodo y examinando la **Base Data Type** propiedad en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="a8083-107">You can see which table applies to a node of a message schema by opening the schema in BizTalk Editor, clicking a node, and looking at the **Base Data Type** property in the Properties pane.</span></span>  
  
 <span data-ttu-id="a8083-108">No podrá ver lo que los valores aceptables para este nodo son, sin embargo, mediante la visualización de la enumeración en el panel de propiedades para el nodo de esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="a8083-108">You will not be able to see what the acceptable values for this node are, however, by viewing the enumeration in the Properties pane for the message-schema node.</span></span> <span data-ttu-id="a8083-109">Esto es porque el archivo de esquema común de valores de tabla define la enumeración.</span><span class="sxs-lookup"><span data-stu-id="a8083-109">This is because the table values common schema file defines the enumeration.</span></span> <span data-ttu-id="a8083-110">Para ver las enumeraciones, haga clic en  **tablevalues_*\<versión >*.xsd ** en el esquema del árbol del Editor de BizTalk y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón en la fila de la enumeración en el panel Propiedades.</span><span class="sxs-lookup"><span data-stu-id="a8083-110">To view the enumerations, click **tablevalues_*\<version>*.xsd** in the Schema tree in BizTalk Editor, and then click the ellipsis (**...**) button on the Enumeration row in the Properties pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8083-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8083-111">See Also</span></span>  
 <span data-ttu-id="a8083-112">[Archivos de esquema HL7 2.X comunes](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="a8083-112">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="a8083-113">[Los esquemas comunes de los tipos de datos](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="a8083-113">[Data Types Common Schemas](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span></span>  
 [<span data-ttu-id="a8083-114">Esquemas comunes de segmentos</span><span class="sxs-lookup"><span data-stu-id="a8083-114">Segments Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)