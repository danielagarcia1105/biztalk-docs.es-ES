---
title: "Paso 8: configurar la información de entidad para el sistema ADT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0d750c2-a3c6-4571-a4e1-0d0aaaa4d400
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42b92e3b55cd4de181103e28526abf3ecde29412
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-8a-configure-party-information-for-the-adt-system"></a><span data-ttu-id="34f3d-102">Paso 8: configurar la información de entidad para el sistema ADT</span><span class="sxs-lookup"><span data-stu-id="34f3d-102">Step 8A: Configure Party Information for the ADT System</span></span>
<span data-ttu-id="34f3d-103">En este paso, configurará la información de entidad para el sistema ADT.</span><span class="sxs-lookup"><span data-stu-id="34f3d-103">In this step, you configure the party information for the ADT System.</span></span>  
  
### <a name="to-configure-the-adt-system-party-information"></a><span data-ttu-id="34f3d-104">Para configurar la información de entidad del sistema ADT</span><span class="sxs-lookup"><span data-stu-id="34f3d-104">To configure the ADT System party information</span></span>  
  
1.  <span data-ttu-id="34f3d-105">En la consola de administración de BizTalk Server, haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="34f3d-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="34f3d-106">En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **Tutorial_ADTSystem**.</span><span class="sxs-lookup"><span data-stu-id="34f3d-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_ADTSystem**.</span></span> <span data-ttu-id="34f3d-107">(El valor que escriba en este cuadro es de la instancia de mensaje HL7 original, ADT^A03.txt MSH3).</span><span class="sxs-lookup"><span data-stu-id="34f3d-107">(The value you type in this box is from the original HL7 message instance, ADT^A03.txt MSH3.)</span></span>  
  
3.  <span data-ttu-id="34f3d-108">En el árbol de consola, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="34f3d-108">In the console tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="34f3d-109">En el panel de puertos de envío, haga clic en el campo en blanco en el **nombre** columna, seleccione **Tutorial_sendAck_ADT**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="34f3d-109">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_sendAck_ADT**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="34f3d-110">Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="34f3d-110">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6.  <span data-ttu-id="34f3d-111">En el Explorador de configuración BTAHL7, seleccione la **confirmación** ficha. Para **tipo de confirmación**, seleccione **EnhancedMode**.</span><span class="sxs-lookup"><span data-stu-id="34f3d-111">In the BTAHL7 Configuration Explorer, select the **Acknowledgment** tab. For **Acknowledgment type**, select **EnhancedMode**.</span></span>  
  
7.  <span data-ttu-id="34f3d-112">Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="34f3d-112">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  
  
 <span data-ttu-id="34f3d-113">Continúe con [paso 8B: configurar la información de entidad para el sistema RX](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md).</span><span class="sxs-lookup"><span data-stu-id="34f3d-113">Proceed to [Step 8B: Configure Party Information for the RX System](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-rx-system.md).</span></span>