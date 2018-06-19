---
title: Componente de canalización de desarrollar un desensamblado | Documentos de Microsoft
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
ms.openlocfilehash: fc4e831561f9940ad7e8ee91479a2fada1fcd910
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239708"
---
# <a name="developing-a-disassembling-pipeline-component"></a><span data-ttu-id="dd7ee-102">Desarrollar un componente de canalización de desensamblado</span><span class="sxs-lookup"><span data-stu-id="dd7ee-102">Developing a Disassembling Pipeline Component</span></span>
<span data-ttu-id="dd7ee-103">Un componente de canalización de desensamblado recibe un mensaje en la entrada y produce cero o más mensajes en la salida.</span><span class="sxs-lookup"><span data-stu-id="dd7ee-103">A disassembling pipeline component receives one message on input and produces zero or more messages on output.</span></span> <span data-ttu-id="dd7ee-104">Los componentes de desensamblado se utilizan para dividir intercambios de mensajes en documentos individuales.</span><span class="sxs-lookup"><span data-stu-id="dd7ee-104">Disassembling components are used to split interchanges of messages into individual documents.</span></span> <span data-ttu-id="dd7ee-105">Los componentes de desensamblado deben implementar las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd7ee-105">Disassembler components must implement the following interfaces:</span></span>  
  
-   `IBaseComponent`
  
-   `IDisassemblerComponent`
  
-   `IComponentUI`
  
-   <span data-ttu-id="dd7ee-106">**IPersistPropertyBag.**</span><span class="sxs-lookup"><span data-stu-id="dd7ee-106">**IPersistPropertyBag .**</span></span> <span data-ttu-id="dd7ee-107">Consulte la documentación de .NET Framework SDK para esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="dd7ee-107">Refer to the .NET Framework SDK documentation for this interface.</span></span>  
  
 <span data-ttu-id="dd7ee-108">Puede crear su propio desensamblado componente extendiendo la **FFDasmComp** o **XMLDasmComp** clase.</span><span class="sxs-lookup"><span data-stu-id="dd7ee-108">You can create your own disassembling component by extending the **FFDasmComp** or **XMLDasmComp** class.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="dd7ee-109">Si el desensamblador personalizado define la propiedad de contexto MessageDestination como SuspendQueue, la secuencia que aquél devuelve debe ser compatible con Seek(0) para que funcione la suspensión.</span><span class="sxs-lookup"><span data-stu-id="dd7ee-109">If your custom disassembler will be setting the MessageDestination context property to SuspendQueue, the stream returned by the disassembler must to support Seek(0) for the suspension to work.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd7ee-110">Los componentes de canalización personalizados deberían copiar todas las partes adicionales del mensaje de entrada en los mensajes de salida.</span><span class="sxs-lookup"><span data-stu-id="dd7ee-110">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="dd7ee-111">Con ello, se conservan para el procesamiento ulterior en la canalización.</span><span class="sxs-lookup"><span data-stu-id="dd7ee-111">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dd7ee-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="dd7ee-112">In This Section</span></span>  
  
-   [<span data-ttu-id="dd7ee-113">Control de flujos de datos entrantes en componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="dd7ee-113">Handling Incoming Data Streams in Pipeline Components</span></span>](../core/handling-incoming-data-streams-in-pipeline-components.md)  
  
-   [<span data-ttu-id="dd7ee-114">Controlar la codificación en un componente de canalización de desensamblador</span><span class="sxs-lookup"><span data-stu-id="dd7ee-114">Handling Encoding in a Disassembler Pipeline Component</span></span>](../core/handling-encoding-in-a-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="dd7ee-115">Extender el componente de canalización de desensamblador de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="dd7ee-115">Extending the Flat File Disassembler Pipeline Component</span></span>](../core/extending-the-flat-file-disassembler-pipeline-component.md)