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
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="data-types-common-schemas"></a>Los esquemas comunes de los tipos de datos
El **datatypes_*\<versión\>*.xsd** archivo de esquema (donde  *\<versión\>*  es el número de versión de HL7) contiene la definición de todos los tipos de datos elementales y de materiales compuestos de HL7 para la versión de HL7 correspondiente. El segments_*\<versión\>*archivo .xsd usa este archivo para que coincida con la versión de HL7 correspondiente. La tabla de base de datos de DataStructures Access genera el DataTypes_*\<versión\>*archivo de esquema XSD. El ejemplo siguiente es una entrada para el tipo de datos básico HL7 **ST**:  
  
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