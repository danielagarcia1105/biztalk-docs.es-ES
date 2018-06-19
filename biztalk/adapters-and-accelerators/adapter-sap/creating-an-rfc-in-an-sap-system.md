---
title: Información general de creación de una solicitud de cambio en una SAP para utilizar con el adaptador SAP en BizTalk | Documentos de Microsoft
description: 'Crear una solicitud de cambio, RFC destino y envíe una solicitud de cambio de sistema SAP: módulo de adaptador de BizTalk (BAP)'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 35937183-fc1e-49cd-8a75-8f62effe0013
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 802a2e33b8bc902dc784276ce7c1d9c3f37f3b12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216524"
---
# <a name="create-and-send-an-rfc-in-sap"></a><span data-ttu-id="741b9-103">Crear y enviar una solicitud de cambio en SAP</span><span class="sxs-lookup"><span data-stu-id="741b9-103">Create and send an RFC in SAP</span></span>
<span data-ttu-id="741b9-104">Enumera las tareas de alto nivel que se complete en el sistema SAP para crear una solicitud de cambio.</span><span class="sxs-lookup"><span data-stu-id="741b9-104">Lists high-level tasks to complete on the SAP system to create an RFC.</span></span> <span data-ttu-id="741b9-105">Cada tarea puede implicar procedimientos muy detallados.</span><span class="sxs-lookup"><span data-stu-id="741b9-105">Each task may involve very detailed procedures.</span></span> <span data-ttu-id="741b9-106">Como resultado, se recomienda ponerse en contacto con el Administrador de SAP para completar estas tareas, o consulte la Guía de SAP.</span><span class="sxs-lookup"><span data-stu-id="741b9-106">As a result, we recommend contacting your SAP administrator to complete these tasks, or refer to the SAP guidance.</span></span>  
  
## <a name="create-an-rfc"></a><span data-ttu-id="741b9-107">Crear una solicitud de cambio</span><span class="sxs-lookup"><span data-stu-id="741b9-107">Create an RFC</span></span>  
  
1.  <span data-ttu-id="741b9-108">Inicie la GUI de SAP.</span><span class="sxs-lookup"><span data-stu-id="741b9-108">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="741b9-109">Vaya a la transacción SE37 (generador de función), escriba el nombre RFC y haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="741b9-109">Go to Transaction SE37 (Function Builder), enter the RFC name, and click **Create**.</span></span>  
  
3.  <span data-ttu-id="741b9-110">Escriba un función grupo existente en la que se creará la solicitud de cambio, una descripción breve de la solicitud de cambio y haga clic en **guardar**.</span><span class="sxs-lookup"><span data-stu-id="741b9-110">Enter an existing function group under which the RFC will be created, a short description for the RFC, and click **Save**.</span></span>  
  
4.  <span data-ttu-id="741b9-111">En el **atributos** ficha, seleccione la **Remote-Enabled módulo** botón de radio.</span><span class="sxs-lookup"><span data-stu-id="741b9-111">In the **Attributes** tab, select the **Remote-Enabled Module** radio button.</span></span>  
  
5.  <span data-ttu-id="741b9-112">En el **importar** ficha, especifique los parámetros de importación.</span><span class="sxs-lookup"><span data-stu-id="741b9-112">In the **Import** tab, enter the import parameters.</span></span> <span data-ttu-id="741b9-113">Estos parámetros se utilizan para pasar los datos externos para el módulo de función.</span><span class="sxs-lookup"><span data-stu-id="741b9-113">These parameters are used for passing the external data to the function module.</span></span>  
  
6.  <span data-ttu-id="741b9-114">En el **exportar** ficha, especifique los parámetros de exportación.</span><span class="sxs-lookup"><span data-stu-id="741b9-114">In the **Export** tab, enter the export parameters.</span></span>  
  
7.  <span data-ttu-id="741b9-115">En el **Changing** ficha, especifique los parámetros de la variables.</span><span class="sxs-lookup"><span data-stu-id="741b9-115">In the **Changing** tab, enter the changing parameters.</span></span>  
  
8.  <span data-ttu-id="741b9-116">En el **tablas** ficha, escriba los nombres de tabla.</span><span class="sxs-lookup"><span data-stu-id="741b9-116">In the **Tables** tab, enter the table names.</span></span>  
  
9. <span data-ttu-id="741b9-117">En el **excepciones** ficha, escriba las excepciones para controlar los errores.</span><span class="sxs-lookup"><span data-stu-id="741b9-117">In the **Exceptions** tab, enter the exceptions to handle errors.</span></span>  
  
10. <span data-ttu-id="741b9-118">En el **código fuente** ficha, escriba el código fuente (lógica) para la solicitud de cambio.</span><span class="sxs-lookup"><span data-stu-id="741b9-118">In the **Source Code** tab, enter the source code (logic) for the RFC.</span></span>  
  
11. <span data-ttu-id="741b9-119">Haga clic en el **activar** icono en la barra de herramientas para activar el módulo de función.</span><span class="sxs-lookup"><span data-stu-id="741b9-119">Click the **Activate** icon on the toolbar to activate the function module.</span></span>  

## <a name="create-an-rfc-destination"></a><span data-ttu-id="741b9-120">Crear un destino RFC</span><span class="sxs-lookup"><span data-stu-id="741b9-120">Create an RFC destination</span></span>  
  
1.  <span data-ttu-id="741b9-121">Inicie la GUI de SAP.</span><span class="sxs-lookup"><span data-stu-id="741b9-121">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="741b9-122">Vaya a SM59 de transacciones (mostrar y mantener destinos RFC).</span><span class="sxs-lookup"><span data-stu-id="741b9-122">Go to Transaction SM59 (Display and Maintain RFC Destinations).</span></span>  
  
3.  <span data-ttu-id="741b9-123">En la barra de menús, haga clic en **crear**.</span><span class="sxs-lookup"><span data-stu-id="741b9-123">From the menu bar, click **Create**.</span></span>  
  
4.  <span data-ttu-id="741b9-124">Escriba el destino RFC, el tipo de conexión, la descripción y, a continuación, presione ENTRAR.</span><span class="sxs-lookup"><span data-stu-id="741b9-124">Enter the RFC destination, connection type, description, and then press Enter.</span></span>  
  
5.  <span data-ttu-id="741b9-125">Seleccione el **programa de servidor registrado** botón de opción, escriba el Id. de programa, el host de puerta de enlace y el servicio de puerta de enlace.</span><span class="sxs-lookup"><span data-stu-id="741b9-125">Select the **Registered Server Program** radio-button, enter the program ID, gateway host, and gateway service.</span></span>  
  
6.  <span data-ttu-id="741b9-126">Guarde el destino RFC.</span><span class="sxs-lookup"><span data-stu-id="741b9-126">Save the RFC destination.</span></span>  

## <a name="send-an-rfc-from-an-sap-system"></a><span data-ttu-id="741b9-127">Enviar una solicitud de cambio de un sistema SAP</span><span class="sxs-lookup"><span data-stu-id="741b9-127">Send an RFC from an SAP system</span></span>  
  
1.  <span data-ttu-id="741b9-128">Inicie la GUI de SAP.</span><span class="sxs-lookup"><span data-stu-id="741b9-128">Start the SAP GUI.</span></span>  
  
2.  <span data-ttu-id="741b9-129">Crear un sistema lógico con la transacción de BD54.</span><span class="sxs-lookup"><span data-stu-id="741b9-129">Create a logical system using BD54 transaction.</span></span>  
  
3.  <span data-ttu-id="741b9-130">Crear un destino RFC en conexiones de TCP/IP con la transacción SM59.</span><span class="sxs-lookup"><span data-stu-id="741b9-130">Create an RFC destination in TCP/IP connections using SM59 transaction.</span></span>  
  
4.  <span data-ttu-id="741b9-131">Crear un puerto mediante transacciones WE21 y adjuntarlo al destino RFC creado en el último paso.</span><span class="sxs-lookup"><span data-stu-id="741b9-131">Create a port using WE21 transaction and attach it to the RFC destination created in the last step.</span></span>  
  
5.  <span data-ttu-id="741b9-132">Desencadenar una solicitud de cambio mediante SE37.</span><span class="sxs-lookup"><span data-stu-id="741b9-132">Trigger an RFC by using SE37.</span></span> <span data-ttu-id="741b9-133">Este RFC debe contener la lógica para realizar una solicitud de cambio de llamar a una aplicación externa y, a continuación, recibir una respuesta de esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="741b9-133">This RFC must contain the logic to make an RFC call to an external application and then receive a response from that application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="741b9-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="741b9-134">See Also</span></span>  
 [<span data-ttu-id="741b9-135">Realizar tareas mediante la GUI de SAP para escenarios de adaptadores SAP específicos</span><span class="sxs-lookup"><span data-stu-id="741b9-135">Performing Tasks Using the SAP GUI for Specific SAP Adapter Scenarios</span></span>](performing-tasks-using-the-sap-gui-for-specific-sap-adapter-scenarios.md)