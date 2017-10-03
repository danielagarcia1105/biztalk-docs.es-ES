---
title: "Cómo crear puertos de envío para JD Edwards OneWorld | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- send ports, creating
ms.assetid: 858425ef-bdb7-4d2d-90ca-b3655e389749
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc77fd72171983ab2fbc7de42ddf36d770d045c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-oneworld"></a><span data-ttu-id="b6554-102">Creación de puertos de envío para JD Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="b6554-102">How to Create Send Ports for JD Edwards OneWorld</span></span>
<span data-ttu-id="b6554-103">Use el procedimiento siguiente para crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="b6554-103">Use the following procedure to create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="b6554-104">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="b6554-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="b6554-105">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, navegue hasta el aplicación necesaria.</span><span class="sxs-lookup"><span data-stu-id="b6554-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then navigate to the required application.</span></span>  
  
2.  <span data-ttu-id="b6554-106">Haga clic en **puertos de envío**, seleccione **New**y, a continuación, haga clic en **puerto de envío de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="b6554-106">Right-click **Send Ports**, point to **New**, and then click **Static Solicit-Response Send Port**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b6554-107">También puede usar **Puerto unidireccional estático**.</span><span class="sxs-lookup"><span data-stu-id="b6554-107">You can also use **Static One-Way Port**.</span></span>  
  
3.  <span data-ttu-id="b6554-108">En el **propiedades de puerto de envío** cuadro de diálogo, en la **nombre** , a continuación, escriba un nombre de puerto de envío (por ejemplo, escriba **SendToJDE**.)</span><span class="sxs-lookup"><span data-stu-id="b6554-108">In the **Send Port Properties** dialog box, in the **Name** field, type a send port name (for example, type **SendToJDE**.)</span></span>  
  
4.  <span data-ttu-id="b6554-109">En el **tipo** lista desplegable, seleccione **JDEOneWorld**.</span><span class="sxs-lookup"><span data-stu-id="b6554-109">In the **Type** drop-down list, select **JDEOneWorld**.</span></span>  
  
5.  <span data-ttu-id="b6554-110">En el **URI** lista desplegable, seleccione el controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="b6554-110">In the **URI** drop-down list, select the send handler.</span></span>  
  
6.  <span data-ttu-id="b6554-111">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b6554-111">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6554-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6554-112">See Also</span></span>  
 [<span data-ttu-id="b6554-113">Crear controladores de envío de OneWorld JD Edwards</span><span class="sxs-lookup"><span data-stu-id="b6554-113">Creating JD Edwards OneWorld Send Handlers</span></span>](../core/creating-jd-edwards-oneworld-send-handlers.md)