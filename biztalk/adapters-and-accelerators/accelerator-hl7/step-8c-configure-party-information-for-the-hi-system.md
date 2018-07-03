---
title: 'Paso 8c: configurar la información de entidad para el sistema de HI | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4ac5c113-7ee7-4009-8ca3-d263f74c7a8d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aba42674a78bbed850c0994ec23c477c36b29c2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970829"
---
# <a name="step-8c-configure-party-information-for-the-hi-system"></a><span data-ttu-id="de729-102">Paso 8c: configurar la información de entidad para el sistema de HI</span><span class="sxs-lookup"><span data-stu-id="de729-102">Step 8C: Configure Party Information for the HI System</span></span>
<span data-ttu-id="de729-103">En este paso, configure la información de entidad para el sistema de HI.</span><span class="sxs-lookup"><span data-stu-id="de729-103">In this step, you configure the party information for the HI System.</span></span>  

### <a name="to-configure-the-hi-system-party-information"></a><span data-ttu-id="de729-104">Para configurar la información de entidad del sistema de HI</span><span class="sxs-lookup"><span data-stu-id="de729-104">To configure the HI System party information</span></span>  

1. <span data-ttu-id="de729-105">En la consola de administración de BizTalk Server, haga clic en **partes**, apunte a **New**y, a continuación, haga clic en **entidad**.</span><span class="sxs-lookup"><span data-stu-id="de729-105">In the BizTalk Server Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  

2. <span data-ttu-id="de729-106">En el cuadro de diálogo Propiedades de entidad en el **nombre** , escriba **Tutorial_HISystem**.</span><span class="sxs-lookup"><span data-stu-id="de729-106">In the Party Properties dialog box, in the **Name** box, type **Tutorial_HISystem**.</span></span>  

3. <span data-ttu-id="de729-107">En el árbol de consola, haga clic en **puertos de envío**.</span><span class="sxs-lookup"><span data-stu-id="de729-107">In the console tree, click **Send Ports**.</span></span>  

4. <span data-ttu-id="de729-108">En el panel puertos de envío, haga clic en el campo en blanco en el **nombre** columna, seleccione **Tutorial_MllpSend**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="de729-108">In the Send Ports pane, click the blank field in the **Name** column, select **Tutorial_MllpSend**, and then click **OK**.</span></span>  

5. <span data-ttu-id="de729-109">Haga clic en **iniciar**, apunte a **programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para HL7**y, a continuación, haga clic en  **BTAHL7 Explorador de configuración**.</span><span class="sxs-lookup"><span data-stu-id="de729-109">Click **Start**, point to **Programs**, point to **Microsoft BizTalk \<version\> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  

6. <span data-ttu-id="de729-110">En el Explorador de configuración de BTAHL7, seleccione el **asignación de MSH** pestaña y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="de729-110">In BTAHL7 Configuration Explorer, select the **MSH Map** tab, and then do the following:</span></span>  


   | <span data-ttu-id="de729-111">Use</span><span class="sxs-lookup"><span data-stu-id="de729-111">Use this</span></span>  |                                             <span data-ttu-id="de729-112">Para</span><span class="sxs-lookup"><span data-stu-id="de729-112">To do this</span></span>                                             |
   |-----------|----------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="de729-113">**MSH3**</span><span class="sxs-lookup"><span data-stu-id="de729-113">**MSH3**</span></span>  | <span data-ttu-id="de729-114">Tipo **BTAHL7**, **IE**, y **UUID** en el primer, segundo y tercer mensaje cuadros, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="de729-114">Type **BTAHL7**, **IE**, and **UUID** in the first, second, and third message boxes, respectively.</span></span> |
   | <span data-ttu-id="de729-115">**MSH5**</span><span class="sxs-lookup"><span data-stu-id="de729-115">**MSH5**</span></span>  | <span data-ttu-id="de729-116">Tipo **HI**, **sistema**, y **GUID** en el primer, segundo y tercer mensaje cuadros, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="de729-116">Type **HI**, **System**, and **GUID** in the first, second, and third message boxes, respectively.</span></span> |
   | <span data-ttu-id="de729-117">**MSH9**</span><span class="sxs-lookup"><span data-stu-id="de729-117">**MSH9**</span></span>  |           <span data-ttu-id="de729-118">Tipo **ADT** y **A04** en los cuadros de mensaje de primer y segundo, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="de729-118">Type **ADT** and **A04** in the first and second message boxes, respectively.</span></span>            |
   | <span data-ttu-id="de729-119">**MSH12**</span><span class="sxs-lookup"><span data-stu-id="de729-119">**MSH12**</span></span> |                                           <span data-ttu-id="de729-120">Tipo **2.4**.</span><span class="sxs-lookup"><span data-stu-id="de729-120">Type **2.4**.</span></span>                                            |
   | <span data-ttu-id="de729-121">**MSH15**</span><span class="sxs-lookup"><span data-stu-id="de729-121">**MSH15**</span></span> |         <span data-ttu-id="de729-122">Seleccione **SU** para enviar confirmaciones después de la transmisión correcta de un mensaje.</span><span class="sxs-lookup"><span data-stu-id="de729-122">Select **SU** to send acknowledgments after successful transmission of a message.</span></span>          |
   | <span data-ttu-id="de729-123">**MSH16**</span><span class="sxs-lookup"><span data-stu-id="de729-123">**MSH16**</span></span> |                            <span data-ttu-id="de729-124">Seleccione **NE** nunca enviar confirmaciones.</span><span class="sxs-lookup"><span data-stu-id="de729-124">Select **NE** to never send acknowledgments.</span></span>                            |


7. <span data-ttu-id="de729-125">Haga clic en **guardar**y, a continuación, cierre el Explorador de configuración de BTAHL7.</span><span class="sxs-lookup"><span data-stu-id="de729-125">Click **Save**, and then close the BTAHL7 Configuration Explorer.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="de729-126">No es necesario crear la información de entidad para el sistema de motor de interfaz de BTAHL7, porque la información de configuración no es necesaria para este escenario.</span><span class="sxs-lookup"><span data-stu-id="de729-126">You do not need to create party information for the BTAHL7 Interface Engine System, because configuration information is not required for this scenario.</span></span>  

   <span data-ttu-id="de729-127">Continúe con [paso 9: reiniciar BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md).</span><span class="sxs-lookup"><span data-stu-id="de729-127">Proceed to [Step 9: Restart BizTalk Server](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md).</span></span>