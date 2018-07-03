---
title: Personalizaciones no declaradas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- undeclared customizations
- Z objects, undeclared customizations
- customizing, Z objects
- customizing, undeclared customizations
ms.assetid: f062dbb7-2c78-47ea-a927-99e1fba4854b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05a33abb76d49cfa5db640b1d15d9fde420f19c6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974229"
---
# <a name="undeclared-customizations"></a>Personalizaciones no declaradas
Puede agregar datos a un mensaje sin tener que definir el formato o la naturaleza de los datos. Hacerlo mediante el uso de los segmentos de Z no declarados. Segmentos de Z no declarados son instancias inesperadas al final de un mensaje. El validador de XML/analizador no valida el segmento. No se define ningún esquema. Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) trata el segmento como un objeto binario grande (BLOB).  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] pasa los datos de segmentos de Z no declarados a través como la tercera parte de un mensaje de tres partes. Las tres partes son el encabezado, el cuerpo y el segmento de Z no declarado, que también se denomina parte Z. Un principio de Id. de segmento con la letra "Z", por ejemplo, "ZPD" para obtener información personalizada datos demográficos de los pacientes, identifica la parte de la Z.  
  
## <a name="see-also"></a>Vea también  
 [Personalizaciones declaradas](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md)   
 [Extender esquemas HL7 2.X con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [Procesamiento de mensajes de HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Uso de esquemas HL7 2.X](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)