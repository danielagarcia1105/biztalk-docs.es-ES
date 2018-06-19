---
title: 'Paso 6 (de forma local): Crear una transformación para asignar el mensaje de la cola en el esquema de inserción | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 30a55f1e-32cc-409a-a814-084026f51b35
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 02b2be9659714beb4b9a52f4c2a9dd1e5b3ea47f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22276596"
---
# <a name="step-6-on-premises-create-a-transform-to-map-the-message-from-the-queue-to-the-insert-schema"></a><span data-ttu-id="8efef-102">Paso 6 (de forma local): Crear una transformación para asignar el mensaje de la cola en el esquema de inserción</span><span class="sxs-lookup"><span data-stu-id="8efef-102">Step 6 (On Premises): Create a Transform to Map the Message from the Queue to the Insert Schema</span></span>
<span data-ttu-id="8efef-103">El mensaje que se recibe por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] desde la cola de Bus de servicio será de la **ECommerceSalesOrder.xsd** esquema.</span><span class="sxs-lookup"><span data-stu-id="8efef-103">The message that is received by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] from the Service Bus Queue will be of the **ECommerceSalesOrder.xsd** schema.</span></span> <span data-ttu-id="8efef-104">Sin embargo, para insertar un mensaje en el **SalesOrder** tabla, el mensaje debe ser de **insertar** esquema que generó en [(local) del paso 5: generar el esquema para insertar un mensaje en la Tabla SalesOrder](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md).</span><span class="sxs-lookup"><span data-stu-id="8efef-104">However, to insert a message into the **SalesOrder** table, the message must be of **Insert** schema that you generated in [Step 5 (On Premises): Generate the Schema for Inserting a Message inito SalesOrder Table](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md).</span></span> <span data-ttu-id="8efef-105">Por lo tanto, en este tema, se creará una asignación para transformar la **ECommerceSalesOrder.xsd** esquema en el esquema de la operación de inserción.</span><span class="sxs-lookup"><span data-stu-id="8efef-105">So, in this topic, we create a map to transform the **ECommerceSalesOrder.xsd** schema into the Insert operation schema.</span></span>  
  
### <a name="to-create-a-map"></a><span data-ttu-id="8efef-106">Para crear un mapa</span><span class="sxs-lookup"><span data-stu-id="8efef-106">To create a map</span></span>  
  
1.  <span data-ttu-id="8efef-107">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ya ha creado, haga clic en el proyecto y seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.</span><span class="sxs-lookup"><span data-stu-id="8efef-107">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you already created, right-click the project, point to **Add**, and then click **New Item**.</span></span> <span data-ttu-id="8efef-108">En el **nuevo elemento** cuadro de diálogo, seleccione **mapa**, escriba el nombre de asignación `SalesOrder_SQL.btm`y, a continuación, haga clic en **agregar**.</span><span class="sxs-lookup"><span data-stu-id="8efef-108">In the **New Item** dialog box, select **Map**, enter the map name as `SalesOrder_SQL.btm`, and then click **Add**.</span></span>  
  
2.  <span data-ttu-id="8efef-109">En el mapa, para el esquema de origen, seleccione **ECommerceSalesOrder.xsd**.</span><span class="sxs-lookup"><span data-stu-id="8efef-109">In the map, for the source schema, select **ECommerceSalesOrder.xsd**.</span></span> <span data-ttu-id="8efef-110">Para el esquema de destino, seleccione **TableOperations.SalesOrder.xsd (Insert)** esquema.</span><span class="sxs-lookup"><span data-stu-id="8efef-110">For the destination schema, select **TableOperations.SalesOrder.xsd (Insert)** schema.</span></span>  
  
3.  <span data-ttu-id="8efef-111">Asigne directamente los siguientes nodos en los esquemas de origen y de destino:</span><span class="sxs-lookup"><span data-stu-id="8efef-111">Directly map the following nodes in the source and destination schemas:</span></span>  
  
    |<span data-ttu-id="8efef-112">Esquema de origen</span><span class="sxs-lookup"><span data-stu-id="8efef-112">Source Schema</span></span>|<span data-ttu-id="8efef-113">Esquema de destino</span><span class="sxs-lookup"><span data-stu-id="8efef-113">Destination Schema</span></span>|  
    |-------------------|------------------------|  
    |<span data-ttu-id="8efef-114">CompanyCode</span><span class="sxs-lookup"><span data-stu-id="8efef-114">CompanyCode</span></span>|<span data-ttu-id="8efef-115">CompanyCode</span><span class="sxs-lookup"><span data-stu-id="8efef-115">CompanyCode</span></span>|  
    |<span data-ttu-id="8efef-116">PartId</span><span class="sxs-lookup"><span data-stu-id="8efef-116">PartId</span></span>|<span data-ttu-id="8efef-117">PartNum</span><span class="sxs-lookup"><span data-stu-id="8efef-117">PartNum</span></span>|  
    |<span data-ttu-id="8efef-118">Cantidad</span><span class="sxs-lookup"><span data-stu-id="8efef-118">Quantity</span></span>|<span data-ttu-id="8efef-119">Qty</span><span class="sxs-lookup"><span data-stu-id="8efef-119">Qty</span></span>|  
    |<span data-ttu-id="8efef-120">AskPrice</span><span class="sxs-lookup"><span data-stu-id="8efef-120">AskPrice</span></span>|<span data-ttu-id="8efef-121">UnitAskPrice</span><span class="sxs-lookup"><span data-stu-id="8efef-121">UnitAskPrice</span></span>|  
    |<span data-ttu-id="8efef-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8efef-122">Comments</span></span>|<span data-ttu-id="8efef-123">CustomerComments</span><span class="sxs-lookup"><span data-stu-id="8efef-123">CustomerComments</span></span>|  
  
4.  <span data-ttu-id="8efef-124">Use la **fecha y hora** functoid para asignar valores a la **DateRequested** y **ShipDate** elementos del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8efef-124">Use the **Date and Time** functoid to map values to the **DateRequested** and **ShipDate** elements in the destination schema.</span></span> <span data-ttu-id="8efef-125">Estos nodos no se asignan a los nodos correspondientes en el esquema de origen.</span><span class="sxs-lookup"><span data-stu-id="8efef-125">These nodes are not mapped to the respective nodes in the source schema.</span></span> <span data-ttu-id="8efef-126">En su lugar, la fecha y hora actuales se pasan a estos nodos mediante la **fecha y hora** functoid.</span><span class="sxs-lookup"><span data-stu-id="8efef-126">Instead, the current date and time is passed on to these nodes by using the **Date and Time** functoid.</span></span>  
  
    1.  <span data-ttu-id="8efef-127">Arrastre y coloque una **fecha y hora** functoid del cuadro de herramientas a la superficie del asignador.</span><span class="sxs-lookup"><span data-stu-id="8efef-127">Drag and drop a **Date and Time** functoid from toolbox to the mapper surface.</span></span>  
  
    2.  <span data-ttu-id="8efef-128">Conecte el functoid a la **DateRequested** elemento del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8efef-128">Connect the functoid to the **DateRequested** element in the destination schema.</span></span>  
  
    3.  <span data-ttu-id="8efef-129">Arrastre y coloque otra **fecha y hora** functoid y conectarlo a la **ShipDate** elemento del esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8efef-129">Drag and drop another **Date and Time** functoid and connect it to the **ShipDate** element in the destination schema.</span></span>  
  
5.  <span data-ttu-id="8efef-130">Asigne los siguientes nodos en los esquemas de origen y destino con un **concatenación de cadenas** functoid:</span><span class="sxs-lookup"><span data-stu-id="8efef-130">Map the following nodes in the source and destination schemas using a **String Concatenate** functoid:</span></span>  
  
    |<span data-ttu-id="8efef-131">Esquema de origen</span><span class="sxs-lookup"><span data-stu-id="8efef-131">Source Schema</span></span>|<span data-ttu-id="8efef-132">Esquema de destino</span><span class="sxs-lookup"><span data-stu-id="8efef-132">Destination Schema</span></span>|  
    |-------------------|------------------------|  
    |<span data-ttu-id="8efef-133">Address\Line1</span><span class="sxs-lookup"><span data-stu-id="8efef-133">Address\Line1</span></span>|<span data-ttu-id="8efef-134">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-134">SellToAddress</span></span><br /><br /> <span data-ttu-id="8efef-135">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-135">BillToAddress</span></span>|  
    |<span data-ttu-id="8efef-136">Address\Line2</span><span class="sxs-lookup"><span data-stu-id="8efef-136">Address\Line2</span></span>|<span data-ttu-id="8efef-137">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-137">SellToAddress</span></span><br /><br /> <span data-ttu-id="8efef-138">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-138">BillToAddress</span></span>|  
    |<span data-ttu-id="8efef-139">Address\City</span><span class="sxs-lookup"><span data-stu-id="8efef-139">Address\City</span></span>|<span data-ttu-id="8efef-140">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-140">SellToAddress</span></span><br /><br /> <span data-ttu-id="8efef-141">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-141">BillToAddress</span></span>|  
    |<span data-ttu-id="8efef-142">Address\State</span><span class="sxs-lookup"><span data-stu-id="8efef-142">Address\State</span></span>|<span data-ttu-id="8efef-143">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-143">SellToAddress</span></span><br /><br /> <span data-ttu-id="8efef-144">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-144">BillToAddress</span></span>|  
    |<span data-ttu-id="8efef-145">Address\Country</span><span class="sxs-lookup"><span data-stu-id="8efef-145">Address\Country</span></span>|<span data-ttu-id="8efef-146">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-146">SellToAddress</span></span><br /><br /> <span data-ttu-id="8efef-147">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-147">BillToAddress</span></span>|  
    |<span data-ttu-id="8efef-148">Address\ZipCode</span><span class="sxs-lookup"><span data-stu-id="8efef-148">Address\ZipCode</span></span>|<span data-ttu-id="8efef-149">SellToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-149">SellToAddress</span></span><br /><br /> <span data-ttu-id="8efef-150">BillToAddress</span><span class="sxs-lookup"><span data-stu-id="8efef-150">BillToAddress</span></span>|  
    |<span data-ttu-id="8efef-151">Contact\FirstName</span><span class="sxs-lookup"><span data-stu-id="8efef-151">Contact\FirstName</span></span>|<span data-ttu-id="8efef-152">PartnerContact</span><span class="sxs-lookup"><span data-stu-id="8efef-152">PartnerContact</span></span>|  
    |<span data-ttu-id="8efef-153">Contact\LastName</span><span class="sxs-lookup"><span data-stu-id="8efef-153">Contact\LastName</span></span>||  
  
     <span data-ttu-id="8efef-154">Realice los siguientes pasos para cada uno de los conjuntos de asignación de concatenación de cadenas:</span><span class="sxs-lookup"><span data-stu-id="8efef-154">Perform the following steps for each of the string concatenation mapping sets:</span></span>  
  
    1.  <span data-ttu-id="8efef-155">Arrastre y coloque una **concatenación de cadenas** functoid del cuadro de herramientas a la superficie del asignador.</span><span class="sxs-lookup"><span data-stu-id="8efef-155">Drag and drop a **String Concatenate** functoid from toolbox to the mapper surface.</span></span>  
  
    2.  <span data-ttu-id="8efef-156">Agregue cada elemento del árbol de origen como entrada para la **concatenación de cadenas** functoid.</span><span class="sxs-lookup"><span data-stu-id="8efef-156">Add each element from the source tree as an input to the **String Concatenate** functoid.</span></span>  
  
    3.  <span data-ttu-id="8efef-157">Arrastre y configurar la salida de la **concatenación de cadenas** functoid al elemento en el esquema de destino.</span><span class="sxs-lookup"><span data-stu-id="8efef-157">Drag and configure the output of the **String Concatenate** functoid to the element in the destination schema.</span></span>  
  
         <span data-ttu-id="8efef-158">El mapa completado queda de una forma similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="8efef-158">The completed map resembles the following:</span></span>  
  
         <span data-ttu-id="8efef-159">![Asignación para transformar esquemas](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")</span><span class="sxs-lookup"><span data-stu-id="8efef-159">![Map to transform schemas](../core/media/bts2010r2-tut1-map.jpg "BTS2010R2_Tut1_Map")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8efef-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="8efef-160">See Also</span></span>  
 [<span data-ttu-id="8efef-161">Tutorial 4: Crear una aplicación híbrida mediante BizTalk Server 2013</span><span class="sxs-lookup"><span data-stu-id="8efef-161">Tutorial 4: Creating a Hybrid Application Using BizTalk Server 2013</span></span>](../core/tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013.md)