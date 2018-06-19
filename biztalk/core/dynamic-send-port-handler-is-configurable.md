---
title: Controlador de puerto de envío dinámico es Configurable | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5eb8f5ef-af95-4b2e-9a43-6f1240b25855
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11dffbe28d44d7665bc86ff0842c17ea01f7b3d3
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
ms.locfileid: "22240596"
---
# <a name="dynamic-send-port-handler-is-configurable"></a><span data-ttu-id="09ad2-102">El controlador de puerto de envío dinámico es configurable</span><span class="sxs-lookup"><span data-stu-id="09ad2-102">Dynamic Send Port Handler is Configurable</span></span>
<span data-ttu-id="09ad2-103">Al crear un puerto de envío dinámico, puede configurar un controlador de envío de adaptador para *cada* adaptador instalado.</span><span class="sxs-lookup"><span data-stu-id="09ad2-103">When creating a Dynamic Send Port, an adapter Send Handler is configurable for *every* installed adapter.</span></span> <span data-ttu-id="09ad2-104">Considere el caso siguiente:</span><span class="sxs-lookup"><span data-stu-id="09ad2-104">Consider the following scenario:</span></span>  
  
 <span data-ttu-id="09ad2-105">**Escenario**</span><span class="sxs-lookup"><span data-stu-id="09ad2-105">**Scenario**</span></span>  
  
 <span data-ttu-id="09ad2-106">Hay dos itinerarios de ESB en una aplicación.</span><span class="sxs-lookup"><span data-stu-id="09ad2-106">There are two ESB itineraries in an application.</span></span> <span data-ttu-id="09ad2-107">Itinerary1 usa un puerto de envío dinámico para enviar datos a un recurso compartido de archivo.</span><span class="sxs-lookup"><span data-stu-id="09ad2-107">Itinerary1 uses a Dynamic Send Port to send data to a File share.</span></span> <span data-ttu-id="09ad2-108">Itinerary2 usa un puerto de envío dinámico para enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="09ad2-108">Itinerary2 uses a Dynamic Send Port to send e-mail.</span></span> <span data-ttu-id="09ad2-109">Anteriormente, los puertos de envío dinámicos se ejecutaban en el host predeterminado del adaptador.</span><span class="sxs-lookup"><span data-stu-id="09ad2-109">In the past, Dynamic send ports execute in the adapter's default host.</span></span> <span data-ttu-id="09ad2-110">Itinerary1 está destinado a escenarios de bajo volumen de mensajes de gran tamaño.</span><span class="sxs-lookup"><span data-stu-id="09ad2-110">Itinerary1 is designed to target a low volume - big message size scenario.</span></span> <span data-ttu-id="09ad2-111">Itinerary2 está destinado a escenarios de alto volumen de mensajes de tamaño pequeño.</span><span class="sxs-lookup"><span data-stu-id="09ad2-111">Itinerary2 targets a high volume - small message size scenario.</span></span> <span data-ttu-id="09ad2-112">Puesto que solo hay un host predeterminado para un adaptador, todos los mensajes se enrutan con el mismo host, lo que reduce el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="09ad2-112">Since there is only one default host for an adapter, all messages are routed using the same host, decreasing the performance.</span></span>  
  
 <span data-ttu-id="09ad2-113">**El cambio**</span><span class="sxs-lookup"><span data-stu-id="09ad2-113">**The Change**</span></span>  
  
 <span data-ttu-id="09ad2-114">Para mejorar el rendimiento de los puertos de envío dinámico, puede configurarse un controlador de envío de adaptador para que use cualquier host.</span><span class="sxs-lookup"><span data-stu-id="09ad2-114">To improve the performance of Dynamic Send Ports, an adapter Send Handler is configurable to use any host.</span></span> <span data-ttu-id="09ad2-115">En el escenario de ESB, Itinerary1 usa HostA para enviar datos a un recurso compartido de archivos.</span><span class="sxs-lookup"><span data-stu-id="09ad2-115">In the ESB scenario, Itinerary1 uses HostA to send data to a File share.</span></span> <span data-ttu-id="09ad2-116">Itinerary2 usa un puerto HostB para enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="09ad2-116">Itinerary2 uses HostB Port to send e-mail.</span></span>  
  
## <a name="select-a-send-handler"></a><span data-ttu-id="09ad2-117">Seleccione un controlador de envío</span><span class="sxs-lookup"><span data-stu-id="09ad2-117">Select a Send Handler</span></span>  
 <span data-ttu-id="09ad2-118">Al crear un puerto de envío unidireccional dinámico o un puerto de envío de petición-respuesta dinámico, el controlador de envío se puede configurar para usar cada adaptador instalado.</span><span class="sxs-lookup"><span data-stu-id="09ad2-118">When creating a Dynamic One-Way Send Port or Dynamic Solicit-Response Send Port, the Send Handler is configurable for every installed adapter.</span></span> <span data-ttu-id="09ad2-119">Pasos:</span><span class="sxs-lookup"><span data-stu-id="09ad2-119">Steps:</span></span>  
  
1.  <span data-ttu-id="09ad2-120">En el **administración de BizTalk Server** de la consola, expanda **grupo de BizTalk [*GroupName*]**, expanda **aplicaciones**y, a continuación, expanda la aplicación que contendrá el puerto de envío.</span><span class="sxs-lookup"><span data-stu-id="09ad2-120">In the **BizTalk Server Administration** console, expand **BizTalk Group [*GroupName*]**, expand **Applications**, and then expand the application to contain the send port.</span></span>  
  
2.  <span data-ttu-id="09ad2-121">Haga clic en **puertos de envío**, haga clic en **New**y, a continuación, haga clic en **puerto de envío unidireccional dinámico** o **puerto de envío de petición-respuesta dinámico**.</span><span class="sxs-lookup"><span data-stu-id="09ad2-121">Right-click **Send Ports**, click **New**, and then click **Dynamic One-way Send Port** or **Dynamic Solicit-Response Send Port**.</span></span>  
  
3.  <span data-ttu-id="09ad2-122">En **propiedades**, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="09ad2-122">In  **Properties**, click **Configure**.</span></span>  
  
     <span data-ttu-id="09ad2-123">Los adaptadores se mostrarán con el controlador de envío predeterminado.</span><span class="sxs-lookup"><span data-stu-id="09ad2-123">The adapters are listed with the default Send Handler.</span></span> <span data-ttu-id="09ad2-124">Haga clic en la flecha hacia abajo para seleccionar el host diferente.</span><span class="sxs-lookup"><span data-stu-id="09ad2-124">Click the down arrow to select a different host.</span></span>  
  
4.  <span data-ttu-id="09ad2-125">Haga clic en **Aceptar** guardar la configuración.</span><span class="sxs-lookup"><span data-stu-id="09ad2-125">Click **OK** save the settings.</span></span>  
  
5.  <span data-ttu-id="09ad2-126">De de baja y vuelva a inscribir el nuevo puerto de envío dinámico.</span><span class="sxs-lookup"><span data-stu-id="09ad2-126">Unenlist and reenlist the new dynamic send port.</span></span>  
  
6.  <span data-ttu-id="09ad2-127">Reinicie la instancia de host original.</span><span class="sxs-lookup"><span data-stu-id="09ad2-127">Restart the original host instance.</span></span>  
  
7.  <span data-ttu-id="09ad2-128">Reinicie la instancia de host nueva.</span><span class="sxs-lookup"><span data-stu-id="09ad2-128">Restart the new host instance.</span></span>  
  
 <span data-ttu-id="09ad2-129">Entre las opciones de configuración adicionales del puerto de envío se incluyen:</span><span class="sxs-lookup"><span data-stu-id="09ad2-129">Additional Send Port configuration options include:</span></span>  
  
-   [<span data-ttu-id="09ad2-130">Cómo configurar opciones avanzadas de transporte para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="09ad2-130">How to Configure Transport Advanced Options for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267697)  
  
-   [<span data-ttu-id="09ad2-131">Cómo configurar opciones de copia de seguridad de transporte para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="09ad2-131">How to Configure Backup Transport Options for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267698)  
  
-   [<span data-ttu-id="09ad2-132">Cómo configurar asignaciones de salida para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="09ad2-132">How to Configure Outbound Maps for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267699)  
  
-   [<span data-ttu-id="09ad2-133">Cómo configurar filtros para un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="09ad2-133">How to Configure Filters for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267700)  
  
-   [<span data-ttu-id="09ad2-134">Cómo asignar un certificado a un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="09ad2-134">How to Assign a Certificate to a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267701)  
  
-   [<span data-ttu-id="09ad2-135">Cómo configurar el seguimiento de un puerto de envío</span><span class="sxs-lookup"><span data-stu-id="09ad2-135">How to Configure Tracking for a Send Port</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267702)  
  
 <span data-ttu-id="09ad2-136">Los distintos host se pueden ajustar.</span><span class="sxs-lookup"><span data-stu-id="09ad2-136">The different hosts can be fine-tuned.</span></span> <span data-ttu-id="09ad2-137">Los siguientes vínculos tratan la optimización de rendimiento:</span><span class="sxs-lookup"><span data-stu-id="09ad2-137">The following links discuss performance optimization:</span></span>  
  
 [<span data-ttu-id="09ad2-138">Optimizaciones generales de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="09ad2-138">General BizTalk Server Optimizations</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267703)  
  
 [<span data-ttu-id="09ad2-139">Administración de la configuración de rendimiento de BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="09ad2-139">Managing BizTalk Server Performance Settings</span></span>](http://go.microsoft.com/fwlink/p/?LinkId=267704)