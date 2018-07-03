---
title: 'Paso 4: Crear un acuerdo comercial | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, trade agreeements
- loopback tutorial, creating trade agreements
- agreements, creating
ms.assetid: 9bcb80b1-fefc-4f1c-ae03-fb736cdfd524
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbe74e1b214d733615bbc46deaea9f8a7e6c5134
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994637"
---
# <a name="step-4-create-a-trade-agreement"></a><span data-ttu-id="22883-102">Paso 4: Crear un acuerdo comercial</span><span class="sxs-lookup"><span data-stu-id="22883-102">Step 4: Create a Trade Agreement</span></span>
<span data-ttu-id="22883-103">En este paso, creará un acuerdo comercial entre la organización principal y socios mediante el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="22883-103">In this step, you create a trade agreement between the home and partner organization using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span>  

### <a name="to-create-a-trade-agreement"></a><span data-ttu-id="22883-104">Para crear un acuerdo comercial</span><span class="sxs-lookup"><span data-stu-id="22883-104">To create a trade agreement</span></span>  

1. <span data-ttu-id="22883-105">En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda **BizTalk \<versión\> Acelerador para RosettaNet**, haga clic en **acuerdos**, haga clic en **New**y, a continuación, haga clic en **contrato**.</span><span class="sxs-lookup"><span data-stu-id="22883-105">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand **BizTalk \<version\> Accelerator for RosettaNet**, right-click **Agreements**, click **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="22883-106">En el **nuevas propiedades de acuerdo** cuadro de diálogo el **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22883-106">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="22883-107">Use</span><span class="sxs-lookup"><span data-stu-id="22883-107">Use this</span></span>          |                     <span data-ttu-id="22883-108">Para</span><span class="sxs-lookup"><span data-stu-id="22883-108">To do this</span></span>                     |
   |---------------------------|----------------------------------------------------|
   |         <span data-ttu-id="22883-109">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="22883-109">**Name**</span></span>          |             <span data-ttu-id="22883-110">Tipo **comercio contrato**.</span><span class="sxs-lookup"><span data-stu-id="22883-110">Type **Trade Agreement**.</span></span>              |
   | <span data-ttu-id="22883-111">**Configuración del proceso**</span><span class="sxs-lookup"><span data-stu-id="22883-111">**Process Configuration**</span></span> | <span data-ttu-id="22883-112">Seleccione **STD_0C1_R01.02** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="22883-112">Select **STD_0C1_R01.02** from the drop-down list.</span></span> |
   |    <span data-ttu-id="22883-113">**Mi organización**</span><span class="sxs-lookup"><span data-stu-id="22883-113">**My organization**</span></span>    |      <span data-ttu-id="22883-114">Seleccione **inicio** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="22883-114">Select **HOME** from the drop-down list.</span></span>      |
   | <span data-ttu-id="22883-115">**Organización del asociado**</span><span class="sxs-lookup"><span data-stu-id="22883-115">**Partner organization**</span></span>  |    <span data-ttu-id="22883-116">Seleccione **asociado** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="22883-116">Select **PARTNER** from the drop-down list.</span></span>     |
   |       <span data-ttu-id="22883-117">**Rol principal**</span><span class="sxs-lookup"><span data-stu-id="22883-117">**Home role**</span></span>       |   <span data-ttu-id="22883-118">Seleccione **iniciador** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="22883-118">Select **Initiator** from the drop-down list.</span></span>    |


3. <span data-ttu-id="22883-119">En el **nuevas propiedades de acuerdo** cuadro de diálogo el **puertos** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="22883-119">In the **New Agreement Properties** dialog box, on the **Ports** tab, do the following:</span></span>  


   |    <span data-ttu-id="22883-120">Use</span><span class="sxs-lookup"><span data-stu-id="22883-120">Use this</span></span>    |                                         <span data-ttu-id="22883-121">Para</span><span class="sxs-lookup"><span data-stu-id="22883-121">To do this</span></span>                                         |
   |----------------|--------------------------------------------------------------------------------------------|
   | <span data-ttu-id="22883-122">**Dirección URL de acción**</span><span class="sxs-lookup"><span data-stu-id="22883-122">**Action URL**</span></span> |                   <span data-ttu-id="22883-123">Tipo **<http://localhost/BTARNApp/RNIFReceive.aspx>**.</span><span class="sxs-lookup"><span data-stu-id="22883-123">Type **<http://localhost/BTARNApp/RNIFReceive.aspx>**.</span></span>                   |
   | <span data-ttu-id="22883-124">**URL de la señal**</span><span class="sxs-lookup"><span data-stu-id="22883-124">**Signal URL**</span></span> |                   <span data-ttu-id="22883-125">Tipo **<http://localhost/BTARNApp/RNIFReceive.aspx>**.</span><span class="sxs-lookup"><span data-stu-id="22883-125">Type **<http://localhost/BTARNApp/RNIFReceive.aspx>**.</span></span>                   |
   |  <span data-ttu-id="22883-126">**Dirección URL de la sincronización**</span><span class="sxs-lookup"><span data-stu-id="22883-126">**Sync URL**</span></span>  | <span data-ttu-id="22883-127">Deje en blanco.</span><span class="sxs-lookup"><span data-stu-id="22883-127">Leave blank.</span></span> <span data-ttu-id="22883-128">URL de sincronización no es necesaria para el proceso de interfaz de socio (PIP) sincrónico.</span><span class="sxs-lookup"><span data-stu-id="22883-128">Sync URL is not required for the synchronous Partner Interface Process (PIP).</span></span> |


4. <span data-ttu-id="22883-129">Haga clic en **aplicar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="22883-129">Click **Apply**, and then click **OK**.</span></span>  

   <span data-ttu-id="22883-130">Después de crear el acuerdo comercial, primero debe activarlo.</span><span class="sxs-lookup"><span data-stu-id="22883-130">After you create the trade agreement, you must activate it.</span></span>  

### <a name="to-activate-the-trade-agreement"></a><span data-ttu-id="22883-131">Para activar el acuerdo comercial</span><span class="sxs-lookup"><span data-stu-id="22883-131">To activate the trade agreement</span></span>  

- <span data-ttu-id="22883-132">En el [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **acuerdos**, haga clic en **acuerdo comercial** en el panel de resultados y, a continuación, haga clic en **activar**.</span><span class="sxs-lookup"><span data-stu-id="22883-132">In the [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], click **Agreements**, right-click **Trade Agreement** in the results pane, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="22883-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="22883-133">See Also</span></span>  
 [<span data-ttu-id="22883-134">Paso 5: Crear un acuerdo reflejado</span><span class="sxs-lookup"><span data-stu-id="22883-134">Step 5: Create a Mirror Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)