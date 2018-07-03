---
title: No se pudo mensajes y objetos ErrorCollection | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- failed messages, ErrorCollection objects
- ErrorCollection objects
ms.assetid: 8a2ff3b5-d7a0-4595-8b74-3133e9e3a821
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4f9fd17807d9bc1b92b1eae1ac75662843c8e17
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993165"
---
# <a name="failed-messages-and-errorcollection-objects"></a>Mensajes de error y objetos ErrorCollection
Además de decoración de un mensaje con errores con propiedades promocionadas, Microsoft [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] publica el mensaje error en la base de datos de cuadro de mensajes con un mensaje adicional *parte*, llamado **ErrorSegment**. Esta parte de error contiene XML que representa un **ErrorCollection** objeto. El Desensamblador de A4SWIFT rellena el **ErrorCollection** objeto durante cada fase de procesamiento (análisis, validación de XML y la validación de motor de reglas de negocios (BRE)) de mensajes.  
  
 El **ErrorCollection** objeto es una colección de *objetos error*, cada uno de los cuales representa un error concreto o un error durante el procesamiento del mensaje. Los objetos individuales de error contienen detalles acerca de un único error (por ejemplo, la ubicación en el mensaje y una descripción del error).  
  
 Para obtener más información sobre la **ErrorCollection** programación de aplicaciones (API) de la interfaz y obtener detalles de uso, vea la clase ErrorCollection. Para obtener más información acerca de los objetos de errores individuales, consulte ErrorBase clase (la clase base para los objetos de error), clase BreValidationError, ParseError clase y clase XmlValidationError.  
  
 Esta sección contiene:  
  
-   [Ampliación de la solución para la captura y reparación de mensajes](../../adapters-and-accelerators/accelerator-swift/extending-the-solution-for-capture-and-message-repair.md)