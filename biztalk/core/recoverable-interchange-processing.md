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
# <a name="recoverable-interchange-processing"></a><span data-ttu-id="4d470-102">Procesamiento de intercambio recuperable</span><span class="sxs-lookup"><span data-stu-id="4d470-102">Recoverable Interchange Processing</span></span>
<span data-ttu-id="4d470-103">Esta sección se describen **procesamiento de intercambio recuperable** característica, lo que permite un intercambio que se va a procesarse completamente incluso si hay uno o más mensajes en el intercambio errores en las fases siguientes:</span><span class="sxs-lookup"><span data-stu-id="4d470-103">This section discusses **recoverable interchange processing** feature, which allows an interchange to be processed completely even if one or more messages in the interchange fail at the following stages/phases:</span></span>  
  
-   <span data-ttu-id="4d470-104">Fase de desensamblado de una canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="4d470-104">Disassembly stage of a receive pipeline</span></span>  
  
-   <span data-ttu-id="4d470-105">Fase de validación de XML de una canalización de recepción</span><span class="sxs-lookup"><span data-stu-id="4d470-105">XML validation stage of a receive pipeline</span></span>  
  
-   <span data-ttu-id="4d470-106">Fase de ejecución de la asignación de un puerto de recepción</span><span class="sxs-lookup"><span data-stu-id="4d470-106">Map execution phase of a receive port</span></span>  
  
 <span data-ttu-id="4d470-107">El procesamiento de intercambio recuperable está motivado por la necesidad de ofrecer compatibilidad con el procesamiento correcto de un solo intercambio que contiene varios mensajes identificables con el fin de que los mensajes válidos se propaguen por la ruta de mensajería y se suspendan los mensajes no válidos.</span><span class="sxs-lookup"><span data-stu-id="4d470-107">Recoverable interchange processing is motivated by the need to support successful processing of a single interchange that contains multiple identifiable messages so that valid messages are propagated through the messaging pathway and invalid messages are suspended.</span></span> <span data-ttu-id="4d470-108">Con el procesamiento de intercambio estándar, la existencia de cualquier mensaje no válido en un intercambio dado provoca la suspensión de todo el intercambio, aunque contenga uno o más mensajes válidos.</span><span class="sxs-lookup"><span data-stu-id="4d470-108">With standard interchange processing, the existence of any invalid message in a given interchange causes the entire interchange to be suspended even if it contains one or more valid messages.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4d470-109">En esta sección</span><span class="sxs-lookup"><span data-stu-id="4d470-109">In This Section</span></span>  
  
-   [<span data-ttu-id="4d470-110">Fase de desensamblado (procesamiento de intercambio recuperable)</span><span class="sxs-lookup"><span data-stu-id="4d470-110">Disassembly Stage (Recoverable Interchange Processing)</span></span>](../core/disassembly-stage-recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="4d470-111">Fase de validación de XML (procesamiento de intercambio recuperable)</span><span class="sxs-lookup"><span data-stu-id="4d470-111">XML Validation Stage (Recoverable Interchange Processing)</span></span>](../core/xml-validation-stage-recoverable-interchange-processing.md)  
  
-   [<span data-ttu-id="4d470-112">Asignación de fase (procesamiento de intercambio recuperable)</span><span class="sxs-lookup"><span data-stu-id="4d470-112">Mapping Phase (Recoverable Interchange Processing)</span></span>](../core/mapping-phase-recoverable-interchange-processing.md)