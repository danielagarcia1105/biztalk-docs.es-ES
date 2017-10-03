---
title: Con Visual Studio para facilitar la prueba automatizada | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 78f622af-08d5-480c-bd5e-f1db52e8d490
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43d6e7d9757ccfe0a5c633dab926f2acbec7e5df
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-visual-studio-to-facilitate-automated-testing"></a><span data-ttu-id="ad179-102">Con Visual Studio para facilitar la prueba automatizada</span><span class="sxs-lookup"><span data-stu-id="ad179-102">Using Visual Studio to Facilitate Automated Testing</span></span>
<span data-ttu-id="ad179-103">Visual Studio 2010 proporciona funcionalidad de prueba de carga eficaz que puede simular un perfil de carga de hasta cientos de usuarios que acceden al mismo tiempo a una aplicación de servidor.</span><span class="sxs-lookup"><span data-stu-id="ad179-103">Visual Studio 2010 provides powerful load test functionality that can simulate a load profile of up to hundreds of users simultaneously accessing a server application.</span></span> <span data-ttu-id="ad179-104">Esta funcionalidad de la prueba de carga proporciona métricas de tiempo real para los indicadores clave de rendimiento seleccionado, así como la capacidad para almacenar estas métricas en una base de datos para su posterior análisis.</span><span class="sxs-lookup"><span data-stu-id="ad179-104">This load testing functionality provides real time metrics for selected key performance indicators as well as the ability to store these metrics in a database for future analysis.</span></span> <span data-ttu-id="ad179-105">Esta sección describe el uso de Visual Studio de pruebas de carga para evaluar el rendimiento de una aplicación de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="ad179-105">This section describes the use of Visual Studio Load testing to evaluate the performance of a BizTalk Server application.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ad179-106">En esta sección</span><span class="sxs-lookup"><span data-stu-id="ad179-106">In This Section</span></span>  
  
-   [<span data-ttu-id="ad179-107">Paso 1: Crear una prueba unitaria para enviar documentos a BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ad179-107">Step 1: Create a Unit Test to Submit Documents to BizTalk Server</span></span>](../technical-guides/step-1-create-a-unit-test-to-submit-documents-to-biztalk-server.md)  
  
-   [<span data-ttu-id="ad179-108">Paso 2: Configurar el controlador de pruebas de carga y equipos de agente</span><span class="sxs-lookup"><span data-stu-id="ad179-108">Step 2: Configure Load Test Controller and Agent Computers</span></span>](../technical-guides/step-2-configure-load-test-controller-and-agent-computers.md)  
  
-   [<span data-ttu-id="ad179-109">Paso 3: Crear una prueba de carga para llevar a cabo al mismo tiempo varias pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="ad179-109">Step 3: Create a Load Test to Perform Multiple Unit Tests Simultaneously</span></span>](../technical-guides/step-3-create-a-load-test-to-perform-multiple-unit-tests-simultaneously.md)  
  
-   [<span data-ttu-id="ad179-110">Paso 4: Configurar el entorno de BizTalk Server para pruebas de carga</span><span class="sxs-lookup"><span data-stu-id="ad179-110">Step 4: Configure BizTalk Server Environment for Load Testing</span></span>](~/technical-guides/step-4-configure-biztalk-server-environment-for-load-testing.md)  
  
-   [<span data-ttu-id="ad179-111">Paso 5: Realizar pruebas de patrón de carga de paso para determinar el rendimiento máximo sostenible</span><span class="sxs-lookup"><span data-stu-id="ad179-111">Step 5: Perform Step Load Pattern Tests to Determine Maximum Sustainable Throughput</span></span>](../technical-guides/step-5-complete-step-load-tests-to-determine-maximum-sustainable-throughput.md)  
  
-   [<span data-ttu-id="ad179-112">Paso 6: Realizar pruebas de modelo de carga constante para comprobar el rendimiento máximo sostenible</span><span class="sxs-lookup"><span data-stu-id="ad179-112">Step 6: Perform Constant Load Pattern Tests to Verify Maximum Sustainable Throughput</span></span>](../technical-guides/step-6-complete-load-pattern-tests-to-verify-maximum-sustainable-throughput.md)