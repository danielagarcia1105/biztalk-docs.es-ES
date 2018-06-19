---
title: 'Paso 4c: crear una instancia de prueba para el escenario en tiempo real de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 80e0cb59-8b4f-4273-a7a4-db3446008061
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04952616f1b49eb30b4eb00462e4e5295ade0cfc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22225044"
---
# <a name="step-4c-create-a-test-instance-for-the-fileact-real-time-scenario"></a><span data-ttu-id="a08c3-102">Paso 4c: crear una instancia de prueba para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="a08c3-102">Step 4C: Create a Test Instance for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="a08c3-103">Antes de comenzar este paso, debe completar [paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="a08c3-103">Before you begin this step, you must complete [Step 4B: Start the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-create-a-test-instance"></a><span data-ttu-id="a08c3-104">Para crear una instancia de prueba</span><span class="sxs-lookup"><span data-stu-id="a08c3-104">To create a test instance</span></span>  
  
1.  <span data-ttu-id="a08c3-105">Abra un nuevo archivo en un editor de texto, como el Bloc de notas y pegue lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a08c3-105">Open a new file in a text editor, such as Notepad, and paste the following:</span></span>  
  
    ```  
    <?xml version="1.0" encoding="utf-8"?>  
    <Sw-ExchangeFileRequest>  
    <Sw-FileRequest>  
    <Sw-FileOpRequest>  
    <Sw-PutFileRequest>  
    <Sw-PhysicalName>%PhysicalFolderName%\sample_put.txt</Sw-PhysicalName>  
    </Sw-PutFileRequest>  
    </Sw-FileOpRequest>  
    </Sw-FileRequest>  
    </Sw-ExchangeFileRequest>  
    ```  
  
2.  <span data-ttu-id="a08c3-106">Guarde el archivo con el nombre "PutReqSimple.xml".</span><span class="sxs-lookup"><span data-stu-id="a08c3-106">Save the file with the name “PutReqSimple.xml”.</span></span>  
  
3.  <span data-ttu-id="a08c3-107">Asegúrese de que el archivo (Sample_put.txt) se encuentra en la carpeta de ubicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="a08c3-107">Make sure that the file (Sample_put.txt) is placed in the Client Location folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a08c3-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="a08c3-108">See Also</span></span>  
 <span data-ttu-id="a08c3-109">[Paso 4: Probar el escenario de extremo a extremo en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a08c3-109">[Step 4: Test FileAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="a08c3-110">[El paso 4A: iniciar el servicio SWIFTNet para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a08c3-110">[Step 4A: Start the SWIFTNet Service for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="a08c3-111">[Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="a08c3-111">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="a08c3-112">Paso 4d: pruebe una instancia válida para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="a08c3-112">Step 4D: Test a Valid Instance for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario.md)