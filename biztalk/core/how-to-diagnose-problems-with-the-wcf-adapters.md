---
title: Cómo diagnosticar problemas con los adaptadores de WCF | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 997a4ecd-6077-45d6-82d3-3f658ca62fd4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dfa941fb5d19559447740f4f74e00f61b63fdacc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22250532"
---
# <a name="how-to-diagnose-problems-with-the-wcf-adapters"></a><span data-ttu-id="bf348-102">Cómo diagnosticar problemas con los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="bf348-102">How to Diagnose Problems with the WCF Adapters</span></span>
<span data-ttu-id="bf348-103">Esta sección contiene los pasos que pueden seguirse para ayudar al diagnóstico de problemas con los adaptadores de WCF.</span><span class="sxs-lookup"><span data-stu-id="bf348-103">This section contains steps that you can follow to help diagnose problems with the WCF adapters.</span></span>  
  
### <a name="check-the-iis-log-and-httperr-log-of-the-iis-server-for-errors"></a><span data-ttu-id="bf348-104">Compruebe si existen errores detallados en el registro IIS y HTTPERR del servidor IIS</span><span class="sxs-lookup"><span data-stu-id="bf348-104">Check the IIS log and HTTPERR log of the IIS server for errors</span></span>  
  
-   <span data-ttu-id="bf348-105">Los archivos de registro del servidor IIS de origen o de destino pueden contener información útil para la solución de problemas con los adaptadores de WCF aislados.</span><span class="sxs-lookup"><span data-stu-id="bf348-105">The source or target IIS server log files can contain information that is helpful for troubleshooting problems with the isolated WCF adapters.</span></span> <span data-ttu-id="bf348-106">De forma predeterminada, en un equipo [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)], los archivos de registro de IIS se encuentran en el siguiente directorio:</span><span class="sxs-lookup"><span data-stu-id="bf348-106">By default the IIS log files on a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] computer are located in the following directory:</span></span>  
  
     <span data-ttu-id="bf348-107">*% WinDir %\\*system32\LogFiles\W3SVC1\\</span><span class="sxs-lookup"><span data-stu-id="bf348-107">*%WinDir%\\*system32\LogFiles\W3SVC1\\</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf348-108">*% WinDir %* es un marcador de posición para la ubicación de la [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] directorio en el servidor IIS.</span><span class="sxs-lookup"><span data-stu-id="bf348-108">*%WinDir%* is a placeholder for the location of the [!INCLUDE[btsWinNoVersion](../includes/btswinnoversion-md.md)] directory on the IIS server.</span></span>  
  
     <span data-ttu-id="bf348-109">De manera predeterminada, los archivos de registro de HTTPERR en equipos basados en [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] y [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] están ubicados en el directorio siguiente:</span><span class="sxs-lookup"><span data-stu-id="bf348-109">By default the HTTPERR log files on a [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] based computers are located in the following directory:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf348-110">El archivo de registro de HTTPERR únicamente está disponible en equipos basados en [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] y [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf348-110">The HTTPERR log file is available only on [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] and [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] based computers.</span></span>  
  
     <span data-ttu-id="bf348-111">*% WinDir %\\*system32\LogFiles\HTTPERR\\</span><span class="sxs-lookup"><span data-stu-id="bf348-111">*%WinDir%\\*system32\LogFiles\HTTPERR\\</span></span>  
  
### <a name="use-wcf-message-logging-for-fault-monitoring-and-diagnosis-of-problems-from-the-wcf-adapters"></a><span data-ttu-id="bf348-112">Utilizar el registro de mensajes WCF para la supervisión de los errores y el diagnóstico de problemas derivados de los adaptadores de WCF</span><span class="sxs-lookup"><span data-stu-id="bf348-112">Use WCF message logging for fault monitoring and diagnosis of problems from the WCF adapters</span></span>  
  
1.  <span data-ttu-id="bf348-113">WCF ofrece la posibilidad de registrar los mensajes entrantes y salientes para el consumo fuera de línea.</span><span class="sxs-lookup"><span data-stu-id="bf348-113">WCF provides the capability to log incoming and outgoing messages for offline consumption.</span></span> <span data-ttu-id="bf348-114">Puede utilizar el registro de mensajes para ver qué aspecto tienen los mensajes entrantes y salientes a través de los adaptadores de WCF.</span><span class="sxs-lookup"><span data-stu-id="bf348-114">You can use message logging to see what the messages incoming and outgoing through the WCF adapters look like.</span></span> <span data-ttu-id="bf348-115">WCF no registra los mensajes de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="bf348-115">WCF does not log messages by default.</span></span> <span data-ttu-id="bf348-116">Para activar el registro de mensajes, debe modificar los archivos de configuración que utilizan los adaptadores de WCF.</span><span class="sxs-lookup"><span data-stu-id="bf348-116">To activate message logging, you have to modify the configuration files that the WCF adapters use.</span></span> <span data-ttu-id="bf348-117">Para obtener más información sobre el registro de mensajes WCF, consulte "Registro de mensajes" en [http://go.microsoft.com/fwlink/?LinkId=89003](http://go.microsoft.com/fwlink/?LinkId=89003).</span><span class="sxs-lookup"><span data-stu-id="bf348-117">For more information about WCF message logging, see "Message Logging" at [http://go.microsoft.com/fwlink/?LinkId=89003](http://go.microsoft.com/fwlink/?LinkId=89003).</span></span>  
  
2.  <span data-ttu-id="bf348-118">Para los adaptadores WCF en curso, puede habilitar el registro de mensajes WCF modificando el archivo de configuración de aplicación, **BTSNtSvc.exe.config**, para **BTSNtSvc.exe**.</span><span class="sxs-lookup"><span data-stu-id="bf348-118">For the in-process WCF adapters, you can enable WCF message logging by modifying the application configuration file, **BTSNtSvc.exe.config**, for **BTSNtSvc.exe**.</span></span> <span data-ttu-id="bf348-119">El archivo de configuración puede encontrarse en la ruta de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf348-119">The configuration file can be found in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation path.</span></span> <span data-ttu-id="bf348-120">Si ha instalado [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en la ubicación predeterminada, BtsNtSvc.exe estará en el directorio [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf348-120">If you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to the default location, BtsNtSvc.exe will be in the directory [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)].</span></span>  
  
3.  <span data-ttu-id="bf348-121">Para los adaptadores WCF aislados, puede habilitar el registro de mensajes WCF modificando el **Web.config** archivos creados por el Asistente para publicación de servicio WCF de BizTalk en la carpeta de aplicación Web.</span><span class="sxs-lookup"><span data-stu-id="bf348-121">For the isolated WCF adapters, you can enable WCF message logging by modifying the **Web.config** file that the BizTalk WCF Service Publishing Wizard creates in the Web application folder.</span></span>  
  
4.  <span data-ttu-id="bf348-122">Para modificar **BTSNtSvc.exe.config** o **Web.config**, abrir el archivo de configuración mediante el Bloc de notas y, a continuación, configure el registro de mensajes WCF, como se indica en el siguiente ejemplo de configuración:</span><span class="sxs-lookup"><span data-stu-id="bf348-122">To modify **BTSNtSvc.exe.config** or **Web.config**, open the configuration file by using Notepad, and then configure WCF message logging, as indicated in the following configuration example:</span></span>  
  
    ```  
    <configuration>  
      <system.serviceModel>  
        <diagnostics>  
          <messageLogging   
               logEntireMessage="true"   
               logMalformedMessages="false"  
               logMessagesAtServiceLevel="true"   
               logMessagesAtTransportLevel="true"  
               maxMessagesToLog="300000"  
               maxSizeOfMessageToLog="200000"   
        />  
        </diagnostics>  
      </system.serviceModel>  
  
      <system.diagnostics>  
        <sources>  
          <source name="System.ServiceModel.MessageLogging">  
            <listeners>  
              <add name="messages"  
              type="System.Diagnostics.XmlWriterTraceListener"  
              initializeData="c:\wcfTrace.e2e" />  
            </listeners>  
          </source>  
        </sources>  
      </system.diagnostics>  
    </configuration>  
    ```  
  
5.  <span data-ttu-id="bf348-123">Puede utilizar la herramienta Service Trace Viewer de Windows Communication Foundation (WCF) para analizar los mensajes registrados por WCF.</span><span class="sxs-lookup"><span data-stu-id="bf348-123">You can use the Windows Communication Foundation (WCF) Service Trace Viewer Tool to analyze messages logged by WCF.</span></span> <span data-ttu-id="bf348-124">Service Trace Viewer está incluida en el kit de desarrollo de software (SDK) de Microsoft Windows de los componentes en tiempo de ejecución de [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] y Windows Vista.</span><span class="sxs-lookup"><span data-stu-id="bf348-124">Service Trace Viewer is included in the Microsoft Windows Software Development Kit (SDK) for Windows Vista and [!INCLUDE[btsDotNetFramework](../includes/btsdotnetframework-md.md)] Runtime Components.</span></span> <span data-ttu-id="bf348-125">Puede descargar el SDK de Windows desde Microsoft Download Center en [http://go.microsoft.com/fwlink/?LinkID=75636](http://go.microsoft.com/fwlink/?LinkID=75636).</span><span class="sxs-lookup"><span data-stu-id="bf348-125">You can download the Windows SDK from the Microsoft Download Center at [http://go.microsoft.com/fwlink/?LinkID=75636](http://go.microsoft.com/fwlink/?LinkID=75636).</span></span> <span data-ttu-id="bf348-126">Para obtener más información sobre el uso de esta herramienta, vea "herramienta Service Trace Viewer (SvcTraceViewer.exe)"at [http://go.microsoft.com/fwlink/?LinkId=88991](http://go.microsoft.com/fwlink/?LinkId=88991).</span><span class="sxs-lookup"><span data-stu-id="bf348-126">For more information about using this tool, see "Service Trace Viewer Tool (SvcTraceViewer.exe)"at [http://go.microsoft.com/fwlink/?LinkId=88991](http://go.microsoft.com/fwlink/?LinkId=88991).</span></span>  
  
### <a name="return-managed-exception-information-to-the-client-in-a-soap-fault-to-ease-debugging"></a><span data-ttu-id="bf348-127">Devolver información de excepción administrada al cliente si se produce un error de SOAP para una depuración sencilla.</span><span class="sxs-lookup"><span data-stu-id="bf348-127">Return managed exception information to the client in a SOAP fault to ease debugging</span></span>  
  
1.  <span data-ttu-id="bf348-128">Puede seleccionar la **incluir excepción en errores** opción de WCF estándar ubicación de recepción para devolver información de excepción administrada al cliente en errores SOAP para una depuración sencilla.</span><span class="sxs-lookup"><span data-stu-id="bf348-128">You can select the **Include exception in faults** option for the standard WCF receive location to return managed exception information to the client in SOAP faults to ease debugging.</span></span> <span data-ttu-id="bf348-129">Siga estos pasos para seleccionar el **incluir excepción en errores** opción.</span><span class="sxs-lookup"><span data-stu-id="bf348-129">Use the following steps to select the **Include exception in faults** option.</span></span>  
  
    1.  <span data-ttu-id="bf348-130">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **Ubicaciones de recepción**, haga clic en una ubicación de recepción mediante un adaptador WCF estándar y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bf348-130">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand **Receive Locations**, right-click a receive location using a standard WCF adapter, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="bf348-131">En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="bf348-131">In the **Receive Location Properties** dialog box, click **Configure**.</span></span>  
  
    3.  <span data-ttu-id="bf348-132">En el cuadro de diálogo de transporte, en la **mensajes** ficha, seleccione la **incluir excepción en errores** opción.</span><span class="sxs-lookup"><span data-stu-id="bf348-132">In the transport dialog box, on the **Messages** tab, select the **Include exception in faults** option.</span></span>  
  
2.  <span data-ttu-id="bf348-133">Si usas el WCF-Custom o el adaptador WCF-CustomIsolated, puede establecer la **IncludeExceptionDetailInFaults** propiedad de la [ServiceDebugElement](http://go.microsoft.com/fwlink/?LinkId=89004) para devolver información de excepción administrada a la cliente.</span><span class="sxs-lookup"><span data-stu-id="bf348-133">If you use the WCF-Custom or the WCF-CustomIsolated adapter, you can set the **IncludeExceptionDetailInFaults** property of the [ServiceDebugElement](http://go.microsoft.com/fwlink/?LinkId=89004) to return managed exception information to the client.</span></span> <span data-ttu-id="bf348-134">Para ello, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="bf348-134">To do so, use the following steps:</span></span>  
  
    1.  <span data-ttu-id="bf348-135">En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración de la consola, expanda [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **administración**, expanda **grupo de BizTalk**, expanda **aplicaciones**, expanda **Ubicaciones de recepción**, haga clic en una ubicación de recepción mediante WCF-Custom o el adaptador WCF-CustomIsolated y, a continuación, haga clic en **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="bf348-135">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, expand **BizTalk Group**, expand **Applications**, expand **Receive Locations**, right-click a receive location using the WCF-Custom or the WCF-CustomIsolated adapter, and then click **Properties**.</span></span>  
  
    2.  <span data-ttu-id="bf348-136">En el **propiedades de la ubicación de recepción** cuadro de diálogo, haga clic en **configurar**.</span><span class="sxs-lookup"><span data-stu-id="bf348-136">In the **Receive Location Properties** dialog box, click **Configure**.</span></span>  
  
    3.  <span data-ttu-id="bf348-137">En el cuadro de diálogo de transporte, en la **comportamiento** pestaña, haga clic en el **ServiceBehavior** nodo y, a continuación, haga clic en **Agregar extensión**.</span><span class="sxs-lookup"><span data-stu-id="bf348-137">In the transport dialog box, on the **Behavior** tab, right-click the **ServiceBehavior** node, and then click **Add extension**.</span></span>  
  
    4.  <span data-ttu-id="bf348-138">En el **Seleccionar extensión de comportamiento** cuadro de diálogo, seleccione **serviceDebug**y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bf348-138">In the **Select Behavior Extension** dialog box, select **serviceDebug**, and then click **OK**.</span></span>  
  
    5.  <span data-ttu-id="bf348-139">En el cuadro de diálogo de transporte, en la **comportamiento** , haga clic en el **serviceDebug** nodo y, a continuación, seleccione **True** para el **includeExceptionDetail** propiedad en el **configuración** vista de lista.</span><span class="sxs-lookup"><span data-stu-id="bf348-139">In the transport dialog box, on the **Behavior** tab, click the **serviceDebug** node, and then select **True** for the **includeExceptionDetail** property in the **Configuration** list view.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bf348-140">La devolución de información de excepción administrada a los clientes puede suponer un riesgo para la seguridad, ya que los detalles de la excepción exponen información acerca de la implementación del servicio interna que podría utilizarse por clientes no autorizados.</span><span class="sxs-lookup"><span data-stu-id="bf348-140">Returning managed exception information to clients can be a security risk because exception details expose information about the internal service implementation that could be used by unauthorized clients.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf348-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="bf348-141">See Also</span></span>  
 <span data-ttu-id="bf348-142">[Herramientas y utilidades que se utilizan para solucionar problemas](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span><span class="sxs-lookup"><span data-stu-id="bf348-142">[Tools and Utilities to Use for Troubleshooting](../core/tools-and-utilities-to-use-for-troubleshooting.md) </span></span>  
 <span data-ttu-id="bf348-143">[Solución de problemas de los adaptadores de WCF](../core/troubleshooting-the-wcf-adapters.md) </span><span class="sxs-lookup"><span data-stu-id="bf348-143">[Troubleshooting the WCF Adapters](../core/troubleshooting-the-wcf-adapters.md) </span></span>  
 [<span data-ttu-id="bf348-144">Archivo BTSNTSvc.exe.config</span><span class="sxs-lookup"><span data-stu-id="bf348-144">BTSNTSvc.exe.config File</span></span>](../core/btsntsvc-exe-config-file.md)