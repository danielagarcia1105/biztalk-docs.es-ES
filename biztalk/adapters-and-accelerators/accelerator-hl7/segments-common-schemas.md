---
title: Los segmentos de esquemas comunes | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, segments
- common schemas
ms.assetid: 6f66bce9-ead8-46c1-a66c-830750adc73b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ff61c73b51eb08d1e6f845980686b49b3440d88c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="segments-common-schemas"></a><span data-ttu-id="47fbe-102">Esquemas comunes de segmentos</span><span class="sxs-lookup"><span data-stu-id="47fbe-102">Segments Common Schemas</span></span>
<span data-ttu-id="47fbe-103">El  **segments_\<*versión*> archivo .xsd ** incluye datatypes_\<*versión*> .xsd y contiene la definición de todos los segmentos relacionada con la versión de HL7.</span><span class="sxs-lookup"><span data-stu-id="47fbe-103">The **segments_\<*version*>.xsd** file includes datatypes_\<*version*>.xsd and contains the definition of all the segments related to the HL7 version.</span></span> <span data-ttu-id="47fbe-104">Cada esquema de mensaje utiliza segments_\<*versión*> .xsd.</span><span class="sxs-lookup"><span data-stu-id="47fbe-104">Each message schema uses segments_\<*version*>.xsd.</span></span> <span data-ttu-id="47fbe-105">Mensaje de HL7 definiciones están bajo cada subcarpeta e incluyen segments_\<*versión*> .xsd.</span><span class="sxs-lookup"><span data-stu-id="47fbe-105">HL7 message definitions are under each subfolder and include segments_\<*version*>.xsd.</span></span> <span data-ttu-id="47fbe-106">Las tablas de base de datos SegmentDataElements y DataElements acceso generan el segments_\<*versión*> archivo .xsd, que incluye un puntero al archivo de esquema Fields.xsd para todos los tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="47fbe-106">The SegmentDataElements and DataElements Access database tables generate the segments_\<*version*>.xsd file, which includes a pointer to the Fields.xsd schema file for all data types.</span></span> <span data-ttu-id="47fbe-107">El formato de nombre de archivo de esquema es:</span><span class="sxs-lookup"><span data-stu-id="47fbe-107">The schema file name format is:</span></span>  
  
```  
  
<xxx>_<nnn>_<vaa>_GLO_DEF.xsd  
```  
  
 <span data-ttu-id="47fbe-108">Donde *xxx* es el tipo de mensaje,  *nnn*  es el evento de desencadenador, *vaa* es el número de versión, GLO indica globalizar, y DEF indica de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="47fbe-108">Where *xxx* is the message type, *nnn* is the trigger event, *vaa* is the version number, GLO indicates globalize, and DEF indicates default.</span></span> <span data-ttu-id="47fbe-109">El archivo de esquema  *\<xxx >*_*\<nnn>*\_*\<vaa >* \_  *\<glo >*\_*\<def >*.xsdis generados a partir de la base de datos EventMessageTypeSegments y SegmentDataElements acceso tablas e incluye un puntero a los segmentos\_\<*versión*> archivo de esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="47fbe-109">The schema file *\<xxx>*_*\<nnn>*\_*\<vaa>*\_*\<glo>*\_*\<def>*.xsdis generated from the EventMessageTypeSegments and SegmentDataElements Access database tables and includes a pointer to the Segments\_\<*version*>.xsd schema file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47fbe-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="47fbe-110">See Also</span></span>  
 <span data-ttu-id="47fbe-111">[Archivos de esquema HL7 2.X comunes](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="47fbe-111">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="47fbe-112">[Los esquemas comunes de los tipos de datos](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="47fbe-112">[Data Types Common Schemas](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span></span>  
 [<span data-ttu-id="47fbe-113">Valores de tabla de esquemas comunes</span><span class="sxs-lookup"><span data-stu-id="47fbe-113">Table Values Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)