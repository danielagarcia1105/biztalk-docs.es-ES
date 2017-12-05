---
title: "Crear esquemas de encabezado personalizado para la detección del tipo de mensaje dinámico | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, dynamic resolution
- schemas, message types
- schemas, custom headers
- header schemas
ms.assetid: 0c936c57-b533-47ca-9258-576b021fd016
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c87ba83961b9daac07028a994d7c01add0c11a73
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="creating-custom-header-schemas-for-dynamic-message-type-discovery"></a>Crear esquemas de encabezado personalizado para la detección del tipo de mensaje dinámico
En la mayoría de los escenarios, debe especificar el esquema de encabezado SWIFT predeterminado (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) para la propiedad de configuración de esquema de encabezado de SWIFT del desensamblador SWIFT. El Desensamblador SWIFT usa el esquema de encabezado SWIFT predeterminado para analizar los encabezados del mensaje que se ajustan a la especificación estándar de SWIFT, y se las necesarias las propiedades promocionadas para facilitar la resolución de esquema dinámico (y subtipo de "tipo dual" Los mensajes de SWIFT como MT574_IRSLST y MT574_W8BENO). Para obtener más información sobre el esquema de encabezado SWIFT predeterminado y para comprender cómo el Desensamblador SWIFT realiza la resolución de esquemas, consulte [detección dinámica de tipo de mensaje y la resolución de esquema](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md).  
  
 Para otros escenarios donde los mensajes contienen datos de encabezado de SWIFT no estándar, puede usar un esquema de encabezado personalizado para su análisis de encabezado y detección de tipo de mensaje dinámico. Para crear y utilizar un esquema de encabezado personalizado para la resolución de esquema dinámico, haga lo siguiente:  
  
1.  Crear un esquema personalizado que puede utilizar el Desensamblador SWIFT estructuralmente analizar el formato de datos de encabezado esperado.  
  
2.  Identificar los campos en el esquema contendrán los valores que indica el tipo de mensaje.  
  
3.  Agregue el esquema de propiedades de A4SWIFT (Microsoft.Solutions.A4SWIFT.Property.PropertySchema) a la "lista de esquemas de propiedad" del esquema de encabezado personalizado y promocionar los campos correspondientes que indican el tipo de mensaje con los siguientes [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] propiedades:  
  
    -   **A4SWIFT_MessageType**  
  
    -   **A4SWIFT_MessageType2** (opcional si **A4SWIFT_MessageTypes** se utiliza)  
  
    -   **A4SWIFT_SecondaryMessageType** (opcional)  
  
4.  Compile e implemente el esquema de encabezado personalizado.  
  
5.  Establezca la propiedad de configuración de esquema de encabezado de SWIFT del desensamblador SWIFT (en el proyecto de canalización de recepción) en el esquema de encabezado personalizado.  
  
 Para obtener más información sobre estas y otras propiedades promocionadas, consulte [A4SWIFT_ * las propiedades promocionadas](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md). Para obtener más información sobre cómo usar el Editor de BizTalk para crear y editar esquemas, promocionar propiedades mediante un esquema de propiedades y generar e implementar proyectos de esquema, vea la Ayuda de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con el desensamblador y el ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)