---
title: Esquemas de documento EDI | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc3a30b8-0686-4c06-985b-13f2c95f8e99
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b96089f7f76af1183f457202bb2e22b5be7f146
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="edi-document-schemas"></a>Esquemas de documentos EDI
Los esquemas de documento definen el cuerpo de un tipo de documento de transacción EDI.  
  
## <a name="schema-delivery-and-setup"></a>Entrega y configuración de esquemas  
 Esquemas de documento EDI se entregan en estado comprimido en un archivo ejecutable autoextraíble, [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\MicrosoftEdiXSDTemplates.exe. El archivo ejecutable autoextraíble garantiza que se ha creado una estructura de carpetas adecuada (según el tipo de codificación y los subtipos de versión y lanzamiento). Cuando se ejecuta, el ejecutable deposita esquemas EANCOM, EDIFACT, HIPAA y X12 en subcarpetas del mismo directorio que el ejecutable.  
  
 Los espacios de nombres de esquema predeterminados son:  
  
-   Para X12: `http://schemas.microsoft.com/BizTalk/EDI/X12/2006`  
  
-   Para EDIFACT: `http://schemas.microsoft.com/BizTalk/EDI/EDIFACT/2006`  
  
## <a name="schema-naming-convention"></a>Convención de nomenclatura de esquemas  
 La convención de nomenclatura para el X12 y tipo de codificación EDIFACT es \<codificación\>_\<versión\>\<versión\>\_\<Doctype\>. El esquema X12_00401_864.xsd es un ejemplo para el tipo de documento X12 864 (versión 004, lanzamiento 01) y el esquema EDIFACT_D01C_AUTHOR.xsd es un ejemplo del tipo de documento EDIFACT AUTHOR (versión D01, lanzamiento C).  
  
> [!NOTE]
>  El nombre los esquemas EDIFACT distingue mayúsculas de minúsculas. Por ejemplo, EFACT_D98B_ORDERS y EFACT_d98B_Orders serían dos esquemas diferentes.  
  
## <a name="schema-contents"></a>Contenido de esquema  
 Un esquema de documento comienza con el encabezado de conjunto de transacciones ST y termina con el finalizador de conjunto de transacciones SE para un documento con codificación X12. Comienza con el encabezado de mensaje UNH y termina con el finalizador de mensaje UNT para un documento con codificación EDIFACT. El esquema define cada elemento de datos de estos encabezados y finalizadores.  
  
 Después, un esquema de documento define cada segmento en el conjunto de transacciones/mensaje y los elementos de datos en esos segmentos. Por ejemplo, el esquema X12_00401_864.xsd define los elementos BMG01, BMG02 y BMG03 de los segmentos BMG. El esquema especifica las características del tipo de datos complejos del segmento, por ejemplo el orden de campos, el tipo de delimitador y el espacio de nombres. Si hay reglas de validación de campos cruzados para el segmento, el esquema define las reglas. Para obtener más información, consulte [validación cruzada de segmentos de campos](../core/cross-field-segment-validation.md).  
  
 El esquema especifica las características de cada elemento de datos en el segmento, por ejemplo el tipo de datos simples, número mínimo de apariciones, longitud mínima y máxima.  
  
 Si hay un bucle en el tipo de mensaje, el esquema define los elementos de datos en cada bucle, el número mínimo y máximo de apariciones y si el bucle está enlazado o no. El esquema también define el anidamiento de un mensaje y si el bucle es explícito o implícito.  
  
## <a name="see-also"></a>Vea también  
 [Estructura de mensaje EDI](../core/edi-message-structure.md)   
 [Validación de mensajes EDI](../core/edi-message-validation.md)