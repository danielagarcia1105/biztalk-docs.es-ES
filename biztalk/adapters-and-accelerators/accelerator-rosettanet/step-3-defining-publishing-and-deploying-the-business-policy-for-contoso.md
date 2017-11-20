---
title: "Paso 3: Definición, publicación e implementación de la directiva empresarial para Contoso | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, deploying
- policies, publishing
- private process tutorial, creating policies
- policies, creating
ms.assetid: 529b16d8-226b-4046-a95d-64162ebd59a3
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cbdd1133145aada8b1a1abf0ccdde25547b7fed3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-defining-publishing-and-deploying-the-business-policy-for-contoso"></a><span data-ttu-id="a1bda-102">Paso 3: Definir, publicar e implementar la directiva empresarial de Contoso</span><span class="sxs-lookup"><span data-stu-id="a1bda-102">Step 3: Defining, Publishing, and Deploying the Business Policy for Contoso</span></span>
<span data-ttu-id="a1bda-103">En este paso, creará una directiva empresarial que se reserva una cantidad de conjunto de unidades de cada producto que fabrica Contoso para usarse en caso de emergencia.</span><span class="sxs-lookup"><span data-stu-id="a1bda-103">In this step, you create a business policy that reserves a set quantity of units for each product that Contoso manufactures to be used in case of an emergency.</span></span>  
  
### <a name="to-add-a-new-policy"></a><span data-ttu-id="a1bda-104">Para agregar una nueva directiva</span><span class="sxs-lookup"><span data-stu-id="a1bda-104">To add a new policy</span></span>  
  
1.  <span data-ttu-id="a1bda-105">En el Compositor de reglas de negocios, en el panel Explorador de directivas, haga clic en **directivas**y, a continuación, haga clic en **agregar nueva directiva**.</span><span class="sxs-lookup"><span data-stu-id="a1bda-105">In the Business Rule Composer, in the Policy Explorer pane, right-click **Policies**, and then click **Add New Policy**.</span></span>  
  
2.  <span data-ttu-id="a1bda-106">Nombre de la nueva directiva **3A2PriceAvailabilityPolicy**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="a1bda-106">Name the new policy **3A2PriceAvailabilityPolicy**, and then press **Enter**.</span></span>  
  
### <a name="to-add-a-policy-rule-to-enforce-the-emergency-quantity-needs"></a><span data-ttu-id="a1bda-107">Para agregar una regla de directivas para exigir la cantidad de emergencia necesita</span><span class="sxs-lookup"><span data-stu-id="a1bda-107">To add a policy rule to enforce the emergency quantity needs</span></span>  
  
1.  <span data-ttu-id="a1bda-108">Haga clic en **versión 1.0 (sin guardar)** en **3A2PriceAvailabilityPolicy**y, a continuación, haga clic en **agregar nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="a1bda-108">Right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityPolicy**, and then click **Add New Rule**.</span></span>  
  
2.  <span data-ttu-id="a1bda-109">Nombre de la regla **Emergency proporcionar regla - cantidad agotado**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="a1bda-109">Name the rule **Emergency Supply Rule - Quantity Exhausted**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="a1bda-110">En el Compositor de reglas de negocios, en el panel derecho, haga clic en **condiciones** en el panel IF, seleccione **predicados**y, a continuación, haga clic en el **menor que o igual** predicado.</span><span class="sxs-lookup"><span data-stu-id="a1bda-110">In the Business Rule Composer, in the right pane, right-click **Conditions** under the IF pane, point to **Predicates**, and then click the **Less than equal** predicate.</span></span>  
  
4.  <span data-ttu-id="a1bda-111">En el panel Explorador de hechos, expanda **vocabularios**, expanda **3A2PriceAvailabilityVocabulary**, expanda **versión 1.0 - publicada**, seleccione **cantidad Disponible**y arrástrelo hasta el `argument1` marcador de posición en la superficie del compositor.</span><span class="sxs-lookup"><span data-stu-id="a1bda-111">In the Facts Explorer pane, expand **Vocabularies**, expand **3A2PriceAvailabilityVocabulary**, expand **Version 1.0 - Published**, select **Quantity Available**, and drag it onto the `argument1` placeholder on the composer surface.</span></span>  
  
5.  <span data-ttu-id="a1bda-112">Repita el paso 4 arrastrando **cantidad de emergencia necesaria** en el `argument2` marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="a1bda-112">Repeat step 4 by dragging **Emergency Quantity Needed** onto the `argument2` placeholder.</span></span>  
  
6.  <span data-ttu-id="a1bda-113">Seleccione **Final cantidad disponible**y, a continuación, arrástrelo hasta **acciones** en el panel entonces.</span><span class="sxs-lookup"><span data-stu-id="a1bda-113">Select **Final Quantity Available**, and then drag it onto **Actions** in the THEN pane.</span></span>  
  
### <a name="to-add-a-policy-to-revise-the-number-available-field-in-the-response"></a><span data-ttu-id="a1bda-114">Para agregar una directiva para revisar el campo número disponible en la respuesta</span><span class="sxs-lookup"><span data-stu-id="a1bda-114">To add a policy to revise the Number Available field in the response</span></span>  
  
1.  <span data-ttu-id="a1bda-115">Haga clic en **versión 1.0 (sin guardar)** en **3A2PriceAvailabilityPolicy**y, a continuación, haga clic en **agregar nueva regla**.</span><span class="sxs-lookup"><span data-stu-id="a1bda-115">Right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityPolicy**, and then click **Add New Rule**.</span></span>  
  
2.  <span data-ttu-id="a1bda-116">Nombre de la nueva regla **Emergency proporcionar regla - cantidad disponible**y, a continuación, presione **ENTRAR**.</span><span class="sxs-lookup"><span data-stu-id="a1bda-116">Name the new rule **Emergency Supply Rule - Quantity Available**, and then press **Enter**.</span></span>  
  
3.  <span data-ttu-id="a1bda-117">En el Compositor de reglas de negocios, en el panel derecho, haga clic **condiciones** en el panel IF, seleccione **predicados**y, a continuación, haga clic en el **mayor** predicado.</span><span class="sxs-lookup"><span data-stu-id="a1bda-117">In the Business Rule Composer, in the right pane, right click **Conditions** under the IF pane, point to **Predicates**, and then click the **Greater than** predicate.</span></span>  
  
4.  <span data-ttu-id="a1bda-118">En el panel Explorador de hechos, expanda **vocabularios**, expanda **3A2PriceAvailabilityVocabulary**, expanda **versión 1.0 - publicada**, seleccione **cantidad Disponible**y, a continuación, arrástrelo hasta el `argument1` marcador de posición en la superficie del compositor.</span><span class="sxs-lookup"><span data-stu-id="a1bda-118">In the Facts Explorer pane, expand **Vocabularies**, expand **3A2PriceAvailabilityVocabulary**, expand **Version 1.0 - Published**, select **Quantity Available**, and then drag it onto the `argument1` placeholder on the composer surface.</span></span>  
  
5.  <span data-ttu-id="a1bda-119">Repita el mismo paso arrastrando **cantidad de emergencia necesaria** en el `argument2` marcador de posición.</span><span class="sxs-lookup"><span data-stu-id="a1bda-119">Repeat that same step by dragging **Emergency Quantity Needed** onto the `argument2` placeholder.</span></span>  
  
6.  <span data-ttu-id="a1bda-120">Seleccione **Final cantidad disponible**y, a continuación, arrástrelo hasta **acciones** en el panel entonces.</span><span class="sxs-lookup"><span data-stu-id="a1bda-120">Select **Final Quantity Available**, and then drag it onto **Actions** in the THEN pane.</span></span>  
  
7.  <span data-ttu-id="a1bda-121">En el panel Explorador de hechos, expanda **versión 1.0 - publicada** en **funciones**y arrastre la `Subtract` funcionando en el **0** argumento junto a  **Última cantidad disponible** en el panel entonces.</span><span class="sxs-lookup"><span data-stu-id="a1bda-121">In the Facts Explorer pane, expand **Version 1.0 - Published** under **Functions**, and drag the `Subtract` function onto the **0** argument next to **Final Quantity Available** in the THEN pane.</span></span>  
  
8.  <span data-ttu-id="a1bda-122">Arrastre **cantidad disponible** (en **3A2PriceAvailabilityVocabulary**) y se coloca en el `value1` marcador de posición en el panel entonces.</span><span class="sxs-lookup"><span data-stu-id="a1bda-122">Drag **Quantity Available** (under **3A2PriceAvailabilityVocabulary**) and drop it on the `value1` placeholder in the THEN pane.</span></span>  
  
9. <span data-ttu-id="a1bda-123">Arrastre **cantidad de emergencia necesaria**y colóquela en la `value2` marcador de posición en el panel entonces.</span><span class="sxs-lookup"><span data-stu-id="a1bda-123">Drag **Emergency Quantity Needed**, and drop it on the `value2` placeholder in the THEN pane.</span></span>  
  
### <a name="to-save-publish-and-deploy-the-business-policy"></a><span data-ttu-id="a1bda-124">Para guardar, publicar e implementar la directiva empresarial</span><span class="sxs-lookup"><span data-stu-id="a1bda-124">To save, publish, and deploy the business policy</span></span>  
  
1.  <span data-ttu-id="a1bda-125">En el panel Explorador de directivas, haga clic en **versión 1.0 (sin guardar)** en **3A2PriceAvailabilityPolicy**y, a continuación, haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="a1bda-125">In the Policy Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityPolicy**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="a1bda-126">Haga clic en ese mismo nodo y, a continuación, haga clic en **publicar**.</span><span class="sxs-lookup"><span data-stu-id="a1bda-126">Right-click that same node, and then click **Publish**.</span></span>  
  
3.  <span data-ttu-id="a1bda-127">Haga clic en ese mismo nodo y, a continuación, haga clic en **implementar**.</span><span class="sxs-lookup"><span data-stu-id="a1bda-127">Right-click that same node, and then click **Deploy**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1bda-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="a1bda-128">See Also</span></span>  
 [<span data-ttu-id="a1bda-129">Paso 4: Crear el proyecto HeaderHelper</span><span class="sxs-lookup"><span data-stu-id="a1bda-129">Step 4: Creating the HeaderHelper Project</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-headerhelper-project.md)