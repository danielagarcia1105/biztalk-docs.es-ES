---
title: Ensamblador de SWIFT | Microsoft Docs
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
ms.openlocfilehash: 39f89720a36c026fa0e8f02902a8fefb08fcebf9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973317"
---
# <a name="swift-assembler"></a>Ensamblador de SWIFT
Una canalización de envío saliente procesa todos los mensajes transmitidos por un [!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)] aplicación (que se envían a través de un puerto de envío).  
  
 Fases de la lógica de ejecución relacionados con el procesamiento de salida son las canalizaciones de envío de BizTalk. Un componente de canalización de servicios o implementa cada fase. En concreto, el ensamblador de servicios de la fase de ensamblado en la canalización de recepción. A4SWIFT proporciona funcionalidad de procesamiento en un componente de ensamblador personalizados de mensaje saliente de SWIFT específicos.  
  
 El ensamblador de SWIFT, un ensamblador de archivo sin formato personalizado, proporciona funcionalidad para procesar los mensajes salientes de SWIFT y realiza las siguientes funciones:  
  
- Detecta el tipo de mensaje dinámicamente y se resuelve el esquema de documento  
  
- Serializa el XML analizado en archivos planos SWIFT  
  
  La siguiente ilustración muestra los datos del ensamblador de SWIFT flujo.  
  
  ![](../../adapters-and-accelerators/accelerator-swift/media/fsa-intro3.gif "FSA_Intro3")  
  
  Para obtener más información acerca del ensamblador de SWIFT, consulte [trabajar con el Desensamblador de SWIFT y ensamblador](../../adapters-and-accelerators/accelerator-swift/working-with-the-swift-disassembler-and-assembler.md).  
  
## <a name="see-also"></a>Vea también  
 [Acelerador de BizTalk para el tiempo de ejecución de SWIFT](../../adapters-and-accelerators/accelerator-swift/biztalk-accelerator-for-swift-runtime.md)