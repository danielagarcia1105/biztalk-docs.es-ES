---
title: 'Paso 3A: crear una orquestación para el puerto de envío dinámico para el escenario de reenvío (extracción) y almacenamiento de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5675d476-ad36-4bbc-8e87-786edc9c805d
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c91f9054885de1d19b467646ee7b82b342a76d6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223548"
---
# <a name="step-3a-create-an-orchestration-for-dynamic-send-port-for-fileact-store-and-forward-pull-scenario"></a>Paso 3A: crear una orquestación para el puerto de envío dinámico para el escenario de reenvío (extracción) y almacenamiento de FileAct
Antes de comenzar los pasos descritos en esta sección, debe completar los pasos descritos en la [paso 2c: agregar un puerto de envío de FILEACT para el escenario de reenvío (extracción) y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-2c-add-a-fileact-send-port-for-fileact-store-and-forward-pull-scenario.md) sección.  
  
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
  
    MessageFormat="FileactMessage";  
    IsPull=true;  
  
    ```  
  
3.  Crear un mensaje de tipo PullSnFRequest y la dirección URL de envío dinámico. Consulte el ejemplo de asignación forma de construir mensaje:  
  
    ```  
    PullMessage = new System.Xml.XmlDocument();  
    PullMessage.LoadXml(@"<Sw-PullSnFRequest/>");  
    PullRequest = PullMessage;  
  
    DynamicPull(Microsoft.XLANGs.BaseTypes.Address) = "FILEACT://localhost/" + QueueName + "/" + SessionMode + "/" + ForceAcquire + "/" + OrderBy + "/" + RecoveryMode + "/" + MessageFormat;  
  
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
    PullResponseNode=PullResponseDoc.SelectSingleNode("/Sw-PullSnFResponse/SwGbl-Status/SwGbl-StatusAttributes/SwGbl-Code");  
    if(PullResponseNode !=null && PullResponseNode.InnerText=="Sw.SnF.QueueEmpty")  
    {  
        IsPull=false;  
    }  
  
    ```  
  
12. Esta acción establecerá el IsPull = false, una vez que la cola está vacía.  
  
## <a name="see-also"></a>Vea también  
 [Paso 3B: enlazar la orquestación con el puerto de envío dinámico para el escenario de reenvío (extracción) y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-3b-bind-orchestration-with-dynamic-send-for-fileact-store-and-forward.md)