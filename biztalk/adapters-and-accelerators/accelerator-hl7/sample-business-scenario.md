---
title: Escenario empresarial de ejemplo | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTAHL7, business example
- examples, business processes
- health care organizations, business example
- business processes, example
ms.assetid: 54bfbe45-4638-4488-bbd8-c642926a35d3
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78229d903461fe2b84033b036ef02b2838832fc0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
ms.locfileid: "26004805"
---
# <a name="sample-business-scenario"></a><span data-ttu-id="1fcd2-102">Escenario empresarial de ejemplo</span><span class="sxs-lookup"><span data-stu-id="1fcd2-102">Sample Business Scenario</span></span>
<span data-ttu-id="1fcd2-103">Procesos de atención sanitaria a menudo son complejos e implican muchos sistemas.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-103">Health care processes are often complex and involve many systems.</span></span> <span data-ttu-id="1fcd2-104">Un ejemplo es el proceso que se produce cuando un paciente introduce un hospital y un médico envía al paciente para una prueba de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-104">An example is the process that occurs when a patient enters a hospital, and a physician sends the patient for a lab test.</span></span> <span data-ttu-id="1fcd2-105">Implicadas en este procedimiento son cinco partes:</span><span class="sxs-lookup"><span data-stu-id="1fcd2-105">Involved in this procedure are five parties:</span></span>  
  
-   <span data-ttu-id="1fcd2-106">El médico que le</span><span class="sxs-lookup"><span data-stu-id="1fcd2-106">The attending physician</span></span>  
  
-   <span data-ttu-id="1fcd2-107">El sistema de registro de Hospital</span><span class="sxs-lookup"><span data-stu-id="1fcd2-107">The Hospital Registration System</span></span>  
  
-   <span data-ttu-id="1fcd2-108">El sistema de entrada de pedidos clínicos</span><span class="sxs-lookup"><span data-stu-id="1fcd2-108">The Clinical Order Entry System</span></span>  
  
-   <span data-ttu-id="1fcd2-109">El sistema de laboratorio</span><span class="sxs-lookup"><span data-stu-id="1fcd2-109">The Laboratory System</span></span>  
  
-   <span data-ttu-id="1fcd2-110">El sistema de facturación</span><span class="sxs-lookup"><span data-stu-id="1fcd2-110">The Billing System</span></span>  
  
 <span data-ttu-id="1fcd2-111">En este proceso, pueden producirse los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="1fcd2-111">The following steps might occur in this process:</span></span>  
  
1.  <span data-ttu-id="1fcd2-112">El médico impedimento registra al paciente.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-112">The attending doctor registers the patient.</span></span>  
  
    1.  <span data-ttu-id="1fcd2-113">Un ADT ^ O04 mensaje de registro se difunde por el sistema de registro de Hospital.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-113">An ADT^O04 registration message is broadcast by the Hospital Registration System.</span></span>  
  
    2.  <span data-ttu-id="1fcd2-114">El ADT ^ O04 recibirlo por todos los departamentos que se suscriben al mensaje, incluido el sistema de entrada de pedido clínicos y el sistema de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-114">The ADT^O04 message is received by all departments that subscribe to the message, including the Clinical Order Entry System and the Laboratory System.</span></span>  
  
2.  <span data-ttu-id="1fcd2-115">El médico ordena un estudio de diagnóstico de la instalación de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-115">The doctor orders a diagnostic study from the laboratory facility.</span></span>  
  
    1.  <span data-ttu-id="1fcd2-116">Un ORM ^ O01 mensaje del pedido se envía desde el sistema de entrada de pedidos clínicos, después de la validación de reglas de negocios.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-116">An ORM^O01 order message is sent from the Clinical Order Entry System, after validation of business rules.</span></span>  
  
    2.  <span data-ttu-id="1fcd2-117">La ORM ^ O01 recibirlo por el sistema de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-117">The ORM^O01 message is received by the Laboratory System.</span></span>  
  
3.  <span data-ttu-id="1fcd2-118">El laboratorio recibe el pedido y devuelve una confirmación.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-118">The laboratory receives the order, and returns a confirmation.</span></span>  
  
    1.  <span data-ttu-id="1fcd2-119">Un ORR ^ O02 mensaje de confirmación del pedido es enviado por el sistema de laboratorio, que indica que se puede ejecutar el orden.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-119">An ORR^O02 order-confirmation message is sent by the Laboratory System, indicating that the order can be executed.</span></span>  
  
    2.  <span data-ttu-id="1fcd2-120">El ORR ^ O02 recibirlo por el sistema de entrada de pedidos clínicos.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-120">The ORR^O02 message is received by the Clinical Order Entry System.</span></span>  
  
4.  <span data-ttu-id="1fcd2-121">En la realización de las pruebas, el laboratorio envía los resultados al médico y otros departamentos.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-121">On completion of the tests, the laboratory sends the results to the doctor and other departments.</span></span>  
  
    1.  <span data-ttu-id="1fcd2-122">Un ORU ^ R01 mensaje de resultados de pruebas se envía desde el sistema de laboratorio.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-122">An ORU^R01 test-results message is sent from the Laboratory System.</span></span>  
  
    2.  <span data-ttu-id="1fcd2-123">El ORU ^ R01 recibirlo por el sistema de entrada de pedidos clínicos y el sistema de facturación.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-123">The ORU^R01 message is received by the Clinical Order Entry System and the Billing System.</span></span>  
  
    3.  <span data-ttu-id="1fcd2-124">El motor de interfaz se envía un mensaje de correo electrónico al médico, que recibe los resultados de laboratorio en su PDA inalámbrico.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-124">The Interface Engine sends out an e-mail message to the doctor, who receives the lab results on his wireless PDA.</span></span>  
  
## <a name="the-btahl7-solution"></a><span data-ttu-id="1fcd2-125">La solución BTAHL7</span><span class="sxs-lookup"><span data-stu-id="1fcd2-125">The BTAHL7 Solution</span></span>  
 <span data-ttu-id="1fcd2-126">El escenario empresarial de ejemplo que se ha descrito anteriormente es un ejemplo de un sistema de atención médica que necesita la integración.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-126">The sample business scenario outlined above is an example of a health care system that needs integration.</span></span> [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="1fcd2-127">BizTalk Server con [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) proporciona una solución para este escenario que ofrece la funcionalidad siguiente:</span><span class="sxs-lookup"><span data-stu-id="1fcd2-127">BizTalk Server with [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) provides a solution for this scenario that features the following functionality:</span></span>  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="1fcd2-128">se integra todos los sistemas implicados en una organización de concentrador y radio.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-128"> integrates all of the systems involved in a hub-and-spoke arrangement.</span></span> <span data-ttu-id="1fcd2-129">Cada sistema se comunica directamente con [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="1fcd2-129">Each system communicates directly with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="1fcd2-130">No tienen que comunicarse directamente entre ellas.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-130">They do not have to communicate directly to each other.</span></span>  
  
2.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1fcd2-131">controla los mensajes con codificación HL7 de forma nativa.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-131"> handles HL7-encoded messages natively.</span></span> <span data-ttu-id="1fcd2-132">No se requiere ningún código personalizado.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-132">No custom coding is required.</span></span>  
  
3.  <span data-ttu-id="1fcd2-133">El ADT ^ O04 mensaje de registro se difunde a todos los sistemas que se suscriben a él.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-133">The ADT^O04 registration message is broadcast to all systems that subscribe to it.</span></span> <span data-ttu-id="1fcd2-134">El modelo de mensajería de publicador y el suscriptor para [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] proporciona flexibilidad en la configuración y mantenimiento de la lista de sistemas de suscripción al mensaje.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-134">The publisher-subscriber messaging model for [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] provides flexibility in setting up and maintaining the list of systems subscribing to the message.</span></span> <span data-ttu-id="1fcd2-135">Puede agregar sistemas o eliminarlos de la lista de suscripciones sin afectar al resto del sistema.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-135">You can add systems to or delete them from the subscription list without affecting the rest of the system.</span></span>  
  
4.  <span data-ttu-id="1fcd2-136">La regla de negocios que se usa para validar la ORM ^ O01 mensaje de pedido puede cambiarse dinámicamente sin afectar al resto del sistema.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-136">The business rule used to validate the ORM^O01 order message can be changed dynamically without affecting the rest of the system.</span></span>  
  
5.  [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="1fcd2-137">puede configurarse para generar automáticamente el ORR ^ O02 mensaje de confirmación del pedido (ACK).</span><span class="sxs-lookup"><span data-stu-id="1fcd2-137"> can be configured to automatically generate the ORR^O02 order-confirmation (ACK) message.</span></span>  
  
6.  <span data-ttu-id="1fcd2-138">Si es necesario, puede procesar por lotes cualquiera de los mensajes con otros usuarios para el envío y procesarlos en recepción desde dentro del lote.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-138">If necessary, you can batch any of the messages with others for sending, and process them on receipt from within the batch.</span></span>  
  
7.  <span data-ttu-id="1fcd2-139">Puede validar todos los mensajes en el motor y en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2 esquemas X fabricado por la organización de HL7.</span><span class="sxs-lookup"><span data-stu-id="1fcd2-139">You can validate all messages in the engine and against the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2X schemas published by the HL7 organization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fcd2-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="1fcd2-140">See Also</span></span>  
 [<span data-ttu-id="1fcd2-141">Cómo resuelve BizTalk Server la necesidad empresarial</span><span class="sxs-lookup"><span data-stu-id="1fcd2-141">How BizTalk Server Solves the Business Need</span></span>](../../adapters-and-accelerators/accelerator-hl7/how-biztalk-server-solves-the-business-need2.md)