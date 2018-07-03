---
title: Desarrollo de desensamblado de un componente de canalización | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDisassemblerComponent interface, disassembling
- pipeline components [custom], IDisassemblerComponent
- pipeline components [custom], IBaseComponent
- IBaseComponent interface, disassembling
- pipeline components [custom], disassembling
ms.assetid: 77c0aa7d-4d1b-4a8f-bef8-d38e7e4045c6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 843958cdfe00a9fc9d1a2c178cb85adfe4ffc8d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999725"
---
# <a name="developing-a-disassembling-pipeline-component"></a>Desarrollar un componente de canalización de desensamblado
Un componente de canalización de desensamblado recibe un mensaje en la entrada y produce cero o más mensajes en la salida. Los componentes de desensamblado se utilizan para dividir intercambios de mensajes en documentos individuales. Los componentes de desensamblado deben implementar las interfaces siguientes:  
  
- `IBaseComponent`
  
- `IDisassemblerComponent`
  
- `IComponentUI`
  
- **IPersistPropertyBag.** Consulte la documentación de .NET Framework SDK para esta interfaz.  
  
  Puede crear componente desensamblado propio extendiendo el **FFDasmComp** o **XMLDasmComp** clase.  
  
> [!WARNING]
>  Si el desensamblador personalizado define la propiedad de contexto MessageDestination como SuspendQueue, la secuencia que aquél devuelve debe ser compatible con Seek(0) para que funcione la suspensión.  
  
> [!NOTE]
>  Los componentes de canalización personalizados deberían copiar todas las partes adicionales del mensaje de entrada en los mensajes de salida. Con ello, se conservan para el procesamiento ulterior en la canalización.  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Control de flujos de datos de entrada en componentes de canalización](../core/handling-incoming-data-streams-in-pipeline-components.md)  
  
-   [Control de la codificación en un componente de canalización de desensamblador](../core/handling-encoding-in-a-disassembler-pipeline-component.md)  
  
-   [Ampliación del componente de canalización de desensamblador de archivos sin formato](../core/extending-the-flat-file-disassembler-pipeline-component.md)