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
ms.openlocfilehash: 0e7d693cdf70f7d29a79aa8999dde49f408b8815
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="data-types-common-schemas"></a><span data-ttu-id="c1528-102">Los esquemas comunes de los tipos de datos</span><span class="sxs-lookup"><span data-stu-id="c1528-102">Data Types Common Schemas</span></span>
<span data-ttu-id="c1528-103">El  **datatypes_*\<versión\>*el archivo de esquema .xsd ** (donde  *\<versión\>*  es el número de versión de HL7 ) contiene la definición de todos los tipos de datos elementales y de materiales compuestos de HL7 para la versión de HL7 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c1528-103">The **datatypes_*\<version\>*.xsd** schema file (where *\<version\>* is the HL7 version number) contains the definition of all the HL7 elementary and composite data types for the corresponding HL7 version.</span></span> <span data-ttu-id="c1528-104">El segments_*\<versión\>*archivo .xsd usa este archivo para que coincida con la versión de HL7 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="c1528-104">The segments_*\<version\>*.xsd file uses this file to match the corresponding HL7 version.</span></span> <span data-ttu-id="c1528-105">La tabla de base de datos de DataStructures Access genera el DataTypes_*\<versión\>*archivo de esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="c1528-105">The DataStructures Access database table generates the DataTypes_*\<version\>*.xsd schema file.</span></span> <span data-ttu-id="c1528-106">El ejemplo siguiente es una entrada para el tipo de datos básico HL7 **ST**:</span><span class="sxs-lookup"><span data-stu-id="c1528-106">The following example is an entry for the HL7 elementary data type **ST**:</span></span>  
  
```  
<xsd:simpleType name="ST">  
  <xsd:restriction base="xsd:string" />   
</xsd:simpleType>  
```  
  
 <span data-ttu-id="c1528-107">Este ejemplo se define **ST** como un **cadena**.</span><span class="sxs-lookup"><span data-stu-id="c1528-107">This example defines **ST** as a **string**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1528-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1528-108">See Also</span></span>  
 <span data-ttu-id="c1528-109">[Archivos de esquema HL7 2.X comunes](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="c1528-109">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="c1528-110">[Esquemas comunes de segmentos](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="c1528-110">[Segments Common Schemas](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md) </span></span>  
 [<span data-ttu-id="c1528-111">Valores de tabla de esquemas comunes</span><span class="sxs-lookup"><span data-stu-id="c1528-111">Table Values Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)