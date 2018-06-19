---
title: Configurar el Desensamblador SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, disassembler
- disassembler, configuring
ms.assetid: f3773781-7412-421c-943c-18cc665da8d9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26147924950a73b0f654531e9e0eff8e5ac82541
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005365"
---
# <a name="configuring-the-swift-disassembler"></a>Configurar el Desensamblador SWIFT
El Desensamblador SWIFT (DASM) realiza las tareas siguientes cuando se invoca en un [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalización de recepción:  
  
-   Detecta el tipo de mensaje dinámicamente y resuelve el esquema del documento  
  
-   Analiza los archivos planos SWIFT en XML  
  
-   Invoca el lector para realizar la validación XML (esquema) de validación de XML  
  
-   Invoca el motor de reglas de negocios (BRE) para realizar la validación del BRE  
  
-   Publica un mensaje XML analizado en la base de datos de cuadro de mensajes con propiedades promocionadas de contexto y la colección de errores serializado de XML  
  
-   Lotes de entrada de procesos  
  
 Puede configurar la funcionalidad mencionada anteriormente para satisfacer los requisitos específicos para un escenario de usuario y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] solución.  
  
 Diseñador de canalizaciones de BizTalk se configura el Desensamblador SWIFT durante el tiempo de desarrollo de la canalización de recepción personalizada.  
  
 Para configurar el Desensamblador SWIFT una vez agregada a la fase de desensamblado de una canalización de recepción personalizada, seleccione el componente de desensamblador SWIFT en el lienzo del Diseñador de canalizaciones de BizTalk. El Desensamblador SWIFT, a continuación, recibe el foco y se puede establecer sus propiedades de configuración mediante la ventana Propiedades en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].  
  
 Para una tabla de propiedades de configuración disponibles y sus descripciones y obtener detalles de uso, vea [propiedades de configuración de SWIFT Desensamblador](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md).  
  
 Para obtener información sobre cómo usar el Desensamblador SWIFT para diferentes escenarios y establecer las propiedades de configuración, consulte [trabajar con el Desensamblador de SWIFT y de ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).  
  
 Cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] compila la canalización personalizada binaria, estáticamente escribe los valores de configuración en la canalización personalizada. Por lo tanto, no se puede cambiar las propiedades de configuración durante la implementación o tiempo de ejecución.  
  
> [!NOTE]
>  Una vez que configura, compila e implementa una canalización personalizada, cambios en la configuración requieren volver a compilar y volver a implementar la canalización personalizada.  
  
 Para obtener información acerca de cómo crear, compilar e implementar canalizaciones personalizadas, consulte la Ayuda de BizTalk Server.  
  
 Esta sección contiene:  
  
-   [Propiedades de configuración del desensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)