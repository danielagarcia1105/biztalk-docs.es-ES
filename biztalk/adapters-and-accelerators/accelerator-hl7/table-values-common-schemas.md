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
ms.openlocfilehash: a55491f0a44bec6a5cd5eaf4fe120f693b3996c5
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="table-values-common-schemas"></a>Valores de tabla de esquemas comunes
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) genera el **tablevalues_*\<versión\>*.xsd** de archivos para cada versión de HL7 y busca el archivo en la raíz de la HL7 carpeta específica de la versión. El archivo de esquema común de tipos de datos hace referencia el archivo de esquema común de valores de tabla.  
  
 Valores de estas tablas están en el formulario de enumeraciones. Cada enumeración define los valores que son aceptables en los campos de uno o varios de los esquemas de mensaje. Puede ver qué tabla se aplica a un nodo de un esquema de mensaje abrir el esquema en el Editor de BizTalk, haga clic en un nodo y examinando la **Base Data Type** propiedad en el panel de propiedades.  
  
 No podrá ver lo que los valores aceptables para este nodo son, sin embargo, mediante la visualización de la enumeración en el panel de propiedades para el nodo de esquema de mensaje. Esto es porque el archivo de esquema común de valores de tabla define la enumeración. Para ver las enumeraciones, haga clic en **tablevalues_*\<versión\>*.xsd** en el esquema de árbol en el Editor de BizTalk y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón en la fila de la enumeración en el panel Propiedades.  
  
## <a name="see-also"></a>Vea también  
 [Archivos de esquema HL7 2.X comunes](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [Los esquemas comunes de los tipos de datos](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md)   
 [Esquemas comunes de segmentos](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)