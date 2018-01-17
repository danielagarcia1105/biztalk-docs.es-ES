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
ms.openlocfilehash: 50bdcacfe1459ba4a236c3701b786d97217db8ef
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="segments-common-schemas"></a>Esquemas comunes de segmentos
El **segments_\<*versión*\>.xsd** archivo incluye datatypes_\<*versión*\>.xsd y contiene el definición de todos los segmentos relacionada con la versión de HL7. Cada esquema de mensaje utiliza segments_\<*versión*\>.xsd. Mensaje de HL7 definiciones están bajo cada subcarpeta e incluyen segments_\<*versión*\>.xsd. Las tablas de base de datos SegmentDataElements y DataElements acceso generan el segments_\<*versión*\>archivo .xsd, que incluye un puntero al archivo de esquema Fields.xsd para todos los tipos de datos. El formato de nombre de archivo de esquema es:  
  
```  
  
<xxx>_<nnn>_<vaa>_GLO_DEF.xsd  
```  
  
 Donde *xxx* es el tipo de mensaje,  *nnn*  es el evento de desencadenador, *vaa* es el número de versión, GLO indica globalizar, y DEF indica de forma predeterminada. El archivo de esquema  *\<xxx\>*_*\<nnn\>*\_*\<vaa\>*  \_  *\<glo\>*\_*\<def\>*.xsdis generados a partir de la EventMessageTypeSegments y SegmentDataElements acceso de base de datos las tablas e incluye un puntero a los segmentos\_\<*versión*\>archivo de esquema XSD.  
  
## <a name="see-also"></a>Vea también  
 [Archivos de esquema HL7 2.X comunes](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [Los esquemas comunes de los tipos de datos](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md)   
 [Valores de tabla de esquemas comunes](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)