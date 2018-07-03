---
title: 'Paso 5: Creación de los intercambios de 3A2 de Contoso contrato de socios | Microsoft Docs'
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
ms.assetid: 5c602c9c-22bd-450f-bb14-6848b1414c03
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c5d4004b7ac0d068a2f2621affc34f18ecf21f9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970629"
---
# <a name="step-5-creating-the-contoso-3a2-trading-partner-agreement"></a><span data-ttu-id="537c7-102">Paso 5: Creación del acuerdo de socios comerciales Contoso 3A2</span><span class="sxs-lookup"><span data-stu-id="537c7-102">Step 5: Creating the Contoso 3A2 Trading Partner Agreement</span></span>
<span data-ttu-id="537c7-103">En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="537c7-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="537c7-104">Crear un nuevo acuerdo entre socios comerciales para el proceso de interfaz de socio (PIP) de 3A2.</span><span class="sxs-lookup"><span data-stu-id="537c7-104">You create a new trading partner agreement for the 3A2 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="537c7-105">Para iniciar la consola de administración de BTARN</span><span class="sxs-lookup"><span data-stu-id="537c7-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="537c7-106">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="537c7-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-3a2-trading-partner-agreement"></a><span data-ttu-id="537c7-107">Para crear el acuerdo de socio comercial de 3A2</span><span class="sxs-lookup"><span data-stu-id="537c7-107">To create the 3A2 trading partner agreement</span></span>  

1. <span data-ttu-id="537c7-108">En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **acuerdo** .</span><span class="sxs-lookup"><span data-stu-id="537c7-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="537c7-109">En el **nuevas propiedades de acuerdo** cuadro de diálogo el **General** ficha, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="537c7-109">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="537c7-110">Use</span><span class="sxs-lookup"><span data-stu-id="537c7-110">Use this</span></span>          |                            <span data-ttu-id="537c7-111">Para</span><span class="sxs-lookup"><span data-stu-id="537c7-111">To do this</span></span>                            |
   |---------------------------|------------------------------------------------------------------|
   |         <span data-ttu-id="537c7-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="537c7-112">**Name**</span></span>          |                <span data-ttu-id="537c7-113">Tipo **Fabrikam_To_Contoso_3A2**.</span><span class="sxs-lookup"><span data-stu-id="537c7-113">Type **Fabrikam_To_Contoso_3A2**.</span></span>                 |
   | <span data-ttu-id="537c7-114">**Configuración del proceso**</span><span class="sxs-lookup"><span data-stu-id="537c7-114">**Process Configuration**</span></span> |      <span data-ttu-id="537c7-115">Seleccione **STD_3A2_R02.00.00A** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="537c7-115">Select **STD_3A2_R02.00.00A** from the drop-down list.</span></span>      |
   |    <span data-ttu-id="537c7-116">**Mi organización**</span><span class="sxs-lookup"><span data-stu-id="537c7-116">**My Organization**</span></span>    |           <span data-ttu-id="537c7-117">Seleccione **Contoso** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="537c7-117">Select **Contoso** from the drop-down list.</span></span>            |
   | <span data-ttu-id="537c7-118">**Organización del asociado**</span><span class="sxs-lookup"><span data-stu-id="537c7-118">**Partner Organization**</span></span>  |           <span data-ttu-id="537c7-119">Seleccione **Fabrikam** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="537c7-119">Select **Fabrikam** from the drop-down list.</span></span>           |
   |     <span data-ttu-id="537c7-120">**Versión RNIF**</span><span class="sxs-lookup"><span data-stu-id="537c7-120">**RNIF Version**</span></span>      |          <span data-ttu-id="537c7-121">Seleccione **V02.00.01** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="537c7-121">Select **V02.00.01** from the drop-down list.</span></span>           |
   |       <span data-ttu-id="537c7-122">**Rol principal**</span><span class="sxs-lookup"><span data-stu-id="537c7-122">**Home Role**</span></span>       | <span data-ttu-id="537c7-123">Seleccione **proveedor del producto (respondedor)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="537c7-123">Select **Product Supplier (Responder)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="537c7-124">**Usage**</span><span class="sxs-lookup"><span data-stu-id="537c7-124">**Usage**</span></span>         |             <span data-ttu-id="537c7-125">Seleccione **Prueba** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="537c7-125">Select **Test** from the drop-down list.</span></span>             |


3. <span data-ttu-id="537c7-126">Haga clic en la ficha **Puertos** y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="537c7-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="537c7-127">Use</span><span class="sxs-lookup"><span data-stu-id="537c7-127">Use this</span></span>    |                          <span data-ttu-id="537c7-128">Para</span><span class="sxs-lookup"><span data-stu-id="537c7-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="537c7-129">**Dirección URL de acción**</span><span class="sxs-lookup"><span data-stu-id="537c7-129">**Action URL**</span></span> | <span data-ttu-id="537c7-130">Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="537c7-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   | <span data-ttu-id="537c7-131">**URL de la señal**</span><span class="sxs-lookup"><span data-stu-id="537c7-131">**Signal URL**</span></span> | <span data-ttu-id="537c7-132">Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="537c7-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   |  <span data-ttu-id="537c7-133">**Dirección URL de la sincronización**</span><span class="sxs-lookup"><span data-stu-id="537c7-133">**Sync URL**</span></span>  | <span data-ttu-id="537c7-134">Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="537c7-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |


4. <span data-ttu-id="537c7-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="537c7-135">Click **OK**.</span></span>  

5. <span data-ttu-id="537c7-136">Haga clic en el **Fabrikam_To_Contoso_3A2** acuerdo y, a continuación, haga clic en **activar**.</span><span class="sxs-lookup"><span data-stu-id="537c7-136">Right-click the **Fabrikam_To_Contoso_3A2** agreement, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="537c7-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="537c7-137">See Also</span></span>  
 [<span data-ttu-id="537c7-138">Paso 6: Creación del acuerdo entre socios comerciales Contoso 3A4</span><span class="sxs-lookup"><span data-stu-id="537c7-138">Step 6: Creating the Contoso 3A4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-contoso-3a4-trading-partner-agreement.md)