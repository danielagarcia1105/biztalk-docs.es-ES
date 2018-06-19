---
title: 'Paso 3: Crear los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct | Documentos de Microsoft'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d7d39c7-a08b-4fbb-85fe-b30a8d62524b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa7b0465ca6909998379ea94ef173d30387da602
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223780"
---
# <a name="step-3-create-the-send-ports-and-receive-ports-for-the-fileact-real-time-scenario"></a><span data-ttu-id="20417-102">Paso 3: Crear los puertos de envío y puertos de recepción para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="20417-102">Step 3: Create the Send Ports and Receive Ports for the FileAct Real-Time Scenario</span></span>
<span data-ttu-id="20417-103">Antes de comenzar los pasos descritos en esta sección, debe completar [paso 2: Agregar configuración SWIFTNet a la Paramfile para el escenario de en tiempo real de FileAct](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md).</span><span class="sxs-lookup"><span data-stu-id="20417-103">Before you begin the steps in this section, you must complete [Step 2: Add SWIFTNet Configuration to the Paramfile for the FileAct Real-Time Scenario](../../adapters-and-accelerators/fileact-interact/step-2-add-swiftnet-configuration-to-paramfile-for-fileact-real-time-scenario.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="20417-104">En esta sección</span><span class="sxs-lookup"><span data-stu-id="20417-104">In This Section</span></span>  
  
-   [<span data-ttu-id="20417-105">Paso 3A: agregar un archivo de ubicación de recepción para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="20417-105">Step 3A: Add a FILE Receive Location for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3a-add-a-file-receive-location-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="20417-106">Paso 3B: agregar un FILEACT ubicación de recepción para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="20417-106">Step 3B: Add a FILEACT Receive Location for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3b-add-a-fileact-receive-location-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="20417-107">Paso 3c: agregar un puerto de envío de archivo para capturar los mensajes de Sw:HandleRequest para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="20417-107">Step 3C: Add a FILE Send Port to Capture Sw:HandleRequest Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3c-add-file-send-port-to-get-sw-handlerequest-message-for-fileact.md)  
  
-   [<span data-ttu-id="20417-108">Paso 3D: agregar un puerto de envío de FILEACT para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="20417-108">Step 3D: Add a FILEACT Send Port for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3d-add-a-fileact-send-port-for-the-fileact-real-time-scenario.md)  
  
-   [<span data-ttu-id="20417-109">Paso 3E: agregar un puerto de envío de archivo para capturar los mensajes de Sw:ExchangeFileResponse para el escenario en tiempo real de FileAct</span><span class="sxs-lookup"><span data-stu-id="20417-109">Step 3E: Add a FILE Send Port to Capture Sw:ExchangeFileResponse Message for the FileAct Real-Time Scenario</span></span>](../../adapters-and-accelerators/fileact-interact/step-3e-add-file-send-port-to-get-sw-exchangefileresponse-message-for-fileact.md)  
  
-   [<span data-ttu-id="20417-110">Paso 3F: agregar un puerto de envío de archivos para el escenario en tiempo real de FileAct capturar los mensajes de Sw-HandleFileEventRequest</span><span class="sxs-lookup"><span data-stu-id="20417-110">Step 3F: Add a FILE Send Port for the FileAct Real-Time Scenario to Capture Sw-HandleFileEventRequest Messages</span></span>](../../adapters-and-accelerators/fileact-interact/step-3f-add-file-send-port-to-get-sw-handlefileeventrequest-messages--fileact.md)