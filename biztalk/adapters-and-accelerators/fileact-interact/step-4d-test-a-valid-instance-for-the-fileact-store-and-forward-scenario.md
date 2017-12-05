---
title: "Paso 4d: probar una instancia válida para el escenario de reenvío y almacenamiento de FileAct | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7f47b1fd-a4ef-4b1d-812a-8c2fa946f98c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b2074e5360e6dfee766546f27a560208f920688
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="step-4d-test-a-valid-instance-for-the-fileact-store-and-forward-scenario"></a><span data-ttu-id="6ddeb-102">Paso 4d: probar una instancia válida para el escenario de reenvío y almacenamiento de FileAct</span><span class="sxs-lookup"><span data-stu-id="6ddeb-102">Step 4D: Test a Valid Instance for the FileAct Store and Forward Scenario</span></span>
<span data-ttu-id="6ddeb-103">Antes de comenzar este paso, debe completar [paso 4c: crear una instancia de prueba para el escenario al día y el almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="6ddeb-103">Before you begin this step, you must complete [Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md).</span></span>  
  
### <a name="to-test-a-valid-instance"></a><span data-ttu-id="6ddeb-104">Para probar una instancia válida</span><span class="sxs-lookup"><span data-stu-id="6ddeb-104">To test a valid instance</span></span>  
  
1.  <span data-ttu-id="6ddeb-105">Coloque el archivo PutReqSimple.xml en C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF.</span><span class="sxs-lookup"><span data-stu-id="6ddeb-105">Drop the file PutReqSimple.xml into C:\SWIFTAdapterTutorial\Fileact\FileRequestDropSnF.</span></span>  
  
2.  <span data-ttu-id="6ddeb-106">Compruebe que, tras unos instantes, el archivo PutReqSimple.xml desaparece de la carpeta.</span><span class="sxs-lookup"><span data-stu-id="6ddeb-106">Verify that after a moment, the PutReqSimple.xml file disappears from the folder.</span></span>  
  
3.  <span data-ttu-id="6ddeb-107">Compruebe que el archivo Sample_Put.txt se transfiere desde C:\SWIFTAdapterTurorial\Fileact\ClientLocation C:\SWIFTAdapterTutorial\Fileact\ServerLocation y que las respuestas aparecen en C:\SWIFTAdapterTutorial\ResponseServer.</span><span class="sxs-lookup"><span data-stu-id="6ddeb-107">Verify that the Sample_Put.txt file is transferred from C:\SWIFTAdapterTurorial\Fileact\ClientLocation to C:\SWIFTAdapterTutorial\Fileact\ServerLocation, and that responses appear in C:\SWIFTAdapterTutorial\ResponseServer.</span></span>  
  
4.  <span data-ttu-id="6ddeb-108">Compruebe la carpeta de eventos (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) de estado para los tres mensajes HandleFileEventRequest.</span><span class="sxs-lookup"><span data-stu-id="6ddeb-108">Check status event (c:\SWIFTAdapterTutorial\Fileact\StatusEvents) folder for three HandleFileEventRequest messages.</span></span> <span data-ttu-id="6ddeb-109">Estos mensajes deben contener los siguientes estados de transferencia:</span><span class="sxs-lookup"><span data-stu-id="6ddeb-109">These messages should contain the following Transfer status:</span></span>  
  
     <span data-ttu-id="6ddeb-110">Mensaje de HandleFileEventRequest\<Sw-TransferStatus\>aceptado\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="6ddeb-110">HandleFileEventRequest message\<Sw-TransferStatus\>Accepted\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="6ddeb-111">Mensaje de HandleFileEventRequest \<Sw-TransferStatus\>inició\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="6ddeb-111">HandleFileEventRequest message \<Sw-TransferStatus\>Initiated\</Sw-TransferStatus\></span></span>  
  
     <span data-ttu-id="6ddeb-112">Mensaje de HandleFileEventRequest \<Sw-TransferStatus\>completado\</Sw-TransferStatus\></span><span class="sxs-lookup"><span data-stu-id="6ddeb-112">HandleFileEventRequest message \<Sw-TransferStatus\>Completed\</Sw-TransferStatus\></span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ddeb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6ddeb-113">See Also</span></span>  
 <span data-ttu-id="6ddeb-114">[Paso 4: Probar el escenario de reenvío-to-End y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6ddeb-114">[Step 4: Test FileAct Store and Forward End-to-End Scenario](../../adapters-and-accelerators/fileact-interact/step-4-test-fileact-store-and-forward-end-to-end-scenario.md) </span></span>  
 <span data-ttu-id="6ddeb-115">[El paso 4A: iniciar el servicio SWIFTNet para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span><span class="sxs-lookup"><span data-stu-id="6ddeb-115">[Step 4A: Start the SWIFTNet Service for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4a-start-the-swiftnet-service-for-the-fileact-store-and-forward-scenario.md) </span></span>  
 <span data-ttu-id="6ddeb-116">[Paso 4B: iniciar los puertos de envío y puertos de recepción para el escenario de reenvío y almacenamiento de FileAct](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span><span class="sxs-lookup"><span data-stu-id="6ddeb-116">[Step 4B: Start the Send Ports and Receive Ports for the FileAct Store and Forward Scenario](../../adapters-and-accelerators/fileact-interact/step-4b-start-the-send-ports-and-receive-ports-for-fileact-store-and-forward.md) </span></span>  
 [<span data-ttu-id="6ddeb-117">Paso 4C: Crear una instancia de prueba para el escenario de almacenamiento y reenvío de FileAct</span><span class="sxs-lookup"><span data-stu-id="6ddeb-117">Step 4C: Create a Test Instance for the FileAct Store and Forward Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-4c-create-a-test-instance-for-the-fileact-store-and-forward-scenario.md)