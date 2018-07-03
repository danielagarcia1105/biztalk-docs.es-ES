---
title: Creación de esquemas de encabezado personalizado para la detección del tipo de mensaje dinámicos | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- schemas, dynamic resolution
- schemas, message types
- schemas, custom headers
- header schemas
ms.assetid: 0c936c57-b533-47ca-9258-576b021fd016
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf73b5cf02d6fa25fdea1347e56573ff023d934a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009125"
---
# <a name="creating-custom-header-schemas-for-dynamic-message-type-discovery"></a>Creación de esquemas de encabezado personalizado para la detección del tipo de mensaje dinámicos
En la mayoría de los escenarios, debe especificar el esquema predeterminado de encabezados de SWIFT (Microsoft.Solutions.FinancialServices.SWIFT.RuntimeSchemas.HeaderSchema) para la propiedad de configuración de esquema de encabezado de SWIFT del desensamblador de SWIFT. El Desensamblador de SWIFT usa el esquema predeterminado de encabezados de SWIFT para analizar los encabezados del mensaje que se ajustan a la especificación estándar de SWIFT, y se las necesarias las propiedades promocionadas para facilitar la resolución de esquema dinámico (y subtipo de "tipo dual" Los mensajes de SWIFT como MT574_IRSLST y MT574_W8BENO). Para obtener más información sobre el esquema predeterminado de encabezados de SWIFT y comprender cómo el Desensamblador de SWIFT realiza la resolución de esquemas, vea [detección dinámica de tipos de mensaje y la resolución de esquemas](../../adapters-and-accelerators/accelerator-swift/dynamic-message-type-discovery-and-schema-resolution.md).  
  
 Para otros escenarios donde los mensajes contienen datos de encabezado estándar que no sean de SWIFT, puede usar un esquema de encabezado personalizado para el encabezado de análisis y detección de tipos de mensaje dinámicos. Para crear y usar un esquema de encabezado personalizado para la resolución de esquemas dinámico, realice lo siguiente:  
  
1. Crear un esquema personalizado que puede usar el Desensamblador de SWIFT estructuralmente analizar el formato de datos de encabezado esperado.  
  
2. Identificar los campos en el esquema que va a contener los valores que indica el tipo de mensaje.  
  
3. Agregue el esquema de propiedades de A4SWIFT (Microsoft.Solutions.A4SWIFT.Property.PropertySchema) a la "lista de esquemas de propiedades" del esquema de encabezado personalizado y promocionar los campos adecuados que indican el tipo de mensaje con el siguiente [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] propiedades:  
  
   -   **A4SWIFT_MessageType**  
  
   -   **A4SWIFT_MessageType2** (opcional si **A4SWIFT_MessageTypes** se utiliza)  
  
   -   **A4SWIFT_SecondaryMessageType** (opcional)  
  
4. Compile e implemente el esquema de encabezado personalizado.  
  
5. Establezca la propiedad de configuración de esquema de encabezado de SWIFT del desensamblador de SWIFT (en el proyecto de canalización de recepción) en el esquema de encabezado personalizado.  
  
   Para obtener más información sobre estas y otras propiedades promocionadas, consulte [A4SWIFT_ * las propiedades promocionadas](../../adapters-and-accelerators/accelerator-swift/a4swift-promoted-properties.md). Para obtener más información sobre cómo usar el Editor de BizTalk para crear y editar esquemas, promocionar propiedades mediante un esquema de propiedades y crear e implementar proyectos de esquema, vea la Ayuda de BizTalk Server.  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con el desensamblador y el ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)