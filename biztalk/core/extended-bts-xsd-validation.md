---
title: Validación extendida (BTS-XSD) | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f225115d-8890-4149-8e46-d1bc8af17e62
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed147515b48a23c55e552710d6a76d6df981edd7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22245956"
---
# <a name="extended-bts-xsd-validation"></a>Validación extendida (BTS-XSD)
La canalización de recepción EDI y la canalización de envío EDI realizan la validación extendida solo si el esquema se ha personalizado con elementos cuyos tipos de datos no sean EDI. No se validaría estos elementos agregados por la validación de EDI, por lo que se cubrirán mediante la validación extendida. La validación extendida usa `System.Xml.XmlValidatingReader` e incluye todas las comprobaciones que se pueden definir en un XSD estándar.  
  
 La validación extendida se configura para todos los mensajes que se envían a una entidad o que esta recibe. Para ello, seleccione la **validación extendida** checkbox en el **validación** página (en el **configuración del conjunto de transacciones** sección para X12 o EDIFACT), en el ficha de acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo. Puede habilitar la validación extendida sin habilitar la validación EDI, o viceversa.  
  
 La validación extendida consta de las siguientes comprobaciones:  
  
-   Requisito del elemento de datos y repeticiones permitidas  
  
-   Enumeraciones  
  
-   Validación de la longitud del elemento de datos (mín./máx.)  
  
> [!IMPORTANT]
>  No se admite la validación ampliada para mensajes procesados por lotes en el lado de envío de EDI.  
  
## <a name="see-also"></a>Vea también  
 [Validación del mensaje EDI](../core/edi-message-validation.md)