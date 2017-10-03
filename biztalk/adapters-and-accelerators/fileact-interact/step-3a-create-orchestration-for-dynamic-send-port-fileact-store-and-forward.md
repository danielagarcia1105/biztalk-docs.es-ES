---
title: "Paso 3A: crear una orquestación para el puerto de envío dinámico para el escenario de reenvío (extracción) y almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5675d476-ad36-4bbc-8e87-786edc9c805d
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c91f9054885de1d19b467646ee7b82b342a76d6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3a-create-an-orchestration-for-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a><span data-ttu-id="d3930-102">Paso 3A: crear una orquestación para el puerto de envío dinámico para el escenario de reenvío (extracción) y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="d3930-102">Step 3A: Create an orchestration for dynamic send port for FileAct Store and Forward (Pull) Scenario</span></span>
<span data-ttu-id="d3930-103">Antes de comenzar los pasos descritos en esta sección, debe completar los pasos descritos en la [paso 2c: agregar un puerto de envío de FILEACT para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md) sección.</span><span class="sxs-lookup"><span data-stu-id="d3930-103">Before you begin the steps in this section, you must complete the steps in the [Step 2C: Add a FILEACT Send Port for the FileAct Store and Forward (Pull) Scenario](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md) section.</span></span>  
  
### <a name="to-create-an-orchestration"></a><span data-ttu-id="d3930-104">Para crear una orquestación</span><span class="sxs-lookup"><span data-stu-id="d3930-104">To Create an Orchestration</span></span>  
  
1.  <span data-ttu-id="d3930-105">Cree la forma recepción que se suscribe a todos los mensajes de tipo de mensaje Sw-ExchangeSnFRequest.</span><span class="sxs-lookup"><span data-stu-id="d3930-105">Create the Receive shape that subscribes to all of the messages of message type Sw-ExchangeSnFRequest.</span></span>  
  
2.  <span data-ttu-id="d3930-106">Agregar una forma de expresión para obtener todos los valores necesarios del mensaje ExchangeRequestSnF.</span><span class="sxs-lookup"><span data-stu-id="d3930-106">Add an Expression shape to get all of the required values from the ExchangeRequestSnF message.</span></span> <span data-ttu-id="d3930-107">Consulte el ejemplo siguiente de la forma expresión:</span><span class="sxs-lookup"><span data-stu-id="d3930-107">Refer to the following Expression Shape sample:</span></span>  
  
    ```  
    ExchangeSnFRequestDoc=ExchangeSnFRequest;  
    AcquireQueuePath="/Sw-ExchangeSnFRequest/Sw-SnFRequest/Sw-SnFOpRequest/Sw-AcquireSnFRequest/";  
  
    QueueNameNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath + "SwInt-Queue");  
    SessionModeNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-SessionMode");  
    ForceAcquireNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-ForceAcquire");  
    OrderByNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-OrderBy");  
    RecoveryModeNode=ExchangeSnFRequestDoc.SelectSingleNode(AcquireQueuePath+ "Sw-RecoveryMode");  
  
    QueueName=QueueNameNode.InnerText;  
    SessionMode=SessionModeNode.InnerText;  
    ForceAcquire=ForceAcquireNode.InnerText;  
    OrderBy=OrderByNode.InnerText;  
    RecoveryMode=RecoveryModeNode.InnerText;  
  
    MessageFormat="FileactMessage";  
    IsPull=true;  
  
    ```  
  
3.  <span data-ttu-id="d3930-108">Crear un mensaje de tipo PullSnFRequest y la dirección URL de envío dinámico.</span><span class="sxs-lookup"><span data-stu-id="d3930-108">Construct a message of type PullSnFRequest and the URL for Dynamic Send.</span></span> <span data-ttu-id="d3930-109">Consulte el ejemplo de asignación forma de construir mensaje:</span><span class="sxs-lookup"><span data-stu-id="d3930-109">Refer to the Assignment Shape of Construct Message sample:</span></span>  
  
    ```  
    PullMessage = new System.Xml.XmlDocument();  
    PullMessage.LoadXml(@"<Sw-PullSnFRequest/>");  
    PullRequest = PullMessage;  
  
    DynamicPull(Microsoft.XLANGs.BaseTypes.Address) = "FILEACT://localhost/" + QueueName + "/" + SessionMode + "/" + ForceAcquire + "/" + OrderBy + "/" + RecoveryMode + "/" + MessageFormat;  
  
    ```  
  
4.  <span data-ttu-id="d3930-110">En este ejemplo, PullMessage es un mensaje de tipo Sw-PullSnFRequest.</span><span class="sxs-lookup"><span data-stu-id="d3930-110">In this sample, PullMessage is a message of type Sw-PullSnFRequest.</span></span>  
  
5.  <span data-ttu-id="d3930-111">Agregue una forma de envío para enviar el PullMessage (solicitud de extracción).</span><span class="sxs-lookup"><span data-stu-id="d3930-111">Add a Send shape to send the PullMessage (pull request).</span></span>  
  
6.  <span data-ttu-id="d3930-112">Agregar un puerto de solicitud-respuesta para enviar el mensaje de extracción y para recibir la respuesta de extracción con el enlace dinámico.</span><span class="sxs-lookup"><span data-stu-id="d3930-112">Add a request-response port for sending the pull message and for receiving the pull response with the dynamic binding.</span></span>  
  
7.  <span data-ttu-id="d3930-113">Conecte la forma de envío y el puerto creado en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="d3930-113">Connect the Send shape with the port created in the previous step.</span></span>  
  
8.  <span data-ttu-id="d3930-114">Agregue una forma recepción para recibir el PullResponse (mensaje de tipo PullSnFResponse) y, a continuación, conecte la forma de recepción con el puerto creado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="d3930-114">Add a Receive shape to receive the PullResponse (message of type PullSnFResponse) and then connect the Receive shape with the port previously created.</span></span>  
  
9. <span data-ttu-id="d3930-115">Enviar la respuesta a la carpeta correspondiente mediante una forma de envío.</span><span class="sxs-lookup"><span data-stu-id="d3930-115">Send the response to the respective folder using a Send shape.</span></span>  
  
10. <span data-ttu-id="d3930-116">Agregue todas estas actividades (enviar una solicitud de extracción y recibir la respuesta) en un bucle si desea extraer todos los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d3930-116">Add all of these activities (sending a pull request and receiving the response) in a loop if you want to pull all of the messages.</span></span>  
  
11. <span data-ttu-id="d3930-117">Agregar una forma de expresión CheckQueueEmpty para mantener tirando hasta que el tiempo de la cola está vacía.</span><span class="sxs-lookup"><span data-stu-id="d3930-117">Add an Expression shape CheckQueueEmpty to keep pulling until the time queue is empty.</span></span> <span data-ttu-id="d3930-118">Consulte el ejemplo siguiente de la forma expresión:</span><span class="sxs-lookup"><span data-stu-id="d3930-118">Refer the following Expression Shape sample:</span></span>  
  
    ```  
    PullResponseDoc=PullResponse;  
    PullResponseNode=PullResponseDoc.SelectSingleNode("/Sw-PullSnFResponse/SwGbl-Status/SwGbl-StatusAttributes/SwGbl-Code");  
    if(PullResponseNode !=null && PullResponseNode.InnerText=="Sw.SnF.QueueEmpty")  
    {  
        IsPull=false;  
    }  
  
    ```  
  
12. <span data-ttu-id="d3930-119">Esta acción establecerá el IsPull = false, una vez que la cola está vacía.</span><span class="sxs-lookup"><span data-stu-id="d3930-119">This will set the IsPull = false, once the queue is empty.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3930-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3930-120">See Also</span></span>  
 [<span data-ttu-id="d3930-121">Paso 3B: enlazar la orquestación con el puerto de envío dinámico para el escenario de reenvío (extracción) y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="d3930-121">Step 3B: Bind the orchestration with dynamic send port for FileAct Store and Forward (Pull) Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-for-fileact-store-and-forward.md)