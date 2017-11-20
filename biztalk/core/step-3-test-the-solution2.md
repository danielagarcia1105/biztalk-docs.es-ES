---
title: 'Paso 3: Probar el 2 | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30dbc7c9-3c5f-4953-b26f-5c41141c22ad
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6c0e484a9f6af788775ec4ae7309965327378267
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-3-test-the-solution"></a><span data-ttu-id="5c2c5-102">Paso 3: Probar la solución</span><span class="sxs-lookup"><span data-stu-id="5c2c5-102">Step 3: Test the Solution</span></span>
<span data-ttu-id="5c2c5-103">![Paso 3 de 3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span><span class="sxs-lookup"><span data-stu-id="5c2c5-103">![Step 3 of 3](../adapters-and-accelerators/adapter-oracle-database/media/step-3of3.gif "Step_3of3")</span></span>  
  
 <span data-ttu-id="5c2c5-104">**Tiempo en completarse:** 5 minutos</span><span class="sxs-lookup"><span data-stu-id="5c2c5-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="5c2c5-105">**Objetivo:** en este paso, probará cómo la solución EAI procesa los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-105">**Objective:** In this step, you test how the EAI solution processes messages.</span></span>  
  
 <span data-ttu-id="5c2c5-106">**Propósito:** en este paso, comprobará que la orquestación EAIProcess procesa los mensajes correctamente.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-106">**Purpose:** In this step, you check that the EAIProcess orchestration processes messages correctly.</span></span> <span data-ttu-id="5c2c5-107">Para ello, soltará los mensajes de muestra en la ubicación de recepción especificada para la aplicación EAI.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-107">You do this by dropping sample messages into the receive location specified for the EAI application.</span></span> <span data-ttu-id="5c2c5-108">Si la solución EAI funciona correctamente, cuando la orquestación EAIProcess recibe un mensaje del almacén para solicitar más de 500 elementos, la orquestación genera un mensaje de solicitud de rechazo.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-108">If the EAI solution is working properly, if the EAIProcess orchestration receives a message from the warehouse requesting more than 500 items, the orchestration generates a decline request message.</span></span> <span data-ttu-id="5c2c5-109">Cuando la orquestación EAIProcess recibe un mensaje del almacén para solicitar menos de 500 elementos, la orquestación pasa el mensaje al sistema ERP.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-109">If the EAIProcess orchestration receives a message from the warehouse requesting fewer than 500 items, the orchestration passes the message on to the ERP system.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5c2c5-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="5c2c5-110">Prerequisites</span></span>  
 <span data-ttu-id="5c2c5-111">Antes de comenzar este paso debe completar [paso 2: configurar e iniciar la aplicación](../core/step-2-configure-and-start-the-application1.md).</span><span class="sxs-lookup"><span data-stu-id="5c2c5-111">Before you begin this step you must complete [Step 2: Configure and Start the Application](../core/step-2-configure-and-start-the-application1.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="5c2c5-112">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="5c2c5-112">Procedures</span></span>  
  
#### <a name="to-test-the-eai-solution"></a><span data-ttu-id="5c2c5-113">Para probar la solución EAI</span><span class="sxs-lookup"><span data-stu-id="5c2c5-113">To test the EAI solution</span></span>  
  
1.  <span data-ttu-id="5c2c5-114">Abra el Explorador de Windows y vaya a **C:\BTSTutorials\WareHouse**.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-114">Open Windows Explorer, and navigate to **C:\BTSTutorials\WareHouse**.</span></span>  <span data-ttu-id="5c2c5-115">Esta carpeta se crea al instalar los archivos del tutorial.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-115">This folder is created by installing the tutorial files.</span></span>  
  
2.  <span data-ttu-id="5c2c5-116">Copia **RequestInstance.XML** y péguelo en **C:\BTSTutorials\WareHouse\Request**.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-116">Copy **RequestInstance.XML** and paste it into **C:\BTSTutorials\WareHouse\Request**.</span></span>  
  
3.  <span data-ttu-id="5c2c5-117">Cuando el archivo desaparezca, compruebe **C:\BTSTutorials\ERP\Request**.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-117">When the file disappears, check **C:\BTSTutorials\ERP\Request**.</span></span>  
  
4.  <span data-ttu-id="5c2c5-118">En el Explorador de Windows, vaya a **C:\BTSTutorials\WareHouse**.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-118">In Windows Explorer, navigate to **C:\BTSTutorials\WareHouse**.</span></span>  
  
5.  <span data-ttu-id="5c2c5-119">Copia **RequestInstance (por encima del límite). XML** y péguelo en **C:\BTSTutorials\WareHouse\Request**.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-119">Copy **RequestInstance(Over Limit).XML** and paste it into **C:\BTSTutorials\WareHouse\Request**.</span></span>  
  
6.  <span data-ttu-id="5c2c5-120">Cuando el archivo desaparezca, compruebe **C:\BTSTutorials\WareHouse\RequestDecline**.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-120">When the file disappears, check **C:\BTSTutorials\WareHouse\RequestDecline**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="5c2c5-121">Síntesis</span><span class="sxs-lookup"><span data-stu-id="5c2c5-121">What did I just do?</span></span>  
 <span data-ttu-id="5c2c5-122">Ha probado la solución EAI mediante la colocación de mensajes de muestra en la ubicación de recepción de la aplicación EAI.</span><span class="sxs-lookup"><span data-stu-id="5c2c5-122">You tested the EAI solution by placing sample messages in the receive location for the EAI application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c2c5-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c2c5-123">See Also</span></span>  
 <span data-ttu-id="5c2c5-124">[Paso 1: Implementar los proyectos](../core/step-1-deploy-the-projects.md) </span><span class="sxs-lookup"><span data-stu-id="5c2c5-124">[Step 1: Deploy the Projects](../core/step-1-deploy-the-projects.md) </span></span>  
 [<span data-ttu-id="5c2c5-125">Paso 2: Configurar e iniciar la aplicación</span><span class="sxs-lookup"><span data-stu-id="5c2c5-125">Step 2: Configure and Start the Application</span></span>](../core/step-2-configure-and-start-the-application1.md)