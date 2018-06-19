---
title: Procesamiento de confirmaciones recibidas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67f67a95-7368-40c2-a162-6ffc9de076fc
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1205c7cec5a013fef89eac49e6b953cf5f752626
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25971186"
---
# <a name="processing-a-received-acknowledgment"></a>Procesamiento de confirmaciones recibidas
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] espera una confirmación técnica si se especifica la propiedad relevante en el acuerdo. Para X12, este es el **TA1 esperado** propiedad en el **confirmaciones** página del acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo o de acuerdo de reserva Propiedades. Para EDIFACT, se trata de la **recepción del mensaje (CONTRL) esperada** propiedad en el **confirmaciones** página del acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo cuadro o de propiedades del acuerdo de reserva. Si el acuerdo de recepción procesa el mensaje recibido, generará la confirmación técnica como resultado del valor de ISA14 o UNB9 en el mensaje.  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] espera una confirmación funcional para la codificación X12 o EDIFACT si se especifica la propiedad relevante en el acuerdo. Para X12, esta propiedad es el **997 esperado** en el **confirmaciones** página del acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo o de acuerdo de reserva Propiedades. Para EDIFACT, esta propiedad es el **confirmación (CONTRL) esperada** propiedad en el **confirmaciones** página del acuerdo unidireccional en el **propiedades del acuerdo de** cuadro de diálogo o de propiedades del acuerdo de reserva. Si el acuerdo de recepción procesa el mensaje recibido, generará la confirmación técnica como resultado del valor de ISA14 o UNB9 en el mensaje.  
  
 Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] recibe una confirmación en un mensaje EDI, valida la confirmación mediante los esquemas de control de confirmación. Estos esquemas son X12_\<número de versión\>_997.xsd o X12\_\<número de versión\>_TA1.xsd para X12, EFACT\_\<número de versión\>_CONTRL.xsd para EDIFACT y X12_00501_997.xsd para HIPAA 5010.  
  
 Si la canalización de recepción procesa la confirmación entrante, correlaciona la confirmación en el intercambio EDI enviado. La canalización coloca la confirmación en el cuadro de mensajes. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]no se procesa la confirmación. La confirmación se suspenderá a menos que se configure un mecanismo para procesarla. Para procesar la confirmación, puede configurar un puerto de envío que se suscriba a esta y, a continuación, colocarla en una carpeta donde las confirmaciones se puedan eliminar de forma rutinaria.  
  
## <a name="see-also"></a>Vea también  
 [Estructura de confirmación EDI](../core/edi-acknowledgment-structure.md)   
 [Envío de una confirmación EDI](../core/sending-an-edi-acknowledgment.md)