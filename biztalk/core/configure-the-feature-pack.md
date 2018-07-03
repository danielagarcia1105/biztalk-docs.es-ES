---
title: Configuración del feature pack | Microsoft Docs
description: Instalar y configurar el feature pack 1 de feature pack 2 de. Consulte la lista de características nuevas, incluido API Management, implementación de team services, nuevos adaptadores de Azure, las copias de seguridad y mucho más en BizTalk Server 2016
ms.custom: ''
ms.date: 06/26/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1027bfa6-49b9-4f58-a2e2-3e0ae2fc3bf3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 210089dc225d85271a8c8fdc426d2ca68bf353e1
ms.sourcegitcommit: 080224caa88f9935b5b13fa035d372f8964d2e52
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "36957872"
---
# <a name="configure-the-feature-pack"></a><span data-ttu-id="0cc76-104">Configuración del feature pack</span><span class="sxs-lookup"><span data-stu-id="0cc76-104">Configure the feature pack</span></span>

## <a name="overview"></a><span data-ttu-id="0cc76-105">Información general</span><span class="sxs-lookup"><span data-stu-id="0cc76-105">Overview</span></span>

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0cc76-106"> usa los paquetes de características para proporcionar una integración más estrecha con Azure, mejoras y características.</span><span class="sxs-lookup"><span data-stu-id="0cc76-106"> uses feature packs to provide improvements, features, and closer integration with Azure.</span></span> <span data-ttu-id="0cc76-107">Estos feature packs de extienden la funcionalidad en áreas clave, como la implementación, seguridad, análisis, en tiempo de ejecución, mantenimiento, conformidad con estándares e integración híbrida.</span><span class="sxs-lookup"><span data-stu-id="0cc76-107">These feature packs extend functionality in key areas, such as deployment, security, analytics, runtime, maintainance, standard compliance, and hybrid integration.</span></span> 

> [!NOTE]
> <span data-ttu-id="0cc76-108">Los paquetes de características están disponibles con las ediciones Enterprise y Developer de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] cuando:</span><span class="sxs-lookup"><span data-stu-id="0cc76-108">The feature packs are available with the Enterprise and Developer editions of [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] when:</span></span> 
> 
> - <span data-ttu-id="0cc76-109">Puede usar con Software Assurance (SA), o</span><span class="sxs-lookup"><span data-stu-id="0cc76-109">Used with Software Assurance (SA), OR</span></span>
> - <span data-ttu-id="0cc76-110">Ejecutando [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en Azure mediante un contrato Enterprise</span><span class="sxs-lookup"><span data-stu-id="0cc76-110">Running [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] in Azure using an Enterprise Agreement</span></span>
> 
> <span data-ttu-id="0cc76-111">Los paquetes de características no están disponibles para cualquier otro [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] edition (ediciones Standard y bifurcación), o cualquier otro [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versión (2013 R2, 2013, 2010, y así sucesivamente).</span><span class="sxs-lookup"><span data-stu-id="0cc76-111">The feature packs are not available for any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] edition (Standard and Branch editions), or any other [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] version (2013 R2, 2013, 2010, and so on).</span></span> 

## <a name="download-and-install"></a><span data-ttu-id="0cc76-112">Descargue e instale</span><span class="sxs-lookup"><span data-stu-id="0cc76-112">Download and install</span></span>

<span data-ttu-id="0cc76-113">Los feature packs son acumulativos.</span><span class="sxs-lookup"><span data-stu-id="0cc76-113">The feature packs are cumulative.</span></span> <span data-ttu-id="0cc76-114">Por lo que al instalar el feature pack de 3, también obtendrá las características y actualizaciones en los feature packs de 2 y 1.</span><span class="sxs-lookup"><span data-stu-id="0cc76-114">So when you install feature pack 3, you also get the features and updates in feature packs 2 and 1.</span></span> <span data-ttu-id="0cc76-115">También obtendrá las últimas actualizaciones acumulativas.</span><span class="sxs-lookup"><span data-stu-id="0cc76-115">You also get the latest cumulative updates.</span></span>

* <span data-ttu-id="0cc76-116">Descargue el [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 3 de](https://aka.ms/bts2016fp3).</span><span class="sxs-lookup"><span data-stu-id="0cc76-116">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 3](https://aka.ms/bts2016fp3).</span></span>

* <span data-ttu-id="0cc76-117">Descargue el [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2 de](https://aka.ms/bts2016fp2).</span><span class="sxs-lookup"><span data-stu-id="0cc76-117">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2](https://aka.ms/bts2016fp2).</span></span>

* <span data-ttu-id="0cc76-118">Descargue el [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100).</span><span class="sxs-lookup"><span data-stu-id="0cc76-118">Download the [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1](https://www.microsoft.com/download/details.aspx?id=55100).</span></span>

#### <a name="install"></a><span data-ttu-id="0cc76-119">Install</span><span class="sxs-lookup"><span data-stu-id="0cc76-119">Install</span></span>

1. <span data-ttu-id="0cc76-120">Ejecute el programa de instalación como administrador.</span><span class="sxs-lookup"><span data-stu-id="0cc76-120">Run setup as administrator.</span></span>
2. <span data-ttu-id="0cc76-121">En **bienvenida**, seleccione **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0cc76-121">In **Welcome**, select **Next**.</span></span> 
3. <span data-ttu-id="0cc76-122">Acepte el contrato de licencia y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="0cc76-122">Accept the license agreement, and select **Next**.</span></span> 
4. <span data-ttu-id="0cc76-123">Continúe con la instalación.</span><span class="sxs-lookup"><span data-stu-id="0cc76-123">Continue with the installation.</span></span> <span data-ttu-id="0cc76-124">Durante la instalación, pueden abrir varias ventanas de comandos y se cierre.</span><span class="sxs-lookup"><span data-stu-id="0cc76-124">During the install, several command windows may open and close.</span></span> <span data-ttu-id="0cc76-125">Cuando haya finalizado, se le pedirá que **finalizar**.</span><span class="sxs-lookup"><span data-stu-id="0cc76-125">When complete, you are prompted to **Finish**.</span></span>

<span data-ttu-id="0cc76-126">Se crea un registro de instalación en `C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`.</span><span class="sxs-lookup"><span data-stu-id="0cc76-126">A setup log is created in `C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`.</span></span>

>[!TIP]
> <span data-ttu-id="0cc76-127">Para obtener instrucciones completas sobre la instalación, consulte el [BizTalk Server 2016 característica módulo 3: instalación paso a paso](https://blog.sandro-pereira.com/2018/06/26/biztalk-server-2016-feature-pack-3/) entrada de blog.</span><span class="sxs-lookup"><span data-stu-id="0cc76-127">For comprehensive guidance on the installation, see the [BizTalk Server 2016 Feature Pack 3: step-by-step installation](https://blog.sandro-pereira.com/2018/06/26/biztalk-server-2016-feature-pack-3/) blog post.</span></span>

## <a name="feature-pack-3-updates"></a><span data-ttu-id="0cc76-128">Actualizaciones de características Pack 3</span><span class="sxs-lookup"><span data-stu-id="0cc76-128">Feature Pack 3 updates</span></span>

<span data-ttu-id="0cc76-129">**Adaptadores de Office 365**</span><span class="sxs-lookup"><span data-stu-id="0cc76-129">**Office 365 Adapters**</span></span>


<span data-ttu-id="0cc76-130">Microsoft Office 365 es un servicio de suscripción en la nube que reúne lo mejor herramientas para las personas de manera trabajar hoy en día.</span><span class="sxs-lookup"><span data-stu-id="0cc76-130">Microsoft Office 365 is a cloud-based subscription service that brings together the best tools for the way people work today.</span></span> <span data-ttu-id="0cc76-131">Al combinar lo mejor de su clase aplicaciones como Excel y Outlook con los servicios de nube sólidas, como OneDrive y Microsoft Teams, Office 365 permite a cualquiera que cree y comparta en cualquier lugar en cualquier dispositivo.</span><span class="sxs-lookup"><span data-stu-id="0cc76-131">By combining best-in-class apps like Excel and Outlook with powerful cloud services like OneDrive and Microsoft Teams, Office 365 lets anyone create and share anywhere on any device.</span></span>

<span data-ttu-id="0cc76-132">Adaptadores de Microsoft BizTalk Server para Office 365 permiten a los profesionales de TI y desarrolladores empresariales a integrar correo, contactos y las programaciones de Outlook con nuevas soluciones basadas en BizTalk Server 2016.</span><span class="sxs-lookup"><span data-stu-id="0cc76-132">Microsoft BizTalk Server adapters for Office 365 enable IT professionals and enterprise developers to integrate Outlook mail, contacts, and schedules with new solutions based on BizTalk Server 2016.</span></span>

#### <a name="office-365-mail-adapteroffice365-mail-adaptermd"></a>[<span data-ttu-id="0cc76-133">Adaptador de correo electrónico de Office 365</span><span class="sxs-lookup"><span data-stu-id="0cc76-133">Office 365 Mail adapter</span></span>](office365-mail-adapter.md)
<span data-ttu-id="0cc76-134">El adaptador de BizTalk para el correo de Office 365, puede leer, marcar como leído o eliminar las ubicaciones de recepción de mensajes de correo electrónico a través de servidor de BizTalk unidireccional de Outlook.</span><span class="sxs-lookup"><span data-stu-id="0cc76-134">Using the BizTalk Adapter for Office 365 Mail, you can read, mark as read or delete Outlook e-mail messages through one-way BizTalk Server receive locations.</span></span> <span data-ttu-id="0cc76-135">Con este adaptador, puede escribir mensaje de correo electrónico, incluido el establecimiento de prioridad del mensaje, a través de unidireccional estático o puertos de envío de BizTalk Server dinámico.</span><span class="sxs-lookup"><span data-stu-id="0cc76-135">Using this adapter, you can write e-mail message, including setting message priority, through one-way static or dynamic BizTalk Server send ports.</span></span>

#### <a name="office-365-calendar-adapteroffice365-calendar-adaptermd"></a>[<span data-ttu-id="0cc76-136">Adaptador de calendario de Office 365</span><span class="sxs-lookup"><span data-stu-id="0cc76-136">Office 365 Calendar adapter</span></span>](office365-calendar-adapter.md)
<span data-ttu-id="0cc76-137">El adaptador de BizTalk para el calendario de Office 365, puede obtener calendario futuros eventos mediante unidireccional de BizTalk Server recibir ubicaciones.</span><span class="sxs-lookup"><span data-stu-id="0cc76-137">Using the BizTalk Adapter for Office 365 Calendar, you can get future calendar events through one-way BizTalk Server receive locations.</span></span> <span data-ttu-id="0cc76-138">Con este adaptador, puede crear eventos de calendario y especificar a los asistentes obligatorios y opcionales, puertos de envío unidireccional estático o dinámico BizTalk Server a través de.</span><span class="sxs-lookup"><span data-stu-id="0cc76-138">Using this adapter, you can create calendar events, and enter required and optional attendees, through one-way static or dynamic BizTalk Server send ports.</span></span>

#### <a name="office-365-contact-adapteroffice365-contact-adaptermd"></a>[<span data-ttu-id="0cc76-139">Adaptador de contacto de Office 365</span><span class="sxs-lookup"><span data-stu-id="0cc76-139">Office 365 Contact adapter</span></span>](office365-contact-adapter.md)
<span data-ttu-id="0cc76-140">El adaptador de BizTalk para el contacto de Office 365, puede crear contactos y escriba toda la configuración, los puertos de envío unidireccional estático o dinámico BizTalk Server a través de.</span><span class="sxs-lookup"><span data-stu-id="0cc76-140">Using the BizTalk Adapter for Office 365 Contact, you can create contacts, and enter all settings, through one-way static or dynamic BizTalk Server send ports.</span></span>

## <a name="feature-pack-2-updates"></a><span data-ttu-id="0cc76-141">Actualizaciones de características Pack 2</span><span class="sxs-lookup"><span data-stu-id="0cc76-141">Feature Pack 2 updates</span></span>

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="0cc76-142">Exponer los extremos SOAP con API Management</span><span class="sxs-lookup"><span data-stu-id="0cc76-142">Expose SOAP endpoints with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="0cc76-143">Expansión de la integración de la administración de API realizada con Feature Pack 1, ahora puede exponer un WCF-BasicHTTP ubicación de recepción como un extremo SOAP mediante la consola de administración de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0cc76-143">Expanding on the API management integration made with Feature Pack 1, you can now expose a WCF-BasicHTTP receive location as a SOAP endpoint using the BizTalk Server Administration console.</span></span> 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[<span data-ttu-id="0cc76-144">Utilice el adaptador del centro de eventos</span><span class="sxs-lookup"><span data-stu-id="0cc76-144">Use the Event Hub adapter</span></span>](event-hubs-adapter.md)

<span data-ttu-id="0cc76-145">Enviar mensajes de BizTalk a Azure Event Hubs y recibir mensajes desde Azure Event Hubs a BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0cc76-145">Send messages from BizTalk to Azure Event Hubs, and receive messages from Azure Event Hubs to BizTalk Server.</span></span> <span data-ttu-id="0cc76-146">Al configurar las propiedades de transporte, puede iniciar sesión en su cuenta de Azure fácilmente y seleccionar automáticamente el espacio de nombres de Azure Event Hubs y el centro de eventos.</span><span class="sxs-lookup"><span data-stu-id="0cc76-146">When you configure the transport properties, you can easily sign in to your Azure account, and automatically select your Azure Event Hubs namespace, and Event Hub.</span></span>

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[<span data-ttu-id="0cc76-147">Copia de seguridad en la cuenta de Azure blob</span><span class="sxs-lookup"><span data-stu-id="0cc76-147">Backup to Azure blob account</span></span>](../core/how-to-configure-the-backup-biztalk-server-job.md)
<span data-ttu-id="0cc76-148">El trabajo de copia de seguridad de BizTalk Server realiza una copia de seguridad de los archivos de registro y las bases de datos de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0cc76-148">The Backup BizTalk Server job backs up the BizTalk databases and log files.</span></span> <span data-ttu-id="0cc76-149">Al configurar este trabajo del Agente SQL, puede especificar una cuenta de almacenamiento de blobs de Azure dentro de las propiedades del trabajo.</span><span class="sxs-lookup"><span data-stu-id="0cc76-149">When you configure this SQL Agent job, you can enter an Azure blob storage account within the job properties.</span></span> <span data-ttu-id="0cc76-150">Esto proporciona otra opción para los datos, en lugar de usar un disco físico local de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="0cc76-150">This gives you another option to backup your data, instead of using a local physical disk.</span></span> 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="0cc76-151">Implementación en varios equipos mediante VSTS</span><span class="sxs-lookup"><span data-stu-id="0cc76-151">Multi-machine deployment using VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
<span data-ttu-id="0cc76-152">Uso de grupos de implementación, puede implementar aplicaciones en varios servidores de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0cc76-152">Using deployment groups, you can deploy your applications to multiple BizTalk Servers.</span></span> <span data-ttu-id="0cc76-153">También puede establecer el nombre de la aplicación en el proyecto de aplicación e instalar la aplicación especificando el servidor de administración.</span><span class="sxs-lookup"><span data-stu-id="0cc76-153">You can also set the application name within the application project, and install your application by entering your management server.</span></span>

<span data-ttu-id="0cc76-154">[Grupos de implementación](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) proporciona más detalles sobre cómo hacerlo en VSTS.</span><span class="sxs-lookup"><span data-stu-id="0cc76-154">[Deployment groups](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) provides more details on how this is done in VSTS.</span></span>  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[<span data-ttu-id="0cc76-155">Uso de Service Bus Premium</span><span class="sxs-lookup"><span data-stu-id="0cc76-155">Use Service Bus Premium</span></span>](../core/sb-messaging-adapter.md)

<span data-ttu-id="0cc76-156">El adaptador de Bus de servicio es compatible con Premium de Service Bus, incluido el envío de mensajes a los temas y colas con particiones.</span><span class="sxs-lookup"><span data-stu-id="0cc76-156">The Service Bus adapter supports Service Bus Premium, including sending messages to partitioned queues and topics.</span></span> <span data-ttu-id="0cc76-157">[Niveles de mensajería estándares y Premium de Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging) detalles más sobre Service Bus Premium.</span><span class="sxs-lookup"><span data-stu-id="0cc76-157">[Service Bus Premium and Standard messaging tiers](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging) details more about Service Bus Premium.</span></span> 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="0cc76-158">Uso de las instancias con nombre con Application Insights</span><span class="sxs-lookup"><span data-stu-id="0cc76-158">Use named instances with Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
<span data-ttu-id="0cc76-159">Al habilitar el análisis y escriba la clave de Application Insights, puede obtener el error:</span><span class="sxs-lookup"><span data-stu-id="0cc76-159">When you enable Analytics, and enter the Application Insights key, you may get error:</span></span> 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

<span data-ttu-id="0cc76-160">Esto sucede cuando se usa SQL instancias con nombre.</span><span class="sxs-lookup"><span data-stu-id="0cc76-160">This happens when you use SQL named instances.</span></span> <span data-ttu-id="0cc76-161">Esto se ha corregido en este feature pack; Puede usar las instancias predeterminadas SQL y las instancias con nombre de SQL.</span><span class="sxs-lookup"><span data-stu-id="0cc76-161">This is fixed in this feature pack; you can use SQL default instances, and SQL named instances.</span></span> 

#### <a name="tls-12-support"></a><span data-ttu-id="0cc76-162">Compatibilidad con TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="0cc76-162">TLS 1.2 support</span></span>

<span data-ttu-id="0cc76-163">TLS 1.2 es totalmente compatible en BizTalk Server, incluidos todos los adaptadores y todos los aceleradores.</span><span class="sxs-lookup"><span data-stu-id="0cc76-163">TLS 1.2 is fully supported in BizTalk Server, including all the adapters and all the accelerators.</span></span> <span data-ttu-id="0cc76-164">Puede deshabilitar SSL, TLS 1.0 y 1.1 de TLS en el servidor BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="0cc76-164">You can disable SSL, TLS 1.0, and TLS 1.1 on the BizTalk Server.</span></span> 

<span data-ttu-id="0cc76-165">Información de clave:</span><span class="sxs-lookup"><span data-stu-id="0cc76-165">Key information:</span></span> 

* <span data-ttu-id="0cc76-166">Los sistemas externos que se comunica con BizTalk, también deben admitir TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="0cc76-166">Any external systems communicating with BizTalk also need to support TLS 1.2</span></span>
* <span data-ttu-id="0cc76-167">Cualquier código personalizado, como los functoids, es posible que deba actualizarse para admitir TLS 1.2</span><span class="sxs-lookup"><span data-stu-id="0cc76-167">Any custom code, such as functoids, may need to be updated to support TLS 1.2</span></span>

<span data-ttu-id="0cc76-168">[Descripción del protocolo TLS/SSL](https://support.microsoft.com/kb/3155464) se describe cómo configurar un entorno de TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="0cc76-168">[Description of the TLS/SSL protocol](https://support.microsoft.com/kb/3155464) describes how to setup a TLS 1.2 environment.</span></span> 

#### <a name="use-latest-newtonsoft-json"></a><span data-ttu-id="0cc76-169">Usar JSON Newtonsoft más reciente</span><span class="sxs-lookup"><span data-stu-id="0cc76-169">Use latest Newtonsoft JSON</span></span> 
<span data-ttu-id="0cc76-170">Newtonsoft es un marco JSON para. NET.</span><span class="sxs-lookup"><span data-stu-id="0cc76-170">Newtonsoft is a JSON framework for .NET.</span></span> <span data-ttu-id="0cc76-171">En este feature pack se incluye compatibilidad con la versión 10.0.3.</span><span class="sxs-lookup"><span data-stu-id="0cc76-171">In this feature pack, support for version 10.0.3 is included.</span></span> <span data-ttu-id="0cc76-172">[Descargue v. 10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) directamente desde NuGet.</span><span class="sxs-lookup"><span data-stu-id="0cc76-172">[Download v. 10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) directly from NuGet.</span></span> 


## <a name="feature-pack-1-updates"></a><span data-ttu-id="0cc76-173">Actualizaciones de características Pack 1</span><span class="sxs-lookup"><span data-stu-id="0cc76-173">Feature Pack 1 updates</span></span>

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[<span data-ttu-id="0cc76-174">Enviar datos de diagnóstico a Application Insights.</span><span class="sxs-lookup"><span data-stu-id="0cc76-174">Send tracking data to Application Insights</span></span>](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

<span data-ttu-id="0cc76-175">Enviar datos de seguimiento a Application Insights de Azure para usar sus características, como análisis, aprendizaje automático, diagnósticos y mucho más.</span><span class="sxs-lookup"><span data-stu-id="0cc76-175">Send tracking data to Azure Application Insights to use its features, such as analytics, machine learning, diagnostics, and more.</span></span> 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[<span data-ttu-id="0cc76-176">Configurar los datos operativos fuente mediante Power BI</span><span class="sxs-lookup"><span data-stu-id="0cc76-176">Configure the operational data feed using Power BI</span></span>](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

<span data-ttu-id="0cc76-177">Enviar datos de seguimiento en Power BI con oData.</span><span class="sxs-lookup"><span data-stu-id="0cc76-177">Send tracking data to Power BI using oData.</span></span> <span data-ttu-id="0cc76-178">Por ejemplo, obtener una representación visual de los datos de seguimiento de los puertos y orquestaciones.</span><span class="sxs-lookup"><span data-stu-id="0cc76-178">For example, get a visual representation of your tracking data from your ports and orchestrations.</span></span> 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[<span data-ttu-id="0cc76-179">Conectarse a la administración de las API de REST de BizTalk</span><span class="sxs-lookup"><span data-stu-id="0cc76-179">Connect to the management REST APIs in BizTalk</span></span>](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

<span data-ttu-id="0cc76-180">Use las API de REST para administrar de forma remota los artefactos de BizTalk, incluidos los contratos, las instancias suspendidas, dado de baja orquestaciones y mucho más.</span><span class="sxs-lookup"><span data-stu-id="0cc76-180">Use REST APIs to remotely manage your BizTalk artifacts, including agreements, suspended instances, unenlisted orchestrations, and more.</span></span>

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[<span data-ttu-id="0cc76-181">Configurar la programación avanzada</span><span class="sxs-lookup"><span data-stu-id="0cc76-181">Configure advanced scheduling</span></span>](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

<span data-ttu-id="0cc76-182">Habilitar avanzadas de programación en sus ubicaciones de recepción.</span><span class="sxs-lookup"><span data-stu-id="0cc76-182">Enable advanced scheduling in your receive locations.</span></span> <span data-ttu-id="0cc76-183">Por ejemplo, establezca la zona horaria, o puede establecer una ventana de servicio de periodicidad para un día concreto de un mes concreto.</span><span class="sxs-lookup"><span data-stu-id="0cc76-183">For example, set the timezone, or set a recurrence service window for a specific day on a specific month.</span></span>

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[<span data-ttu-id="0cc76-184">Configurar implementaciones automáticas con VSTS</span><span class="sxs-lookup"><span data-stu-id="0cc76-184">Configure automatic deployments with VSTS</span></span>](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

<span data-ttu-id="0cc76-185">Usar Visual Studio Team Services (VSTS) para implementar automáticamente las soluciones o actualizar aplicaciones existentes.</span><span class="sxs-lookup"><span data-stu-id="0cc76-185">Use Visual Studio Team Services (VSTS) to automatically deploy your solutions, or update existing applications.</span></span> <span data-ttu-id="0cc76-186">VSTS se comunica con un agente instalado en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0cc76-186">VSTS communicates with an agent installed on the [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].</span></span>

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[<span data-ttu-id="0cc76-187">Conectarse a las columnas de SQL Server Always Encrypted con BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="0cc76-187">Connect to SQL Server Always Encrypted columns with BizTalk Server</span></span>](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

<span data-ttu-id="0cc76-188">Usar el adaptador de WCF-SQL para consultar columnas cifradas de una base de datos Always Encrypted en SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0cc76-188">Use the WCF-SQL adapter to query encrypted columns from an Always Encrypted database in SQL Server.</span></span>

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[<span data-ttu-id="0cc76-189">Integración con API Management</span><span class="sxs-lookup"><span data-stu-id="0cc76-189">Integrate with API Management</span></span>](../core/connect-to-azure-api-management.md)

<span data-ttu-id="0cc76-190">Dentro de su servicio de administración de API de Azure, puede crear y exponer una API como WSDL y use el identificador URI a un extremo SOAP de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0cc76-190">Within your Azure API management service, you can create and expose an API as WSDL, and use the URI to a BizTalk SOAP endpoint.</span></span>  
