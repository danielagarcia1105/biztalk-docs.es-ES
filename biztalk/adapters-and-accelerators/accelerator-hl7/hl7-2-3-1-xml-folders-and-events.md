---
title: HL7 2.3.1 XML carpetas y eventos | Microsoft Docs
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
ms.assetid: b3598cc5-46d6-489a-84a7-266ee3c40276
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6bbe1d472f844d57c7770ec4ae425fc6aef44a20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991733"
---
# <a name="hl7-231-xml-folders-and-events"></a>HL7 2.3.1 XML carpetas y eventos
En la tabla siguiente se enumera las subcarpetas creadas por el Asistente de instalación dentro de la carpeta de HL7 versión 2.3.1 para mensajes codificados en XML. Estas subcarpetas contienen los esquemas utilizados por el Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla. Los nombres de subcarpeta describen los tipos de eventos que admiten estos esquemas.  
  
|Subcarpeta|Eventos|  
|---------------|------------|  
|Administración de pacientes|A01 A51|  
|Entrada de pedido|O01, O02, Q06, R0R, RAR, RDR, RER, RGR, V01 V04|  
|Consulta|CNQ, Q01-Q03 Q05, Q07-Q09 R07, R08, R09|  
|Administración financiera|P01 P06|  
|Informes de observación|C01 C12, P06, P07, P09, R01 R06, W01, W02|  
|Archivos maestros|M01-M11, MFA|  
|Administración de registros médicos o información|T01 T12|  
|Programación|S01 S26|  
|Referencia de pacientes|I01 I15|  
|Atención al paciente|PC1-PCH, PCJ, PCK, PCL|  
|Administración de red|N01, N02|  
  
## <a name="see-also"></a>Vea también  
 [Uso de esquemas de HL7 2.XML](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)