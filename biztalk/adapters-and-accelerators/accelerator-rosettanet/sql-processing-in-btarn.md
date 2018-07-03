---
title: Procesamiento de SQL en BTARN | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- LOBs
- SQL processing
- messages, message flow
- BTARN, SQL processing
ms.assetid: cfaf804f-3803-438e-a22e-50f487fe21c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21255c03a9a9c1f2a30eb7f716c5e1bf285a3c5b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000717"
---
# <a name="sql-processing-in-btarn"></a><span data-ttu-id="3f44c-102">Procesamiento de SQL en BTARN</span><span class="sxs-lookup"><span data-stu-id="3f44c-102">SQL Processing in BTARN</span></span>
<span data-ttu-id="3f44c-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] usa un adaptador de SQL para enrutar un mensaje de la aplicación de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="3f44c-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses a SQL adapter to route a message from the line-of-business (LOB) application.</span></span> <span data-ttu-id="3f44c-104">Utiliza un puerto de envío SQL para redirigir un mensaje a la aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="3f44c-104">It uses a SQL send port to route a message to the LOB application.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="3f44c-105">Flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="3f44c-105">Message Flow</span></span>  
 <span data-ttu-id="3f44c-106">En el iniciador o el equipo de respuesta, la aplicación de LOB de back-end enruta un mensaje a la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="3f44c-106">On either the initiator or responder computer, the back-end LOB application routes a message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="3f44c-107"> usa un adaptador de SQL para mover el mensaje de la tabla MessagesFromLOB al proceso privado.</span><span class="sxs-lookup"><span data-stu-id="3f44c-107"> uses a SQL adapter to move the message from the MessagesFromLOB table to the private process.</span></span> <span data-ttu-id="3f44c-108">Para obtener más información, consulte "Adaptador de SQL" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="3f44c-108">For more information, see "SQL Adapter" in BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="3f44c-109">Puede elegir usar un adaptador de archivo para enviar contenido de servicio a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], en lugar de usar el adaptador SQL predeterminado.</span><span class="sxs-lookup"><span data-stu-id="3f44c-109">You can choose to use a File adapter to submit service content to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], instead of using the default SQL adapter.</span></span> <span data-ttu-id="3f44c-110">Si decide usar un adaptador de archivo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no admite datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="3f44c-110">If you choose to use a File adapter, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not support attachments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f44c-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3f44c-111">See Also</span></span>  
 [<span data-ttu-id="3f44c-112">Procesamiento de mensajes en BTARN</span><span class="sxs-lookup"><span data-stu-id="3f44c-112">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)