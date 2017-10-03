---
title: "Paso 4d: pruebe una instancia válida para el escenario en tiempo real de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a8975c90-462b-4c9b-8766-1272ab7ceaba
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77a9b887bc509ddf3dd67ea941e72cbbeb04a5ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-real-time-scenario"></a><span data-ttu-id="35b98-102">Paso 4d: pruebe una instancia válida para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="35b98-102">Step 4D: Test a Valid Instance for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="35b98-103">Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="35b98-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="35b98-104">Para probar una instancia válida</span><span class="sxs-lookup"><span data-stu-id="35b98-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="35b98-105">Coloque el archivo PutReqSimple.xml en C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime.</span><span class="sxs-lookup"><span data-stu-id="35b98-105">Drop the file PutReqSimple.xml into C:\SWIFTAdapterTutorial\Fileact\FileRequestDropRealTime.</span></span>  
  
2.  <span data-ttu-id="35b98-106">Compruebe que, tras unos instantes, el archivo PutReqSimple.xml desaparece de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="35b98-106">Verify that after a moment, the PutReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="35b98-107">Compruebe que el archivo Sample_Put.txt se transfiere desde: C:\SWIFTAdapterTutorial\Fileact\ClientLocation a C:\SWIFTAdapterTutorial\Fileact\ServerLocation y que las respuestas aparecen en C:\SWIFTAdapterTutorial\Fileact\ResponseClient y C:\ SWIFTAdapterTutorial\Fileact\ResponseServer.</span><span class="sxs-lookup"><span data-stu-id="35b98-107">Verify that the Sample_Put.txt file is transferred from: C:\SWIFTAdapterTutorial\Fileact\ClientLocation to C:\SWIFTAdapterTutorial\Fileact\ServerLocation, and that responses appear in C:\SWIFTAdapterTutorial\Fileact\ResponseClient and C:\SWIFTAdapterTutorial\Fileact\ResponseServer.</span></span>  
  
4.  <span data-ttu-id="35b98-108">Compruebe la carpeta de eventos (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) de estado para los tres mensajes HandleFileEventRequest.</span><span class="sxs-lookup"><span data-stu-id="35b98-108">Check status event (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) folder for three HandleFileEventRequest messages.</span></span> <span data-ttu-id="35b98-109">Estos mensajes deben contener los siguientes estados de transferencia:</span><span class="sxs-lookup"><span data-stu-id="35b98-109">These messages should contain the following Transfer status:</span></span>  
  
     <span data-ttu-id="35b98-110">Mensaje de HandleFileEventRequest\<Sw-TransferStatus > aceptado\</Sw-TransferStatus ></span><span class="sxs-lookup"><span data-stu-id="35b98-110">HandleFileEventRequest message\<Sw-TransferStatus>Accepted\</Sw-TransferStatus></span></span>  
  
     <span data-ttu-id="35b98-111">Mensaje de HandleFileEventRequest \<Sw-TransferStatus > inició\</Sw-TransferStatus ></span><span class="sxs-lookup"><span data-stu-id="35b98-111">HandleFileEventRequest message \<Sw-TransferStatus>Initiated\</Sw-TransferStatus></span></span>  
  
     <span data-ttu-id="35b98-112">Mensaje de HandleFileEventRequest \<Sw-TransferStatus > completado\</Sw-TransferStatus ></span><span class="sxs-lookup"><span data-stu-id="35b98-112">HandleFileEventRequest message \<Sw-TransferStatus>Completed\</Sw-TransferStatus></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b98-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="35b98-113">See Also</span></span>  
 <span data-ttu-id="35b98-114">[Paso 4: Probar el escenario de extremo a extremo en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="35b98-114">[Step 4: Test FileAct Real-Time End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-real-time-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="35b98-115">[El paso 4A: iniciar el servicio SWIFTNet para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="35b98-115">[Step 4A: Start the SWIFTNet Service for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-real-time-scenario.md) </span></span>  
 <span data-ttu-id="35b98-116">[Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="35b98-116">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-and-receive-ports-for-the-fileact-real-time-scenario.md) </span></span>  
 [<span data-ttu-id="35b98-117">Paso 4c: crear una instancia de prueba para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="35b98-117">Step 4C: Create a Test Instance for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-real-time-scenario.md)