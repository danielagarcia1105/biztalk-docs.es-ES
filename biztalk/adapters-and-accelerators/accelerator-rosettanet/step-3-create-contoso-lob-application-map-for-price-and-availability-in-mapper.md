---
title: 'Paso 3: Crear la aplicación de LOB de Contoso se asigna para el precio y disponibilidad proyecto utilizando el asignador de BizTalk | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating LOB maps
ms.assetid: a947e0ac-f0cb-4be9-85a8-09daf3675b1a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fef0f6e951798dd2453aa387d8dcde9853968f3a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-3-creating-the-contoso-lob-application-maps-for-the-price-and-availability-project-using-biztalk-mapper"></a><span data-ttu-id="2d1e3-102">Paso 3: Crear las asignaciones de aplicación de LOB de Contoso para el precio y el proyecto de disponibilidad mediante el asignador de BizTalk</span><span class="sxs-lookup"><span data-stu-id="2d1e3-102">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>
<span data-ttu-id="2d1e3-103">En este paso, creará dos asignaciones que definen la transformación debe intercambiar correctamente los mensajes entre los dos socios comerciales.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-103">In this step, you create two maps that define the transformation required to successfully exchange messages between the two trading partners.</span></span> <span data-ttu-id="2d1e3-104">En este escenario, el sistema ERP de Contoso ya ha estandarizado en un formato de mensaje para una solicitud de precio y disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-104">For this scenario, the Contoso ERP system has already standardized on a message format for a Price and Availability request.</span></span> <span data-ttu-id="2d1e3-105">Los dos mapas asignarán los mensajes de solicitud y respuesta del socio comercial, Fabrikam, a y desde los mensajes de Contoso definidos internamente, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-105">The two maps will map the request and response messages from the trading partner, Fabrikam, to and from those internally defined Contoso messages, respectively.</span></span>  
  
### <a name="to-add-a-reference-for-the-3a2-priceandavailability-request-schema"></a><span data-ttu-id="2d1e3-106">Para agregar una referencia para el esquema de solicitud de PriceAndAvailability 3A2</span><span class="sxs-lookup"><span data-stu-id="2d1e3-106">To add a reference for the 3A2 PriceAndAvailability Request schema</span></span>  
  
1.  <span data-ttu-id="2d1e3-107">En el Explorador de soluciones, haga clic en el proyecto ContosoPriceAndAvailability y, a continuación, haga clic en **Agregar referencia**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-107">In Solution Explorer, right-click the ContosoPriceAndAvailability project, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="2d1e3-108">En el cuadro de diálogo Agregar referencia, haga clic en **Examinar**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-108">In the Add Reference dialog box, click **Browse**.</span></span>  
  
3.  <span data-ttu-id="2d1e3-109">Desplácese a la carpeta  *\<unidad\>*: \Program BizTalk \<versión\> Accelerator for RosettaNet\Bin y, a continuación, seleccione la  **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll** ensamblado.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-109">Move to the folder *\<drive\>*:\Program Files\Microsoft BizTalk \<version\> Accelerator for RosettaNet\Bin, and then select the **Microsoft.Solutions.BTARN.Schemas.RNPIPs.dll** assembly.</span></span>  
  
4.  <span data-ttu-id="2d1e3-110">Haga clic en **agregar**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-110">Click **Add**, and then click **OK**.</span></span>  
  
### <a name="to-create-the-3a2-priceandavailability-request-to-contoso-priceandavailability-request-map"></a><span data-ttu-id="2d1e3-111">Para crear la solicitud de PriceAndAvailability 3A2 al mapa de la solicitud de Contoso PriceAndAvailability</span><span class="sxs-lookup"><span data-stu-id="2d1e3-111">To create the 3A2 PriceAndAvailability request to Contoso PriceAndAvailability request map</span></span>  
  
1.  <span data-ttu-id="2d1e3-112">En el Explorador de soluciones, haga clic en el proyecto ContosoPriceAndAvailability, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-112">In Solution Explorer, right-click the ContosoPriceAndAvailability project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="2d1e3-113">En Agregar nuevo elemento - ContosoPriceAndAvailability cuadro de diálogo, seleccione **archivos de asignación** en el panel de categorías y, a continuación, seleccione **mapa** en el **plantillas** panel.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-113">In the Add New Item - ContosoPriceAndAvailability dialog box, select **Map Files** in the Categories pane, and then select **Map** in the **Templates** pane.</span></span> <span data-ttu-id="2d1e3-114">En el **nombre** , escriba **PIP3A2RequestToContosoPriceRequest**y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-114">In the **Name** box, type **PIP3A2RequestToContosoPriceRequest**, and then click **Add**.</span></span>  
  
### <a name="to-associate-the-schemas-for-the-pip3a2requesttocontosopricerequest-map"></a><span data-ttu-id="2d1e3-115">Para asociar los esquemas para la asignación de PIP3A2RequestToContosoPriceRequest</span><span class="sxs-lookup"><span data-stu-id="2d1e3-115">To associate the schemas for the PIP3A2RequestToContosoPriceRequest map</span></span>  
  
1.  <span data-ttu-id="2d1e3-116">En el asignador de BizTalk (con PIP3A2RequestToContosoPriceRequest.btm muestra), en el panel de esquema de origen, haga clic en **Abrir esquema de origen**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-116">In BizTalk Mapper (with PIP3A2RequestToContosoPriceRequest.btm displayed), in the Source Schema pane, click **Open Source Schema**.</span></span>  
  
2.  <span data-ttu-id="2d1e3-117">En el cuadro de diálogo Selector de tipos de BizTalk, expanda **ContosoPriceAndAvailability**, expanda **referencias**, expanda **Microsoft.Solutions.BTARN.Schemas.RNPIPs**y, a continuación, Expanda **esquemas.**</span><span class="sxs-lookup"><span data-stu-id="2d1e3-117">In the BizTalk Type Picker dialog box, expand **ContosoPriceAndAvailability**, expand **References**, expand **Microsoft.Solutions.BTARN.Schemas.RNPIPs**, and then expand **Schemas.**</span></span>  
  
3.  <span data-ttu-id="2d1e3-118">Seleccione **Microsoft.Solutions.BTARN.Schemas.RNPIPs.**</span><span class="sxs-lookup"><span data-stu-id="2d1e3-118">Select **Microsoft.Solutions.BTARN.Schemas.RNPIPs.**</span></span>  
  
     <span data-ttu-id="2d1e3-119">**_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-119">**_3A2PriceAndAvailabilityQueryMessageGuideline_v1_3**, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="2d1e3-120">En el panel de esquema de destino, haga clic en **Abrir esquema de destino**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-120">In the Destination Schema pane, click **Open Destination Schema**.</span></span>  
  
5.  <span data-ttu-id="2d1e3-121">En el cuadro de diálogo Selector de tipos de BizTalk, expanda **ContosoPriceAndAvailability**y, a continuación, expanda **esquemas**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-121">In the BizTalk Type Picker dialog box, expand **ContosoPriceAndAvailability**, and then expand **Schemas**.</span></span>  
  
6.  <span data-ttu-id="2d1e3-122">Seleccione el **ContosoPriceAndAvailability.ContosoPriceSchema** esquema y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-122">Select the **ContosoPriceAndAvailability.ContosoPriceSchema** schema, and then click **OK**.</span></span>  
  
7.  <span data-ttu-id="2d1e3-123">En el nodo raíz para esquema de destino, cuadro de diálogo, seleccione la **rootPriceRequest** esquema y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-123">In the Root Node for Target Schema dialog box, select the **rootPriceRequest** schema, and then click **OK**.</span></span>  
  
### <a name="to-link-schema-fields-in-the-pip3a2requesttocontosopricerequest-map"></a><span data-ttu-id="2d1e3-124">Para vincular los campos de esquema en el mapa de PIP3A2RequestToContosoPriceRequest</span><span class="sxs-lookup"><span data-stu-id="2d1e3-124">To link schema fields in the PIP3A2RequestToContosoPriceRequest map</span></span>  
  
1.  <span data-ttu-id="2d1e3-125">En el panel de esquema de destino, haga clic en el  **\<esquema\>**  nodo y, a continuación, haga clic en **Expandir nodo de árbol**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-125">In the Destination Schema pane, right-click the **\<Schema\>** node, and then click **Expand Tree Node**.</span></span>  
  
2.  <span data-ttu-id="2d1e3-126">En el panel de esquema de origen, haga clic en el  **\<esquema\>**  nodo y, a continuación, haga clic en **Expandir nodo de árbol**.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-126">In the Source Schema pane, right-click the **\<Schema\>** node, and then click **Expand Tree Node**.</span></span>  
  
3.  <span data-ttu-id="2d1e3-127">Arrastre el **GlobalProductIdentifier** campo a la **ProductID** campo en el panel de esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-127">Drag the **GlobalProductIdentifier** field to the **ProductID** field in the Destination Schema pane.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2d1e3-128">Puede encontrar el **GlobalProductIdentifier** campo en el nodo Pip3A2PriceAndAvailabilityQuery/ProductPriceAndAvailabilityQuery /</span><span class="sxs-lookup"><span data-stu-id="2d1e3-128">You can find the **GlobalProductIdentifier** field in the node Pip3A2PriceAndAvailabilityQuery/ProductPriceAndAvailabilityQuery/</span></span>  
    >   
    >  <span data-ttu-id="2d1e3-129">ProductPriceAndAvailability/ProductLineItem/productUnit /</span><span class="sxs-lookup"><span data-stu-id="2d1e3-129">ProductPriceAndAvailability/ProductLineItem/productUnit/</span></span>  
    >   
    >  <span data-ttu-id="2d1e3-130">ProductPackageDescription/ProductIdentification.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-130">ProductPackageDescription/ProductIdentification.</span></span>  
  
4.  <span data-ttu-id="2d1e3-131">En el **archivo** menú, haga clic en **guardar todo** para guardar los cambios.</span><span class="sxs-lookup"><span data-stu-id="2d1e3-131">On the **File** menu, click **Save All** to save your changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d1e3-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="2d1e3-132">See Also</span></span>  
 [<span data-ttu-id="2d1e3-133">Creación y configuración de puertos de BizTalk para Contoso</span><span class="sxs-lookup"><span data-stu-id="2d1e3-133">Creating and Configuring BizTalk Ports for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)