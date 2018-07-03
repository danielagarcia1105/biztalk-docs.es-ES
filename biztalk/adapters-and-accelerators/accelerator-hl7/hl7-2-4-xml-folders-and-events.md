---
title: Eventos y las carpetas de HL7 2.4 XML | Microsoft Docs
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
ms.openlocfilehash: 7e7665a5101f5b49abd9ba087bd07cf799384c2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993293"
---
# <a name="hl7-24-xml-folders-and-events"></a>Eventos y las carpetas de HL7 2.4 XML
En la tabla siguiente se enumera las subcarpetas creadas por el Asistente de instalación dentro de la carpeta de HL7 versión 2.4 para mensajes codificados en XML. Estas subcarpetas contienen los esquemas utilizados por el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla. Los nombres de subcarpeta describen los tipos de eventos que admiten estos esquemas.  
  
|Subcarpeta|Eventos|  
|----------------|------------|  
|Administración de pacientes|A01 A62, K21, K22, K23, K24, Q21 Q24|  
|Entrada de pedido|O01 O22, Q06, P26 Q30, RAR, RDR, RER, RGR, ROR, V01 V04, Z73, Z74|  
|Consulta|J01, J02, K11, K13, K15, Q01 Q05, Q07 Q09, P11, RESPUESTA A P13, RESPUESTA A P15 Q17, R07 R09, Z75 Z99|  
|Administración financiera|P01 ~ P06, P10|  
|Informes de observación|C01 C12, P07, P08, P09, R01, R02, R04, R21, W01, W02|  
|Archivos maestros|M01-M12, MFA|  
|Administración de registros médicos o información|T01 T12|  
|Programación|S01 S26|  
|Referencia de pacientes|I01 I15|  
|Atención al paciente|PC1-PCH, PCJ, PCK, PCL|  
|Automatización del laboratorio clínica|U01 U13|  
|Administración de aplicaciones|N01, N02|  
|Administración de personal|B01-B06, K25, Q25|  
  
## <a name="see-also"></a>Vea también  
 [Uso de esquemas de HL7 2.XML](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)