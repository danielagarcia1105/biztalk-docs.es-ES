---
title: "Enviar y recibir mensajes de gran tamaño mediante el adaptador de MSMQ | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, large messages
- configuring [MSMQ adapters], large messages
- MSMQ adapters, large messages
ms.assetid: 208efbed-7b58-4da5-ba27-65a315c2713b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a23265be84f2767849e4d61c2e9a95bfc9ed4ce
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="sending-and-receiving-large-messages-using-the-msmq-adapter"></a><span data-ttu-id="782e3-102">Enviar y recibir mensajes de gran tamaño mediante el adaptador de MSMQ</span><span class="sxs-lookup"><span data-stu-id="782e3-102">Sending and Receiving Large Messages Using the MSMQ Adapter</span></span>
<span data-ttu-id="782e3-103">El control de mensajes predeterminado del adaptador de MSMQ depende, en parte, del tamaño del mensaje en cuestión.</span><span class="sxs-lookup"><span data-stu-id="782e3-103">The MSMQ adapter default message handling depends, in part, on the size of the message.</span></span> <span data-ttu-id="782e3-104">Cuando un mensaje tiene un tamaño inferior a cuatro megabytes (4 MB), el adaptador de MSMQ utiliza la biblioteca de clases de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="782e3-104">When a message is less than four megabytes (4 MB), the MSMQ adapter uses the .NET Framework Class Library.</span></span> <span data-ttu-id="782e3-105">De lo contrario, utiliza extensiones de mensajes de gran tamaño de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="782e3-105">Otherwise, it uses the large message extensions in Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="782e3-106">Si la aplicación recibe o envía de forma sistemática mensajes de gran tamaño, puede que resulte necesario controlar la cantidad de memoria que utiliza el adaptador.</span><span class="sxs-lookup"><span data-stu-id="782e3-106">If your application consistently receives or sends large messages, you may have to control the amount of memory that the adapter uses.</span></span> <span data-ttu-id="782e3-107">Para obtener más información acerca del ahorro de memoria, vea [optimizar el rendimiento del adaptador de MSMQ](../core/optimizing-performance-of-the-msmq-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="782e3-107">For more information about conserving memory, see [Optimizing Performance of the MSMQ Adapter](../core/optimizing-performance-of-the-msmq-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="782e3-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="782e3-108">See Also</span></span>  
 <span data-ttu-id="782e3-109">[Optimizar el rendimiento del adaptador de MSMQ](../core/optimizing-performance-of-the-msmq-adapter.md) </span><span class="sxs-lookup"><span data-stu-id="782e3-109">[Optimizing Performance of the MSMQ Adapter](../core/optimizing-performance-of-the-msmq-adapter.md) </span></span>  
 [<span data-ttu-id="782e3-110">Configurar el adaptador MSMQ</span><span class="sxs-lookup"><span data-stu-id="782e3-110">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)