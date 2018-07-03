---
title: Cómo agregar un mensaje para un Exception2 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- exceptions, adding messages
- messages, exceptions
- exception handling, adding messages
- fault messages, adding
ms.assetid: 9d8a3801-78cd-4c18-8deb-3fbe4a49a2f9
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57cd4e3e0cdcfe34dd172282ef83768eb63b93fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000805"
---
# <a name="how-to-add-a-message-for-an-exception"></a><span data-ttu-id="47316-102">Cómo agregar un mensaje para una excepción</span><span class="sxs-lookup"><span data-stu-id="47316-102">How to Add a Message for an Exception</span></span>
<span data-ttu-id="47316-103">La primera vez que crea un puerto en el sistema de servidor, contiene una solicitud y una respuesta.</span><span class="sxs-lookup"><span data-stu-id="47316-103">When you first create a port to the back-end system, it contains a request and a response.</span></span> <span data-ttu-id="47316-104">Debe agregar un mensaje de forma que pueda asignarlo al error.</span><span class="sxs-lookup"><span data-stu-id="47316-104">You must add a message so that you can assign it to the fault.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="47316-105">Para agregar un mensaje de error</span><span class="sxs-lookup"><span data-stu-id="47316-105">To add a fault message</span></span>  
  
1. <span data-ttu-id="47316-106">En el **Vista orquestación** ventana, haga clic en **mensajes**y, a continuación, seleccione **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="47316-106">In the **Orchestration View** window, right-click **Messages**, and then select **New Message**.</span></span>  
  
    <span data-ttu-id="47316-107">De este modo, se crea Message_3, que puede asignar específicamente al error.</span><span class="sxs-lookup"><span data-stu-id="47316-107">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2. <span data-ttu-id="47316-108">Haga clic en **Message_3**y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="47316-108">Right-click **Message_3**, and select **Properties**.</span></span>  
  
3. <span data-ttu-id="47316-109">Establecer el **tipo de mensaje** como sigue: seleccione **clases .NET**y, a continuación, seleccione **del sistema, cadena**</span><span class="sxs-lookup"><span data-stu-id="47316-109">Set the **Message Type** as follows: select **.NET Classes**, and then select **System,String**</span></span>  
  
   <span data-ttu-id="47316-110">![](../core/media/jdeoneworld-03-addscope.gif "JdeOneWorld_03_addscope")</span><span class="sxs-lookup"><span data-stu-id="47316-110">![](../core/media/jdeoneworld-03-addscope.gif "JdeOneWorld_03_addscope")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47316-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="47316-111">See Also</span></span>  
 [<span data-ttu-id="47316-112">Uso del control de excepciones de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="47316-112">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling1.md)