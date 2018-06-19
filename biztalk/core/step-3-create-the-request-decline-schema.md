---
title: 'Paso 3: Crear el esquema de declinación de solicitud | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1ce166c-1be1-4ef4-9d00-3da7038d4ada
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ff343c58e836bc0738f0200016308eb7a4d90b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278556"
---
# <a name="step-3-create-the-request-decline-schema"></a><span data-ttu-id="fb6ba-102">Paso 3: Crear el esquema de declinación de la solicitud</span><span class="sxs-lookup"><span data-stu-id="fb6ba-102">Step 3: Create the Request Decline Schema</span></span>
<span data-ttu-id="fb6ba-103">![Paso 3 de 5](../core/media/step-3of5.gif "Step_3of5")</span><span class="sxs-lookup"><span data-stu-id="fb6ba-103">![Step 3 of 5](../core/media/step-3of5.gif "Step_3of5")</span></span>  
  
 <span data-ttu-id="fb6ba-104">**Tiempo en completarse:** 7 minutos</span><span class="sxs-lookup"><span data-stu-id="fb6ba-104">**Time to complete:** 7 minutes</span></span>  
  
 <span data-ttu-id="fb6ba-105">**Objetivo:** en este paso, se creará el esquema para el mensaje [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] devuelve al almacén si el proceso empresarial rechaza la solicitud de reposición de inventario.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-105">**Objective:** In this step, you create the schema for the message [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends back to the warehouse if the business process rejects the inventory replenishment request.</span></span>  
  
 <span data-ttu-id="fb6ba-106">**Propósito:** el esquema define los datos y la estructura del mensaje de rechazo de solicitud.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-106">**Purpose:** The schema defines the data and the structure of the request decline message.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="fb6ba-107">utiliza el esquema para identificar e interactuar con los datos en el mensaje.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-107"> uses the schema to identify and interact with the data in the message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fb6ba-108">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="fb6ba-108">Prerequisites</span></span>  
 <span data-ttu-id="fb6ba-109">Tenga en cuenta los siguientes requisitos antes de iniciar este paso:</span><span class="sxs-lookup"><span data-stu-id="fb6ba-109">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="fb6ba-110">Antes de comenzar este paso debe completar [paso 1: crear el proyecto de EAISchemas](../core/step-1-create-eaischemas-project.md).</span><span class="sxs-lookup"><span data-stu-id="fb6ba-110">Before you begin this step you must complete [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="fb6ba-111">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="fb6ba-111">Procedures</span></span>  
  
#### <a name="to-create-the-request-decline-schema"></a><span data-ttu-id="fb6ba-112">Para crear el esquema de declinación de la solicitud</span><span class="sxs-lookup"><span data-stu-id="fb6ba-112">To create the Request Decline schema</span></span>  
  
1.  <span data-ttu-id="fb6ba-113">En el Explorador de soluciones, haga clic en el **EAISchemas** , seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-113">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="fb6ba-114">En el **Agregar nuevo elemento - EAISchemas** diálogo cuadro, realice lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="fb6ba-114">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="fb6ba-115">Use</span><span class="sxs-lookup"><span data-stu-id="fb6ba-115">Use this</span></span>|<span data-ttu-id="fb6ba-116">Para</span><span class="sxs-lookup"><span data-stu-id="fb6ba-116">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="fb6ba-117">**Plantillas instaladas**</span><span class="sxs-lookup"><span data-stu-id="fb6ba-117">**Installed Templates**</span></span>|<span data-ttu-id="fb6ba-118">Haga clic en **archivos de esquema**y, a continuación, haga clic en **esquema**.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-118">Click **Schema Files**, and then click **Schema**.</span></span>|  
    |<span data-ttu-id="fb6ba-119">**Nombre**</span><span class="sxs-lookup"><span data-stu-id="fb6ba-119">**Name**</span></span>|<span data-ttu-id="fb6ba-120">Type `RequestDecline.xsd`.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-120">Type `RequestDecline.xsd`.</span></span>|  
  
3.  <span data-ttu-id="fb6ba-121">Haga clic en **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-121">Click **Add**.</span></span>  
  
4.  <span data-ttu-id="fb6ba-122">En el Editor de BizTalk, en el árbol de esquema, haga clic en el **raíz** nodo para seleccionarlo.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-122">In BizTalk Editor, from schema tree, click the **Root** node to select it.</span></span>  
  
5.  <span data-ttu-id="fb6ba-123">En el panel Propiedades, cambie el valor de la **nombre de nodo** propiedad `DeclineReq`, y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-123">In the Properties pane, change the value of the **Node Name** property to `DeclineReq`, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="fb6ba-124">En el árbol de esquema, haga clic en el **DeclineReq** nodo, seleccione **Insertar nodo de esquema**y, a continuación, haga clic en **elemento de campo secundario**.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-124">In schema tree, right-click the **DeclineReq** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  
  
7.  <span data-ttu-id="fb6ba-125">Tipo `ReqID` como el nuevo nombre para el elemento y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-125">Type `ReqID` as the new name for the element, and then press ENTER.</span></span>  
  
8.  <span data-ttu-id="fb6ba-126">Agregar un elemento de campo secundario denominado `GrandTotal`.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-126">Add a second child field element named `GrandTotal`.</span></span>  
  
9. <span data-ttu-id="fb6ba-127">En el menú **Archivo** , haga clic en **Guardar todo**.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-127">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="fb6ba-128">Síntesis</span><span class="sxs-lookup"><span data-stu-id="fb6ba-128">What did I just do?</span></span>  
 <span data-ttu-id="fb6ba-129">En este paso, ha creado el esquema del mensaje que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] devuelve al almacén si el proceso empresarial rechaza la solicitud de inventario.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-129">In this step, you created the schema for the message that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends back to the warehouse if the business process rejects the inventory request.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="fb6ba-130">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="fb6ba-130">Next Steps</span></span>  
 <span data-ttu-id="fb6ba-131">Creará la asignación que la orquestación necesita para crear el mensaje de declinación de la solicitud cambiando el formato del mensaje de solicitud.</span><span class="sxs-lookup"><span data-stu-id="fb6ba-131">You create the map needed by the orchestration to create request decline message by reformatting request message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb6ba-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb6ba-132">See Also</span></span>  
 [<span data-ttu-id="fb6ba-133">Paso 1: Crear el proyecto EAISchemas</span><span class="sxs-lookup"><span data-stu-id="fb6ba-133">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
 <span data-ttu-id="fb6ba-134">[Paso 2: Crear el esquema de solicitud de inventario](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="fb6ba-134">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="fb6ba-135">[Paso 4: Crear el mapa](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="fb6ba-135">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="fb6ba-136">[Paso 5: Generar el proyecto EAISchemas](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="fb6ba-136">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 [<span data-ttu-id="fb6ba-137">Crear esquemas con el Editor de BizTalk</span><span class="sxs-lookup"><span data-stu-id="fb6ba-137">Creating Schemas Using BizTalk Editor</span></span>](../core/creating-schemas-using-biztalk-editor.md)