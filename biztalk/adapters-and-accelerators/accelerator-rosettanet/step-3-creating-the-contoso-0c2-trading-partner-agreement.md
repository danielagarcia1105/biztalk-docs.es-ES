---
title: 'Paso 3: Creación del acuerdo de socios comerciales 2 de Contoso 0c | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, creating
- creating, agreements
- double action tutorial, creating agreements
ms.assetid: b4267faa-5f10-4294-9890-169f1d5ad8f7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eedd57a9c18c689d6357cf1467e08b6951cfc531
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36977637"
---
# <a name="step-3-creating-the-contoso-0c2-trading-partner-agreement"></a><span data-ttu-id="8fdc6-102">Paso 3: Creación del acuerdo de socios comerciales 2 de Contoso 0c</span><span class="sxs-lookup"><span data-stu-id="8fdc6-102">Step 3: Creating the Contoso 0C2 Trading Partner Agreement</span></span>
<span data-ttu-id="8fdc6-103">En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="8fdc6-104">Crear un nuevo acuerdo entre socios comerciales para el 0c 2 proceso de interfaz de socio (PIP).</span><span class="sxs-lookup"><span data-stu-id="8fdc6-104">You create a new trading partner agreement for the 0C2 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="8fdc6-105">Para iniciar la consola de administración de BTARN</span><span class="sxs-lookup"><span data-stu-id="8fdc6-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="8fdc6-106">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-0c2-trading-partner-agreement"></a><span data-ttu-id="8fdc6-107">Para crear el 0c contrato de socios comerciales de 2</span><span class="sxs-lookup"><span data-stu-id="8fdc6-107">To create the 0C2 trading partner agreement</span></span>  

1. <span data-ttu-id="8fdc6-108">En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **acuerdos**, haga clic en **New**y, a continuación, haga clic en **contrato**.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, click **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="8fdc6-109">En el cuadro de diálogo Propiedades de nuevo contrato, en la ficha **General** , realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8fdc6-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="8fdc6-110">Use</span><span class="sxs-lookup"><span data-stu-id="8fdc6-110">Use this</span></span>          |                        <span data-ttu-id="8fdc6-111">Para</span><span class="sxs-lookup"><span data-stu-id="8fdc6-111">To do this</span></span>                         |
   |---------------------------|-----------------------------------------------------------|
   |         <span data-ttu-id="8fdc6-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-112">**Name**</span></span>          |             <span data-ttu-id="8fdc6-113">Tipo **Fabrikam_To_Contoso_0C2**.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-113">Type **Fabrikam_To_Contoso_0C2**.</span></span>             |
   | <span data-ttu-id="8fdc6-114">**Configuración del proceso**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-114">**Process configuration**</span></span> |    <span data-ttu-id="8fdc6-115">Seleccione **STD_0C2_R01.02** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-115">Select **STD_0C2_R01.02** from the drop-down list.</span></span>     |
   |    <span data-ttu-id="8fdc6-116">**Mi organización**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-116">**My organization**</span></span>    |        <span data-ttu-id="8fdc6-117">Seleccione **Contoso** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-117">Select **Contoso** from the drop-down list.</span></span>        |
   | <span data-ttu-id="8fdc6-118">**Organización del asociado**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-118">**Partner organization**</span></span>  |       <span data-ttu-id="8fdc6-119">Seleccione **Fabrikam** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-119">Select **Fabrikam** from the drop-down list.</span></span>        |
   |     <span data-ttu-id="8fdc6-120">**Versión RNIF**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-120">**RNIF version**</span></span>      |       <span data-ttu-id="8fdc6-121">Seleccione **V02.00.01** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-121">Select **V02.00.01** from the drop-down list.</span></span>       |
   |       <span data-ttu-id="8fdc6-122">**Rol principal**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-122">**Home role**</span></span>       | <span data-ttu-id="8fdc6-123">Seleccione **Respondedor (Respondedor)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-123">Select **Responder (Responder)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="8fdc6-124">**Usage**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-124">**Usage**</span></span>         |         <span data-ttu-id="8fdc6-125">Seleccione **Prueba** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-125">Select **Test** from the drop-down list.</span></span>          |


3. <span data-ttu-id="8fdc6-126">Haga clic en la ficha **Puertos** y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="8fdc6-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="8fdc6-127">Use</span><span class="sxs-lookup"><span data-stu-id="8fdc6-127">Use this</span></span>    |                          <span data-ttu-id="8fdc6-128">Para</span><span class="sxs-lookup"><span data-stu-id="8fdc6-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="8fdc6-129">**Dirección URL de acción**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-129">**Action URL**</span></span> | <span data-ttu-id="8fdc6-130">Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   | <span data-ttu-id="8fdc6-131">**URL de la señal**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-131">**Signal URL**</span></span> | <span data-ttu-id="8fdc6-132">Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   |  <span data-ttu-id="8fdc6-133">**Dirección URL de la sincronización**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-133">**Sync URL**</span></span>  | <span data-ttu-id="8fdc6-134">Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="8fdc6-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |


4. <span data-ttu-id="8fdc6-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-135">Click **OK**.</span></span>  

5. <span data-ttu-id="8fdc6-136">Haga clic en el **Fabrikam_To_Contoso_0C2** acuerdo y, a continuación, haga clic en **activar**.</span><span class="sxs-lookup"><span data-stu-id="8fdc6-136">Right-click the **Fabrikam_To_Contoso_0C2** agreement, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8fdc6-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="8fdc6-137">See Also</span></span>  
 [<span data-ttu-id="8fdc6-138">Paso 4: Creación del acuerdo entre socios comerciales Contoso 0C4</span><span class="sxs-lookup"><span data-stu-id="8fdc6-138">Step 4: Creating the Contoso 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-contoso-0c4-trading-partner-agreement.md)