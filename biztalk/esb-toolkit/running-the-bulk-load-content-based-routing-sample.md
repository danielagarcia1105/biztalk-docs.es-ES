---
title: Ejecuta la mayor parte cargar muestra de enrutamiento basado en contenido | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7e981567-7c6c-4c13-bd5b-597efdd3fb50
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36c5348563cc52c31b14dbceddf35bdb3d5d94cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="running-the-bulk-load-content-based-routing-sample"></a><span data-ttu-id="255f2-102">Ejecutar el masiva carga contenidos enrutamiento ejemplo</span><span class="sxs-lookup"><span data-stu-id="255f2-102">Running the Bulk Load Content-Based Routing Sample</span></span>
<span data-ttu-id="255f2-103">Esta parte del ejemplo muestra una cola con los mensajes que los ESB y Microsoft BizTalk enrutará a las colas de destino diferente según el nombre de cola especificado en cada mensaje de carga masiva.</span><span class="sxs-lookup"><span data-stu-id="255f2-103">This part of the sample demonstrates bulk loading a queue with messages that the ESB and Microsoft BizTalk will route to different destination queues based on the queue name specified in each message.</span></span> <span data-ttu-id="255f2-104">Usa las características de la muestra que ha visto en las dos partes anteriores.</span><span class="sxs-lookup"><span data-stu-id="255f2-104">It uses the features of the sample that you have seen in the previous two parts.</span></span>  
  
 <span data-ttu-id="255f2-105">**Para ejecutar el ejemplo de acceso de enrutamiento basado en contenido de carga masiva**</span><span class="sxs-lookup"><span data-stu-id="255f2-105">**To run the Bulk Load Content-based Routing Access sample**</span></span>  
  
1.  <span data-ttu-id="255f2-106">Si aún no se está ejecutando la aplicación GlobalBank.ESB, use la consola de administración de BizTalk para iniciarlo.</span><span class="sxs-lookup"><span data-stu-id="255f2-106">If the GlobalBank.ESB application is not already running, use the BizTalk Administration Console to start it.</span></span>  
  
2.  <span data-ttu-id="255f2-107">Ejecute la utilidad de IBM RfhUtil y, a continuación, seleccione el Administrador de cola denominado ESB. JMS. Sample.QueueManager en la primera lista desplegable para conectarse a este administrador de cola, como en la parte 2 de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="255f2-107">Run the IBM RfhUtil utility, and then select the queue manager named ESB.JMS.Sample.QueueManager in the first drop-down list to connect to this queue manager, as in Part 2 of this sample.</span></span>  
  
3.  <span data-ttu-id="255f2-108">En la segunda lista desplegable, seleccione la cola de salida de destino denominada ESB. JMS. EJEMPLO. SENDTOBIZTALK, como en la parte 2 de este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="255f2-108">In the second drop-down list, select the target outbound queue named ESB.JMS.SAMPLE.SENDTOBIZTALK, as in Part 2 of this sample.</span></span>  
  
4.  <span data-ttu-id="255f2-109">Haga clic en el **carga preguntas** situado en la utilidad RfhUtil y, a continuación, navegue hasta el archivo de mensaje de prueba denominado 000128 de prueba. JMS ubicado en la subcarpeta denominada \Source\Samples\JMS\Test\Data\Load\\.</span><span class="sxs-lookup"><span data-stu-id="255f2-109">Click the **Load Q** button in the RfhUtil utility, and then navigate to the test message file named TEST-000128.JMS located in the subfolder named \Source\Samples\JMS\Test\Data\Load\\.</span></span> <span data-ttu-id="255f2-110">Este archivo contiene un lote de 128 mensajes de prueba que el ejemplo enviará al ESB.</span><span class="sxs-lookup"><span data-stu-id="255f2-110">This file contains a batch of 128 test messages that the sample will send to the ESB.</span></span>  
  
5.  <span data-ttu-id="255f2-111">En el **carga** cuadro de diálogo, deje todos los valores se establecen en sus valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="255f2-111">In the **Load** dialog box, leave all values set to their default values.</span></span>  
  
6.  <span data-ttu-id="255f2-112">En el **carga** cuadro de diálogo, haga clic en **Aceptar** para agregar todos los mensajes a la cola de entrada.</span><span class="sxs-lookup"><span data-stu-id="255f2-112">In the **Load** dialog box, click **OK** to add all the messages to the input queue.</span></span>  
  
7.  <span data-ttu-id="255f2-113">Después de un retraso mientras se ejecuta la aplicación, aparecen los mensajes de salida ESB en varias colas de destino, dependiendo de los valores en los encabezados JMS.</span><span class="sxs-lookup"><span data-stu-id="255f2-113">After a delay while the application executes, the ESB output messages appear in various destination queues, depending on the values in their JMS headers.</span></span> <span data-ttu-id="255f2-114">Sin embargo, todos los especifican la misma cola responder a, por lo que todas las respuestas aparecen en ESB. JMS. EJEMPLO. Cola de respuesta.</span><span class="sxs-lookup"><span data-stu-id="255f2-114">However, all specify the same Reply To queue, so all the replies appear in the ESB.JMS.SAMPLE.REPLY queue.</span></span> <span data-ttu-id="255f2-115">Abra el Explorador de la cola de WebSphere y examinar las colas para confirmarlo.</span><span class="sxs-lookup"><span data-stu-id="255f2-115">Open the WebSphere Queue Explorer and browse the queues to confirm this.</span></span>