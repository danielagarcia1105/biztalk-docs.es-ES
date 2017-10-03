---
title: Procesamiento de intercambio recuperable | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interchange processing [Messaging Engine], modes
- parties, party resolution
- Messaging Engine, examples
- messages, interchange modes
- interchange processing [Messaging Engine], examples
- Messaging Engine, Recoverable Interchange Processing property
- Messaging Engine, failures
- interchange processing [Messaging Engine], party resolution
- Messaging Engine, interchange processing
- disassembly stage, pipelines
- Recoverable Interchange Processing property
- Messaging Engine, interchange modes
- receive pipelines, disassembly stage
- interchange processing [Messaging Engine], failures
- interchange processing [Messaging Engine], restrictions
- System.Xml.XmlReader
- interchange modes [Messaging Engine]
ms.assetid: d9e366fe-b2a0-4f1a-b6b9-1264717e4731
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b341b3673cd7118d459197fecea1eca25efe4e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="recoverable-interchange-processing"></a>Procesamiento de intercambio recuperable
Esta sección se describen **procesamiento de intercambio recuperable** característica, lo que permite un intercambio que se va a procesarse completamente incluso si hay uno o más mensajes en el intercambio errores en las fases siguientes:  
  
-   Fase de desensamblado de una canalización de recepción  
  
-   Fase de validación de XML de una canalización de recepción  
  
-   Fase de ejecución de la asignación de un puerto de recepción  
  
 El procesamiento de intercambio recuperable está motivado por la necesidad de ofrecer compatibilidad con el procesamiento correcto de un solo intercambio que contiene varios mensajes identificables con el fin de que los mensajes válidos se propaguen por la ruta de mensajería y se suspendan los mensajes no válidos. Con el procesamiento de intercambio estándar, la existencia de cualquier mensaje no válido en un intercambio dado provoca la suspensión de todo el intercambio, aunque contenga uno o más mensajes válidos.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Fase de desensamblado (procesamiento de intercambio recuperable)](../core/disassembly-stage-recoverable-interchange-processing.md)  
  
-   [Fase de validación de XML (procesamiento de intercambio recuperable)](../core/xml-validation-stage-recoverable-interchange-processing.md)  
  
-   [Asignación de fase (procesamiento de intercambio recuperable)](../core/mapping-phase-recoverable-interchange-processing.md)