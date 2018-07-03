---
title: 'Paso 2: Configurar el controlador de pruebas de carga y los equipos agente | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e9d937ac-55d8-48fa-bba2-3efe151587b8
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b03a191269936311d04f7b773ed3159db66e34f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972453"
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a><span data-ttu-id="8d559-102">Paso 2: Configurar el controlador de pruebas de carga y equipos de agente</span><span class="sxs-lookup"><span data-stu-id="8d559-102">Step 2: Configure Load Test Controller and Agent Computers</span></span>

## <a name="overview"></a><span data-ttu-id="8d559-103">Información general</span><span class="sxs-lookup"><span data-stu-id="8d559-103">Overview</span></span>
<span data-ttu-id="8d559-104">Visual Studio puede generar carga simular hasta 250 usuarios virtuales en una serie de pruebas de carga local.</span><span class="sxs-lookup"><span data-stu-id="8d559-104">Visual Studio can generate load simulating up to 250 virtual users on a local load test run.</span></span> <span data-ttu-id="8d559-105">Para simular más de 250 usuarios virtuales o para iniciar las pruebas desde un equipo remoto equipo requiere Visual Studio Load Test Virtual usuario.</span><span class="sxs-lookup"><span data-stu-id="8d559-105">To simulate more than 250 virtual users and/or to initiate testing from a remote computer requires Visual Studio Load Test Virtual User.</span></span>  
  
 <span data-ttu-id="8d559-106">Todas las pruebas de carga realizadas en esta guía se inició desde dos equipos:</span><span class="sxs-lookup"><span data-stu-id="8d559-106">All load testing performed for this guide was initiated from two computers:</span></span>  
  
- <span data-ttu-id="8d559-107">Un equipo que se ejecuta como un controlador de pruebas de carga y un agente de prueba de carga.</span><span class="sxs-lookup"><span data-stu-id="8d559-107">One computer running as both a Load Test Controller and a Load Test Agent.</span></span>  
  
- <span data-ttu-id="8d559-108">Otro equipo que se ejecuta como un agente de prueba de carga solo.</span><span class="sxs-lookup"><span data-stu-id="8d559-108">Another computer running as a Load Test Agent only.</span></span>  
  
  <span data-ttu-id="8d559-109">Los resultados de pruebas se almacenan en un repositorio de resultados de pruebas de carga remoto en una base de datos de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="8d559-109">Test results were stored in a remote load test results repository in a SQL Server database.</span></span>  
  
  <span data-ttu-id="8d559-110">Para obtener más información sobre cómo usar controladores de pruebas y agentes de prueba para distribuir las pruebas de carga entre varias máquinas de prueba, consulte [distribuir pruebas de carga a través de varias pruebas máquinas utilizando probar controladores y agentes de pruebas](https://msdn.microsoft.com/library/dd728093.aspx).</span><span class="sxs-lookup"><span data-stu-id="8d559-110">For more information about using test controllers and test agents to distribute load tests across multiple test machines, see [Distributing Load Tests Across Multiple Test Machines Using Test Controllers and Test Agents](https://msdn.microsoft.com/library/dd728093.aspx).</span></span>  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a><span data-ttu-id="8d559-111">Instalar y configurar la carga de los agentes de prueba de carga y el controlador de pruebas</span><span class="sxs-lookup"><span data-stu-id="8d559-111">Install and Configure the Load Test Controller and Load Test Agents</span></span>  
 <span data-ttu-id="8d559-112">Para instalar y configurar el controlador de pruebas de carga y los agentes de prueba de carga, consulte [instalar y configurar agentes de prueba](https://docs.microsoft.com/visualstudio/test/lab-management/install-configure-test-agents).</span><span class="sxs-lookup"><span data-stu-id="8d559-112">To install and configure the load test controller and load test agents, see [Install and configure test agents](https://docs.microsoft.com/visualstudio/test/lab-management/install-configure-test-agents).</span></span>
