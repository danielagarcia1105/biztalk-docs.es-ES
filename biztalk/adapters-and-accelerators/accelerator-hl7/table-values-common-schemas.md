---
title: Valores de tabla de esquemas comunes | Microsoft Docs
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
ms.openlocfilehash: 90c66ee201e5a73d8f632a8002a9a3627d1885f1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968069"
---
# <a name="table-values-common-schemas"></a>Valores de tabla de esquemas comunes
Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) genera el **tablevalues_*\<versión\>*.xsd** de archivos para cada versión de HL7 y busca el archivo en la raíz de la carpeta específica de la versión de HL7. El archivo de esquema comunes de tipos de datos hace referencia el archivo de esquema común de valores de tabla.  
  
 Los valores de estas tablas son en forma de enumeraciones. Cada enumeración define los valores que son aceptables en los campos de uno o varios de los esquemas de mensaje. Puede ver qué tabla se aplica a un nodo de un esquema de mensaje abriendo el esquema en el Editor de BizTalk, haga clic en un nodo y examinando el **Base Data Type** propiedad en el panel Propiedades.  
  
 No podrá ver lo que los valores aceptables para este nodo son, sin embargo, mediante la visualización de la enumeración en el panel de propiedades para el nodo de esquema de mensaje. Esto es porque el archivo de esquema común de valores de tabla define la enumeración. Para ver las enumeraciones, haga clic en **tablevalues_*\<versión\>*.xsd** en el esquema de árbol en el Editor de BizTalk y, a continuación, haga clic en el botón de puntos suspensivos (**...** ) botón en la fila de la enumeración en el panel Propiedades.  
  
## <a name="see-also"></a>Vea también  
 [Archivos de esquema comunes de HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/hl7-2-x-common-schema-files.md)   
 [Los esquemas comunes de los tipos de datos](../../adapters-and-accelerators/accelerator-hl7/data-types-common-schemas.md)   
 [Esquemas comunes de segmentos](../../adapters-and-accelerators/accelerator-hl7/segments-common-schemas.md)