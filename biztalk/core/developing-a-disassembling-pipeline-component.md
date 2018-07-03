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
# <a name="developing-a-disassembling-pipeline-component"></a><span data-ttu-id="52c62-102">Desarrollar un componente de canalización de desensamblado</span><span class="sxs-lookup"><span data-stu-id="52c62-102">Developing a Disassembling Pipeline Component</span></span>
<span data-ttu-id="52c62-103">Un componente de canalización de desensamblado recibe un mensaje en la entrada y produce cero o más mensajes en la salida.</span><span class="sxs-lookup"><span data-stu-id="52c62-103">A disassembling pipeline component receives one message on input and produces zero or more messages on output.</span></span> <span data-ttu-id="52c62-104">Los componentes de desensamblado se utilizan para dividir intercambios de mensajes en documentos individuales.</span><span class="sxs-lookup"><span data-stu-id="52c62-104">Disassembling components are used to split interchanges of messages into individual documents.</span></span> <span data-ttu-id="52c62-105">Los componentes de desensamblado deben implementar las interfaces siguientes:</span><span class="sxs-lookup"><span data-stu-id="52c62-105">Disassembler components must implement the following interfaces:</span></span>  
  
- `IBaseComponent`
  
- `IDisassemblerComponent`
  
- `IComponentUI`
  
- <span data-ttu-id="52c62-106">**IPersistPropertyBag.**</span><span class="sxs-lookup"><span data-stu-id="52c62-106">**IPersistPropertyBag .**</span></span> <span data-ttu-id="52c62-107">Consulte la documentación de .NET Framework SDK para esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="52c62-107">Refer to the .NET Framework SDK documentation for this interface.</span></span>  
  
  <span data-ttu-id="52c62-108">Puede crear componente desensamblado propio extendiendo el **FFDasmComp** o **XMLDasmComp** clase.</span><span class="sxs-lookup"><span data-stu-id="52c62-108">You can create your own disassembling component by extending the **FFDasmComp** or **XMLDasmComp** class.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="52c62-109">Si el desensamblador personalizado define la propiedad de contexto MessageDestination como SuspendQueue, la secuencia que aquél devuelve debe ser compatible con Seek(0) para que funcione la suspensión.</span><span class="sxs-lookup"><span data-stu-id="52c62-109">If your custom disassembler will be setting the MessageDestination context property to SuspendQueue, the stream returned by the disassembler must to support Seek(0) for the suspension to work.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52c62-110">Los componentes de canalización personalizados deberían copiar todas las partes adicionales del mensaje de entrada en los mensajes de salida.</span><span class="sxs-lookup"><span data-stu-id="52c62-110">Custom pipeline components should copy any additional parts from the input message to the output message(s).</span></span> <span data-ttu-id="52c62-111">Con ello, se conservan para el procesamiento ulterior en la canalización.</span><span class="sxs-lookup"><span data-stu-id="52c62-111">This preserves them for further processing in the pipeline.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52c62-112">En esta sección</span><span class="sxs-lookup"><span data-stu-id="52c62-112">In This Section</span></span>  
  
-   [<span data-ttu-id="52c62-113">Control de flujos de datos de entrada en componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="52c62-113">Handling Incoming Data Streams in Pipeline Components</span></span>](../core/handling-incoming-data-streams-in-pipeline-components.md)  
  
-   [<span data-ttu-id="52c62-114">Control de la codificación en un componente de canalización de desensamblador</span><span class="sxs-lookup"><span data-stu-id="52c62-114">Handling Encoding in a Disassembler Pipeline Component</span></span>](../core/handling-encoding-in-a-disassembler-pipeline-component.md)  
  
-   [<span data-ttu-id="52c62-115">Ampliación del componente de canalización de desensamblador de archivos sin formato</span><span class="sxs-lookup"><span data-stu-id="52c62-115">Extending the Flat File Disassembler Pipeline Component</span></span>](../core/extending-the-flat-file-disassembler-pipeline-component.md)