---
title: 'Paso 4: Creación del acuerdo de socios comerciales 4 de Contoso 0c | Microsoft Docs'
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
ms.assetid: de2a943f-945a-4bfc-87f3-dd327d5214ef
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 90344af2c2aa1198ecdf95a69a5e411d6097cbc8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002093"
---
# <a name="step-4-creating-the-contoso-0c4-trading-partner-agreement"></a><span data-ttu-id="dca90-102">Paso 4: Creación del acuerdo de socios comerciales 4 de Contoso 0c</span><span class="sxs-lookup"><span data-stu-id="dca90-102">Step 4: Creating the Contoso 0C4 Trading Partner Agreement</span></span>
<span data-ttu-id="dca90-103">En este paso, creará un acuerdo entre socios comerciales entre Contoso y Fabrikam mediante el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración.</span><span class="sxs-lookup"><span data-stu-id="dca90-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="dca90-104">Creará un nuevo contrato de socios comerciales para el proceso de interfaz de socio (PIP) 0C4.</span><span class="sxs-lookup"><span data-stu-id="dca90-104">You create a new trading partner agreement for the 0C4 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="dca90-105">Para iniciar la consola de administración de BTARN</span><span class="sxs-lookup"><span data-stu-id="dca90-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="dca90-106">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="dca90-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console.</span></span>  

### <a name="to-create-the-0c4-trading-partner-agreement"></a><span data-ttu-id="dca90-107">Para crear el contrato de socios comerciales 0C4</span><span class="sxs-lookup"><span data-stu-id="dca90-107">To create the 0C4 trading partner agreement</span></span>  

1. <span data-ttu-id="dca90-108">En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **acuerdos**, apunte a **New**y, a continuación, haga clic en **acuerdo** .</span><span class="sxs-lookup"><span data-stu-id="dca90-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="dca90-109">En el cuadro de diálogo Propiedades de nuevo contrato, en la ficha **General** , realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dca90-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="dca90-110">Use</span><span class="sxs-lookup"><span data-stu-id="dca90-110">Use this</span></span>          |                        <span data-ttu-id="dca90-111">Para</span><span class="sxs-lookup"><span data-stu-id="dca90-111">To do this</span></span>                         |
   |---------------------------|-----------------------------------------------------------|
   |         <span data-ttu-id="dca90-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="dca90-112">**Name**</span></span>          |             <span data-ttu-id="dca90-113">Escriba **Fabrikam_To_Contoso_0C4**.</span><span class="sxs-lookup"><span data-stu-id="dca90-113">Type **Fabrikam_To_Contoso_0C4**.</span></span>             |
   | <span data-ttu-id="dca90-114">**Configuración del proceso**</span><span class="sxs-lookup"><span data-stu-id="dca90-114">**Process Configuration**</span></span> |    <span data-ttu-id="dca90-115">Seleccione **STD_0C4_R01.02** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="dca90-115">Select **STD_0C4_R01.02** from the drop-down list.</span></span>     |
   |    <span data-ttu-id="dca90-116">**Mi organización**</span><span class="sxs-lookup"><span data-stu-id="dca90-116">**My Organization**</span></span>    |        <span data-ttu-id="dca90-117">Seleccione **Contoso** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="dca90-117">Select **Contoso** from the drop-down list.</span></span>        |
   | <span data-ttu-id="dca90-118">**Organización del asociado**</span><span class="sxs-lookup"><span data-stu-id="dca90-118">**Partner Organization**</span></span>  |       <span data-ttu-id="dca90-119">Seleccione **Fabrikam** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="dca90-119">Select **Fabrikam** from the drop-down list.</span></span>        |
   |     <span data-ttu-id="dca90-120">**Versión RNIF**</span><span class="sxs-lookup"><span data-stu-id="dca90-120">**RNIF Version**</span></span>      |       <span data-ttu-id="dca90-121">Seleccione **V02.00.01** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="dca90-121">Select **V02.00.01** from the drop-down list.</span></span>       |
   |       <span data-ttu-id="dca90-122">**Rol principal**</span><span class="sxs-lookup"><span data-stu-id="dca90-122">**Home Role**</span></span>       | <span data-ttu-id="dca90-123">Seleccione **Respondedor (Respondedor)** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="dca90-123">Select **Responder (Responder)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="dca90-124">**Usage**</span><span class="sxs-lookup"><span data-stu-id="dca90-124">**Usage**</span></span>         |         <span data-ttu-id="dca90-125">Seleccione **Prueba** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="dca90-125">Select **Test** from the drop-down list.</span></span>          |


3. <span data-ttu-id="dca90-126">Haga clic en la ficha **Puertos** y, a continuación, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="dca90-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="dca90-127">Use</span><span class="sxs-lookup"><span data-stu-id="dca90-127">Use this</span></span>    |                          <span data-ttu-id="dca90-128">Para</span><span class="sxs-lookup"><span data-stu-id="dca90-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="dca90-129">**Dirección URL de acción**</span><span class="sxs-lookup"><span data-stu-id="dca90-129">**Action URL**</span></span> | <span data-ttu-id="dca90-130">Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="dca90-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   | <span data-ttu-id="dca90-131">**URL de la señal**</span><span class="sxs-lookup"><span data-stu-id="dca90-131">**Signal URL**</span></span> | <span data-ttu-id="dca90-132">Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="dca90-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   |  <span data-ttu-id="dca90-133">**Dirección URL de la sincronización**</span><span class="sxs-lookup"><span data-stu-id="dca90-133">**Sync URL**</span></span>  | <span data-ttu-id="dca90-134">Tipo **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="dca90-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |


4. <span data-ttu-id="dca90-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dca90-135">Click **OK**.</span></span>  

5. <span data-ttu-id="dca90-136">Haga clic con el botón derecho en el acuerdo **Fabrikam_To_Contoso_0C4** y, a continuación, haga clic en **Activar**.</span><span class="sxs-lookup"><span data-stu-id="dca90-136">Right-click the **Fabrikam_To_Contoso_0C4** agreement, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="dca90-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="dca90-137">See Also</span></span>  
 [<span data-ttu-id="dca90-138">Paso 5: Creación del acuerdo entre socios comerciales Contoso 3A2</span><span class="sxs-lookup"><span data-stu-id="dca90-138">Step 5: Creating the Contoso 3A2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-creating-the-contoso-3a2-trading-partner-agreement.md)