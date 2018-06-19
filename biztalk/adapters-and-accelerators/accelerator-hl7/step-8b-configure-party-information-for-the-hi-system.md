---
title: 'Paso 8: configurar la información de entidad para el sistema de HI | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 96338c05-1440-416e-a56a-6f5b19b55a60
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 460840cf3bbbd6556b1684b25851a16778be92b6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206316"
---
# <a name="step-8b-configure-party-information-for-the-hi-system"></a><span data-ttu-id="441c3-102">Paso 8: configurar la información de entidad para el sistema de alta</span><span class="sxs-lookup"><span data-stu-id="441c3-102">Step 8B: Configure Party Information for the HI System</span></span>
<span data-ttu-id="441c3-103">En este paso, configurará la información de entidad para el sistema de alta.</span><span class="sxs-lookup"><span data-stu-id="441c3-103">In this step, you configure the party information for the HI System.</span></span>  
  
### <a name="to-configure-the-hi-system-party-information"></a><span data-ttu-id="441c3-104">Para configurar la información de entidad del sistema de alta</span><span class="sxs-lookup"><span data-stu-id="441c3-104">To configure the HI System party information</span></span>  
  
1.  <span data-ttu-id="441c3-105">En la consola de administración de BizTalk, haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="441c3-105">In the BizTalk Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="441c3-106">En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **HIS**.</span><span class="sxs-lookup"><span data-stu-id="441c3-106">In the Party Properties dialog box, in the **Name** field, type **HIS**.</span></span> <span data-ttu-id="441c3-107">(El valor que escriba en este cuadro debe coincidir con la instancia original del mensaje HL7, QRY^Q01.txt MSH5.)</span><span class="sxs-lookup"><span data-stu-id="441c3-107">(The value you type in this box should match the original HL7 message instance, QRY^Q01.txt MSH5.)</span></span>  
  
3.  <span data-ttu-id="441c3-108">En el árbol de consola, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="441c3-108">In the Console Tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="441c3-109">En el **puerto de envío** panel, para **nombre** en la primera fila, seleccione **HIS_Send**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="441c3-109">In the **Send Port** pane, for **Name** in the first row, select **HIS_Send**, and then click **OK**.</span></span>  
  
 <span data-ttu-id="441c3-110">Continúe con [paso 9: reinicie el servidor BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md).</span><span class="sxs-lookup"><span data-stu-id="441c3-110">Proceed to [Step 9: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md).</span></span>