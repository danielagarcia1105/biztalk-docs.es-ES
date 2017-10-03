---
title: "Cómo crear puertos de envío para JD Edwards EnterpriseOne | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, send ports
- send ports, creating [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], send ports
- send ports, JD Edwards EnterpriseOne adapters
- creating, send ports [JD Edwards EnterpriseOne adapters]
ms.assetid: 687f9207-ad3e-41ea-8640-5b9b6efbc14e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36a3e8d2d3e8e1db230a03d9c4a0351d3a0f8394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-enterpriseone"></a><span data-ttu-id="58510-102">Creación de puertos de envío para JD Edwards EnterpriseOne</span><span class="sxs-lookup"><span data-stu-id="58510-102">How to Create Send Ports for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="58510-103">Mediante[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="58510-103">Using [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], create a send port.</span></span>  
  
### <a name="to-create-a-send-port"></a><span data-ttu-id="58510-104">Procedimiento para crear un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="58510-104">To create a send port</span></span>  
  
1.  <span data-ttu-id="58510-105">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.</span><span class="sxs-lookup"><span data-stu-id="58510-105">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server**, and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="58510-106">En la consola de administración de BizTalk Server, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**y expanda **aplicaciones**y, a continuación, expanda el aplicación para la que desea crear un puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="58510-106">In the BizTalk Server Administration console, expand **BizTalk Server Administration**, expand **BizTalk Group**, and expand **Applications**, and then expand the application for which you want to create a send port.</span></span>  
  
3.  <span data-ttu-id="58510-107">Haga clic en **puertos de envío** y haga clic en **New**y, a continuación, haga clic en **puerto de petición-respuesta estático**.</span><span class="sxs-lookup"><span data-stu-id="58510-107">Right-click **Send Ports** and click **New**, and then click **Static Solicit-Response Port**.</span></span>  
  
4.  <span data-ttu-id="58510-108">En el **propiedades de puerto de envío** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="58510-108">In the **Send Port Properties** dialog box, do the following:</span></span>  
  
    -   <span data-ttu-id="58510-109">En el **nombre** , escriba un nombre de puerto de envío (por ejemplo, `SendToJDE`).</span><span class="sxs-lookup"><span data-stu-id="58510-109">In the **Name** box, type a send port name (for example, `SendToJDE`).</span></span>  
  
    -   <span data-ttu-id="58510-110">Desde el **tipo** lista desplegable, seleccione **JDEdwards**.</span><span class="sxs-lookup"><span data-stu-id="58510-110">From the **Type** drop-down list, select **JDEdwards**.</span></span>  
  
    -   <span data-ttu-id="58510-111">Desde el **controlador de envío** lista desplegable, seleccione la dirección del controlador de envío.</span><span class="sxs-lookup"><span data-stu-id="58510-111">From the **Send handler** drop-down list, select the send handler address.</span></span>  
  
5.  <span data-ttu-id="58510-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="58510-112">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58510-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="58510-113">See Also</span></span>  
 [<span data-ttu-id="58510-114">Crear controladores de JD Edwards EnterpriseOne envío</span><span class="sxs-lookup"><span data-stu-id="58510-114">Creating JD Edwards EnterpriseOne Send Handlers</span></span>](../core/creating-jd-edwards-enterpriseone-send-handlers.md)