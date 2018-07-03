---
title: 'Paso 3: Creación del acuerdo de socios comerciales 2 de Fabrikam 0c | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: 4552f712-f226-423f-b06d-98e943e8efd4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c10881f1ac703f07d6daaf2a87abd96f3086672b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970269"
---
# <a name="step-3-creating-the-fabrikam-0c2-trading-partner-agreement"></a><span data-ttu-id="90dfe-102">Paso 3: Creación del acuerdo de socios comerciales 2 de Fabrikam 0c</span><span class="sxs-lookup"><span data-stu-id="90dfe-102">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>
<span data-ttu-id="90dfe-103">En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="90dfe-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="90dfe-104">Crear un nuevo acuerdo entre socios comerciales para el 0c 2 proceso de interfaz de socio (PIP).</span><span class="sxs-lookup"><span data-stu-id="90dfe-104">You create a new trading partner agreement for the 0C2 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="90dfe-105">Para iniciar la consola de administración de BTARN</span><span class="sxs-lookup"><span data-stu-id="90dfe-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="90dfe-106">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="90dfe-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-0c2-trading-partner-agreement"></a><span data-ttu-id="90dfe-107">Para crear el 0c contrato de socios comerciales de 2</span><span class="sxs-lookup"><span data-stu-id="90dfe-107">To create the 0C2 trading partner agreement</span></span>  

1. <span data-ttu-id="90dfe-108">En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **acuerdo** .</span><span class="sxs-lookup"><span data-stu-id="90dfe-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="90dfe-109">En el cuadro de diálogo Propiedades de nuevo contrato, en la ficha **General** , realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90dfe-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="90dfe-110">Use</span><span class="sxs-lookup"><span data-stu-id="90dfe-110">Use this</span></span>          |                        <span data-ttu-id="90dfe-111">Para</span><span class="sxs-lookup"><span data-stu-id="90dfe-111">To do this</span></span>                         |
   |---------------------------|-----------------------------------------------------------|
   |         <span data-ttu-id="90dfe-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="90dfe-112">**Name**</span></span>          |             <span data-ttu-id="90dfe-113">Tipo **Fabrikam_To_Contoso_0C2**.</span><span class="sxs-lookup"><span data-stu-id="90dfe-113">Type **Fabrikam_To_Contoso_0C2**.</span></span>             |
   | <span data-ttu-id="90dfe-114">**Configuración del proceso**</span><span class="sxs-lookup"><span data-stu-id="90dfe-114">**Process Configuration**</span></span> |    <span data-ttu-id="90dfe-115">Seleccione **STD_0C2_R01.02** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="90dfe-115">Select **STD_0C2_R01.02** from the drop-down list.</span></span>     |
   |    <span data-ttu-id="90dfe-116">**Mi organización**</span><span class="sxs-lookup"><span data-stu-id="90dfe-116">**My Organization**</span></span>    |       <span data-ttu-id="90dfe-117">Seleccione **Fabrikam** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="90dfe-117">Select **Fabrikam** from the drop-down list.</span></span>        |
   | <span data-ttu-id="90dfe-118">**Organización del asociado**</span><span class="sxs-lookup"><span data-stu-id="90dfe-118">**Partner Organization**</span></span>  |        <span data-ttu-id="90dfe-119">Seleccione **Contoso** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="90dfe-119">Select **Contoso** from the drop-down list.</span></span>        |
   |     <span data-ttu-id="90dfe-120">**Versión RNIF**</span><span class="sxs-lookup"><span data-stu-id="90dfe-120">**RNIF Version**</span></span>      |       <span data-ttu-id="90dfe-121">Seleccione **V02.00.01** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="90dfe-121">Select **V02.00.01** from the drop-down list.</span></span>       |
   |       <span data-ttu-id="90dfe-122">**Rol principal**</span><span class="sxs-lookup"><span data-stu-id="90dfe-122">**Home Role**</span></span>       | <span data-ttu-id="90dfe-123">Seleccione **iniciador (iniciador)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="90dfe-123">Select **Initiator (Initiator)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="90dfe-124">**Usage**</span><span class="sxs-lookup"><span data-stu-id="90dfe-124">**Usage**</span></span>         |         <span data-ttu-id="90dfe-125">Seleccione **Prueba** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="90dfe-125">Select **Test** from the drop-down list.</span></span>          |


3. <span data-ttu-id="90dfe-126">Haga clic en la ficha **Puertos** y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="90dfe-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="90dfe-127">Use</span><span class="sxs-lookup"><span data-stu-id="90dfe-127">Use this</span></span>    |                          <span data-ttu-id="90dfe-128">Para</span><span class="sxs-lookup"><span data-stu-id="90dfe-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="90dfe-129">**Dirección URL de acción**</span><span class="sxs-lookup"><span data-stu-id="90dfe-129">**Action URL**</span></span> | <span data-ttu-id="90dfe-130">Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span><span class="sxs-lookup"><span data-stu-id="90dfe-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   | <span data-ttu-id="90dfe-131">**URL de la señal**</span><span class="sxs-lookup"><span data-stu-id="90dfe-131">**Signal URL**</span></span> | <span data-ttu-id="90dfe-132">Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span><span class="sxs-lookup"><span data-stu-id="90dfe-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   |  <span data-ttu-id="90dfe-133">**Dirección URL de la sincronización**</span><span class="sxs-lookup"><span data-stu-id="90dfe-133">**Sync URL**</span></span>  | <span data-ttu-id="90dfe-134">Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span><span class="sxs-lookup"><span data-stu-id="90dfe-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |


4. <span data-ttu-id="90dfe-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="90dfe-135">Click **OK**.</span></span>  

5. <span data-ttu-id="90dfe-136">Haga clic en el **Fabrikam_To_Contoso_0C2** acuerdo y, a continuación, haga clic en **activar**.</span><span class="sxs-lookup"><span data-stu-id="90dfe-136">Right-click the **Fabrikam_To_Contoso_0C2** agreement, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="90dfe-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="90dfe-137">See Also</span></span>  
 [<span data-ttu-id="90dfe-138">Paso 4: Creación del acuerdo entre socios comerciales Fabrikam 0C4</span><span class="sxs-lookup"><span data-stu-id="90dfe-138">Step 4: Creating the Fabrikam 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-fabrikam-0c4-trading-partner-agreement.md)