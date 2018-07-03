---
title: Esquemas comunes de segmentos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- 2.X schemas, common schemas
- 2.X schemas, segments
- common schemas
ms.assetid: 6f66bce9-ead8-46c1-a66c-830750adc73b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46e961934b1595217b94aab82b2adae9fd3e456f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985485"
---
# <a name="segments-common-schemas"></a><span data-ttu-id="29cc4-102">Esquemas comunes de segmentos</span><span class="sxs-lookup"><span data-stu-id="29cc4-102">Segments Common Schemas</span></span>
<span data-ttu-id="29cc4-103">El **segments_\<*versión*\>.xsd** archivo incluye datatypes_\<*versión*\>.xsd y contiene el definición de todos los segmentos relacionada con la versión de HL7.</span><span class="sxs-lookup"><span data-stu-id="29cc4-103">The **segments_\<*version*\>.xsd** file includes datatypes_\<*version*\>.xsd and contains the definition of all the segments related to the HL7 version.</span></span> <span data-ttu-id="29cc4-104">Cada esquema de mensaje utiliza segments_\<*versión*\>.xsd.</span><span class="sxs-lookup"><span data-stu-id="29cc4-104">Each message schema uses segments_\<*version*\>.xsd.</span></span> <span data-ttu-id="29cc4-105">Mensajes de HL7 definiciones están bajo cada subcarpeta e incluyen segments_\<*versión*\>.xsd.</span><span class="sxs-lookup"><span data-stu-id="29cc4-105">HL7 message definitions are under each subfolder and include segments_\<*version*\>.xsd.</span></span> <span data-ttu-id="29cc4-106">Las tablas de base de datos SegmentDataElements y acceso DataElements generan el segments_\<*versión*\>archivo .xsd, que incluye un puntero al archivo de esquema Fields.xsd para todos los tipos de datos.</span><span class="sxs-lookup"><span data-stu-id="29cc4-106">The SegmentDataElements and DataElements Access database tables generate the segments_\<*version*\>.xsd file, which includes a pointer to the Fields.xsd schema file for all data types.</span></span> <span data-ttu-id="29cc4-107">Es el formato de nombre de archivo de esquema:</span><span class="sxs-lookup"><span data-stu-id="29cc4-107">The schema file name format is:</span></span>  
  
```  
  
<xxx>_<nnn>_<vaa>_GLO_DEF.xsd  
```  
  
 <span data-ttu-id="29cc4-108">Donde *xxx* es el tipo de mensaje, *nnn* es el evento de desencadenador, *vaa* es el número de versión, GLO indica globalizar, y DEF indica de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="29cc4-108">Where *xxx* is the message type, *nnn* is the trigger event, *vaa* is the version number, GLO indicates globalize, and DEF indicates default.</span></span> <span data-ttu-id="29cc4-109">El archivo de esquema  *\<xxx\>*<em>*\<nnn\>*  \\</em>   *\< vaa\>*\_*\<glo\>*\_*\<def\>*.xsdis generado a partir de las tablas de base de datos EventMessageTypeSegments y acceso SegmentDataElements e incluye un puntero a los segmentos\_\<*versión*\>archivo de esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="29cc4-109">The schema file *\<xxx\>*<em>*\<nnn\>*\\</em>*\<vaa\>*\_*\<glo\>*\_*\<def\>*.xsdis generated from the EventMessageTypeSegments and SegmentDataElements Access database tables and includes a pointer to the Segments\_\<*version*\>.xsd schema file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="29cc4-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="29cc4-110">See Also</span></span>  
 <span data-ttu-id="29cc4-111">[Archivos de esquema comunes de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span><span class="sxs-lookup"><span data-stu-id="29cc4-111">[HL7 2.X Common Schema Files](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md) </span></span>  
 <span data-ttu-id="29cc4-112">[Los esquemas comunes de los tipos de datos](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="29cc4-112">[Data Types Common Schemas](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md) </span></span>  
 [<span data-ttu-id="29cc4-113">Valores de tabla de esquemas comunes</span><span class="sxs-lookup"><span data-stu-id="29cc4-113">Table Values Common Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)