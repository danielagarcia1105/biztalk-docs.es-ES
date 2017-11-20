---
title: "Cómo consumir matrices de servicios Web | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SOAP adapters, Web services
- Web services, arrays
- orchestrations, Web services
- orchestrations, Web ports
ms.assetid: 29ecaaed-aa8a-4cf9-a7c8-4b0d6dd412ac
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e78f12405c9c331a888a268d39e2a1520c84fdc8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-consume-web-service-arrays"></a><span data-ttu-id="016c6-102">Cómo consumir matrices de servicios Web</span><span class="sxs-lookup"><span data-stu-id="016c6-102">How to Consume Web Service Arrays</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="016c6-103"> proporciona la capacidad de consumir las matrices expuestas en servicios Web de una orquestación de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="016c6-103"> provides the ability to consume arrays that are exposed in Web services from a BizTalk Orchestration.</span></span>  
  
 <span data-ttu-id="016c6-104">**Para configurar una orquestación para consumir una matriz expuesta en un servicio Web:**</span><span class="sxs-lookup"><span data-stu-id="016c6-104">**To configure an Orchestration to consume an array exposed in a Web service:**</span></span>  
  
 <span data-ttu-id="016c6-105">Determine la URL para el servicio Web que expone las matrices.</span><span class="sxs-lookup"><span data-stu-id="016c6-105">Determine the URL for the Web service that exposes arrays.</span></span> <span data-ttu-id="016c6-106">Ésta corresponde normalmente a una página Web asmx que enumera las operaciones admitidas por el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="016c6-106">This is typically an asmx Web page that lists the operations supported by the Web service.</span></span> <span data-ttu-id="016c6-107">Por ejemplo: http://localhost/ArrayWS/ArraySvc.asmx.</span><span class="sxs-lookup"><span data-stu-id="016c6-107">For example: http://localhost/ArrayWS/ArraySvc.asmx.</span></span>  
  
1.  <span data-ttu-id="016c6-108">Agregue una referencia Web a esta URL en el proyecto de Visual Studio que contenga su orquestación.</span><span class="sxs-lookup"><span data-stu-id="016c6-108">Add a Web reference to this URL in the Visual Studio project that contains your orchestration:</span></span>  
  
    -   <span data-ttu-id="016c6-109">En el Explorador de soluciones, haga clic en **referencias**y haga clic en **Agregar referencia de servicio**.</span><span class="sxs-lookup"><span data-stu-id="016c6-109">In the Solution Explorer, right-click **References**, and click **Add Service Reference**.</span></span>  
  
    -   <span data-ttu-id="016c6-110">En el **Agregar referencia de servicio** cuadro de diálogo, haga clic en **avanzadas**.</span><span class="sxs-lookup"><span data-stu-id="016c6-110">In the **Add Service Reference** dialog box, click **Advanced**.</span></span>  
  
    -   <span data-ttu-id="016c6-111">En el **configuración de referencia de servicio** cuadro de diálogo, haga clic en **Agregar referencia Web** en el **compatibilidad** sección.</span><span class="sxs-lookup"><span data-stu-id="016c6-111">In the **Service Reference Settings** dialog box, click **Add Web Reference** in the **Compatibility** section.</span></span>  
  
    -   <span data-ttu-id="016c6-112">En el **Agregar referencia Web** diálogo cuadro, escriba la dirección URL para el servicio Web en el **URL** cuadro de texto y, a continuación, haga clic en **vaya**.</span><span class="sxs-lookup"><span data-stu-id="016c6-112">In the **Add Web Reference** dialog box, enter the URL for the Web service into the **URL** text box and then click **Go**.</span></span>  
  
    -   <span data-ttu-id="016c6-113">Escriba un nombre para la referencia Web en el **nombre de referencia Web** cuadro de texto y haga clic en el **Agregar referencia** botón.</span><span class="sxs-lookup"><span data-stu-id="016c6-113">Enter a name for the Web reference into the **Web reference name** text box and click the **Add Reference** button.</span></span>  
  
    -   <span data-ttu-id="016c6-114">La referencia Web aparecerá en **referencias Web** en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="016c6-114">The Web reference will appear under **Web References** in the Solution Explorer.</span></span>  
  
        > [!TIP]
        >  <span data-ttu-id="016c6-115">Una vez haya agregado al proyecto una referencia Web la **Agregar referencia Web** comando está directamente disponible cuando hace clic en el nombre del proyecto o **referencias** o **referencias Web**.</span><span class="sxs-lookup"><span data-stu-id="016c6-115">Once you have a Web reference added to the project, the **Add Web Reference** command is directly available when you right-click the project name or **References** or **Web References**.</span></span>  
  
2.  <span data-ttu-id="016c6-116">Agregar un puerto Web a la orquestación:</span><span class="sxs-lookup"><span data-stu-id="016c6-116">Add a Web port to your orchestration:</span></span>  
  
    -   <span data-ttu-id="016c6-117">Arrastre un **puerto** superficies de forma desde el cuadro de herramientas a uno de los puertos en el Diseñador de orquestaciones para iniciar la **Asistente de configuración de puerto**.</span><span class="sxs-lookup"><span data-stu-id="016c6-117">Drag a **Port** shape from the toolbox to one of the port surfaces in the Orchestration Designer to launch the **Port Configuration Wizard**.</span></span> <span data-ttu-id="016c6-118">Haga clic en el **siguiente** botón en el **Asistente para configuración de puertos** para mostrar la **propiedades de puerto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="016c6-118">Click the **Next** button in the **Port Configuration Wizard** to display the **Port Properties** dialog.</span></span>  
  
    -   <span data-ttu-id="016c6-119">Especifique un valor para el **nombre** cuadro de texto para identificar el puerto y haga clic en el **siguiente** botón para mostrar el **seleccionar un tipo de puerto** cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="016c6-119">Enter a value into the **Name** text box to identify the port, and click the **Next** button to display the **Select a Port Type** dialog.</span></span>  
  
    -   <span data-ttu-id="016c6-120">Seleccione la opción de **utilizar un tipo de puerto existente**, seleccione el puerto Web tipo que corresponde a la Web hacen referencia a que ha agregado y haga clic en el **siguiente** botón para mostrar el **deenlacedepuerto**cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="016c6-120">Select the option to **Use an existing Port Type**, select the Web Port type that corresponds to the Web reference you added, and click the **Next** button to display the **Port Binding** dialog.</span></span>  
  
    -   <span data-ttu-id="016c6-121">En el **enlace de puerto** cuadro de diálogo Seleccione la **enlace de puerto** opción y haga clic en el **siguiente** , a continuación, haga clic en el **finalizar** botón.</span><span class="sxs-lookup"><span data-stu-id="016c6-121">In the **Port Binding** dialog select the appropriate **Port binding** option and click the **Next** button, then click the **Finish** button.</span></span> <span data-ttu-id="016c6-122">Ahora debería tener un puerto Web que se muestra en el Diseñador de orquestaciones que incluya las operaciones admitidas por el servicio Web.</span><span class="sxs-lookup"><span data-stu-id="016c6-122">You should now have a Web port displayed in the Orchestration Designer that includes the operations supported by the Web service.</span></span>  
  
3.  <span data-ttu-id="016c6-123">Agregar **enviar** y **recepción** formas a la orquestación según corresponda:</span><span class="sxs-lookup"><span data-stu-id="016c6-123">Add **Send** and **Receive** shapes to your Orchestration as appropriate:</span></span>  
  
    -   <span data-ttu-id="016c6-124">Arrastre un **enviar** forma desde el cuadro de herramientas a una línea de conexión en la superficie del Diseñador de orquestaciones para configurar la orquestación para enviar un mensaje de solicitud al puerto Web.</span><span class="sxs-lookup"><span data-stu-id="016c6-124">Drag a **Send** shape from the toolbox to a connecting line in the Orchestration Designer surface to configure the orchestration to send a request message to the Web port.</span></span> <span data-ttu-id="016c6-125">Si se conecta el **enviar** forma a uno del puerto Web de conectores de mensajes de solicitud, BizTalk creará automáticamente un mensaje del tipo adecuado que se utilizará al enviar un mensaje de solicitud a este puerto.</span><span class="sxs-lookup"><span data-stu-id="016c6-125">If you connect the **Send** shape to one of the Web port request message connectors, BizTalk will automatically create a message of the appropriate type to be used when sending a request message to this port.</span></span>  
  
    -   <span data-ttu-id="016c6-126">Arrastre un **recepción** forma desde el cuadro de herramientas a una línea de conexión en la superficie del Diseñador de orquestaciones para configurar la orquestación para recibir un mensaje de respuesta del puerto Web.</span><span class="sxs-lookup"><span data-stu-id="016c6-126">Drag a **Receive** shape from the toolbox to a connecting line in the Orchestration Designer surface to configure the orchestration to receive a response message from the Web port.</span></span> <span data-ttu-id="016c6-127">Si se conecta el **recepción** forma a uno de los conectores de mensaje de respuesta de puerto Web, BizTalk creará automáticamente un mensaje del tipo adecuado que se utilizará al recibir un mensaje de respuesta de este puerto.</span><span class="sxs-lookup"><span data-stu-id="016c6-127">If you connect the **Receive** shape to one of the Web port response message connectors, BizTalk will automatically create a message of the appropriate type to be used when receiving a response message from this port.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="016c6-128">Use el adaptador de SOAP para enviar o recibir mensajes desde un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="016c6-128">Use the SOAP Adapter to send messages to or receive messages from a Web service.</span></span> <span data-ttu-id="016c6-129">Para obtener más información acerca de cómo configurar el adaptador de SOAP, vea [configurar el adaptador de SOAP](../core/configuring-the-soap-adapter.md).</span><span class="sxs-lookup"><span data-stu-id="016c6-129">For more information about configuring the SOAP Adapter see [Configuring the SOAP Adapter](../core/configuring-the-soap-adapter.md).</span></span>  
  
 <span data-ttu-id="016c6-130">El [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] motor de orquestaciones proporciona compatibilidad para consumir una dimensión y escalonadas matrices expuestas por los servicios Web.</span><span class="sxs-lookup"><span data-stu-id="016c6-130">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Orchestration Engine provides support for consuming both one dimensional and jagged arrays that are exposed by Web services.</span></span> <span data-ttu-id="016c6-131">Si agrega una referencia Web a un servicio Web que exponga matrices, el Diseñador de orquestaciones generará un tipo de mensaje Web que describa la matriz.</span><span class="sxs-lookup"><span data-stu-id="016c6-131">If you add a Web reference to a Web service that exposes arrays, the Orchestration Designer will generate a Web message type that describes the array.</span></span> <span data-ttu-id="016c6-132">Puede enviar y recibir mensajes de este tipo de la misma forma que con cualquier otro mensaje.</span><span class="sxs-lookup"><span data-stu-id="016c6-132">You can then send and receive messages of this type like any other message.</span></span> <span data-ttu-id="016c6-133">BizTalk Server no limita el envío de mensajes Web que contengan matrices para solo puertos Web.</span><span class="sxs-lookup"><span data-stu-id="016c6-133">BizTalk Server does not limit the sending of Web messages containing arrays to only Web ports.</span></span>  
  
 <span data-ttu-id="016c6-134">Para obtener un ejemplo sobre cómo consumir matrices de servicios Web, vea el ejemplo SDK "Consume Web Services" y "Consume Web Services with Array Parameters" en [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span><span class="sxs-lookup"><span data-stu-id="016c6-134">For an example of consuming Web service arrays, see the SDK sample "Consume Web Services" and "Consuming Web Services with Array Parameters" at [http://go.microsoft.com/fwlink/?LinkId=73703](http://go.microsoft.com/fwlink/?LinkId=73703).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="016c6-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="016c6-135">See Also</span></span>  
 [<span data-ttu-id="016c6-136">Usar mensajes en orquestaciones</span><span class="sxs-lookup"><span data-stu-id="016c6-136">Using Messages in Orchestrations</span></span>](../core/using-messages-in-orchestrations.md)