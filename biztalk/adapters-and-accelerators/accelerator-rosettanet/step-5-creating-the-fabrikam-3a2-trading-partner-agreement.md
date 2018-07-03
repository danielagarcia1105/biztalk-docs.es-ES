---
title: 'Paso 5: Creación de los intercambios de Fabrikam 3A2 contrato de socios | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: a5fafdc6-e9dd-4d15-98a2-8b603901308c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d69b129744df598d69b3209f4af46123ff22fda3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992370"
---
# <a name="step-5-creating-the-fabrikam-3a2-trading-partner-agreement"></a><span data-ttu-id="275ca-102">Paso 5: Creación del acuerdo de socio comercial Fabrikam 3A2</span><span class="sxs-lookup"><span data-stu-id="275ca-102">Step 5: Creating the Fabrikam 3A2 Trading Partner Agreement</span></span>
<span data-ttu-id="275ca-103">En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="275ca-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="275ca-104">Crear un nuevo acuerdo entre socios comerciales para el proceso de interfaz de socio (PIP) de 3A2.</span><span class="sxs-lookup"><span data-stu-id="275ca-104">You create a new trading partner agreement for the 3A2 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="275ca-105">Para iniciar la consola de administración de BTARN</span><span class="sxs-lookup"><span data-stu-id="275ca-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="275ca-106">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="275ca-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-3a2-trading-partner-agreement"></a><span data-ttu-id="275ca-107">Para crear el acuerdo de socio comercial de 3A2</span><span class="sxs-lookup"><span data-stu-id="275ca-107">To create the 3A2 trading partner agreement</span></span>  

1. <span data-ttu-id="275ca-108">En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **acuerdo** .</span><span class="sxs-lookup"><span data-stu-id="275ca-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="275ca-109">En el **nuevas propiedades de acuerdo** cuadro de diálogo el **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="275ca-109">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="275ca-110">Use</span><span class="sxs-lookup"><span data-stu-id="275ca-110">Use this</span></span>          |                        <span data-ttu-id="275ca-111">Para</span><span class="sxs-lookup"><span data-stu-id="275ca-111">To do this</span></span>                        |
   |---------------------------|----------------------------------------------------------|
   |         <span data-ttu-id="275ca-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="275ca-112">**Name**</span></span>          |            <span data-ttu-id="275ca-113">Tipo **Fabrikam_To_Contoso_3A2**.</span><span class="sxs-lookup"><span data-stu-id="275ca-113">Type **Fabrikam_To_Contoso_3A2**.</span></span>             |
   | <span data-ttu-id="275ca-114">**Configuración del proceso**</span><span class="sxs-lookup"><span data-stu-id="275ca-114">**Process Configuration**</span></span> |  <span data-ttu-id="275ca-115">Seleccione **STD_3A2_R02.00.00A** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="275ca-115">Select **STD_3A2_R02.00.00A** from the drop-down list.</span></span>  |
   |    <span data-ttu-id="275ca-116">**Mi organización**</span><span class="sxs-lookup"><span data-stu-id="275ca-116">**My Organization**</span></span>    |       <span data-ttu-id="275ca-117">Seleccione **Fabrikam** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="275ca-117">Select **Fabrikam** from the drop-down list.</span></span>       |
   | <span data-ttu-id="275ca-118">**Organización del asociado**</span><span class="sxs-lookup"><span data-stu-id="275ca-118">**Partner Organization**</span></span>  |       <span data-ttu-id="275ca-119">Seleccione **Contoso** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="275ca-119">Select **Contoso** from the drop-down list.</span></span>        |
   |     <span data-ttu-id="275ca-120">**Versión RNIF**</span><span class="sxs-lookup"><span data-stu-id="275ca-120">**RNIF Version**</span></span>      |      <span data-ttu-id="275ca-121">Seleccione **V02.00.01** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="275ca-121">Select **V02.00.01** from the drop-down list.</span></span>       |
   |       <span data-ttu-id="275ca-122">**Rol principal**</span><span class="sxs-lookup"><span data-stu-id="275ca-122">**Home Role**</span></span>       | <span data-ttu-id="275ca-123">Seleccione **cliente (iniciador)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="275ca-123">Select **Customer (Initiator)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="275ca-124">**Usage**</span><span class="sxs-lookup"><span data-stu-id="275ca-124">**Usage**</span></span>         |         <span data-ttu-id="275ca-125">Seleccione **Prueba** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="275ca-125">Select **Test** from the drop-down list.</span></span>         |


3. <span data-ttu-id="275ca-126">Haga clic en la ficha **Puertos** y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="275ca-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="275ca-127">Use</span><span class="sxs-lookup"><span data-stu-id="275ca-127">Use this</span></span>    |                          <span data-ttu-id="275ca-128">Para</span><span class="sxs-lookup"><span data-stu-id="275ca-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="275ca-129">**Dirección URL de acción**</span><span class="sxs-lookup"><span data-stu-id="275ca-129">**Action URL**</span></span> | <span data-ttu-id="275ca-130">Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span><span class="sxs-lookup"><span data-stu-id="275ca-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   | <span data-ttu-id="275ca-131">**URL de la señal**</span><span class="sxs-lookup"><span data-stu-id="275ca-131">**Signal URL**</span></span> | <span data-ttu-id="275ca-132">Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span><span class="sxs-lookup"><span data-stu-id="275ca-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   |  <span data-ttu-id="275ca-133">**Dirección URL de la sincronización**</span><span class="sxs-lookup"><span data-stu-id="275ca-133">**Sync URL**</span></span>  | <span data-ttu-id="275ca-134">Tipo **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span><span class="sxs-lookup"><span data-stu-id="275ca-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |


4. <span data-ttu-id="275ca-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="275ca-135">Click **OK**.</span></span>  

5. <span data-ttu-id="275ca-136">Haga clic en el **Fabrikam_To_Contoso_3A2** acuerdo y, a continuación, haga clic en **activar**.</span><span class="sxs-lookup"><span data-stu-id="275ca-136">Right-click the **Fabrikam_To_Contoso_3A2** agreement and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="275ca-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="275ca-137">See Also</span></span>  
 [<span data-ttu-id="275ca-138">Paso 6: Creación del acuerdo entre socios comerciales Fabrikam 3A4</span><span class="sxs-lookup"><span data-stu-id="275ca-138">Step 6: Creating the Fabrikam 3A4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-fabrikam-3a4-trading-partner-agreement.md)