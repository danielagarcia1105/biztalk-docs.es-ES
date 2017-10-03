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
# <a name="data-types-common-schemas"></a>Los esquemas comunes de los tipos de datos
El  **datatypes_*\<versión >*el archivo de esquema .xsd ** (donde  *\<versión >* es el número de versión de HL7) contiene la definición de todos los HL7 elementales y de materiales compuestos tipos de datos de la versión de HL7 correspondiente. El segments_*\<versión >*archivo .xsd usa este archivo para que coincida con la versión de HL7 correspondiente. La tabla de base de datos de DataStructures Access genera el DataTypes_*\<versión >*archivo de esquema XSD. El ejemplo siguiente es una entrada para el tipo de datos básico HL7 **ST**:  
  
```  
<xsd:simpleType name="ST">  
  <xsd:restriction base="xsd:string" />   
</xsd:simpleType>  
```  
  
 Este ejemplo se define **ST** como un **cadena**.  
  
## <a name="see-also"></a>Vea también  
 [Archivos de esquema HL7 2.X comunes](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [Esquemas comunes de segmentos](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)   
 [Valores de tabla de esquemas comunes](../../adapters-and-accelerators/accelerator-hl7/table-values-common-schemas.md)