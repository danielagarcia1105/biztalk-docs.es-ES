---
title: Configuración del ensamblador de SWIFT | Microsoft Docs
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
ms.openlocfilehash: 50c58ad000e465949229400128ce4c47da40806e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993669"
---
# <a name="configuring-the-swift-assembler"></a>Configuración del ensamblador de SWIFT
El ensamblador de SWIFT realiza las tareas siguientes cuando se invoca en una Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalización de envío:  
  
- Detecta el tipo de mensaje dinámicamente y se resuelve el esquema de documento  
  
- Serializa el XML analizado en archivos planos SWIFT  
  
  Puede configurar la codificación juego de caracteres utilizado para codificar el resultado serializado (por ejemplo, para utilizar la codificación ASCII o Unicode).  
  
  Configure el ensamblador de SWIFT durante el desarrollo de la canalización de envío personalizada que utiliza el ensamblador de SWIFT.  
  
  Diseñador de canalizaciones de BizTalk se configura el ensamblador de SWIFT durante el desarrollo de la canalización de envío personalizada.  
  
  Para configurar el Desensamblador de SWIFT después de que se ha agregado a la fase de ensamblado de canalización de envío personalizada, seleccione el componente de ensamblador de SWIFT en el lienzo del Diseñador de canalizaciones. El ensamblador de SWIFT, a continuación, recibe el foco, y puede establecer sus propiedades de configuración mediante la ventana Propiedades de Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].  
  
  Para una tabla de propiedades de configuración disponibles y sus descripciones y los detalles de uso, consulte [propiedades de configuración del ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md).  
  
  Para obtener información sobre cómo usar el ensamblador de SWIFT para diferentes escenarios y establecer las propiedades de configuración, consulte [trabajar con el Desensamblador de SWIFT y ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).  
  
  Cuando se compila el archivo binario de canalización personalizado, estáticamente escribe los valores de configuración a la canalización personalizada. Por lo tanto, no se puede cambiar las propiedades de configuración durante la implementación o tiempo de ejecución.  
  
> [!NOTE]
>  Después configura, compila e implementa una canalización personalizada, los cambios en la configuración requieren volver a compilar y volver a implementar la canalización personalizada.  
  
 Para obtener información acerca de cómo crear, compilar e implementar canalizaciones personalizadas, consulte la Ayuda de BizTalk Server.  
  
 Esta sección contiene:  
  
-   [Propiedades de configuración del ensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-assembler-configuration-properties.md)