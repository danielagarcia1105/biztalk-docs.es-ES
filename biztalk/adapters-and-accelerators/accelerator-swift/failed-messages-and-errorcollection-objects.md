---
title: No se pudo mensajes y objetos ErrorCollection | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- failed messages, ErrorCollection objects
- ErrorCollection objects
ms.assetid: 8a2ff3b5-d7a0-4595-8b74-3133e9e3a821
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65598ef44bfe3e34bd1695aa81bee368c5175793
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="failed-messages-and-errorcollection-objects"></a>Mensajes de error y ErrorCollection objetos
Además de decoración de un mensaje de error con las propiedades promocionadas, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] publica el mensaje error en la base de datos de cuadro de mensajes con un mensaje adicional *parte*, llamado **ErrorSegment** . Esta parte de error contiene XML que representa un **ErrorCollection** objeto. El Desensamblador de A4SWIFT rellena la **ErrorCollection** objeto durante cada fase de procesamiento (análisis, validación de XML y la validación de motor de reglas de negocios (BRE)) de mensajes.  
  
 El **ErrorCollection** objeto es una colección de *objetos de error*, cada uno de los cuales representa un error determinado o un error durante el procesamiento del mensaje. Los objetos de error individuales contienen detalles acerca de un único error (por ejemplo, la ubicación en el mensaje y una descripción del error).  
  
 Para obtener más información sobre la **ErrorCollection** programación de aplicaciones (API) de la interfaz y obtener detalles de uso, vea ErrorCollection (clase). Para obtener más información acerca de los objetos de error individuales, vea clase ErrorBase (la clase base para los objetos de error), clase BreValidationError, ParseError clase y clase XmlValidationError.  
  
 Esta sección contiene:  
  
-   [Ampliar la solución para la captura y reparación de mensajes](../../adapters-and-accelerators/accelerator-swift/extending-the-solution-for-capture-and-message-repair.md)