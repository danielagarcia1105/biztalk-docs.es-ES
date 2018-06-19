---
title: Elemento estructural de mensajes de conjunto de transacciones de EDI | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: caea8408-c09c-4525-a9c9-18abe4432594
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d49288e9a311c9766e61fe985b9e279a8660f4ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239188"
---
# <a name="edi-transaction-set-message-structural-element"></a><span data-ttu-id="9228d-102">Elemento estructural de mensajes de conjunto de transacciones de EDI</span><span class="sxs-lookup"><span data-stu-id="9228d-102">EDI Transaction Set-Message Structural Element</span></span>
<span data-ttu-id="9228d-103">Los conjuntos de transacciones (en la codificación X12) y los mensajes (en la codificación EDIFACT) contienen segmentos que forman los datos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="9228d-103">The transaction set (in X12 encoding) or message (in EDIFACT encoding) contains segments that make up the message data.</span></span> <span data-ttu-id="9228d-104">Un conjunto de transacciones está constituido por un encabezado, una colección de segmentos de datos y un finalizador.</span><span class="sxs-lookup"><span data-stu-id="9228d-104">The transaction set consists of a header, a collection of data segments, and a trailer.</span></span> <span data-ttu-id="9228d-105">En definitiva, contiene todos los detalles que resultan necesarios para procesar la transacción.</span><span class="sxs-lookup"><span data-stu-id="9228d-105">All details that are required to process the transaction are available within the transaction set.</span></span>  
  
 <span data-ttu-id="9228d-106">Un conjunto de transacciones debe empezar con un encabezado de conjunto de transacciones ST (en X12) o un encabezado de mensaje UNH (en EDIFACT).</span><span class="sxs-lookup"><span data-stu-id="9228d-106">A transaction set must start with a ST Transaction Set Header (in X12) or a UNH Message Header (in EDIFACT).</span></span> <span data-ttu-id="9228d-107">Para terminar, utiliza un finalizador de conjunto de transacciones SE (en X12) o un finalizador de mensaje UNT (en EDIFACT).</span><span class="sxs-lookup"><span data-stu-id="9228d-107">It must end with a SE Transaction Set Trailer (in X12) or a UNT Message Trailer (in EDIFACT).</span></span> <span data-ttu-id="9228d-108">El finalizador proporciona un número de los segmentos de datos, en el que se incluyen los segmentos del encabezado y del finalizador.</span><span class="sxs-lookup"><span data-stu-id="9228d-108">The trailer provides a count of the data segments that includes the header and trailer segments.</span></span>  
  
 <span data-ttu-id="9228d-109">Un conjunto de transacciones puede contener uno o varios bucles, los cuales resultan necesarios para repetir una colección de segmentos relacionados.</span><span class="sxs-lookup"><span data-stu-id="9228d-109">A transaction set can contain one or more loops, which are required to repeat a collection of related segments.</span></span>