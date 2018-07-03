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
# <a name="configure-the-feature-pack"></a>Configuración del feature pack

## <a name="overview"></a>Información general

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] usa los paquetes de características para proporcionar una integración más estrecha con Azure, mejoras y características. Estos feature packs de extienden la funcionalidad en áreas clave, como la implementación, seguridad, análisis, en tiempo de ejecución, mantenimiento, conformidad con estándares e integración híbrida. 

> [!NOTE]
> Los paquetes de características están disponibles con las ediciones Enterprise y Developer de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] cuando: 
> 
> - Puede usar con Software Assurance (SA), o
> - Ejecutando [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en Azure mediante un contrato Enterprise
> 
> Los paquetes de características no están disponibles para cualquier otro [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] edition (ediciones Standard y bifurcación), o cualquier otro [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versión (2013 R2, 2013, 2010, y así sucesivamente). 

## <a name="download-and-install"></a>Descargue e instale

Los feature packs son acumulativos. Por lo que al instalar el feature pack de 3, también obtendrá las características y actualizaciones en los feature packs de 2 y 1. También obtendrá las últimas actualizaciones acumulativas.

* Descargue el [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 3 de](https://aka.ms/bts2016fp3).

* Descargue el [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2 de](https://aka.ms/bts2016fp2).

* Descargue el [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100).

#### <a name="install"></a>Install

1. Ejecute el programa de instalación como administrador.
2. En **bienvenida**, seleccione **siguiente**. 
3. Acepte el contrato de licencia y seleccione **Siguiente**. 
4. Continúe con la instalación. Durante la instalación, pueden abrir varias ventanas de comandos y se cierre. Cuando haya finalizado, se le pedirá que **finalizar**.

Se crea un registro de instalación en `C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`.

>[!TIP]
> Para obtener instrucciones completas sobre la instalación, consulte el [BizTalk Server 2016 característica módulo 3: instalación paso a paso](https://blog.sandro-pereira.com/2018/06/26/biztalk-server-2016-feature-pack-3/) entrada de blog.

## <a name="feature-pack-3-updates"></a>Actualizaciones de características Pack 3

**Adaptadores de Office 365**


Microsoft Office 365 es un servicio de suscripción en la nube que reúne lo mejor herramientas para las personas de manera trabajar hoy en día. Al combinar lo mejor de su clase aplicaciones como Excel y Outlook con los servicios de nube sólidas, como OneDrive y Microsoft Teams, Office 365 permite a cualquiera que cree y comparta en cualquier lugar en cualquier dispositivo.

Adaptadores de Microsoft BizTalk Server para Office 365 permiten a los profesionales de TI y desarrolladores empresariales a integrar correo, contactos y las programaciones de Outlook con nuevas soluciones basadas en BizTalk Server 2016.

#### <a name="office-365-mail-adapteroffice365-mail-adaptermd"></a>[Adaptador de correo electrónico de Office 365](office365-mail-adapter.md)
El adaptador de BizTalk para el correo de Office 365, puede leer, marcar como leído o eliminar las ubicaciones de recepción de mensajes de correo electrónico a través de servidor de BizTalk unidireccional de Outlook. Con este adaptador, puede escribir mensaje de correo electrónico, incluido el establecimiento de prioridad del mensaje, a través de unidireccional estático o puertos de envío de BizTalk Server dinámico.

#### <a name="office-365-calendar-adapteroffice365-calendar-adaptermd"></a>[Adaptador de calendario de Office 365](office365-calendar-adapter.md)
El adaptador de BizTalk para el calendario de Office 365, puede obtener calendario futuros eventos mediante unidireccional de BizTalk Server recibir ubicaciones. Con este adaptador, puede crear eventos de calendario y especificar a los asistentes obligatorios y opcionales, puertos de envío unidireccional estático o dinámico BizTalk Server a través de.

#### <a name="office-365-contact-adapteroffice365-contact-adaptermd"></a>[Adaptador de contacto de Office 365](office365-contact-adapter.md)
El adaptador de BizTalk para el contacto de Office 365, puede crear contactos y escriba toda la configuración, los puertos de envío unidireccional estático o dinámico BizTalk Server a través de.

## <a name="feature-pack-2-updates"></a>Actualizaciones de características Pack 2

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[Exponer los extremos SOAP con API Management](../core/connect-to-azure-api-management.md)

Expansión de la integración de la administración de API realizada con Feature Pack 1, ahora puede exponer un WCF-BasicHTTP ubicación de recepción como un extremo SOAP mediante la consola de administración de BizTalk Server. 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[Utilice el adaptador del centro de eventos](event-hubs-adapter.md)

Enviar mensajes de BizTalk a Azure Event Hubs y recibir mensajes desde Azure Event Hubs a BizTalk Server. Al configurar las propiedades de transporte, puede iniciar sesión en su cuenta de Azure fácilmente y seleccionar automáticamente el espacio de nombres de Azure Event Hubs y el centro de eventos.

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[Copia de seguridad en la cuenta de Azure blob](../core/how-to-configure-the-backup-biztalk-server-job.md)
El trabajo de copia de seguridad de BizTalk Server realiza una copia de seguridad de los archivos de registro y las bases de datos de BizTalk. Al configurar este trabajo del Agente SQL, puede especificar una cuenta de almacenamiento de blobs de Azure dentro de las propiedades del trabajo. Esto proporciona otra opción para los datos, en lugar de usar un disco físico local de copia de seguridad. 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[Implementación en varios equipos mediante VSTS](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
Uso de grupos de implementación, puede implementar aplicaciones en varios servidores de BizTalk. También puede establecer el nombre de la aplicación en el proyecto de aplicación e instalar la aplicación especificando el servidor de administración.

[Grupos de implementación](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) proporciona más detalles sobre cómo hacerlo en VSTS.  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[Uso de Service Bus Premium](../core/sb-messaging-adapter.md)

El adaptador de Bus de servicio es compatible con Premium de Service Bus, incluido el envío de mensajes a los temas y colas con particiones. [Niveles de mensajería estándares y Premium de Service Bus](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging) detalles más sobre Service Bus Premium. 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[Uso de las instancias con nombre con Application Insights](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
Al habilitar el análisis y escriba la clave de Application Insights, puede obtener el error: 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

Esto sucede cuando se usa SQL instancias con nombre. Esto se ha corregido en este feature pack; Puede usar las instancias predeterminadas SQL y las instancias con nombre de SQL. 

#### <a name="tls-12-support"></a>Compatibilidad con TLS 1.2

TLS 1.2 es totalmente compatible en BizTalk Server, incluidos todos los adaptadores y todos los aceleradores. Puede deshabilitar SSL, TLS 1.0 y 1.1 de TLS en el servidor BizTalk Server. 

Información de clave: 

* Los sistemas externos que se comunica con BizTalk, también deben admitir TLS 1.2
* Cualquier código personalizado, como los functoids, es posible que deba actualizarse para admitir TLS 1.2

[Descripción del protocolo TLS/SSL](https://support.microsoft.com/kb/3155464) se describe cómo configurar un entorno de TLS 1.2. 

#### <a name="use-latest-newtonsoft-json"></a>Usar JSON Newtonsoft más reciente 
Newtonsoft es un marco JSON para. NET. En este feature pack se incluye compatibilidad con la versión 10.0.3. [Descargue v. 10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) directamente desde NuGet. 


## <a name="feature-pack-1-updates"></a>Actualizaciones de características Pack 1

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[Enviar datos de diagnóstico a Application Insights.](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

Enviar datos de seguimiento a Application Insights de Azure para usar sus características, como análisis, aprendizaje automático, diagnósticos y mucho más. 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[Configurar los datos operativos fuente mediante Power BI](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

Enviar datos de seguimiento en Power BI con oData. Por ejemplo, obtener una representación visual de los datos de seguimiento de los puertos y orquestaciones. 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[Conectarse a la administración de las API de REST de BizTalk](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

Use las API de REST para administrar de forma remota los artefactos de BizTalk, incluidos los contratos, las instancias suspendidas, dado de baja orquestaciones y mucho más.

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[Configurar la programación avanzada](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

Habilitar avanzadas de programación en sus ubicaciones de recepción. Por ejemplo, establezca la zona horaria, o puede establecer una ventana de servicio de periodicidad para un día concreto de un mes concreto.

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[Configurar implementaciones automáticas con VSTS](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

Usar Visual Studio Team Services (VSTS) para implementar automáticamente las soluciones o actualizar aplicaciones existentes. VSTS se comunica con un agente instalado en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[Conectarse a las columnas de SQL Server Always Encrypted con BizTalk Server](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

Usar el adaptador de WCF-SQL para consultar columnas cifradas de una base de datos Always Encrypted en SQL Server.

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[Integración con API Management](../core/connect-to-azure-api-management.md)

Dentro de su servicio de administración de API de Azure, puede crear y exponer una API como WSDL y use el identificador URI a un extremo SOAP de BizTalk.  
