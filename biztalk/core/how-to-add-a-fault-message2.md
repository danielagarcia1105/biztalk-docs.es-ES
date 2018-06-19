---
title: Cómo agregar un Message2 error | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- fault messages, adding
- messages, fault messages
ms.assetid: 8f1b40af-2c75-4167-8b62-a86b791907c9
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6dee8a1fca0e30a96b6a714b5c717c0638bc8144
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246460"
---
# <a name="how-to-add-a-fault-message"></a><span data-ttu-id="3bbfa-102">Cómo agregar un mensaje de error</span><span class="sxs-lookup"><span data-stu-id="3bbfa-102">How to Add a Fault Message</span></span>
<span data-ttu-id="3bbfa-103">Al crear un puerto en el sistema de servidor, contiene una solicitud y una respuesta.</span><span class="sxs-lookup"><span data-stu-id="3bbfa-103">When you create a port to the back-end system, it contains a request and a response.</span></span> <span data-ttu-id="3bbfa-104">Debe agregar un mensaje de forma que pueda asignarlo al error.</span><span class="sxs-lookup"><span data-stu-id="3bbfa-104">You must add a message so that you can assign it to the fault.</span></span>  
  
### <a name="to-add-a-fault-message"></a><span data-ttu-id="3bbfa-105">Para agregar un mensaje de error</span><span class="sxs-lookup"><span data-stu-id="3bbfa-105">To add a fault message</span></span>  
  
1.  <span data-ttu-id="3bbfa-106">En el **Vista orquestación** ventana, haga clic en **mensajes**y seleccione **nuevo mensaje**.</span><span class="sxs-lookup"><span data-stu-id="3bbfa-106">In the **Orchestration View** window, right-click **Messages**, and select **New Message**.</span></span>  
  
     <span data-ttu-id="3bbfa-107">De este modo, se crea Message_3, que puede asignar específicamente al error.</span><span class="sxs-lookup"><span data-stu-id="3bbfa-107">This creates Message_3, which you can assign specifically to the fault.</span></span>  
  
2.  <span data-ttu-id="3bbfa-108">Haga clic en Message_3 y seleccione **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="3bbfa-108">Right-click Message_3, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="3bbfa-109">En el **propiedades** cuadro de diálogo, establezca la **tipo de mensaje**.</span><span class="sxs-lookup"><span data-stu-id="3bbfa-109">In the **Properties** dialog box, set the **Message Type**.</span></span>  
  
     <span data-ttu-id="3bbfa-110">Seleccione **clases .NET** y, a continuación, seleccione **SystemString**.</span><span class="sxs-lookup"><span data-stu-id="3bbfa-110">Select **.NET Classes** and then select **SystemString**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bbfa-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bbfa-111">See Also</span></span>  
 [<span data-ttu-id="3bbfa-112">Uso de control de excepciones de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="3bbfa-112">Using BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)