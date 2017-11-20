---
title: Los esquemas comunes de los tipos de datos | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, data types
- 2.X schemas, common schemas
- common schemas
ms.assetid: 6fd30cd3-9c4f-4391-9c79-a4dff11f2a46
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19ff35b515e70c21e2349ae54847ba312d7ce0f8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="data-types-common-schemas"></a><span data-ttu-id="e6cf1-102">Los esquemas comunes de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="e6cf1-102">Data Types Common Schemas</span></span>
<span data-ttu-id="e6cf1-103">El  **datatypes_*\<versión >*el archivo de esquema .xsd ** (donde  *\<versión >* es el número de versión de HL7) contiene la definición de todos los HL7 elementales y de materiales compuestos tipos de datos de la versión de HL7 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e6cf1-103">The **datatypes_*\<version>*.xsd** schema file (where *\<version>* is the HL7 version number) contains the definition of all the HL7 elementary and composite data types for the corresponding HL7 version.</span></span> <span data-ttu-id="e6cf1-104">El segments_*\<versión >*archivo .xsd usa este archivo para que coincida con la versión de HL7 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="e6cf1-104">The segments_*\<version>*.xsd file uses this file to match the corresponding HL7 version.</span></span> <span data-ttu-id="e6cf1-105">La tabla de base de datos de DataStructures Access genera el DataTypes_*\<versión >*archivo de esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="e6cf1-105">The DataStructures Access database table generates the DataTypes_*\<version>*.xsd schema file.</span></span> <span data-ttu-id="e6cf1-106">El ejemplo siguiente es una entrada para el tipo de datos básico HL7 **ST**:</span><span class="sxs-lookup"><span data-stu-id="e6cf1-106">The following example is an entry for the HL7 elementary data type **ST**:</span></span>  
  
```  
<xsd:simpleType name="ST">  
  <xsd:restriction base="xsd:string" />   
</xsd:simpleType>  
```  
  
 <span data-ttu-id="e6cf1-107">Este ejemplo se define **ST** como un **cadena**.</span><span class="sxs-lookup"><span data-stu-id="e6cf1-107">This example defines **ST** as a **string**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6cf1-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6cf1-108">See Also</span></span>  
 <span data-ttu-id="e6cf1-109">[Archivos de esquema HL7 2.X comunes](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="e6cf1-109">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="e6cf1-110">[Esquemas comunes de segmentos](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="e6cf1-110">[Segments Common Schemas](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md) </span></span>  
 [<span data-ttu-id="e6cf1-111">Valores de tabla de esquemas comunes</span><span class="sxs-lookup"><span data-stu-id="e6cf1-111">Table Values Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)