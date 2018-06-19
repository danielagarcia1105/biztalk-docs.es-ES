---
title: 'Tutorial 2: EDI Interface Developer Tutorial | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d10fb650-cbb9-41e5-a80d-06afd0513814
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cb84454d2570ae6833847b598b55af6cf7777e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286948"
---
# <a name="tutorial-2-edi-interface-developer-tutorial"></a><span data-ttu-id="714ff-102">Tutorial 2: Tutorial de desarrollador de la interfaz EDI</span><span class="sxs-lookup"><span data-stu-id="714ff-102">Tutorial 2: EDI Interface Developer Tutorial</span></span>
<span data-ttu-id="714ff-103">Este tutorial muestra cómo usar la funcionalidad EDI en un escenario de desarrolladores de interfaz de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="714ff-103">This tutorial demonstrates how to use the EDI functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in an Interface Developer scenario.</span></span>  
  
 <span data-ttu-id="714ff-104">**Escenario del tutorial**</span><span class="sxs-lookup"><span data-stu-id="714ff-104">**Tutorial Scenario**</span></span>  
  
 <span data-ttu-id="714ff-105">En este escenario, su socio comercial envía pedidos de compra a su compañía mediante el conjunto de transacciones 850 de ANSI X12 versión 4010 (un mensaje 850).</span><span class="sxs-lookup"><span data-stu-id="714ff-105">In this scenario, your trading partner sends Purchase Orders to your company using the ANSI X12 Version 4010 850 Transaction Set (an 850 message).</span></span> <span data-ttu-id="714ff-106">Su compañía utiliza una aplicación interna, el sistema de pedidos, para procesar los pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="714ff-106">Your company uses an internal application, the Order System, to process purchase orders.</span></span>  
  
 <span data-ttu-id="714ff-107">Usted es el programador responsable del diseño de la interfaz entre el mensaje 850 que recibe de su socio comercial y el sistema de pedidos interno de la compañía.</span><span class="sxs-lookup"><span data-stu-id="714ff-107">You are an interface developer responsible for designing the interface between the 850 message you receive from your trading partner and your company’s internal Order System.</span></span> <span data-ttu-id="714ff-108">Su socio comercial requiere una confirmación funcional (997) para cada mensaje 850 que envía.</span><span class="sxs-lookup"><span data-stu-id="714ff-108">Your trading partner requires a Functional Acknowledgement (997) for each 850 message it sends.</span></span>  
  
 <span data-ttu-id="714ff-109">Para facilitar la referencia, se utilizan los siguientes identificadores:</span><span class="sxs-lookup"><span data-stu-id="714ff-109">For ease of reference, the following identifiers are used:</span></span>  
  
|<span data-ttu-id="714ff-110">Entidad</span><span class="sxs-lookup"><span data-stu-id="714ff-110">Entity</span></span>|<span data-ttu-id="714ff-111">Identificador</span><span class="sxs-lookup"><span data-stu-id="714ff-111">Identifier</span></span>|  
|------------|----------------|  
|<span data-ttu-id="714ff-112">Su compañía</span><span class="sxs-lookup"><span data-stu-id="714ff-112">Your company</span></span>|<span data-ttu-id="714ff-113">El sistema de pedidos</span><span class="sxs-lookup"><span data-stu-id="714ff-113">OrderSystem</span></span>|  
|<span data-ttu-id="714ff-114">Su socio comercial</span><span class="sxs-lookup"><span data-stu-id="714ff-114">Your trading partner</span></span>|<span data-ttu-id="714ff-115">Fabrikam</span><span class="sxs-lookup"><span data-stu-id="714ff-115">Fabrikam</span></span>|  
  
 <span data-ttu-id="714ff-116">El flujo de mensajes en la solución completa será como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="714ff-116">The message flow in the completed solution will be as follows:</span></span>  
  
 <span data-ttu-id="714ff-117">![Flujo de mensajes EDI Interface Developer Tutorial](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")</span><span class="sxs-lookup"><span data-stu-id="714ff-117">![EDI Interface Developer Tutorial message flow](../core/media/4944352a-dc77-47f1-a324-bf71444670c5.gif "4944352a-dc77-47f1-a324-bf71444670c5")</span></span>  
  
 <span data-ttu-id="714ff-118">**Flujo de mensajes**</span><span class="sxs-lookup"><span data-stu-id="714ff-118">**Message Flow**</span></span>  
  
 <span data-ttu-id="714ff-119">La solución de este tutorial hará lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="714ff-119">The solution in this tutorial will do the following:</span></span>  
  
1.  <span data-ttu-id="714ff-120">Recibir un intercambio de archivos sin formato del socio comercial Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="714ff-120">Receive a flat-file interchange from the trading partner Fabrikam.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="714ff-121">Puede que los eventos de esta lista no se produzcan en el orden mostrado.</span><span class="sxs-lookup"><span data-stu-id="714ff-121">The events in this list may not occur in the order shown.</span></span>  
  
2.  <span data-ttu-id="714ff-122">Validar el intercambio EDI con su esquema, desensamblar el mensaje a XML y depositar el mensaje XML en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="714ff-122">Validate the EDI interchange against its schema, disassemble the message into XML, and drop the message XML into the MessageBox.</span></span>  
  
3.  <span data-ttu-id="714ff-123">Generar una confirmación 997 al intercambio EDI recibido y depositarla en el cuadro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="714ff-123">Generate a 997 acknowledgment to the received EDI interchange, and drop it in the MessageBox.</span></span>  
  
4.  <span data-ttu-id="714ff-124">Recoger el XML de 997 mediante un puerto de envío unidireccional y ensamblar el intercambio EDI 997.</span><span class="sxs-lookup"><span data-stu-id="714ff-124">Pick up the 997 XML by a one-way send port, and assemble the 997 EDI interchange.</span></span>  
  
5.  <span data-ttu-id="714ff-125">Enviar un intercambio 997 a Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="714ff-125">Send the 997 interchange to Fabrikam.</span></span>  
  
6.  <span data-ttu-id="714ff-126">Recoger el XML del mensaje mediante un puerto de envío unidireccional y ensamblar el intercambio EDI del mensaje.</span><span class="sxs-lookup"><span data-stu-id="714ff-126">Pick up the Msg XML by a one-way send port, and assemble the message EDI interchange.</span></span>  
  
7.  <span data-ttu-id="714ff-127">Enviar un intercambio EDI a OrderSystem.</span><span class="sxs-lookup"><span data-stu-id="714ff-127">Send the EDI interchange to OrderSystem.</span></span>  
  
 <span data-ttu-id="714ff-128">**Configuración**</span><span class="sxs-lookup"><span data-stu-id="714ff-128">**Configuration**</span></span>  
  
 <span data-ttu-id="714ff-129">En este tutorial, llevará a cabo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="714ff-129">In this tutorial, you will do the following:</span></span>  
  
-   <span data-ttu-id="714ff-130">Configurar BizTalk para recibir un mensaje 850 de su socio comercial y devolver una confirmación 997.t</span><span class="sxs-lookup"><span data-stu-id="714ff-130">Configure BizTalk to expect the 850 message from your trading partner and to send back a 997 acknowledgment</span></span>  
  
-   <span data-ttu-id="714ff-131">Utilizar una asignación de BizTalk para convertir el mensaje 850 al formato necesario según el sistema de pedidos.</span><span class="sxs-lookup"><span data-stu-id="714ff-131">Use a BizTalk map to convert the 850 message data into the format required by the Order System.</span></span> <span data-ttu-id="714ff-132">Este mapa se proporciona en los archivos del tutorial en el SDK de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="714ff-132">This map is provided in the tutorial files in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] SDK.</span></span>  
  
-   <span data-ttu-id="714ff-133">Configurar un puerto de recepción para recibir el mensaje 850.</span><span class="sxs-lookup"><span data-stu-id="714ff-133">Configure a receive port for receiving the 850 message.</span></span>  
  
-   <span data-ttu-id="714ff-134">Configurar un puerto de envío para enviar el mensaje 850 a OrderSystem en el formato correcto.</span><span class="sxs-lookup"><span data-stu-id="714ff-134">Configure a send port to send the 850 message to OrderSystem in the correct format.</span></span>  
  
-   <span data-ttu-id="714ff-135">Configurar un puerto de envío para que se suscriba a la confirmación 997 generada por BizTalk y la devuelva al socio comercial, Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="714ff-135">Configure a send port to subscribe to the BizTalk-generated 997 acknowledgment for routing back to the trading partner, Fabrikam.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="714ff-136">En esta sección</span><span class="sxs-lookup"><span data-stu-id="714ff-136">In This Section</span></span>  
  
-   [<span data-ttu-id="714ff-137">Paso 1: Preparar el Tutorial de programadores de la interfaz EDI</span><span class="sxs-lookup"><span data-stu-id="714ff-137">Step 1: Prepare for the EDI Interface Developer Tutorial</span></span>](../core/step-1-prepare-for-the-edi-interface-developer-tutorial.md)  
  
-   [<span data-ttu-id="714ff-138">Paso 2: Actualizar e implementar la solución del Tutorial</span><span class="sxs-lookup"><span data-stu-id="714ff-138">Step 2: Update and Deploy the Tutorial Solution</span></span>](../core/step-2-update-and-deploy-the-tutorial-solution.md)  
  
-   [<span data-ttu-id="714ff-139">Paso 3: Configurar una entidad y perfil de negocio para su organización</span><span class="sxs-lookup"><span data-stu-id="714ff-139">Step 3: Configure a Party and Business Profile for Your Organization</span></span>](../core/step-3-configure-a-party-and-business-profile-for-your-organization1.md)  
  
-   [<span data-ttu-id="714ff-140">Paso 4: Configurar una entidad y perfil de negocio para el socio comercial</span><span class="sxs-lookup"><span data-stu-id="714ff-140">Step 4: Configure a Party and Business Profile for Your Trading Partner</span></span>](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)  
  
-   [<span data-ttu-id="714ff-141">Paso 5: Configurar un puerto de recepción y ubicación de recepción</span><span class="sxs-lookup"><span data-stu-id="714ff-141">Step 5: Configure a Receive Port and Receive Location</span></span>](../core/step-5-configure-a-receive-port-and-receive-location.md)  
  
-   [<span data-ttu-id="714ff-142">Paso 6: Configurar un puerto de envío para enviar datos a su organización</span><span class="sxs-lookup"><span data-stu-id="714ff-142">Step 6: Configure a Send Port to Send Data to Your Organization</span></span>](../core/step-6-configure-a-send-port-to-send-data-to-your-organization.md)  
  
-   [<span data-ttu-id="714ff-143">Paso 7: Configurar un puerto de envío para enviar la confirmación al socio comercial</span><span class="sxs-lookup"><span data-stu-id="714ff-143">Step 7: Configure a Send Port to Send the Acknowledgment to Your Trading Partner</span></span>](../core/step-7-configure-a-send-port-to-send-the-acknowledgment-to-trading-partner.md)  
  
-   [<span data-ttu-id="714ff-144">Paso 8: Configurar el acuerdo de socio comercial entre las partes</span><span class="sxs-lookup"><span data-stu-id="714ff-144">Step 8: Configure the Trading Partner Agreement between the Parties</span></span>](../core/step-8-configure-the-trading-partner-agreement-between-the-parties.md)  
  
-   [<span data-ttu-id="714ff-145">Paso 9: Probar la solución EDI</span><span class="sxs-lookup"><span data-stu-id="714ff-145">Step 9: Test the EDI Solution</span></span>](../core/step-9-test-the-edi-solution.md)  
  
## <a name="see-also"></a><span data-ttu-id="714ff-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="714ff-146">See Also</span></span>  
 [<span data-ttu-id="714ff-147">Tutoriales de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="714ff-147">BizTalk Server Tutorials</span></span>](../core/biztalk-server-tutorials.md)