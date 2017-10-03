---
title: "Paso 8: configurar la información de entidad para el System_hl7_main ADT | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 693fda8b-9a99-4a6e-89b7-294f84676350
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9285b926edb5ca4f1dccf18ed2d5f76b3af14ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-8a-configure-party-information-for-the-adt-systemhl7main"></a><span data-ttu-id="ab073-102">Paso 8: configurar la información de entidad para el System_hl7_main ADT</span><span class="sxs-lookup"><span data-stu-id="ab073-102">Step 8A: Configure Party Information for the ADT System_hl7_main</span></span>
<span data-ttu-id="ab073-103">En este paso, configurará la información de entidad para el sistema ADT.</span><span class="sxs-lookup"><span data-stu-id="ab073-103">In this step, you configure the party information for the ADT System.</span></span>  
  
### <a name="to-configure-the-adt-system-party-information"></a><span data-ttu-id="ab073-104">Para configurar la información de entidad del sistema ADT</span><span class="sxs-lookup"><span data-stu-id="ab073-104">To configure the ADT System party information</span></span>  
  
1.  <span data-ttu-id="ab073-105">En la consola de administración de BizTalk, expanda **administración de BizTalk Server**y, a continuación, expanda **grupo de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="ab073-105">In the BizTalk Administration Console, expand **BizTalk Server Administration**, and then expand **BizTalk Group**.</span></span> <span data-ttu-id="ab073-106">Haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="ab073-106">Right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="ab073-107">En el cuadro de diálogo Propiedades de la entidad, en la **nombre** , escriba **ADT**.</span><span class="sxs-lookup"><span data-stu-id="ab073-107">In the Party Properties dialog box, in the **Name** field, type **ADT**.</span></span> <span data-ttu-id="ab073-108">(El valor que escriba en este cuadro debe coincidir con la instancia original del mensaje HL7, QRY^Q01.txt MSH3.)</span><span class="sxs-lookup"><span data-stu-id="ab073-108">(The value you type in this box should match the original HL7 message instance, QRY^Q01.txt MSH3.)</span></span>  
  
3.  <span data-ttu-id="ab073-109">En el árbol de consola, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="ab073-109">In the Console Tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="ab073-110">En el **puerto de envío** panel, para **nombre** en la primera fila, seleccione **ADT_Send**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ab073-110">In the **Send Port** pane, for **Name** in the first row, select **ADT_Send**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="ab073-111">Haga clic en **iniciar**, seleccione **programas**, seleccione **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="ab073-111">Click **Start**, point to **Programs**, point to **Microsoft  BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
6.  <span data-ttu-id="ab073-112">En el Explorador de configuración de BTAHL7, haga clic en el **confirmación** ficha. Para **tipo de confirmación**, seleccione **EnhancedMode**.</span><span class="sxs-lookup"><span data-stu-id="ab073-112">In BTAHL7 Configuration Explorer, click the **Acknowledgment** tab. For **Acknowledgment Type**, select **EnhancedMode**.</span></span>  
  
7.  <span data-ttu-id="ab073-113">En las propiedades de confirmación en el panel de mensajes de Inboiund, para **MSH15 - tipo de confirmación que acepte**, seleccione **AL**.</span><span class="sxs-lookup"><span data-stu-id="ab073-113">In the Acknowledgment Properties in Inboiund Message pane, for **MSH15 - Accept Acknowledgment Type**, select **AL**.</span></span>  
  
8.  <span data-ttu-id="ab073-114">En el panel de propiedades de confirmación, para **MSH16 - tipo de confirmación de la aplicación**, seleccione **NE**.</span><span class="sxs-lookup"><span data-stu-id="ab073-114">In the Acknowledgment Properties pane, for **MSH16 - Application Acknowledgment Type**, select **NE**.</span></span>  
  
9. <span data-ttu-id="ab073-115">Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="ab073-115">Click **Save**, and then close BTAHL7 Configuration Explorer.</span></span>  
  
 <span data-ttu-id="ab073-116">Continúe con [paso 8B: configurar la información de entidad para el sistema de HI](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-hi-system.md).</span><span class="sxs-lookup"><span data-stu-id="ab073-116">Proceed to [Step 8B: Configure Party Information for the HI System](../../adapters-and-accelerators/accelerator-hl7/step-8b-configure-party-information-for-the-hi-system.md).</span></span>