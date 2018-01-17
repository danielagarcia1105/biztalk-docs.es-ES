---
title: "Paso 14: La orquestación como un servicio Web de publicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, publishing
- publishing, orchestrations
- Web services, orchestrations
- message enrichment tutorial, orchestrations
- publishing, Web services
- message enrichment tutorial, Web services
ms.assetid: 8f29a7be-a679-4ca6-a648-35338d9e9e98
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c742d21dd2f2e1d95f697beea3d5d5dfa0461d2
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="step-14-publish-the-orchestration-as-a-web-service"></a><span data-ttu-id="afa8d-102">Paso 14: Publicar la orquestación como servicio Web</span><span class="sxs-lookup"><span data-stu-id="afa8d-102">Step 14: Publish the Orchestration as a Web Service</span></span>
<span data-ttu-id="afa8d-103">En este paso, usa al Asistente para publicación de servicios Web de BizTalk para publicar una orquestación como un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="afa8d-103">In this step, you use the BizTalk Web Services Publishing Wizard to publish your orchestration as a Web service.</span></span>  
  
 <span data-ttu-id="afa8d-104">Antes de publicar la orquestación como un servicio Web, debe asegurarse de que la cuenta de inicio de sesión para BizTalkServerIsolatedHost es parte del grupo de usuarios de hosts aislados de BizTalk, por lo que tiene acceso a las bases de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="afa8d-104">Before publishing the orchestration as a Web service, you need to ensure that the logon account for BizTalkServerIsolatedHost is part of the BizTalk Isolated Host Users group, so it has access to the BizTalk databases.</span></span> <span data-ttu-id="afa8d-105">Esto es necesario porque el controlador de recepción para la ubicación de recepción de SOAPReceivePort que se crea mediante el Asistente de publicación de servicio Web para este tutorial es BizTalkServerIsolatedHost, no BizTalkServerApplication.</span><span class="sxs-lookup"><span data-stu-id="afa8d-105">This is necessary because the receive handler for the SOAPReceivePort receive location that is created by the Web Service Publishing Wizard for this tutorial is BizTalkServerIsolatedHost, not BizTalkServerApplication.</span></span> <span data-ttu-id="afa8d-106">El controlador de recepción es BizTalkServerIsolatedHost porque el adaptador de SOAP se ejecuta en el proceso IIS, no el proceso de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="afa8d-106">The receive handler is BizTalkServerIsolatedHost because the SOAP adapter runs under the IIS process, not the BizTalk process.</span></span>  
  
### <a name="to-ensure-access-privileges-for-the-soapreceiveport-receive-location"></a><span data-ttu-id="afa8d-107">Para garantizar un acceso de ubicación de recepción privilegios para la SOAPReceivePort</span><span class="sxs-lookup"><span data-stu-id="afa8d-107">To ensure access privileges for the SOAPReceivePort receive location</span></span>  
  
1.  <span data-ttu-id="afa8d-108">En la consola de administración de BizTalk Server, en **instancias de Host** en el **configuración de plataforma** nodo, haga clic en **BizTalkServerIsolatedHost**y, a continuación, haga clic en  **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-108">In BizTalk Server Administration Console, under **Host Instances** in the **Platform Settings** node, right-click **BizTalkServerIsolatedHost**, and then click **Properties**.</span></span> <span data-ttu-id="afa8d-109">En el cuadro de diálogo Propiedades, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-109">In the Properties dialog box, click **Configure**.</span></span> <span data-ttu-id="afa8d-110">Tenga en cuenta el **inicio de sesión** cuenta.</span><span class="sxs-lookup"><span data-stu-id="afa8d-110">Note the **Logon** account.</span></span>  
  
2.  <span data-ttu-id="afa8d-111">En el cuadro de diálogo Administración de equipos, en **grupos** en el **usuarios y grupos locales** nodo, haga doble clic en **usuarios de hosts aislados de BizTalk**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-111">In the Computer Management dialog box, under **Groups** in the **Local Users and Groups** node, double-click **BizTalk Isolated Host Users**.</span></span> <span data-ttu-id="afa8d-112">Si tiene en cuenta el inicio de sesión **BizTalkServerIsolatedHost** no es un miembro de **BizTalkServerIsolatedHost**, agregar al grupo.</span><span class="sxs-lookup"><span data-stu-id="afa8d-112">If the logon account for **BizTalkServerIsolatedHost** is not a member of **BizTalkServerIsolatedHost**, add it to the group.</span></span>  
  
### <a name="to-run-the-biztalk-web-services-publishing-wizard"></a><span data-ttu-id="afa8d-113">Para ejecutar al Asistente para publicación de servicios Web de BizTalk</span><span class="sxs-lookup"><span data-stu-id="afa8d-113">To run the BizTalk Web Services Publishing Wizard</span></span>  
  
1.  <span data-ttu-id="afa8d-114">En el Explorador de soluciones de Visual Studio, haga clic en **solución 'BTAHL7V22Common'**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-114">In Solution Explorer of Visual Studio, click **Solution 'BTAHL7V22Common'**.</span></span> <span data-ttu-id="afa8d-115">En el **herramientas** menú, haga clic en **Asistente para publicación de BizTalk Web Services**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-115">On the **Tools** menu, click **BizTalk Web Services Publishing Wizard**.</span></span>  
  
2.  <span data-ttu-id="afa8d-116">En el **Asistente para publicación de BizTalk Web Services**, en la **bienvenida** página, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-116">In the **BizTalk Web Services Publishing Wizard**, on the **Welcome** page, click **Next**.</span></span>  
  
3.  <span data-ttu-id="afa8d-117">En el **crear servicio Web** página, seleccione **publicar orquestaciones de BizTalk como servicios web**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-117">On the **Create Web Service** page, select **Publish BizTalk orchestrations as web services**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="afa8d-118">En el **ensamblado de BizTalk** página, en la **archivo de ensamblado de BizTalk (\\*.dll)** campo, busque o escriba  **\< *unidad* \>: \Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**, haga clic en **BTAHL7 Project.dll**, haga clic en **abiertos**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-118">On the **BizTalk Assembly** page, in the **BizTalk assembly file (\\*.dll)** field, browse to or type **\<*drive*\>:\Tutorial\BTAHL7V22Common\BTAHL7 Project\bin\development**, click **BTAHL7 Project.dll**, click **Open**, and then click **Next**.</span></span>  
  
5.  <span data-ttu-id="afa8d-119">En el **orquestaciones y puertos** página, asegúrese de que todos los nodos están seleccionados y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-119">On the **Orchestrations and Ports** page, ensure that all nodes are selected, and then click **Next**.</span></span>  
  
6.  <span data-ttu-id="afa8d-120">En el **propiedades del servicio Web** página, para **espacio de nombres de destino del servicio web**, tipo **http://localhost**y, a continuación, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-120">On the **Web Service Properties** page, for **Target namespace of web service**, type **http://localhost**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="afa8d-121">En el **proyecto de servicio Web** página, seleccione **permitir el acceso anónimo al servicio web** y **ubicaciones de recepción de BizTalk crea en la siguiente aplicación**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-121">On the **Web Service Project** page, select **Allow anonymous access to web service** and **Create BizTalk receive locations in the following application**.</span></span> <span data-ttu-id="afa8d-122">Seleccione **BizTalk Application 1** para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="afa8d-122">Select **BizTalk Application 1** for the application.</span></span> <span data-ttu-id="afa8d-123">Mantenga el valor predeterminado el **ubicación** campo.</span><span class="sxs-lookup"><span data-stu-id="afa8d-123">Keep the default in the **Location** field.</span></span> <span data-ttu-id="afa8d-124">Haga clic en **siguiente** para aceptar la ubicación predeterminada del proyecto.</span><span class="sxs-lookup"><span data-stu-id="afa8d-124">Click **Next** to accept the default project location.</span></span>  
  
8.  <span data-ttu-id="afa8d-125">En el **resumen del proyecto de servicio Web** página, haga clic en **crear** para generar el proyecto de servicio Web ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="afa8d-125">On the **Web Service Project Summary** page, click **Create** to generate the ASP.NET Web Service project.</span></span>  
  
9. <span data-ttu-id="afa8d-126">Haga clic en **Finalizar** para cerrar el asistente.</span><span class="sxs-lookup"><span data-stu-id="afa8d-126">Click **Finish** to close the wizard.</span></span>  
  
10. <span data-ttu-id="afa8d-127">Abra la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="afa8d-127">Open the BizTalk Server Administration Console.</span></span> <span data-ttu-id="afa8d-128">En la consola, expanda **administración de BizTalk Server**, expanda **grupo de BizTalk**, expanda **aplicaciones**y, a continuación, expanda **BizTalk Application 1** .</span><span class="sxs-lookup"><span data-stu-id="afa8d-128">In the console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
11. <span data-ttu-id="afa8d-129">Haga clic en **ubicaciones de recepción**, haga clic en **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-129">Click **Receive Locations**, right-click **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, and then click **Properties**.</span></span>  
  
12. <span data-ttu-id="afa8d-130">En el cuadro de diálogo Propiedades de la ubicación de recepción, haga clic en **canalización de recepción**, seleccione **Microsoft.BizTalk.DefaultPipelines.XMLReceive** desde la lista desplegable y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-130">In the Receive Location Properties dialog box, click **Receive Pipeline**, select **Microsoft.BizTalk.DefaultPipelines.XMLReceive** from the drop-down list, and then click **OK**.</span></span>  
  
13. <span data-ttu-id="afa8d-131">Haga clic en **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**y, a continuación, haga clic en **habilitar**.</span><span class="sxs-lookup"><span data-stu-id="afa8d-131">Right-click **WebService_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**, and then click **Enable**.</span></span>  
  
 <span data-ttu-id="afa8d-132">Continúe con [paso 15: configurar el envío y puertos de recepción](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md).</span><span class="sxs-lookup"><span data-stu-id="afa8d-132">Proceed to [Step 15: Configure the Send and Receive Ports](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afa8d-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="afa8d-133">See Also</span></span>  
 [<span data-ttu-id="afa8d-134">Tutorial de enriquecimiento de mensajes</span><span class="sxs-lookup"><span data-stu-id="afa8d-134">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)