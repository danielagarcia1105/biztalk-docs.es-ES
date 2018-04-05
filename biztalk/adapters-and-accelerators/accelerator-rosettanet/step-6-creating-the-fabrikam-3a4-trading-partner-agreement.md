---
title: 'Paso 6: Crear los intercambios de Fabrikam 3A4 contrato de socios | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: 6ccd2414-a1d4-460e-9529-65b2d30cfca6
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 802d3648d0f7709fdfbed70c3e29a4abc565a51c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-6-creating-the-fabrikam-3a4-trading-partner-agreement"></a><span data-ttu-id="772fd-102">Paso 6: Crear el acuerdo de socio comercial Fabrikam 3A4</span><span class="sxs-lookup"><span data-stu-id="772fd-102">Step 6: Creating the Fabrikam 3A4 Trading Partner Agreement</span></span>
<span data-ttu-id="772fd-103">En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="772fd-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="772fd-104">Crear un nuevo acuerdo de socio comercial para el proceso de interfaz de socio (PIP) 3A4.</span><span class="sxs-lookup"><span data-stu-id="772fd-104">You create a new trading partner agreement for the 3A4 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="772fd-105">Para iniciar la consola de administración de BTARN</span><span class="sxs-lookup"><span data-stu-id="772fd-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="772fd-106">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="772fd-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-the-3a4-trading-partner-agreement"></a><span data-ttu-id="772fd-107">Para crear el acuerdo de socio comercial de 3A4</span><span class="sxs-lookup"><span data-stu-id="772fd-107">To create the 3A4 trading partner agreement</span></span>  
  
1.  <span data-ttu-id="772fd-108">En el  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **contratos**, seleccione **New**y, a continuación, haga clic en **acuerdo** .</span><span class="sxs-lookup"><span data-stu-id="772fd-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="772fd-109">En el **nuevas propiedades de acuerdo** cuadro de diálogo, en la **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="772fd-109">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="772fd-110">Use</span><span class="sxs-lookup"><span data-stu-id="772fd-110">Use this</span></span>|<span data-ttu-id="772fd-111">Para</span><span class="sxs-lookup"><span data-stu-id="772fd-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="772fd-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="772fd-112">**Name**</span></span>|<span data-ttu-id="772fd-113">Tipo de **Fabrikam_To_Contoso_3A4**.</span><span class="sxs-lookup"><span data-stu-id="772fd-113">Type **Fabrikam_To_Contoso_3A4**.</span></span>|  
    |<span data-ttu-id="772fd-114">**Configuración del proceso**</span><span class="sxs-lookup"><span data-stu-id="772fd-114">**Process Configuration**</span></span>|<span data-ttu-id="772fd-115">Seleccione **STD_3A4_V02.02** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="772fd-115">Select **STD_3A4_V02.02** from the drop-down list.</span></span>|  
    |<span data-ttu-id="772fd-116">**Mi organización**</span><span class="sxs-lookup"><span data-stu-id="772fd-116">**My Organization**</span></span>|<span data-ttu-id="772fd-117">Seleccione **Fabrikam** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="772fd-117">Select **Fabrikam** from the drop-down list.</span></span>|  
    |<span data-ttu-id="772fd-118">**Organización de socios comerciales**</span><span class="sxs-lookup"><span data-stu-id="772fd-118">**Partner Organization**</span></span>|<span data-ttu-id="772fd-119">Seleccione **Contoso** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="772fd-119">Select **Contoso** from the drop-down list.</span></span>|  
    |<span data-ttu-id="772fd-120">**Versión RNIF**</span><span class="sxs-lookup"><span data-stu-id="772fd-120">**RNIF Version**</span></span>|<span data-ttu-id="772fd-121">Seleccione **V02.00.01** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="772fd-121">Select **V02.00.01** from the drop-down list.</span></span>|  
    |<span data-ttu-id="772fd-122">**Rol principal**</span><span class="sxs-lookup"><span data-stu-id="772fd-122">**Home Role**</span></span>|<span data-ttu-id="772fd-123">Seleccione **comprador (iniciador)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="772fd-123">Select **Buyer (Initiator)** from the drop-down list.</span></span>|  
    |<span data-ttu-id="772fd-124">**Uso**</span><span class="sxs-lookup"><span data-stu-id="772fd-124">**Usage**</span></span>|<span data-ttu-id="772fd-125">Seleccione **Prueba** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="772fd-125">Select **Test** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="772fd-126">En el **puertos** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="772fd-126">On the **Ports** tab, do the following:</span></span>  
  
    |<span data-ttu-id="772fd-127">Use</span><span class="sxs-lookup"><span data-stu-id="772fd-127">Use this</span></span>|<span data-ttu-id="772fd-128">Para</span><span class="sxs-lookup"><span data-stu-id="772fd-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="772fd-129">**Dirección URL de acción**</span><span class="sxs-lookup"><span data-stu-id="772fd-129">**Action URL**</span></span>|<span data-ttu-id="772fd-130">Tipo de **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span><span class="sxs-lookup"><span data-stu-id="772fd-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="772fd-131">**Dirección URL de señal**</span><span class="sxs-lookup"><span data-stu-id="772fd-131">**Signal URL**</span></span>|<span data-ttu-id="772fd-132">Tipo de **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span><span class="sxs-lookup"><span data-stu-id="772fd-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="772fd-133">**Dirección URL de la sincronización**</span><span class="sxs-lookup"><span data-stu-id="772fd-133">**Sync URL**</span></span>|<span data-ttu-id="772fd-134">Tipo de **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span><span class="sxs-lookup"><span data-stu-id="772fd-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
  
4.  <span data-ttu-id="772fd-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="772fd-135">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="772fd-136">Haga clic en el **Fabrikam_To_Contoso_3A4** acuerdo y, a continuación, haga clic en **activar**.</span><span class="sxs-lookup"><span data-stu-id="772fd-136">Right-click the **Fabrikam_To_Contoso_3A4** agreement and then click **Activate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="772fd-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="772fd-137">See Also</span></span>  
 [<span data-ttu-id="772fd-138">Paso 7: Compilación e implementación del ejemplo de SDK de LOBWebApplication</span><span class="sxs-lookup"><span data-stu-id="772fd-138">Step 7: Building and Deploying the LOBWebApplication SDK Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-lobwebapplication-sdk-sample.md)