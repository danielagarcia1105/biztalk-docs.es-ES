---
title: Los esquemas comunes de los valores de tabla | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, table values
- common schemas
ms.assetid: 2421e150-1bae-43bd-aba3-6322c679b22b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a55491f0a44bec6a5cd5eaf4fe120f693b3996c5
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "25962042"
---
# <a name="table-values-common-schemas"></a><span data-ttu-id="3c061-102">Valores de tabla de esquemas comunes</span><span class="sxs-lookup"><span data-stu-id="3c061-102">Table Values Common Schemas</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="3c061-103">Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) genera el **tablevalues_*\<versión\>*.xsd** de archivos para cada versión de HL7 y busca el archivo en la raíz de la HL7 carpeta específica de la versión.</span><span class="sxs-lookup"><span data-stu-id="3c061-103"> BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) generates the **tablevalues_*\<version\>*.xsd** file for each HL7 version, and locates the file at the root of the HL7 version-specific folder.</span></span> <span data-ttu-id="3c061-104">El archivo de esquema común de tipos de datos hace referencia el archivo de esquema común de valores de tabla.</span><span class="sxs-lookup"><span data-stu-id="3c061-104">The data type common schema file references the table values common schema file.</span></span>  
  
 <span data-ttu-id="3c061-105">Valores de estas tablas están en el formulario de enumeraciones.</span><span class="sxs-lookup"><span data-stu-id="3c061-105">Values in these tables are in the form of enumerations.</span></span> <span data-ttu-id="3c061-106">Cada enumeración define los valores que son aceptables en los campos de uno o varios de los esquemas de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3c061-106">Each enumeration defines the values that are acceptable within one or more fields of the message schemas.</span></span> <span data-ttu-id="3c061-107">Puede ver qué tabla se aplica a un nodo de un esquema de mensaje abrir el esquema en el Editor de BizTalk, haga clic en un nodo y examinando la **Base Data Type** propiedad en el panel de propiedades.</span><span class="sxs-lookup"><span data-stu-id="3c061-107">You can see which table applies to a node of a message schema by opening the schema in BizTalk Editor, clicking a node, and looking at the **Base Data Type** property in the Properties pane.</span></span>  
  
 <span data-ttu-id="3c061-108">No podrá ver lo que los valores aceptables para este nodo son, sin embargo, mediante la visualización de la enumeración en el panel de propiedades para el nodo de esquema de mensaje.</span><span class="sxs-lookup"><span data-stu-id="3c061-108">You will not be able to see what the acceptable values for this node are, however, by viewing the enumeration in the Properties pane for the message-schema node.</span></span> <span data-ttu-id="3c061-109">Esto es porque el archivo de esquema común de valores de tabla define la enumeración.</span><span class="sxs-lookup"><span data-stu-id="3c061-109">This is because the table values common schema file defines the enumeration.</span></span> <span data-ttu-id="3c061-110">Para ver las enumeraciones, haga clic en **tablevalues_*\<versión\>*.xsd** en el esquema de árbol en el Editor de BizTalk y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón en la fila de la enumeración en el panel Propiedades.</span><span class="sxs-lookup"><span data-stu-id="3c061-110">To view the enumerations, click **tablevalues_*\<version\>*.xsd** in the Schema tree in BizTalk Editor, and then click the ellipsis (**...**) button on the Enumeration row in the Properties pane.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c061-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c061-111">See Also</span></span>  
 <span data-ttu-id="3c061-112">[Archivos de esquema HL7 2.X comunes](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="3c061-112">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="3c061-113">[Los esquemas comunes de los tipos de datos](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="3c061-113">[Data Types Common Schemas](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span></span>  
 [<span data-ttu-id="3c061-114">Esquemas comunes de segmentos</span><span class="sxs-lookup"><span data-stu-id="3c061-114">Segments Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)