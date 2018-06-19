---
title: Ensamblador SWIFT | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- assembler
- send pipelines, messages
- messages, send pipelines
ms.assetid: 2a95c7d4-da10-4058-bc2c-3efc35958e14
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 91d9411cce90079e8a84fc6919bd6ebf8b2b4371
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22214436"
---
# <a name="swift-assembler"></a>Ensamblador SWIFT
Una canalización de envío saliente procesa todos los mensajes transmitidos por un [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] aplicación (que se envían a través de un puerto de envío).  
  
 Fases de ejecución lógico relacionados con el procesamiento de salida son las canalizaciones de envío de BizTalk. Un componente de canalización de servicios o que implemente cada fase. En concreto, el ensamblador de servicios de la fase de ensamblado en la canalización de recepción. A4SWIFT proporciona funcionalidad en un componente de ensamblador personalizados de procesamiento de mensajes salientes de SWIFT específica.  
  
 El ensamblador de SWIFT, un ensamblador de archivos sin formato personalizado, proporciona funcionalidad para procesar los mensajes salientes de SWIFT y realiza las siguientes funciones:  
  
-   Detecta el tipo de mensaje dinámicamente y resuelve el esquema del documento  
  
-   Serializa el XML analizado en archivos planos SWIFT  
  
 En la siguiente ilustración se muestra los datos de ensamblador SWIFT flujo.  
  
 ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")  
  
 Para obtener más información acerca de cómo el ensamblador SWIFT, consulte [trabajar con el Desensamblador de SWIFT y de ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).  
  
## <a name="see-also"></a>Vea también  
 [Acelerador de BizTalk para SWIFT en tiempo de ejecución](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)