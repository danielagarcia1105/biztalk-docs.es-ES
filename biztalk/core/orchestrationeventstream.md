---
title: OrchestrationEventStream | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7c63610-6344-4b71-8d65-3add7883bc79
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dc1fd0dc229c38b3a060c75a9c584259175d72fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263324"
---
# <a name="orchestrationeventstream"></a><span data-ttu-id="1250d-102">OrchestrationEventStream</span><span class="sxs-lookup"><span data-stu-id="1250d-102">OrchestrationEventStream</span></span>
<span data-ttu-id="1250d-103">Utilice la API OrchestrationEventStream (OES) cuando la aplicación se ejecute en un equipo en el que BizTalk Server está instalado y cuando realice el seguimiento de elementos que forman parte de las transacciones de orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="1250d-103">You use the OrchestrationEventStream (OES) API when your application runs on a computer on which BizTalk Server is installed and you are tracking items that are part of BizTalk orchestration transactions.</span></span>  
  
 <span data-ttu-id="1250d-104">La API de OES almacena primero los datos de seguimiento en la base de datos de cuadro de mensajes de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="1250d-104">The OES API stores tracking data first in the BizTalk MessageBox database.</span></span> <span data-ttu-id="1250d-105">De forma periódica, el Servicio de descodificación de datos de seguimiento (TDDS) los datos se procesan y se almacenan de forma permanente en la base de datos de importación principal de BAM.</span><span class="sxs-lookup"><span data-stu-id="1250d-105">Periodically the data is processed and persisted to the BAM Primary Import database by the Tracking Data Decode Service (TDDS).</span></span>  
  
 <span data-ttu-id="1250d-106">La API de OES se encuentra en el espacio de nombres Microsoft.BizTalk.Bam.EventObservation.</span><span class="sxs-lookup"><span data-stu-id="1250d-106">The OES API is found in the Microsoft.BizTalk.Bam.EventObservation namespace.</span></span> <span data-ttu-id="1250d-107">Para usar la API debe agregar Microsoft.Biztalk.BAM.Xlangs.dll al proyecto.</span><span class="sxs-lookup"><span data-stu-id="1250d-107">To use the API you must add the Microsoft.Biztalk.BAM.Xlangs.dll to your project.</span></span>  
  
## <a name="oes-members"></a><span data-ttu-id="1250d-108">Miembros de OES</span><span class="sxs-lookup"><span data-stu-id="1250d-108">OES Members</span></span>  
 <span data-ttu-id="1250d-109">La API de OES se deriva de la clase [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) .</span><span class="sxs-lookup"><span data-stu-id="1250d-109">The OES API is derived from the [Microsoft.BizTalk.Bam.EventObservation.EventStream](http://msdn.microsoft.com/library/microsoft.biztalk.bam.eventobservation.eventstream.aspx) class.</span></span>  
  
 <span data-ttu-id="1250d-110">OES implementa todos los métodos dentro de la clase EventStream, aunque presenta la siguiente excepción en los comportamientos:</span><span class="sxs-lookup"><span data-stu-id="1250d-110">OES implements all of the methods within the EventStream class, but has the  following exception in behaviors:</span></span>  
  
 <span data-ttu-id="1250d-111">**public static void Clear();}**</span><span class="sxs-lookup"><span data-stu-id="1250d-111">**public static void Clear();**</span></span>  
  
 <span data-ttu-id="1250d-112">No realiza ninguna operación.</span><span class="sxs-lookup"><span data-stu-id="1250d-112">No operation.</span></span>  
  
 <span data-ttu-id="1250d-113">**pública Flush() void estático;**</span><span class="sxs-lookup"><span data-stu-id="1250d-113">**public static void Flush();**</span></span>  
  
 <span data-ttu-id="1250d-114">No realiza ninguna operación.</span><span class="sxs-lookup"><span data-stu-id="1250d-114">No operation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1250d-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="1250d-115">See Also</span></span>  
 [<span data-ttu-id="1250d-116">Clases EventStream</span><span class="sxs-lookup"><span data-stu-id="1250d-116">EventStream Classes</span></span>](../core/eventstream-classes.md)