---
title: "Paso 2: Crear la organización del socio comercial Fabrikam | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, trading partners
- double action tutorial, creating partner organizations
- trading partners, partner organization
ms.assetid: 4d2ddc4c-2275-4faf-9a36-8a912cc06527
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3133f5e2ae7b3a234bef276af67afda391c1f7cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-creating-the-fabrikam-partner-organization"></a><span data-ttu-id="b603d-102">Paso 2: Crear la organización del socio comercial Fabrikam</span><span class="sxs-lookup"><span data-stu-id="b603d-102">Step 2: Creating the Fabrikam Partner Organization</span></span>
<span data-ttu-id="b603d-103">En este paso, usará el [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] consola de administración para crear un nuevo socio comercial.</span><span class="sxs-lookup"><span data-stu-id="b603d-103">In this step, you use the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create a new trading partner.</span></span> <span data-ttu-id="b603d-104">El socio comercial para este tutorial es la organización de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="b603d-104">The trading partner for this tutorial is the Fabrikam organization.</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="b603d-105">Para iniciar la consola de administración de BTARN</span><span class="sxs-lookup"><span data-stu-id="b603d-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="b603d-106">En el equipo de Contoso, haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft BizTalk \<versión > Acelerador para RosettaNet**y, a continuación, Haga clic en  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  consola de administración.</span><span class="sxs-lookup"><span data-stu-id="b603d-106">On the Contoso computer, click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-fabrikam-as-a-trading-partner"></a><span data-ttu-id="b603d-107">Para crear a Fabrikam socio comercial</span><span class="sxs-lookup"><span data-stu-id="b603d-107">To create Fabrikam as a trading partner</span></span>  
  
1.  <span data-ttu-id="b603d-108">En el  **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]**  Management Console, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], haga clic en **asociados**, seleccione **New**y, a continuación, haga clic en **asociado**.</span><span class="sxs-lookup"><span data-stu-id="b603d-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Partners**, point to **New**, and then click **Partner**.</span></span>  
  
2.  <span data-ttu-id="b603d-109">En el cuadro de diálogo Propiedades de nuevo socio, en la ficha **General** , realice lo siguiente**:**</span><span class="sxs-lookup"><span data-stu-id="b603d-109">In the New Partner Properties dialog box, on the **General** tab, do the following**:**</span></span>  
  
    |<span data-ttu-id="b603d-110">Use</span><span class="sxs-lookup"><span data-stu-id="b603d-110">Use this</span></span>|<span data-ttu-id="b603d-111">Para</span><span class="sxs-lookup"><span data-stu-id="b603d-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b603d-112">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="b603d-112">**Name**</span></span>|<span data-ttu-id="b603d-113">Escriba **FABRIKAM**.</span><span class="sxs-lookup"><span data-stu-id="b603d-113">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="b603d-114">**GBI**</span><span class="sxs-lookup"><span data-stu-id="b603d-114">**GBI**</span></span>|<span data-ttu-id="b603d-115">Escriba **987654321**.</span><span class="sxs-lookup"><span data-stu-id="b603d-115">Type **987654321**.</span></span> <span data-ttu-id="b603d-116">**Nota:** si ha ejecutado el tutorial de bucle invertido en el mismo equipo, tendrá que especificar un valor para GBI que es diferente de "987654321".</span><span class="sxs-lookup"><span data-stu-id="b603d-116">**Note:**  If you have run the Loopback tutorial on the same computer, you will have to enter a value for GBI that is different than "987654321".</span></span>|  
    |<span data-ttu-id="b603d-117">**Clasificación de socio comercial**</span><span class="sxs-lookup"><span data-stu-id="b603d-117">**Partner Classification**</span></span>|<span data-ttu-id="b603d-118">En la lista desplegable, seleccione **Comprador** .</span><span class="sxs-lookup"><span data-stu-id="b603d-118">Select **Shopper** from the drop-down list.</span></span>|  
    |<span data-ttu-id="b603d-119">**Certificado de firma**</span><span class="sxs-lookup"><span data-stu-id="b603d-119">**Signature Certificate**</span></span>|<span data-ttu-id="b603d-120">Seleccione **Fabrikam firma [huella digital]** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b603d-120">Select **Fabrikam Signature [Thumbprint]** from the drop-down list.</span></span>|  
    |<span data-ttu-id="b603d-121">**Certificado de cifrado**</span><span class="sxs-lookup"><span data-stu-id="b603d-121">**Encryption Certificate**</span></span>|<span data-ttu-id="b603d-122">Seleccione **Fabrikam cifrado [huella digital]** en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="b603d-122">Select **Fabrikam Encryption [Thumbprint]** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="b603d-123">Haga clic en la ficha **Propiedades del contacto** y, a continuación, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b603d-123">Click the **Contact Properties** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="b603d-124">Use</span><span class="sxs-lookup"><span data-stu-id="b603d-124">Use this</span></span>|<span data-ttu-id="b603d-125">Para</span><span class="sxs-lookup"><span data-stu-id="b603d-125">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="b603d-126">**Nombre de contacto**</span><span class="sxs-lookup"><span data-stu-id="b603d-126">**Contact Name**</span></span>|<span data-ttu-id="b603d-127">Escriba **Jane Doe**.</span><span class="sxs-lookup"><span data-stu-id="b603d-127">Type **Jane Doe**.</span></span>|  
    |<span data-ttu-id="b603d-128">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="b603d-128">**E-mail Address**</span></span>|<span data-ttu-id="b603d-129">Tipo de  **jdoe@fabrikam.com** .</span><span class="sxs-lookup"><span data-stu-id="b603d-129">Type **jdoe@fabrikam.com**.</span></span>|  
    |<span data-ttu-id="b603d-130">**Número de teléfono**</span><span class="sxs-lookup"><span data-stu-id="b603d-130">**Telephone Number**</span></span>|<span data-ttu-id="b603d-131">Escriba **555-555-5555**.</span><span class="sxs-lookup"><span data-stu-id="b603d-131">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="b603d-132">**Número de fax**</span><span class="sxs-lookup"><span data-stu-id="b603d-132">**Fax Number**</span></span>|<span data-ttu-id="b603d-133">Escriba **555-555-5555**.</span><span class="sxs-lookup"><span data-stu-id="b603d-133">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="b603d-134">**Código de la cadena de suministro**</span><span class="sxs-lookup"><span data-stu-id="b603d-134">**Supply chain code**</span></span>|<span data-ttu-id="b603d-135">Escriba **Componentes electrónicos**.</span><span class="sxs-lookup"><span data-stu-id="b603d-135">Type **Electronic Components**.</span></span>|  
  
4.  <span data-ttu-id="b603d-136">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b603d-136">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b603d-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="b603d-137">See Also</span></span>  
 [<span data-ttu-id="b603d-138">Paso 3: Crear el acuerdo de socios comerciales 2 0c de Contoso</span><span class="sxs-lookup"><span data-stu-id="b603d-138">Step 3: Creating the Contoso 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-contoso-0c2-trading-partner-agreement.md)