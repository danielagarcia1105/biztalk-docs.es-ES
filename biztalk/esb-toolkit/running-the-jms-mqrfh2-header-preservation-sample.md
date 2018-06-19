---
title: Ejecutar el ejemplo de conservación de JMS MQRFH2 encabezado | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 65982dca-77e1-4267-9528-26c59237e9b1
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab840ed1d319f8fd50d3a386e0ffc9b349f61b9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295132"
---
# <a name="running-the-jms-mqrfh2-header-preservation-sample"></a><span data-ttu-id="07ee6-102">Ejecutar el ejemplo de conservación de JMS MQRFH2 encabezado</span><span class="sxs-lookup"><span data-stu-id="07ee6-102">Running the JMS MQRFH2 Header Preservation Sample</span></span>
<span data-ttu-id="07ee6-103">Esta parte de este ejemplo coloca un mensaje en una cola de WebSphere.</span><span class="sxs-lookup"><span data-stu-id="07ee6-103">This part of this sample deposits a message into a WebSphere queue.</span></span> <span data-ttu-id="07ee6-104">ESB toma este mensaje y coloca en una cola de salida de WebSphere.</span><span class="sxs-lookup"><span data-stu-id="07ee6-104">The ESB picks up this message and deposits it into an outbound WebSphere queue.</span></span> <span data-ttu-id="07ee6-105">Esto demuestra que el ESB y Microsoft BizTalk conservan encabezados de RFH2 plena fidelidad como un mensaje se transmite a través de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="07ee6-105">This demonstrates that the ESB and Microsoft BizTalk preserve full-fidelity RFH2 headers as a message travels through BizTalk Server.</span></span>  
  
 <span data-ttu-id="07ee6-106">**Para ejecutar el ejemplo de conservación de encabezado**</span><span class="sxs-lookup"><span data-stu-id="07ee6-106">**To run the Header Preservation sample**</span></span>  
  
1.  <span data-ttu-id="07ee6-107">Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="07ee6-107">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="07ee6-108">Ejecute la utilidad de IBM RfhUtil y, a continuación, seleccione el Administrador de cola denominado ESB. JMS. Sample.QueueManager en la primera lista desplegable para conectarse a este administrador de cola.</span><span class="sxs-lookup"><span data-stu-id="07ee6-108">Run the IBM RfhUtil utility, and then select the queue manager named ESB.JMS.Sample.QueueManager in the first drop-down list to connect to this queue manager.</span></span>  
  
3.  <span data-ttu-id="07ee6-109">En la segunda lista desplegable, seleccione la cola de salida de destino denominada ESB. JMS. EJEMPLO. SENDTOBIZTALK, tal como se muestra en la figura 1.</span><span class="sxs-lookup"><span data-stu-id="07ee6-109">In the second drop-down list, select the target outbound queue named ESB.JMS.SAMPLE.SENDTOBIZTALK, as shown in Figure 1.</span></span>  
  
     <span data-ttu-id="07ee6-110">![Administrador de cola](../esb-toolkit/media/ch6-queuemanager.gif "Ch6-QueueManager")</span><span class="sxs-lookup"><span data-stu-id="07ee6-110">![Queue Manager](../esb-toolkit/media/ch6-queuemanager.gif "Ch6-QueueManager")</span></span>  
  
     <span data-ttu-id="07ee6-111">**Figura 1**</span><span class="sxs-lookup"><span data-stu-id="07ee6-111">**Figure 1**</span></span>  
  
     <span data-ttu-id="07ee6-112">**Conectar con el Administrador de cola y la cola de salida en RfhUtil**</span><span class="sxs-lookup"><span data-stu-id="07ee6-112">**Connecting to the queue manager and the outbound queue in RfhUtil**</span></span>  
  
4.  <span data-ttu-id="07ee6-113">Si la lista desplegable no contiene ninguna cola, asegúrese de que el Administrador de cola se ejecuta mediante la comprobación del elemento de WebSphere MQ servicios, como se muestra en la figura 2.</span><span class="sxs-lookup"><span data-stu-id="07ee6-113">If the drop-down list does not contain any queues, make sure that the queue manager is running by checking the WebSphere MQ Services item, as shown in Figure 2.</span></span>  
  
     <span data-ttu-id="07ee6-114">![Web esfera](../esb-toolkit/media/ch6-websphere.gif "Ch6-WebSphere")</span><span class="sxs-lookup"><span data-stu-id="07ee6-114">![Web Sphere](../esb-toolkit/media/ch6-websphere.gif "Ch6-WebSphere")</span></span>  
  
     <span data-ttu-id="07ee6-115">**Figura 2**</span><span class="sxs-lookup"><span data-stu-id="07ee6-115">**Figure 2**</span></span>  
  
     <span data-ttu-id="07ee6-116">**Comprobación de que el Administrador de cola se está ejecutando en el elemento de servicios de WebSphere**</span><span class="sxs-lookup"><span data-stu-id="07ee6-116">**Checking that the queue manager is running in the WebSphere Services item**</span></span>  
  
5.  <span data-ttu-id="07ee6-117">Haga clic en el **ReadFile** situado en la utilidad RfhUtil y navegue hasta el archivo de mensaje de prueba denominado 000128 de prueba. JMS ubicado en la subcarpeta denominada \Source\Samples\JMS\Test\Data\Load\\.</span><span class="sxs-lookup"><span data-stu-id="07ee6-117">Click the **ReadFile** button in the RfhUtil utility and navigate to the test message file named TEST-000128.JMS located in the subfolder named \Source\Samples\JMS\Test\Data\Load\\.</span></span> <span data-ttu-id="07ee6-118">Este archivo contiene un lote de mensajes de prueba 128, pero la utilidad carga solo la primera de ellas.</span><span class="sxs-lookup"><span data-stu-id="07ee6-118">This file contains a batch of 128 test messages, but the utility loads only the first one.</span></span>  
  
6.  <span data-ttu-id="07ee6-119">Haga clic en el **RFH** ficha y, a continuación, asegúrese de que sólo el **JMS** casilla está activada.</span><span class="sxs-lookup"><span data-stu-id="07ee6-119">Click the **RFH** tab, and then make sure that only the **JMS** check box is selected.</span></span>  
  
7.  <span data-ttu-id="07ee6-120">Haga clic en el **jms** ficha y, a continuación, asegúrese de que el seleccionado **responder a** cola es ESB. JMS. EJEMPLO. DYNAMICQ1 y que el seleccionado **cola de destino** es ESB. JMS. EJEMPLO. DYNAMICQ2.</span><span class="sxs-lookup"><span data-stu-id="07ee6-120">Click the **jms** tab, and then make sure that the selected **Reply To** queue is ESB.JMS.SAMPLE.DYNAMICQ1 and that the selected **Destination Queue** is ESB.JMS.SAMPLE.DYNAMICQ2.</span></span>  
  
8.  <span data-ttu-id="07ee6-121">Haga clic en el **Main** ficha y, a continuación, haga clic en el **escribir preguntas** botón para escribir el mensaje en la cola.</span><span class="sxs-lookup"><span data-stu-id="07ee6-121">Click the **Main** tab, and then click the **Write Q** button to write the message into the queue.</span></span>  
  
9. <span data-ttu-id="07ee6-122">Después de un retraso mientras se ejecuta la aplicación, aparece el mensaje de salida ESB en ESB. JMS. EJEMPLO. DYNAMICQ1 y ESB. JMS. EJEMPLO. Colas de DYNAMICQ1.</span><span class="sxs-lookup"><span data-stu-id="07ee6-122">After a delay while the application executes, the ESB output message appears in the ESB.JMS.SAMPLE.DYNAMICQ1 and ESB.JMS.SAMPLE.DYNAMICQ1 queues.</span></span> <span data-ttu-id="07ee6-123">Abra el Explorador de la cola de WebSphere y examinar las colas para confirmarlo.</span><span class="sxs-lookup"><span data-stu-id="07ee6-123">Open the WebSphere Queue Explorer and browse the queues to confirm this.</span></span>  
  
10. <span data-ttu-id="07ee6-124">Vuelva a la utilidad RfhUtil y conectarse a las colas para ver los mensajes.</span><span class="sxs-lookup"><span data-stu-id="07ee6-124">Go back to the RfhUtil utility and connect to the queues to see the messages.</span></span> <span data-ttu-id="07ee6-125">Haga clic en el **MQMD, RFH,** y **jms** excepción en las pestañas para comprobar que los valores de entrada y salidos se ha modificado para el mensaje en la cola de destino y que el mensaje en la cola de respuesta es el mismo que, en lugar de un mensaje JMS estándar, el mensaje se marca como "Sí".</span><span class="sxs-lookup"><span data-stu-id="07ee6-125">Click the **MQMD, RFH,** and **jms** tabs to verify that the input and output values are unchanged for the message in the Destination Queue, and that the message in the Reply To queue is the same except that, instead of being a standard JMS message, the message is marked as "other".</span></span>