---
title: Configurar el Desensamblador de SWIFT | Microsoft Docs
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
ms.openlocfilehash: 5ad88310f5bbf600edd576bc0bc17c64fe3ecbea
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001469"
---
# <a name="configuring-the-swift-disassembler"></a>Configurar el Desensamblador de SWIFT
El Desensamblador de SWIFT (DASM) realiza las tareas siguientes cuando se invoca en una Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] canalización de recepción:  
  
- Detecta el tipo de mensaje dinámicamente y se resuelve el esquema de documento  
  
- Analiza archivos planos SWIFT en XML  
  
- Invoca el lector para realizar la validación de XML (esquema) de validación de XML  
  
- Invoca el motor de reglas de negocios (BRE) para realizar la validación del BRE  
  
- Publica un mensaje XML analizado en la base de datos de cuadro de mensajes con propiedades promocionadas de contexto y la colección de errores serializado XML  
  
- Lotes de entrada de procesos  
  
  Puede configurar las funciones enumeradas anteriormente para satisfacer los requisitos específicos para un escenario de usuario y [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] solución.  
  
  Diseñador de canalizaciones de BizTalk se configura el Desensamblador de SWIFT durante el desarrollo de la canalización de recepción personalizada.  
  
  Para configurar el Desensamblador de SWIFT después de que se ha agregado a la fase de desensamblado de una canalización de recepción personalizada, seleccione el componente de desensamblador de SWIFT en el lienzo del Diseñador de canalizaciones de BizTalk. El Desensamblador de SWIFT, a continuación, recibe el foco y puede establecer sus propiedades de configuración mediante la ventana Propiedades de Microsoft [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)].  
  
  Para una tabla de propiedades de configuración disponibles y sus descripciones y los detalles de uso, consulte [propiedades de configuración del desensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md).  
  
  Para obtener información sobre cómo usar el Desensamblador de SWIFT para diferentes escenarios y establecer las propiedades de configuración, consulte [trabajar con el Desensamblador de SWIFT y ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).  
  
  Cuando [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] compila la canalización personalizada binaria, estáticamente escribe los valores de configuración en la canalización personalizada. Por lo tanto, no se puede cambiar las propiedades de configuración durante la implementación o tiempo de ejecución.  
  
> [!NOTE]
>  Después configura, compila e implementa una canalización personalizada, los cambios en la configuración requieren volver a compilar y volver a implementar la canalización personalizada.  
  
 Para obtener información acerca de cómo crear, compilar e implementar canalizaciones personalizadas, consulte la Ayuda de BizTalk Server.  
  
 Esta sección contiene:  
  
-   [Propiedades de configuración del desensamblador de SWIFT](../../adapters-and-accelerators/accelerator-swift/swift-disassembler-configuration-properties.md)