---
title: 'Paso 2: Configurar el controlador de pruebas de carga y de los equipos agente | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e9d937ac-55d8-48fa-bba2-3efe151587b8
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0f931a05796856816e19b53ff5cba9f53b48c3e2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-2-configure-load-test-controller-and-agent-computers"></a><span data-ttu-id="3ffda-102">Paso 2: Configurar el controlador de pruebas de carga y equipos de agente</span><span class="sxs-lookup"><span data-stu-id="3ffda-102">Step 2: Configure Load Test Controller and Agent Computers</span></span>
<span data-ttu-id="3ffda-103">Edición Visual Studio 2010 Ultimate puede generar carga simular hasta 250 usuarios virtuales en una serie de pruebas de carga local.</span><span class="sxs-lookup"><span data-stu-id="3ffda-103">Visual Studio 2010 Ultimate edition can generate load simulating up to 250 virtual users on a local load test run.</span></span> <span data-ttu-id="3ffda-104">Para simular más de 250 usuarios virtuales o para iniciar la prueba desde un equipo remoto equipo requiere Visual Studio Load Test Virtual usuario Pack 2010.</span><span class="sxs-lookup"><span data-stu-id="3ffda-104">To simulate more than 250 virtual users and/or to initiate testing from a remote computer requires Visual Studio Load Test Virtual User Pack 2010.</span></span>  
  
 <span data-ttu-id="3ffda-105">Todas las pruebas de carga realizadas para esta guía se inició desde dos equipos:</span><span class="sxs-lookup"><span data-stu-id="3ffda-105">All load testing performed for this guide was initiated from two computers:</span></span>  
  
-   <span data-ttu-id="3ffda-106">Un equipo que ejecuta como un controlador de pruebas de carga y un agente de prueba de carga.</span><span class="sxs-lookup"><span data-stu-id="3ffda-106">One computer running as both a Load Test Controller and a Load Test Agent.</span></span>  
  
-   <span data-ttu-id="3ffda-107">Otro equipo que ejecute como sólo un agente de prueba de carga.</span><span class="sxs-lookup"><span data-stu-id="3ffda-107">Another computer running as a Load Test Agent only.</span></span>  
  
 <span data-ttu-id="3ffda-108">Resultados de pruebas se almacenan en un repositorio de resultados de pruebas de carga remoto en una base de datos de SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="3ffda-108">Test results were stored in a remote load test results repository in a SQL Server 2008 R2 database.</span></span>  
  
 <span data-ttu-id="3ffda-109">Para obtener más información sobre el uso de controladores de pruebas y agentes de prueba para distribuir las pruebas de carga entre varias máquinas de pruebas, vea [distribuir cargar pruebas en varias pruebas máquinas usando controladores de pruebas y agentes de prueba](http://go.microsoft.com/fwlink/?LinkId=208406) (http:// ¿go.Microsoft.com/fwlink/? LinkId = 208406).</span><span class="sxs-lookup"><span data-stu-id="3ffda-109">For more information about using test controllers and test agents to distribute load tests across multiple test machines, see [Distributing Load Tests Across Multiple Test Machines Using Test Controllers and Test Agents](http://go.microsoft.com/fwlink/?LinkId=208406) (http://go.microsoft.com/fwlink/?LinkId=208406).</span></span>  
  
## <a name="install-and-configure-the-load-test-controller-and-load-test-agents"></a><span data-ttu-id="3ffda-110">Instalar y configurar la carga de los agentes de prueba de carga y el controlador de pruebas</span><span class="sxs-lookup"><span data-stu-id="3ffda-110">Install and Configure the Load Test Controller and Load Test Agents</span></span>  
 <span data-ttu-id="3ffda-111">Para instalar y configurar el controlador de pruebas de carga y agentes de prueba de carga, consulte las secciones siguientes en el tema [instalar y configurar los agentes de Visual Studio y prueba y controladores de compilación](http://go.microsoft.com/fwlink/?LinkId=208455) (http://go.microsoft.com/fwlink/?LinkId=208455):</span><span class="sxs-lookup"><span data-stu-id="3ffda-111">To install and configure the load test controller and load test agents, see the following sections in the topic [Installing and Configuring Visual Studio Agents and Test and Build Controllers](http://go.microsoft.com/fwlink/?LinkId=208455) (http://go.microsoft.com/fwlink/?LinkId=208455):</span></span>  
  
-   <span data-ttu-id="3ffda-112">Para configurar un controlador de pruebas, siga los procedimientos descritos en la [instalar un controlador de pruebas](http://go.microsoft.com/fwlink/?LinkId=208454) sección (http://go.microsoft.com/fwlink/?LinkId=208454).</span><span class="sxs-lookup"><span data-stu-id="3ffda-112">To setup a test controller, follow the procedures in the [Install a Test Controller](http://go.microsoft.com/fwlink/?LinkId=208454) (http://go.microsoft.com/fwlink/?LinkId=208454) section.</span></span>  
  
-   <span data-ttu-id="3ffda-113">Para configurar agentes de prueba, siga los procedimientos descritos en la [instalar un agente de prueba](http://go.microsoft.com/fwlink/?LinkId=208456) sección (http://go.microsoft.com/fwlink/?LinkId=208456).</span><span class="sxs-lookup"><span data-stu-id="3ffda-113">To setup test agents, follow the procedures in the [Install a Test Agent](http://go.microsoft.com/fwlink/?LinkId=208456) (http://go.microsoft.com/fwlink/?LinkId=208456) section.</span></span>