---
title: Compatibilidad con juego de caracteres de EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4f4492b-8cbe-48ed-810a-3e73e1cb5996
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: da903e0cde796c6b12c30ea32dfe4012215a231e
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005837"
---
# <a name="edi-character-set-support"></a>Compatibilidad de juegos de caracteres de EDI
Este tema indican qué juegos de caracteres compatibles con las características EDI de BizTalk Server.  
  
|Codificación EDI|Juegos de caracteres admitidos|  
|------------------|------------------------------|  
|X 12 (incluida HIPAA)|X12: juego de caracteres básico (subjuego de ASCII)|  
|-|X12: juego de caracteres ampliado (subjuego de ASCII que también incluye caracteres ISO8859-1)|  
|-|UTF8/UNICODE|  
|EDIFACT|UNOA|  
|-|UNOB|  
|-|UNOC - ISO 8859-1: procesamiento de información - parte 1: alfabeto latino N.º 1|  
|-|KECA - KS_C_5601-1987 (página de códigos 949 de Windows)|  
|-|UNOX (ISO2022 – JP)|  
|-|Datos codificados en UTF8 UNOY - **Nota:** los caracteres UNOD a UNOK establece que admiten UTF8 también se admiten los datos codificados.|  
  
## <a name="setting-the-edi-character-set"></a>Configurar el juego de caracteres de EDI  
 En el caso de intercambios con codificación X12, se puede establecer el juego de caracteres para una canalización configurando la propiedad de canalización CharacterSet. Para obtener más información, consulte [configurar propiedades de canalización de EDI](../core/configuring-edi-pipeline-properties.md).  
  
> [!NOTE]
>  Existe un control de juego de caracteres de X12 en la página Generación de sobres de intercambio X12 del cuadro de diálogo de propiedades X12 de EDI de la consola de administración de BizTalk Server, pero dicho control solo se usa para validar los valores especificados de las propiedades del cuadro de diálogo Propiedades de EDI.  
  
 En el caso de intercambios con codificación EDIFACT, se puede establecer el conjunto de caracteres para una entidad configurando la propiedad de entidad UNB1.1 en la página de propiedades Definición de segmento UNB para la entidad como receptor de intercambio. El valor del campo UNB1.1 que figura en el encabezado del intercambio determina la codificación empleada en un intercambio entrante. Para obtener más información, consulte [configuración de sobres (configuración del conjunto de transacciones EDIFACT)](../core/configuring-envelopes-edifact-transaction-set-settings.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar propiedades de canalización EDI](../core/configuring-edi-pipeline-properties.md)   
 [Configuración de sobres (configuración del conjunto de transacciones EDIFACT)](../core/configuring-envelopes-edifact-transaction-set-settings.md)