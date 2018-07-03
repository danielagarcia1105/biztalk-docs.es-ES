---
title: 'Paso 2: Creación de la organización del asociado de Contoso | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating partner organizations
ms.assetid: ebb3b166-3781-40b9-89d4-2ca0c83d05f3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97e811493c1347bc016671469da8a0dc18483e85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969781"
---
# <a name="step-2-creating-the-contoso-partner-organization"></a><span data-ttu-id="e2b7c-102">Paso 2: Creación de la organización del asociado de Contoso</span><span class="sxs-lookup"><span data-stu-id="e2b7c-102">Step 2: Creating the Contoso Partner Organization</span></span>
<span data-ttu-id="e2b7c-103">En este paso, usará el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración para crear un nuevo socio comercial.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-103">In this step, you use the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create a new trading partner.</span></span> <span data-ttu-id="e2b7c-104">El socio comercial para este tutorial es la organización de Contoso.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-104">The trading partner for this tutorial is the Contoso organization.</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="e2b7c-105">Para iniciar la consola de administración de BTARN</span><span class="sxs-lookup"><span data-stu-id="e2b7c-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="e2b7c-106">Haga clic en **iniciar**, apunte a **todos los programas**, apunte a **Microsoft BizTalk \<versión\> Acelerador para RosettaNet**y, a continuación, haga clic en **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Consola de administración.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-fabrikam-as-a-trading-partner"></a><span data-ttu-id="e2b7c-107">Para crear a Fabrikam socio comercial</span><span class="sxs-lookup"><span data-stu-id="e2b7c-107">To create Fabrikam as a trading partner</span></span>  

1. <span data-ttu-id="e2b7c-108">En el **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **asociados**, apunte a **New**y, a continuación, haga clic en **asociado**.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Partners**, point to **New**, and then click **Partner**.</span></span>  

2. <span data-ttu-id="e2b7c-109">En el cuadro de diálogo Propiedades de nuevo socio, en el **General** ficha, realice lo siguiente<strong>:</strong></span><span class="sxs-lookup"><span data-stu-id="e2b7c-109">In the New Partner Properties dialog box, on the **General** tab, do the following<strong>:</strong></span></span>  


   |          <span data-ttu-id="e2b7c-110">Use</span><span class="sxs-lookup"><span data-stu-id="e2b7c-110">Use this</span></span>          |                             <span data-ttu-id="e2b7c-111">Para</span><span class="sxs-lookup"><span data-stu-id="e2b7c-111">To do this</span></span>                              |
   |----------------------------|---------------------------------------------------------------------|
   |          <span data-ttu-id="e2b7c-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="e2b7c-112">**Name**</span></span>          |                          <span data-ttu-id="e2b7c-113">Escriba **CONTOSO**.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-113">Type **CONTOSO**.</span></span>                          |
   |          <span data-ttu-id="e2b7c-114">**GBI**</span><span class="sxs-lookup"><span data-stu-id="e2b7c-114">**GBI**</span></span>           |                         <span data-ttu-id="e2b7c-115">Escriba **123456789**.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-115">Type **123456789**.</span></span>                         |
   | <span data-ttu-id="e2b7c-116">**Clasificación de socio**</span><span class="sxs-lookup"><span data-stu-id="e2b7c-116">**Partner Classification**</span></span> |          <span data-ttu-id="e2b7c-117">En la lista desplegable, seleccione **Fabricante** .</span><span class="sxs-lookup"><span data-stu-id="e2b7c-117">Select **Manufacturer** from the drop-down list.</span></span>           |
   | <span data-ttu-id="e2b7c-118">**Certificado de firma**</span><span class="sxs-lookup"><span data-stu-id="e2b7c-118">**Signature Certificate**</span></span>  | <span data-ttu-id="e2b7c-119">Seleccione **Firma de Contoso [huella digital]** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-119">Select **Contoso Signature [Thumbprint]** from the drop-down list.</span></span>  |
   | <span data-ttu-id="e2b7c-120">**Certificado de cifrado**</span><span class="sxs-lookup"><span data-stu-id="e2b7c-120">**Encryption Certificate**</span></span> | <span data-ttu-id="e2b7c-121">Seleccione **Cifrado de Contoso [huella digital]** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-121">Select **Contoso Encryption [Thumbprint]** from the drop-down list.</span></span> |


3. <span data-ttu-id="e2b7c-122">Haga clic en la ficha **Propiedades del contacto** y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e2b7c-122">Click the **Contact Properties** tab, and then do the following:</span></span>  


   |       <span data-ttu-id="e2b7c-123">Use</span><span class="sxs-lookup"><span data-stu-id="e2b7c-123">Use this</span></span>        |               <span data-ttu-id="e2b7c-124">Para</span><span class="sxs-lookup"><span data-stu-id="e2b7c-124">To do this</span></span>                |
   |-----------------------|-----------------------------------------|
   |   <span data-ttu-id="e2b7c-125">**Nombre de contacto**</span><span class="sxs-lookup"><span data-stu-id="e2b7c-125">**Contact Name**</span></span>    |           <span data-ttu-id="e2b7c-126">Escriba **John Doe**.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-126">Type **John Doe**.</span></span>            |
   |  <span data-ttu-id="e2b7c-127">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="e2b7c-127">**E-mail Address**</span></span>   | <span data-ttu-id="e2b7c-128">Tipo <strong>jdoe@contoso.com</strong>.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-128">Type <strong>jdoe@contoso.com</strong>.</span></span> |
   | <span data-ttu-id="e2b7c-129">**Número de teléfono**</span><span class="sxs-lookup"><span data-stu-id="e2b7c-129">**Telephone Number**</span></span>  |         <span data-ttu-id="e2b7c-130">Escriba **555-555-5555**.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-130">Type **555-555-5555**.</span></span>          |
   |    <span data-ttu-id="e2b7c-131">**Número de fax**</span><span class="sxs-lookup"><span data-stu-id="e2b7c-131">**Fax Number**</span></span>     |         <span data-ttu-id="e2b7c-132">Escriba **555-555-5555**.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-132">Type **555-555-5555**.</span></span>          |
   | <span data-ttu-id="e2b7c-133">**Código de la cadena de suministro**</span><span class="sxs-lookup"><span data-stu-id="e2b7c-133">**Supply chain code**</span></span> |     <span data-ttu-id="e2b7c-134">Escriba **Componentes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-134">Type **Electronic Components**.</span></span>     |


4. <span data-ttu-id="e2b7c-135">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="e2b7c-135">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e2b7c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2b7c-136">See Also</span></span>  
 [<span data-ttu-id="e2b7c-137">Paso 3: Creación del acuerdo entre socios comerciales Fabrikam 0C2</span><span class="sxs-lookup"><span data-stu-id="e2b7c-137">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-fabrikam-0c2-trading-partner-agreement.md)