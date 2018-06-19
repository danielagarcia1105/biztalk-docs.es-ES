---
title: Eventos y las carpetas de 2,4 XML de HL7 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- events, HL7 2.XML versions
- HL7, default sub-folders
- HL7, events
ms.assetid: bc6c5d75-66c7-4269-bfb9-59cab5999a73
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 10c9445a1d5c7978b526fd0347dc6defa3214640
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204812"
---
# <a name="hl7-24-xml-folders-and-events"></a>Eventos y las carpetas de 2,4 XML HL7
En la tabla siguiente se enumera las subcarpetas creadas por el Asistente para la instalación en la carpeta de la versión 2.4 HL7 para mensajes codificados en XML. Estas subcarpetas contienen los esquemas utilizados por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla. Los nombres de la subcarpeta describen los tipos de eventos que admiten estos esquemas.  
  
|Subcarpeta.|Eventos|  
|----------------|------------|  
|Administración de pacientes|A01 A62, K21, K22, K23, K24, Q21 Q24|  
|Entrada de pedido|O01 O22, Q06, Q30 P26, RAR, RDR, RER, RGR, ERROR, V01 V04, Z73, Z74|  
|Query|J01, J02, K11, K13, K15, Q01 Q05, Q07 Q09, PREGUNTA 11, RESPUESTA A P13, RESPUESTA A P15-Q17, R07 R09, Z75 Z99|  
|Administración financiera|P01 ~ P06, P10|  
|Informes de observación|C01 C12, P07, P08, P09, R01, R02, R04, R21, W01, W02|  
|Archivos maestros|M01-M12, MFA|  
|Administración de registros/información médica|T01 T12|  
|Programación|S26 S01|  
|Referencia de pacientes|I01 I15|  
|Atención del paciente|PC1-PCH, PCJ, PCK, PCL|  
|Automatización de clínicos de laboratorio|U01 U13|  
|Administración de aplicaciones|N01, N02|  
|Administración del personal|B01-B06, K25, Q25|  
  
## <a name="see-also"></a>Vea también  
 [Uso de esquemas XML de HL7 2.](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)