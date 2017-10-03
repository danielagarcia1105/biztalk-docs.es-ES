---
title: "Control de flujos de datos entrantes en componentes de canalización | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1b7c4f7-99ba-4bfa-89ab-1fabfe0845d1
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 20fc34da3a5c8e65f81cd6bbbb699f52506cdc6b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="handling-incoming-data-streams-in-pipeline-components"></a><span data-ttu-id="7edef-102">Controlar secuencias de datos entrantes en componentes de canalización</span><span class="sxs-lookup"><span data-stu-id="7edef-102">Handling Incoming Data Streams in Pipeline Components</span></span>
<span data-ttu-id="7edef-103">Las siguientes consideraciones se deben tener en cuenta cuando se escribe un código de desensamblador personalizado para los componentes de canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7edef-103">The following considerations should be made when writing custom disassembler code for pipeline components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="do-not-close-the-incoming-data-stream-in-custom-dissasember-code"></a><span data-ttu-id="7edef-104">No cerrar la secuencia de datos entrantes del código desensamblador personalizado</span><span class="sxs-lookup"><span data-stu-id="7edef-104">Do not close the incoming data stream in custom dissasember code</span></span>  
 <span data-ttu-id="7edef-105">Cuando escriba un código de desensamblador personalizado para los componentes de canalización de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], asegúrese de no cerrar la secuencia de datos entrantes correspondiente.</span><span class="sxs-lookup"><span data-stu-id="7edef-105">When you write custom disassembler code for pipeline components in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], ensure that you do not close the incoming data stream in the disassembler code.</span></span> <span data-ttu-id="7edef-106">La secuencia entrante de mensaje de entrada es un recurso compartido.</span><span class="sxs-lookup"><span data-stu-id="7edef-106">The incoming stream from the input message is a shared resource.</span></span> <span data-ttu-id="7edef-107">La secuencia entrante también la usa el componente de seguimiento de cuerpos de mensaje en el motor de mensajes de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7edef-107">The incoming stream is also used by the message body tracking component in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] message engine.</span></span>  
  
 <span data-ttu-id="7edef-108">Si cierra implícita o explícitamente la secuencia entrante, se pueden perder los datos de seguimiento y no podrá examinar los datos de la secuencia mediante el seguimiento de eventos de mensaje e instancias de servicio en [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7edef-108">If you either implicitly or explicitly close the incoming stream, tracking data may be lost and you will be unable to examine the stream data using message event and service instance tracking in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
## <a name="use-the-seek-method-of-the-stream-class-to-set-the-data-stream-pointer-to-the-start-of-the-stream"></a><span data-ttu-id="7edef-109">Utilizar el método Seek de la clase Stream para establecer el puntero de la secuencia de datos en el inicio de la secuencia</span><span class="sxs-lookup"><span data-stu-id="7edef-109">Use the Seek method of the Stream class to set the data stream pointer to the start of the stream</span></span>  
 <span data-ttu-id="7edef-110">Asegúrese de leer desde la secuencia de datos entrantes hasta que se alcance el final de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="7edef-110">Ensure that you read from the incoming data stream until the end of the stream is reached.</span></span> <span data-ttu-id="7edef-111">Por ejemplo, si el código personalizado solicita una lectura de 300 KB de datos y el código sólo recibe 34 KB, no suponga que se ha alcanzado el final de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="7edef-111">For example, if custom code makes a read request for 300 KB of data and the code only receives 34 KB of data, do not assume that the end of the stream has been reached.</span></span> <span data-ttu-id="7edef-112">El código personalizado siempre debería leer desde la secuencia entrante hasta que se devuelvan 0 bytes.</span><span class="sxs-lookup"><span data-stu-id="7edef-112">The custom code should always read from the incoming stream until 0 bytes is returned.</span></span>  
  
 <span data-ttu-id="7edef-113">Antes de devolver la secuencia de datos en la lógica de componentes personalizada, vuelva a establecer el puntero de la secuencia de datos al principio de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="7edef-113">Before returning the data stream in the custom component logic, set the data stream pointer back to the start of the stream.</span></span> <span data-ttu-id="7edef-114">Por ejemplo, este código muestra la lógica para utilizar el método seek para señalar el principio de la secuencia antes de devolver la secuencia:</span><span class="sxs-lookup"><span data-stu-id="7edef-114">For example, this code illustrates logic to use the seek method to point to the beginning of the stream before returning the stream:</span></span>  
  
```  
myDataStream.Seek(0, SeekOrigin.Begin);  
return myDataStream;  
```  
  
 <span data-ttu-id="7edef-115">Si no lo realiza y la secuencia se le desde el final del componente actual, el componente siguiente recibe lo que parece ser una secuencia vacía porque el puntero de la secuencia de datos no está establecido al principio de la secuencia.</span><span class="sxs-lookup"><span data-stu-id="7edef-115">If you do not do this and the stream is read to the end in the current component, the next component receives what appears to be an empty stream because the data stream pointer was not set to the start of the stream.</span></span> <span data-ttu-id="7edef-116">Se puede generar un error inesperado en los componentes de canalización posteriores al analizar y validar.</span><span class="sxs-lookup"><span data-stu-id="7edef-116">This can cause unexpected parsing and validation errors in subsequent pipeline components.</span></span>