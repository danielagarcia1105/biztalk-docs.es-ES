---
title: Configurar el feature pack | Documentos de Microsoft
description: "Instalar y configurar feature pack de 1 y 2 del paquete de características. Ver la lista de características nuevas, como administración de API, implementación de servicios de equipo, nuevos adaptadores de Azure, las copias de seguridad etc. en BizTalk Server 2016"
ms.custom: 
ms.date: 11/22/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1027bfa6-49b9-4f58-a2e2-3e0ae2fc3bf3
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e5b4164cf1f1355ab9a0d2f350aa5b3b5ce411e0
ms.sourcegitcommit: f4c0d7bc4b617688c643101a34062db90014851a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2017
---
# <a name="configure-the-feature-pack"></a><span data-ttu-id="04bd1-104">Configurar el feature pack</span><span class="sxs-lookup"><span data-stu-id="04bd1-104">Configure the feature pack</span></span>

## <a name="overview"></a><span data-ttu-id="04bd1-105">Información general</span><span class="sxs-lookup"><span data-stu-id="04bd1-105">Overview</span></span>

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="04bd1-106">utiliza paquetes de características para proporcionar una integración más estrecha con Azure, mejoras y características.</span><span class="sxs-lookup"><span data-stu-id="04bd1-106"> uses feature packs to provide improvements, features, and closer integration with Azure.</span></span> <span data-ttu-id="04bd1-107">Estos paquetes de características extienden la funcionalidad en áreas clave, como la implementación, seguridad, análisis, en tiempo de ejecución y copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="04bd1-107">These feature packs extend functionality in key areas, such as deployment, security, analytics, runtime, and backup.</span></span> 

> [!NOTE]
> <span data-ttu-id="04bd1-108">Los paquetes de características están disponibles con las ediciones Enterprise y Developer de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] cuando:</span><span class="sxs-lookup"><span data-stu-id="04bd1-108">The feature packs are available with the Enterprise and Developer editions of [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] when:</span></span> 
> 
> - <span data-ttu-id="04bd1-109">Usar con Software Assurance (SA), o</span><span class="sxs-lookup"><span data-stu-id="04bd1-109">Used with Software Assurance (SA), OR</span></span>
> - <span data-ttu-id="04bd1-110">Ejecutando [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en Azure con un contrato Enterprise</span><span class="sxs-lookup"><span data-stu-id="04bd1-110">Running [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in Azure using an Enterprise Agreement</span></span>
> 
> <span data-ttu-id="04bd1-111">Los paquetes de características no están disponibles para cualquier otro [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] edition o cualquier otro [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versión.</span><span class="sxs-lookup"><span data-stu-id="04bd1-111">The feature packs are not available for any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] edition, or any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] version.</span></span> 

## <a name="download-and-install"></a><span data-ttu-id="04bd1-112">Descargue e instale</span><span class="sxs-lookup"><span data-stu-id="04bd1-112">Download and install</span></span>

<span data-ttu-id="04bd1-113">Los paquetes de características son acumulativos.</span><span class="sxs-lookup"><span data-stu-id="04bd1-113">The feature packs are cumulative.</span></span> <span data-ttu-id="04bd1-114">Por lo que al instalar el feature pack de 2, también obtendrá las características y actualizaciones en feature pack 1.</span><span class="sxs-lookup"><span data-stu-id="04bd1-114">So when you install feature pack 2, you also get the features and updates in feature pack 1.</span></span>

* <span data-ttu-id="04bd1-115">Descargue el [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2 de](https://aka.ms/bts2016fp2).</span><span class="sxs-lookup"><span data-stu-id="04bd1-115">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2](https://aka.ms/bts2016fp2).</span></span>

* <span data-ttu-id="04bd1-116">Descargue el [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100).</span><span class="sxs-lookup"><span data-stu-id="04bd1-116">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100).</span></span>

#### <a name="install"></a><span data-ttu-id="04bd1-117">Install</span><span class="sxs-lookup"><span data-stu-id="04bd1-117">Install</span></span>

1. <span data-ttu-id="04bd1-118">Ejecute el programa de instalación como administrador.</span><span class="sxs-lookup"><span data-stu-id="04bd1-118">Run setup as administrator.</span></span>
2. <span data-ttu-id="04bd1-119">En **bienvenida**, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="04bd1-119">In **Welcome**, select **Next**.</span></span> 
3. <span data-ttu-id="04bd1-120">Acepte el contrato de licencia y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="04bd1-120">Accept the license agreement, and select **Next**.</span></span> 
4. <span data-ttu-id="04bd1-121">Continúe con la instalación.</span><span class="sxs-lookup"><span data-stu-id="04bd1-121">Continue with the installation.</span></span> <span data-ttu-id="04bd1-122">Durante la instalación, pueden abrir varias ventanas de comandos y se cierre.</span><span class="sxs-lookup"><span data-stu-id="04bd1-122">During the install, several command windows may open and close.</span></span> <span data-ttu-id="04bd1-123">Cuando haya finalizado, deberá **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="04bd1-123">When complete, you are prompted to **Finish**.</span></span>

<span data-ttu-id="04bd1-124">Se crea un registro de instalación en `C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`.</span><span class="sxs-lookup"><span data-stu-id="04bd1-124">A setup log is created in `C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`.</span></span>

>[!TIP]
> <span data-ttu-id="04bd1-125">Para obtener instrucciones completas sobre la instalación, consulte el [instalación paso a paso de Feature Pack](https://blog.sandro-pereira.com/2017/04/27/microsoft-biztalk-server-2016-feature-pack-1-step-by-step-installation/) entrada de blog.</span><span class="sxs-lookup"><span data-stu-id="04bd1-125">For comprehensive guidance on the installation, see the [Feature Pack step-by-step installation](https://blog.sandro-pereira.com/2017/04/27/microsoft-biztalk-server-2016-feature-pack-1-step-by-step-installation/) blog post.</span></span>

## <a name="feature-pack-2-updates"></a><span data-ttu-id="04bd1-126">Actualizaciones de características Pack 2</span><span class="sxs-lookup"><span data-stu-id="04bd1-126">Feature Pack 2 updates</span></span>

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="04bd1-127">Exponer los extremos SOAP con administración de API</span><span class="sxs-lookup"><span data-stu-id="04bd1-127">Expose SOAP endpoints with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="04bd1-128">Analizando la integración de administración de API realizada con Feature Pack 1, ahora puede exponer un WCF-BasicHTTP ubicación de recepción como un extremo SOAP mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="04bd1-128">Expanding on the API management integration made with Feature Pack 1, you can now expose a WCF-BasicHTTP receive location as a SOAP endpoint using the BizTalk Server Administration console.</span></span> 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[<span data-ttu-id="04bd1-129">Usar el adaptador de concentrador de eventos</span><span class="sxs-lookup"><span data-stu-id="04bd1-129">Use the Event Hub adapter</span></span>](event-hubs-adapter.md)

<span data-ttu-id="04bd1-130">Enviar mensajes de BizTalk a los centros de eventos de Azure y recibir mensajes desde los centros de eventos de Azure a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="04bd1-130">Send messages from BizTalk to Azure Event Hubs, and receive messages from Azure Event Hubs to BizTalk Server.</span></span> <span data-ttu-id="04bd1-131">Al configurar las propiedades de transporte, puede iniciar sesión fácilmente en su cuenta de Azure y seleccionar automáticamente el espacio de nombres de los centros de eventos de Azure y centro de eventos.</span><span class="sxs-lookup"><span data-stu-id="04bd1-131">When you configure the transport properties, you can easily sign in to your Azure account, and automatically select your Azure Event Hubs namespace, and Event Hub.</span></span>

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[<span data-ttu-id="04bd1-132">Copia de seguridad para la cuenta de blobs de Azure</span><span class="sxs-lookup"><span data-stu-id="04bd1-132">Backup to Azure blob account</span></span>](../core/how-to-configure-the-backup-biztalk-server-job.md)
<span data-ttu-id="04bd1-133">El trabajo de copia de seguridad de BizTalk Server realiza una copia de seguridad de los archivos de registro y las bases de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="04bd1-133">The Backup BizTalk Server job backs up the BizTalk databases and log files.</span></span> <span data-ttu-id="04bd1-134">Al configurar este trabajo del Agente SQL, puede especificar una cuenta de almacenamiento de blobs de Azure dentro de las propiedades del trabajo.</span><span class="sxs-lookup"><span data-stu-id="04bd1-134">When you configure this SQL Agent job, you can enter an Azure blob storage account within the job properties.</span></span> <span data-ttu-id="04bd1-135">Esto le ofrece otra opción para copia de seguridad de los datos, en lugar de usar un disco físico local.</span><span class="sxs-lookup"><span data-stu-id="04bd1-135">This gives you another option to backup your data, instead of using a local physical disk.</span></span> 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="04bd1-136">Implementación en varios equipos mediante VSTS</span><span class="sxs-lookup"><span data-stu-id="04bd1-136">Multi-machine deployment using VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
<span data-ttu-id="04bd1-137">Uso de grupos de implementación, puede implementar las aplicaciones en varios servidores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="04bd1-137">Using deployment groups, you can deploy your applications to multiple BizTalk Servers.</span></span> <span data-ttu-id="04bd1-138">También puede establecer el nombre de la aplicación en el proyecto de aplicación y la instalación de la aplicación especificando el servidor de administración.</span><span class="sxs-lookup"><span data-stu-id="04bd1-138">You can also set the application name within the application project, and install your application by entering your management server.</span></span>

<span data-ttu-id="04bd1-139">[Grupos de implementación](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) proporciona información detallada sobre cómo hacerlo en VSTS.</span><span class="sxs-lookup"><span data-stu-id="04bd1-139">[Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) provides more details on how this is done in VSTS.</span></span>  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[<span data-ttu-id="04bd1-140">Usar Premium de Bus de servicio</span><span class="sxs-lookup"><span data-stu-id="04bd1-140">Use Service Bus Premium</span></span>](../core/sb-messaging-adapter.md)

<span data-ttu-id="04bd1-141">El adaptador de Bus de servicio admite Premium de Bus de servicio, incluido el envío de mensajes a colas con particiones y temas.</span><span class="sxs-lookup"><span data-stu-id="04bd1-141">The Service Bus adapter supports Service Bus Premium, including sending messages to partitioned queues and topics.</span></span> <span data-ttu-id="04bd1-142">[Niveles de mensajes estándares y Premium de Bus de servicio](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging) detalles más información acerca de Premium de Bus de servicio.</span><span class="sxs-lookup"><span data-stu-id="04bd1-142">[Service Bus Premium and Standard messaging tiers](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging) details more about Service Bus Premium.</span></span> 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="04bd1-143">Usar las instancias con nombre con Application Insights</span><span class="sxs-lookup"><span data-stu-id="04bd1-143">Use named instances with Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
<span data-ttu-id="04bd1-144">Al habilitar el análisis y escriba la clave de Application Insights, es posible recibir el error:</span><span class="sxs-lookup"><span data-stu-id="04bd1-144">When you enable Analytics, and enter the Application Insights key, you may get error:</span></span> 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

<span data-ttu-id="04bd1-145">Esto sucede cuando se usa SQL instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="04bd1-145">This happens when you use SQL named instances.</span></span> <span data-ttu-id="04bd1-146">Esto se corrigió en este feature pack; Puede usar instancias predeterminadas SQL y SQL las instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="04bd1-146">This is fixed in this feature pack; you can use SQL default instances, and SQL named instances.</span></span> 

#### <a name="tls-12-support"></a><span data-ttu-id="04bd1-147">Soporte de TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="04bd1-147">TLS 1.2 support</span></span>

<span data-ttu-id="04bd1-148">TLS 1.2 es totalmente compatible en BizTalk Server, incluidos todos los adaptadores y todos los aceleradores.</span><span class="sxs-lookup"><span data-stu-id="04bd1-148">TLS 1.2 is fully supported in BizTalk Server, including all the adapters and all the accelerators.</span></span> <span data-ttu-id="04bd1-149">Puede deshabilitar SSL, TLS 1.0 y 1.1 de TLS en el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="04bd1-149">You can disable SSL, TLS 1.0, and TLS 1.1 on the BizTalk Server.</span></span> 

<span data-ttu-id="04bd1-150">Información de clave:</span><span class="sxs-lookup"><span data-stu-id="04bd1-150">Key information:</span></span> 

* <span data-ttu-id="04bd1-151">Los sistemas externos comunicarse con BizTalk también necesitan admitir TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="04bd1-151">Any external systems communicating with BizTalk also need to support TLS 1.2</span></span>
* <span data-ttu-id="04bd1-152">Cualquier código personalizado, como los functoids, necesite actualizarse para admitir TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="04bd1-152">Any custom code, such as functoids, may need to be updated to support TLS 1.2</span></span>

<span data-ttu-id="04bd1-153">[Descripción del protocolo TLS/SSL](https://support.microsoft.com/kb/3155464) describe cómo configurar un entorno de TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="04bd1-153">[Description of the TLS/SSL protocol](https://support.microsoft.com/kb/3155464) describes how to setup a TLS 1.2 environment.</span></span> 

#### <a name="use-latest-newtonsoft-json"></a><span data-ttu-id="04bd1-154">Usar JSON Newtonsoft más reciente</span><span class="sxs-lookup"><span data-stu-id="04bd1-154">Use latest Newtonsoft JSON</span></span> 
<span data-ttu-id="04bd1-155">Newtonsoft es un marco JSON para. NET.</span><span class="sxs-lookup"><span data-stu-id="04bd1-155">Newtonsoft is a JSON framework for .NET.</span></span> <span data-ttu-id="04bd1-156">En este feature pack se incluye compatibilidad con la versión 10.0.3.</span><span class="sxs-lookup"><span data-stu-id="04bd1-156">In this feature pack, support for version 10.0.3 is included.</span></span> <span data-ttu-id="04bd1-157">[Descargar v. 10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) directamente de NuGet.</span><span class="sxs-lookup"><span data-stu-id="04bd1-157">[Download v. 10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) directly from NuGet.</span></span> 


## <a name="feature-pack-1-updates"></a><span data-ttu-id="04bd1-158">Actualizaciones de características Pack 1</span><span class="sxs-lookup"><span data-stu-id="04bd1-158">Feature Pack 1 updates</span></span>

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="04bd1-159">Enviar datos de diagnóstico a Application Insights.</span><span class="sxs-lookup"><span data-stu-id="04bd1-159">Send tracking data to Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

<span data-ttu-id="04bd1-160">Enviar datos de seguimiento a Azure Application Insights para usar sus características, como el análisis, aprendizaje automático, diagnósticos y mucho más.</span><span class="sxs-lookup"><span data-stu-id="04bd1-160">Send tracking data to Azure Application Insights to use its features, such as analytics, machine learning, diagnostics, and more.</span></span> 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[<span data-ttu-id="04bd1-161">Configurar la fuente con Power BI de datos operativos</span><span class="sxs-lookup"><span data-stu-id="04bd1-161">Configure the operational data feed using Power BI</span></span>](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

<span data-ttu-id="04bd1-162">Enviar datos de seguimiento a Power BI con oData.</span><span class="sxs-lookup"><span data-stu-id="04bd1-162">Send tracking data to Power BI using oData.</span></span> <span data-ttu-id="04bd1-163">Por ejemplo, obtener una representación visual de los datos de seguimiento de los puertos y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="04bd1-163">For example, get a visual representation of your tracking data from your ports and orchestrations.</span></span> 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[<span data-ttu-id="04bd1-164">Conectarse a la administración de API de REST de BizTalk</span><span class="sxs-lookup"><span data-stu-id="04bd1-164">Connect to the management REST APIs in BizTalk</span></span>](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

<span data-ttu-id="04bd1-165">Use las API de REST para administrar de forma remota los artefactos de BizTalk, incluidos los contratos, las instancias suspendidas, dado de baja orquestaciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="04bd1-165">Use REST APIs to remotely manage your BizTalk artifacts, including agreements, suspended instances, unenlisted orchestrations, and more.</span></span>

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[<span data-ttu-id="04bd1-166">Configurar la programación avanzada</span><span class="sxs-lookup"><span data-stu-id="04bd1-166">Configure advanced scheduling</span></span>](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

<span data-ttu-id="04bd1-167">Habilitar avanzadas de programación en sus ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="04bd1-167">Enable advanced scheduling in your receive locations.</span></span> <span data-ttu-id="04bd1-168">Por ejemplo, establecer la zona horaria o establecer una ventana de servicio de periodicidad para un día determinado en un mes específico.</span><span class="sxs-lookup"><span data-stu-id="04bd1-168">For example, set the timezone, or set a recurrence service window for a specific day on a specific month.</span></span>

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="04bd1-169">Configurar implementaciones automáticas con VSTS</span><span class="sxs-lookup"><span data-stu-id="04bd1-169">Configure automatic deployments with VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

<span data-ttu-id="04bd1-170">Usar Visual Studio Team Services (VSTS) para implementar automáticamente las soluciones o actualizar las aplicaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="04bd1-170">Use Visual Studio Team Services (VSTS) to automatically deploy your solutions, or update existing applications.</span></span> <span data-ttu-id="04bd1-171">VSTS se comunica con un agente instalado en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="04bd1-171">VSTS communicates with an agent installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[<span data-ttu-id="04bd1-172">Conectarse a SQL Server Always Encrypted columnas con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="04bd1-172">Connect to SQL Server Always Encrypted columns with BizTalk Server</span></span>](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

<span data-ttu-id="04bd1-173">Utilice el adaptador de WCF-SQL para consultar columnas cifradas de una base de datos Always Encrypted en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="04bd1-173">Use the WCF-SQL adapter to query encrypted columns from an Always Encrypted database in SQL Server.</span></span>

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="04bd1-174">Integrar con administración de API</span><span class="sxs-lookup"><span data-stu-id="04bd1-174">Integrate with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="04bd1-175">Dentro de su servicio de administración de API de Azure, puede crear y exponer una API como WSDL y usar el URI para un extremo SOAP de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="04bd1-175">Within your Azure API management service, you can create and expose an API as WSDL, and use the URI to a BizTalk SOAP endpoint.</span></span>  