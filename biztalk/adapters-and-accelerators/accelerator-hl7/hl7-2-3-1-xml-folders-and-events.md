---
title: HL7 2.3.1 eventos y las carpetas XML | Documentos de Microsoft
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
ms.openlocfilehash: 79b25e0563f404d0f8b0600829398729a6c80e65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204324"
---
# <a name="hl7-231-xml-folders-and-events"></a>HL7 2.3.1 eventos y las carpetas XML
En la tabla siguiente se enumera las subcarpetas creadas por el Asistente para la instalación en la carpeta de versión 2.3.1 HL7 para mensajes codificados en XML. Estas subcarpetas contienen los esquemas utilizados por [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) para validar, analizar y serializar los eventos enumerados en la columna de eventos de esta tabla. Los nombres de la subcarpeta describen los tipos de eventos que admiten estos esquemas.  
  
|Subcarpeta|Eventos|  
|---------------|------------|  
|Administración de pacientes|A01 A51|  
|Entrada de pedido|O01, O02, Q06, R0R, RAR, RDR, RER, RGR, V04 V01|  
|Query|CNQ, Q01-Q03, Q05, Q07-Q09, R07, R08, R09|  
|Administración financiera|P01 P06|  
|Informes de observación|C01 C12, P06, P07, P09, R01 R06, W01, W02|  
|Archivos maestros|M01-M11, MFA|  
|Administración de registros/información médica|T01 T12|  
|Programación|S26 S01|  
|Referencia de pacientes|I01 I15|  
|Atención del paciente|PC1-PCH, PCJ, PCK, PCL|  
|Administración de red|N01, N02|  
  
## <a name="see-also"></a>Vea también  
 [Uso de esquemas XML de HL7 2.](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-xml-schemas.md)