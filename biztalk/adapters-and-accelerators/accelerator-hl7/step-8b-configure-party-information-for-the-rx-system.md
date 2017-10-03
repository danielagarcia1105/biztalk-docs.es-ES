---
title: "Paso 8: configurar la información de entidad para el sistema RX | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0b34ec9-220d-4a6b-9712-54c8099b663b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29ab7194e0e1b81a773c61123de9171f1c65eb0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-8b-configure-party-information-for-the-rx-system"></a><span data-ttu-id="0e64f-102">Paso 8: configurar la información de entidad para el sistema RX</span><span class="sxs-lookup"><span data-stu-id="0e64f-102">Step 8B: Configure Party Information for the RX System</span></span>
<span data-ttu-id="0e64f-103">En este paso, configurará la información de entidad para el sistema de recepción.</span><span class="sxs-lookup"><span data-stu-id="0e64f-103">In this step, you configure the party information for the RX System.</span></span>  
  
### <a name="to-configure-the-rx-system-party-information"></a><span data-ttu-id="0e64f-104">Para configurar la información de entidad del sistema RX</span><span class="sxs-lookup"><span data-stu-id="0e64f-104">To configure the RX System party information</span></span>  
  
1.  <span data-ttu-id="0e64f-105">En la consola de administración de BizTalk Server, haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="0e64f-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="0e64f-106">En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **Tutorial_RXSystem**.</span><span class="sxs-lookup"><span data-stu-id="0e64f-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_RXSystem**.</span></span>  
  
3.  <span data-ttu-id="0e64f-107">En el árbol de consola, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="0e64f-107">In the console tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="0e64f-108">En el panel de puertos de envío, haga clic en el campo en blanco en el **nombre** columna, seleccione **Tutorial_sendMsg_RX**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e64f-108">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_sendMsg_RX**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="0e64f-109">Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="0e64f-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6.  <span data-ttu-id="0e64f-110">En el Explorador de configuración BTAHL7, seleccione la **MSH mapa** ficha y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0e64f-110">In the BTAHL7 Configuration Explorer, select the **MSH Map** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="0e64f-111">Use</span><span class="sxs-lookup"><span data-stu-id="0e64f-111">Use this</span></span>|<span data-ttu-id="0e64f-112">Para</span><span class="sxs-lookup"><span data-stu-id="0e64f-112">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="0e64f-113">**MSH3**</span><span class="sxs-lookup"><span data-stu-id="0e64f-113">**MSH3**</span></span>|<span data-ttu-id="0e64f-114">Tipo de **BTAHL7** en el cuadro de texto a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="0e64f-114">Type **BTAHL7** in the left text box.</span></span>|  
    |<span data-ttu-id="0e64f-115">**MSH5**</span><span class="sxs-lookup"><span data-stu-id="0e64f-115">**MSH5**</span></span>|<span data-ttu-id="0e64f-116">Tipo de **Tutorial_RXSystem** en el cuadro de texto a la izquierda.</span><span class="sxs-lookup"><span data-stu-id="0e64f-116">Type **Tutorial_RXSystem** in the left text box.</span></span>|  
  
7.  <span data-ttu-id="0e64f-117">Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="0e64f-117">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  
  
 <span data-ttu-id="0e64f-118">Continúe con [paso 8C: configurar la información de entidad para el sistema de HI](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md).</span><span class="sxs-lookup"><span data-stu-id="0e64f-118">Proceed to [Step 8C: Configure Party Information for the HI System](../../adapters-and-accelerators/accelerator-hl7/step-8c-configure-party-information-for-the-hi-system.md).</span></span>