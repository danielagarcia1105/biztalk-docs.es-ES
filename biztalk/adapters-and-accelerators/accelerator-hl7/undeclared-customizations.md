---
title: Las personalizaciones no declaradas | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- undeclared customizations
- Z objects, undeclared customizations
- customizing, Z objects
- customizing, undeclared customizations
ms.assetid: f062dbb7-2c78-47ea-a927-99e1fba4854b
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77f688e4cf6a4bbb55243d9f5f6f60e144bad862
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="undeclared-customizations"></a>Personalizaciones no declaradas
Puede agregar datos a un mensaje sin tener que definir el formato o la naturaleza de los datos. La forma de hacerlo es mediante el uso de los segmentos de Z no declarados. Segmentos de Z no declarados son instancias inesperados al final de un mensaje. El validador de analizador/XML no valida el segmento. No se define ningún esquema. [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) trata el segmento como un objeto binario grande (BLOB).  
  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]no declarados segmentar datos de Z a través de se pasa como la tercera parte de un mensaje de tres partes. Las tres partes son el encabezado, el cuerpo y el segmento de Z no declarado, también denominado elemento Z. Un segmento identificador que comienza con la letra "Z", por ejemplo, "ZPD" para obtener información de datos demográficos de los pacientes personalizado, identifica la parte de Z.  
  
## <a name="see-also"></a>Vea también  
 [Personalizaciones declaradas](../../adapters-and-accelerators/accelerator-hl7/declared-customizations.md)   
 [Extender HL7 2.X esquemas con objetos de Z](../../adapters-and-accelerators/accelerator-hl7/extending-hl7-2-x-schemas-with-z-objects.md)   
 [Procesamiento de mensajes HL7](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [Procesamiento de mensajes](../../adapters-and-accelerators/accelerator-hl7/message-processing.md)   
 [Utilizar esquemas 2.X HL7](../../adapters-and-accelerators/accelerator-hl7/using-hl7-2-x-schemas.md)