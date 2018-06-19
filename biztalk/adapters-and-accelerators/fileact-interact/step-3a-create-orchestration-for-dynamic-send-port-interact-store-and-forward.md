---
title: 'Paso 3A: crear una orquestación para el puerto de envío dinámico para el almacén de interacción y escenario de reenvío (extracción) | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d5bbfed-f2cb-4caa-91e2-58f0bdb3b3c5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 486133586a3db8669a58aae59c3ec67a4f561999
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225284"
---
# <a name="step-3a-create-an-orchestration-for-dynamic-send-port-for-interact-store-and-forward-pull-scenario"></a>Paso 3A: crear una orquestación para el puerto de envío dinámico para el almacén de interacción y escenario de reenvío (extracción)
Antes de comenzar los pasos descritos en esta sección, debe completar los pasos descritos en la [paso 2c: agregar un puerto de envío de interacción para el almacén de interacción y el escenario de reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-2c-add-interact-send-port-for-interact-store-and-forward-pull-scenario.md) sección.  
  
### <a name="to-create-an-orchestration"></a>Para crear una orquestación  
  
1.  Cree la forma recepción que se suscribe a todos los mensajes de tipo de mensaje Sw-ExchangeSnFRequest.  
  
2.  Agregar una forma de expresión para obtener todos los valores necesarios del mensaje ExchangeRequestSnF. Consulte el ejemplo siguiente de la forma expresión:  
  
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
  
    MessageFormat="InteractMessage";  
    IsPull=true;  
    ```  
  
3.  Crear un mensaje de tipo PullSnFRequest y la dirección URL de envío dinámico. Consulte el ejemplo de asignación forma de construir mensaje:  
  
    ```  
    PullMessage = new System.Xml.XmlDocument();  
    PullMessage.LoadXml(@"<Sw-PullSnFRequest/>");  
    PullRequest = PullMessage;  
  
    DynamicPull(Microsoft.XLANGs.BaseTypes.Address) = "INTERACT://<machine  
     name>/" + QueueName + "/" + SessionMode + "/" + ForceAcquire + "/" +   
    OrderBy + "/" + RecoveryMode + "/" + MessageFormat;  
    ```  
  
4.  En este ejemplo, PullMessage es un mensaje de tipo Sw-PullSnFRequest.  
  
5.  Agregue una forma de envío para enviar el PullMessage (solicitud de extracción).  
  
6.  Agregar un puerto de solicitud-respuesta para enviar el mensaje de extracción y para recibir la respuesta de extracción con el enlace dinámico.  
  
7.  Conecte la forma de envío y el puerto creado en el paso anterior.  
  
8.  Agregue una forma recepción para recibir el PullResponse (mensaje de tipo PullSnFResponse) y, a continuación, conecte la forma de recepción con el puerto creado anteriormente.  
  
9. Enviar la respuesta a la carpeta correspondiente mediante una forma de envío.  
  
10. Agregue todas estas actividades (enviar una solicitud de extracción y recibir la respuesta) en un bucle si desea extraer todos los mensajes.  
  
11. Agregar una forma de expresión CheckQueueEmpty para mantener tirando hasta que el tiempo de la cola está vacía. Consulte el ejemplo siguiente de la forma expresión:  
  
    ```  
    PullResponseDoc=PullResponse;  
    PullResponseNode=PullResponseDoc.SelectSingleNode("/SwPullSnFResponse/  
    SwGbl-Status/SwGbl-StatusAttributes/SwGbl-Code");  
    if(PullResponseNode !=null && PullResponseNode.InnerText=="Sw.SnF.QueueEmpty")  
    {  
        IsPull=false;  
    }  
    ```  
  
12. Esta acción establecerá el IsPull = false, una vez que la cola está vacía.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3B: enlazar la orquestación con el puerto de envío dinámico para interactuar almacén y escenario de reenvío (extracción)](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-port-for-interact-scenario.md)