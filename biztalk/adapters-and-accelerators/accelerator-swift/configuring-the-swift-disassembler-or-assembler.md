---
title: Configurar el Desensamblador SWIFT o ensamblador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, disassembler
- disassembler, configuring
- configuring, assembler
ms.assetid: 56e421f2-0292-40af-b878-0cba1b034e19
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8920a8b74da14eeb8186d153444ced7c54d57724
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-the-swift-disassembler-or-assembler"></a>Configurar el Desensamblador SWIFT o ensamblador
Después de agregar el SWIFT Desensamblador o ensamblador SWIFT a una canalización personalizada, debe configurarlo para proporcionar la funcionalidad que desee para el escenario concreto (por ejemplo, la habilitación o deshabilitación de detección de tipo de mensaje dinámico, anulando entrante, validación de XML Validación de motor de reglas de negocios (BRE) y así sucesivamente). Debe configurar el Desensamblador SWIFT y ensamblador durante el tiempo de desarrollo antes de compilar e implementar las canalizaciones personalizadas que invocación. Para configurar el ensamblador/desensamblador SWIFT, seleccione el componente en el Diseñador de canalizaciones y editar las propiedades de configuración en la ventana Propiedades.  
  
 Hacer referencia a [propiedades de configuración de SWIFT Desensamblador](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md) para obtener información detallada y las descripciones de cada propiedad de configuración, así como otra información de uso y la configuración.  
  
 Hacer referencia a [propiedades de configuración de ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md) para obtener información detallada y las descripciones de la propiedad de configuración de codificación de juego de caracteres, así como otra información de uso y la configuración.  
  
> [!NOTE]
>  Después configura, compila e implementa las canalizaciones personalizadas, cambios en la configuración será necesario volver a compilar y volver a hacer la implementación de las canalizaciones personalizadas.  
  
 Después configura, compila e implementa sus canalizaciones personalizadas para procesar los mensajes de SWIFT, puede establecer hasta ubicaciones de recepción que utilizan el SWIFT personalizada canalización de recepción y puertos que usan su SWIFT personalizado envían una canalización de envío. Para obtener más información sobre cómo implementar canalizaciones y configurar puertos de recepción, ubicaciones de recepción y puertos de envío, vea [módulo 4: creación de XML de recepción y puertos de envío de archivo sin formato](../../adapters-and-accelerators/accelerator-swift/module-4-adding-an-xml-receive-location-and-flat-file-send-port.md), [módulo 5: creación de recepción de archivo sin formato y Puertos de envío XML](../../adapters-and-accelerators/accelerator-swift/module-5-adding-a-flat-file-receive-location-and-xml-send-port.md)y la Ayuda de BizTalk Server.  
  
 Esta sección contiene:  
  
-   [Configuración del desensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-disassembler.md)  
  
-   [Configuración del ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/configuring-the-swift-assembler.md)  
  
## <a name="see-also"></a>Vea también  
 [Trabajar con el desensamblador y el ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md)