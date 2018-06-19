---
title: 'Paso 2: Definir y publicar el vocabulario de Contoso | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- vocabularies, creating
- vocabularies, publishing
- private process tutorial, creating vocabularies
ms.assetid: e23880c0-772c-48c6-a6b5-32eb951527c8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15937a1235cc1776be38fe2b0e5529c19d3f6fd5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22211092"
---
# <a name="step-2-defining-and-publishing-the-vocabulary-for-contoso"></a><span data-ttu-id="da032-102">Paso 2: Definir y publicar el vocabulario de Contoso</span><span class="sxs-lookup"><span data-stu-id="da032-102">Step 2: Defining and Publishing the Vocabulary for Contoso</span></span>
<span data-ttu-id="da032-103">En este escenario, Contoso implementa una directiva empresarial que se asegura de que el inventario está siempre disponible si se produce una emergencia.</span><span class="sxs-lookup"><span data-stu-id="da032-103">In this scenario, Contoso implements a business policy that makes sure that inventory is always on hand if an emergency occurs.</span></span> <span data-ttu-id="da032-104">Crear directivas de negocio mediante el Compositor de reglas de negocios en [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="da032-104">You create business policies using the Business Rule Composer in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="da032-105">En este paso, creará el vocabulario que se va a usar al definir la directiva empresarial.</span><span class="sxs-lookup"><span data-stu-id="da032-105">In this step, you create the vocabulary to use when you define the business policy.</span></span>  
  
### <a name="to-add-a-new-vocabulary"></a><span data-ttu-id="da032-106">Para agregar un vocabulario nuevo</span><span class="sxs-lookup"><span data-stu-id="da032-106">To add a new vocabulary</span></span>  
  
1.  <span data-ttu-id="da032-107">Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)]y, a continuación, haga clic en **Compositor de reglas de negocios**.</span><span class="sxs-lookup"><span data-stu-id="da032-107">Click **Start**, point to **All Programs**, point to **Microsoft**[!INCLUDE[btsBizTalkServer2006r3ui](../../includes/btsbiztalkserver2006r3ui-md.md)], and then click **Business Rule Composer**.</span></span>  
  
2.  <span data-ttu-id="da032-108">En el cuadro de diálogo Abrir almacén de reglas, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da032-108">In the Open Rule Store dialog box, click **OK**.</span></span>  
  
3.  <span data-ttu-id="da032-109">En el panel Explorador de hechos, en la ficha **Vocabularios** , haga clic con el botón derecho en **Vocabularios**y, a continuación, haga clic en **Agregar nuevo vocabulario**.</span><span class="sxs-lookup"><span data-stu-id="da032-109">In the Facts Explorer pane, on the **Vocabularies** tab, right-click **Vocabularies**, and then click **Add New Vocabulary**.</span></span>  
  
4.  <span data-ttu-id="da032-110">Asigne al vocabulario el nombre **3A2PriceAvailabilityVocabulary**y, a continuación, presione **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="da032-110">Name the vocabulary **3A2PriceAvailabilityVocabulary**, and then press **Enter**.</span></span>  
  
### <a name="to-define-a-constant-vocabulary-value"></a><span data-ttu-id="da032-111">Para definir un valor constante de vocabulario</span><span class="sxs-lookup"><span data-stu-id="da032-111">To define a constant vocabulary value</span></span>  
  
1.  <span data-ttu-id="da032-112">En el Compositor de reglas de negocio, haga clic en **3A2PriceAvailabilityVocabulary**, haga clic con el botón derecho en **Versión 1.0 (sin guardar)** y, a continuación, haga clic en **Agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="da032-112">In Business Rule Composer, click **3A2PriceAvailabilityVocabulary**, right-click **Version 1.0(not saved)**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="da032-113">En la página **Asistente para definición de vocabulario** , seleccione **Valor, rango de valores o conjunto de valores constantes**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da032-113">On the **Vocabulary Definition Wizard** page, select **Constant Value, Range of Values, or Set of Values**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="da032-114">En la página **Valor, rango de valores o conjunto de valores constantes** , en el cuadro **Nombre de definición** , escriba **Cantidad de emergencia necesaria**y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da032-114">On the **Constant Value, Range of Values, or Set of Values** page, in the **Definition name** box, type **Emergency Quantity Needed**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="da032-115">En la página **Definir un valor constante** , en el cuadro **Valor** , escriba **800**y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="da032-115">On the **Define a Constant Value** page, in the **Value** box, type **800**, and then click **Finish**.</span></span>  
  
### <a name="to-define-an-xml-document-get-element"></a><span data-ttu-id="da032-116">Para definir un elemento "Get" de documento XML</span><span class="sxs-lookup"><span data-stu-id="da032-116">To define an XML document 'Get' element</span></span>  
  
1.  <span data-ttu-id="da032-117">En el Compositor de reglas de negocio, en el Explorador de hechos, haga clic con el botón derecho en **Versión 1.0 (sin guardar)** en **3A2PriceAvailabilityVocabulary**y, a continuación, haga clic en **Agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="da032-117">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="da032-118">En el **VocabularyDefinition asistente** página, seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da032-118">On the **VocabularyDefinition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="da032-119">En la página **Atributo o elemento de documento XML** , en el cuadro **Nombre de definición** , escriba **Cantidad disponible**.</span><span class="sxs-lookup"><span data-stu-id="da032-119">On the **XML Document Element or Attribute** page, in the **Definition Name** box, type **Quantity Available**.</span></span>  
  
4.  <span data-ttu-id="da032-120">Haga clic en **Examinar** (junto al campo **Esquema** ), vaya al proyecto **ContosoPriceAndAvailability** en la carpeta de la solución, seleccione el esquema **ContosoPriceAndAvailability.xsd** y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="da032-120">Click **Browse** (next to the **Schema** field), move to the **ContosoPriceAndAvailability** project in your solution folder, select the **ContosoPriceAndAvailability.xsd** schema, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="da032-121">En el cuadro de diálogo Seleccionar enlace, expanda **rootPriceResponse**y después **Productos**, seleccione el elemento **NumberAvailable** y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da032-121">In the Select Binding dialog box, expand **rootPriceResponse**, expand **Products**, select the **NumberAvailable** element, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="da032-122">En la página **Atributo o elemento de documento XML** , en el cuadro **Tipo de documento** , asegúrese de que el valor es **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span><span class="sxs-lookup"><span data-stu-id="da032-122">On the **XML Document Element or Attribute** page, in the **Document Type** box, ensure that the value is **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span></span>  
  
7.  <span data-ttu-id="da032-123">En la sección **Seleccionar operación** , seleccione **Realizar operación "Get"** y, a continuación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="da032-123">In the **Select operation** section, select **Perform "Get" Operation**, and then click **Finish**.</span></span>  
  
### <a name="to-define-an-xml-document-set-element"></a><span data-ttu-id="da032-124">Para definir un elemento "Set" de documento XML</span><span class="sxs-lookup"><span data-stu-id="da032-124">To define an XML document 'Set' element</span></span>  
  
1.  <span data-ttu-id="da032-125">En el Compositor de reglas de negocio, en el Explorador de hechos, haga clic con el botón derecho en **Versión 1.0 (sin guardar)** en **3A2PriceAvailabilityVocabulary**y, a continuación, haga clic en **Agregar nueva definición**.</span><span class="sxs-lookup"><span data-stu-id="da032-125">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Add New Definition**.</span></span>  
  
2.  <span data-ttu-id="da032-126">En el **VocabularyDefinition asistente** página, seleccione **atributo o elemento de documento XML**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da032-126">On the **VocabularyDefinition Wizard** page, select **XML Document Element or Attribute**, and then click **Next**.</span></span>  
  
3.  <span data-ttu-id="da032-127">En la página **Atributo o elemento de documento XML** , en el cuadro **Nombre de definición** , escriba **Cantidad final disponible**.</span><span class="sxs-lookup"><span data-stu-id="da032-127">On the **XML Document Element or Attribute** page, in the **Definition Name** box, type **Final Quantity Available**.</span></span>  
  
4.  <span data-ttu-id="da032-128">Haga clic en **Examinar** (junto al campo **Esquema** ), vaya al proyecto **ContosoPriceAndAvailability** en la carpeta de la solución, seleccione el esquema **ContosoPriceAndAvailability.xsd** y, a continuación, haga clic en **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="da032-128">Click **Browse** (next to the **Schema** field), move to the **ContosoPriceAndAvailability** project in your solution folder, select the **ContosoPriceAndAvailability.xsd** schema, and then click **Open**.</span></span>  
  
5.  <span data-ttu-id="da032-129">En el **Seleccionar enlace** cuadro de diálogo, expanda **rootPriceResponse**, expanda **productos**y, a continuación, seleccione la **NumberAvailable** elemento.</span><span class="sxs-lookup"><span data-stu-id="da032-129">In the **Select Binding** dialog box, expand **rootPriceResponse**, expand **Products**, and then select the **NumberAvailable** element.</span></span> <span data-ttu-id="da032-130">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="da032-130">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="da032-131">En la página **Atributo o elemento de documento XML** , en el cuadro **Tipo de documento** , asegúrese de que el valor es **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span><span class="sxs-lookup"><span data-stu-id="da032-131">On the **XML Document Element or Attribute** page, in the **Document Type** box, ensure that the value is **ContosoPriceAndAvailability.ContosoPriceSchema.rootPriceResponse**.</span></span>  
  
7.  <span data-ttu-id="da032-132">En la sección **Seleccionar operación** , seleccione **Realizar operación "Set"** y, a continuación, haga clic en **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="da032-132">In the **Select operation** section, select **Perform "Set" Operation**, and then click **Next**.</span></span>  
  
8.  <span data-ttu-id="da032-133">En la página **Especificar el nombre para mostrar** , haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="da032-133">In the **Specify the Display Name** page, click **Finish**.</span></span>  
  
### <a name="to-save-and-publish-the-vocabulary"></a><span data-ttu-id="da032-134">Para guardar y publicar el vocabulario</span><span class="sxs-lookup"><span data-stu-id="da032-134">To save and publish the vocabulary</span></span>  
  
1.  <span data-ttu-id="da032-135">En el Compositor de reglas de negocio, en el Explorador de hechos, haga clic con el botón derecho en **Versión 1.0 (sin guardar)** en **3A2PriceAvailabilityVocabulary**y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="da032-135">In Business Rule Composer, in the Facts Explorer pane, right-click **Version 1.0 (not saved)** under **3A2PriceAvailabilityVocabulary**, and then click **Save**.</span></span>  
  
2.  <span data-ttu-id="da032-136">Haga clic con el botón derecho en el mismo nodo de **Versión 1.0** y, a continuación, haga clic en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="da032-136">Right-click that same **Version 1.0** node and then click **Publish**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="da032-137">Deje el Compositor de reglas de negocio abierto para el siguiente paso del tutorial.</span><span class="sxs-lookup"><span data-stu-id="da032-137">Leave the Business Rule Composer open for the next step in the tutorial.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da032-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="da032-138">See Also</span></span>  
 [<span data-ttu-id="da032-139">Paso 3: Definir, publicar e implementar la directiva empresarial de Contoso</span><span class="sxs-lookup"><span data-stu-id="da032-139">Step 3: Defining, Publishing, and Deploying the Business Policy for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-defining-publishing-and-deploying-the-business-policy-for-contoso.md)