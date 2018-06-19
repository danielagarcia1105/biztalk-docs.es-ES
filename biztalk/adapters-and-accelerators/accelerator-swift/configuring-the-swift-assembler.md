---
title: Configurar el ensamblador SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler, configuring
- configuring, assembler
ms.assetid: 76944226-e29b-4a7f-a4ab-3c3d5f13ec51
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f77d47b2b3ab687f2fd72242f4ddbbc68ae8530c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004613"
---
# <a name="configuring-the-swift-assembler"></a>Configurar el ensamblador SWIFT
El ensamblador de SWIFT realiza las tareas siguientes cuando se invoca en un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalización de envío:  
  
-   Detecta el tipo de mensaje dinámicamente y resuelve el esquema del documento  
  
-   Serializa el XML analizado en archivos planos SWIFT  
  
 Puede configurar la codificación juego de caracteres utilizado para codificar el resultado serializado (por ejemplo, para utilizar la codificación ASCII o Unicode).  
  
 Configurar el ensamblador SWIFT durante el tiempo de desarrollo de la canalización de envío personalizada que utiliza el ensamblador SWIFT.  
  
 Diseñador de canalizaciones de BizTalk se configura el ensamblador SWIFT durante el tiempo de desarrollo de la canalización de envío personalizada.  
  
 Para configurar el ensamblador SWIFT una vez agregada a la fase de ensamblado de canalización de envío personalizada, seleccione el componente de ensamblador SWIFT en el lienzo del Diseñador de canalizaciones. El ensamblador SWIFT, a continuación, recibe el foco, y puede establecer sus propiedades de configuración mediante la ventana Propiedades en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].  
  
 Para una tabla de propiedades de configuración disponibles y sus descripciones y obtener detalles de uso, vea [propiedades de configuración de ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md).  
  
 Para obtener información sobre cómo usar el ensamblador SWIFT para diferentes escenarios y establecer las propiedades de configuración, consulte [trabajar con el Desensamblador de SWIFT y de ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).  
  
 Cuando se compila el archivo binario de canalización personalizado, estáticamente escribe los valores de configuración a la canalización personalizada. Por lo tanto, no se puede cambiar las propiedades de configuración durante la implementación o tiempo de ejecución.  
  
> [!NOTE]
>  Una vez que configura, compila e implementa una canalización personalizada, cambios en la configuración requieren volver a compilar y volver a implementar la canalización personalizada.  
  
 Para obtener información acerca de cómo crear, compilar e implementar canalizaciones personalizadas, consulte la Ayuda de BizTalk Server.  
  
 Esta sección contiene:  
  
-   [Propiedades de configuración del ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)