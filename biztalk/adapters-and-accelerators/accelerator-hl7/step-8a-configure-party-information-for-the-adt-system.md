---
title: 'Paso 8A: configurar la información de entidad para el sistema ADT | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c0d750c2-a3c6-4571-a4e1-0d0aaaa4d400
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c1a608571c9cc3f939f9387c2e3a113273af554
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969765"
---
# <a name="step-8a-configure-party-information-for-the-adt-system"></a><span data-ttu-id="812e0-102">Paso 8A: configurar la información de entidad para el sistema ADT</span><span class="sxs-lookup"><span data-stu-id="812e0-102">Step 8A: Configure Party Information for the ADT System</span></span>
<span data-ttu-id="812e0-103">En este paso, configure la información de entidad para el sistema de ADT.</span><span class="sxs-lookup"><span data-stu-id="812e0-103">In this step, you configure the party information for the ADT System.</span></span>  
  
### <a name="to-configure-the-adt-system-party-information"></a><span data-ttu-id="812e0-104">Para configurar la información de entidad del sistema de ADT</span><span class="sxs-lookup"><span data-stu-id="812e0-104">To configure the ADT System party information</span></span>  
  
1. <span data-ttu-id="812e0-105">En la consola de administración de BizTalk Server, haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="812e0-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2. <span data-ttu-id="812e0-106">En el cuadro de diálogo Propiedades de entidad en el **nombre** , escriba **Tutorial_ADTSystem**.</span><span class="sxs-lookup"><span data-stu-id="812e0-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_ADTSystem**.</span></span> <span data-ttu-id="812e0-107">(El valor que escriba en este cuadro es de la instancia de mensaje original de HL7, ADT^A03.txt MSH3).</span><span class="sxs-lookup"><span data-stu-id="812e0-107">(The value you type in this box is from the original HL7 message instance, ADT^A03.txt MSH3.)</span></span>  
  
3. <span data-ttu-id="812e0-108">En el árbol de consola, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="812e0-108">In the console tree, click **Send Ports**.</span></span>  
  
4. <span data-ttu-id="812e0-109">En el panel puertos de envío, haga clic en el campo en blanco en el **nombre** columna, seleccione **Tutorial_sendAck_ADT**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="812e0-109">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_sendAck_ADT**, and then click **OK**.</span></span>  
  
5. <span data-ttu-id="812e0-110">Haga clic en **iniciar**, apunte a **programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="812e0-110">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6. <span data-ttu-id="812e0-111">En el Explorador de configuración de BTAHL7, seleccione el **confirmación** ficha. Para **tipo de confirmación**, seleccione **EnhancedMode**.</span><span class="sxs-lookup"><span data-stu-id="812e0-111">In the BTAHL7 Configuration Explorer, select the **Acknowledgment** tab. For **Acknowledgment type**, select **EnhancedMode**.</span></span>  
  
7. <span data-ttu-id="812e0-112">Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="812e0-112">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  
  
   <span data-ttu-id="812e0-113">Continúe con [paso 8B: configurar la información de entidad para el sistema de RX](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md).</span><span class="sxs-lookup"><span data-stu-id="812e0-113">Proceed to [Step 8B: Configure Party Information for the RX System](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md).</span></span>