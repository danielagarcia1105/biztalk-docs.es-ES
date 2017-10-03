---
title: 'Paso 7: Crear y configurar una entidad de origen | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d8788a9c-ae6f-461b-82e5-f4276d1d5e0c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32539b1c352ac1fd2b60d2acd4c5ee975e2c3d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-7-create-and-configure-a-source-party"></a><span data-ttu-id="b3e45-102">Paso 7: Crear y configurar una entidad de origen</span><span class="sxs-lookup"><span data-stu-id="b3e45-102">Step 7: Create and Configure a Source Party</span></span>
<span data-ttu-id="b3e45-103">En este paso, crear y configurar una entidad de origen y asignar los puertos de envío para habilitar las transformaciones de encabezado de mensaje para el mensaje saliente.</span><span class="sxs-lookup"><span data-stu-id="b3e45-103">In this step, you create and configure a source party, and assign send ports to enable message header transformations for the outgoing message.</span></span>  
  
### <a name="to-create-and-configure-a-source-party"></a><span data-ttu-id="b3e45-104">Para crear y configurar una entidad de origen</span><span class="sxs-lookup"><span data-stu-id="b3e45-104">To create and configure a source party</span></span>  
  
1.  <span data-ttu-id="b3e45-105">En la consola de administración de BizTalk, haga clic en **partes**, seleccione **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="b3e45-105">In the BizTalk Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="b3e45-106">En el **propiedades de la entidad** cuadro de diálogo, en el campo nombre, escriba **Tutorial_BatchSource**.</span><span class="sxs-lookup"><span data-stu-id="b3e45-106">In the **Party Properties** dialog box, in the Name field, type **Tutorial_BatchSource**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b3e45-107">El valor que escriba en este cuadro es de FHS3.1 del original [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] mensaje por lotes, FragmentedInboundBatch.txt.</span><span class="sxs-lookup"><span data-stu-id="b3e45-107">The value that you type in this box is from FHS3.1 of the original [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] batched message, FragmentedInboundBatch.txt.</span></span>  
  
3.  <span data-ttu-id="b3e45-108">En el árbol de consola, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="b3e45-108">In the console tree, click **Send Ports**.</span></span>  
  
4.  <span data-ttu-id="b3e45-109">En el panel de puertos de envío, para el campo nombre, seleccione **Tutorial_2wayAck**.</span><span class="sxs-lookup"><span data-stu-id="b3e45-109">In the Send Ports pane, for the Name field, select **Tutorial_2wayAck**.</span></span>  
  
5.  <span data-ttu-id="b3e45-110">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b3e45-110">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="b3e45-111">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión > Accelerator for HL7**y, a continuación, haga clic en **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="b3e45-111">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
7.  <span data-ttu-id="b3e45-112">En el Explorador de configuración de BTAHL7, en la **partes** , haga clic en **Tutorial_BatchSource**.</span><span class="sxs-lookup"><span data-stu-id="b3e45-112">In BTAHL7 Configuration Explorer, on the **Parties** tab, click **Tutorial_BatchSource**.</span></span>  
  
8.  <span data-ttu-id="b3e45-113">Seleccione el **definición por lotes** pestaña del explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="b3e45-113">Select the **Batch Definition** tab of BTAHL7 Configuration Explorer.</span></span> <span data-ttu-id="b3e45-114">Seleccione **Sí** para **requerida fragmentación**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="b3e45-114">Select **Yes** for **Fragmentation Required**, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="b3e45-115">Seleccione el **confirmación** ficha. Para **tipo de confirmación**, seleccione **OriginalMode**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="b3e45-115">Select the **Acknowledgment** tab. For **Acknowledgment Type**, select **OriginalMode**, and then click **Save**.</span></span>  
  
 <span data-ttu-id="b3e45-116">Continúe con [paso 8: reinicie el servidor BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="b3e45-116">Proceed to [Step 8: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-8-restart-biztalk-server.md).</span></span>