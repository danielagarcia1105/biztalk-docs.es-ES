---
title: Procesamiento de SQL en BTARN | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- line-of-business applications (LOBs)
- LOBs
- SQL processing
- messages, message flow
- BTARN, SQL processing
ms.assetid: cfaf804f-3803-438e-a22e-50f487fe21c3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24798038ef7110a87efef2850c7787c066ae9511
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="sql-processing-in-btarn"></a><span data-ttu-id="1414b-102">Procesamiento de SQL en BTARN</span><span class="sxs-lookup"><span data-stu-id="1414b-102">SQL Processing in BTARN</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="1414b-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] utiliza un adaptador de SQL para enrutar un mensaje de la aplicación de línea de negocio (LOB).</span><span class="sxs-lookup"><span data-stu-id="1414b-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] uses a SQL adapter to route a message from the line-of-business (LOB) application.</span></span> <span data-ttu-id="1414b-104">Utiliza un puerto de envío SQL para redirigir un mensaje a la aplicación de LOB.</span><span class="sxs-lookup"><span data-stu-id="1414b-104">It uses a SQL send port to route a message to the LOB application.</span></span>  
  
## <a name="message-flow"></a><span data-ttu-id="1414b-105">Flujo de mensajes</span><span class="sxs-lookup"><span data-stu-id="1414b-105">Message Flow</span></span>  
 <span data-ttu-id="1414b-106">En el iniciador o el equipo de respuesta, la aplicación de LOB de back-end enruta un mensaje a la tabla MessagesFromLOB de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]datos [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] base de datos.</span><span class="sxs-lookup"><span data-stu-id="1414b-106">On either the initiator or responder computer, the back-end LOB application routes a message to the MessagesFromLOB table of the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]DATA [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="1414b-107">usa un adaptador de SQL para mover el mensaje de la tabla MessagesFromLOB al proceso privado.</span><span class="sxs-lookup"><span data-stu-id="1414b-107"> uses a SQL adapter to move the message from the MessagesFromLOB table to the private process.</span></span> <span data-ttu-id="1414b-108">Para obtener más información, vea "Adaptador de SQL" en la Ayuda de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="1414b-108">For more information, see "SQL Adapter" in BizTalk Server Help.</span></span>  
  
 <span data-ttu-id="1414b-109">Puede elegir usar un adaptador de archivo para enviar contenido de servicio a [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], en lugar de usar el adaptador SQL predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1414b-109">You can choose to use a File adapter to submit service content to [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)], instead of using the default SQL adapter.</span></span> <span data-ttu-id="1414b-110">Si decide usar un adaptador de archivo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no admite datos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="1414b-110">If you choose to use a File adapter, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not support attachments.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1414b-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="1414b-111">See Also</span></span>  
 [<span data-ttu-id="1414b-112">Procesamiento de mensajes en BTARN</span><span class="sxs-lookup"><span data-stu-id="1414b-112">Message Processing in BTARN</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)