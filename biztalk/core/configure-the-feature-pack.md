---
title: Configurar el feature pack | Documentos de Microsoft
description: Instalar y configurar feature pack de 1 y 2 del paquete de características. Ver la lista de características nuevas, como administración de API, implementación de servicios de equipo, nuevos adaptadores de Azure, las copias de seguridad etc. en BizTalk Server 2016
ms.custom: ''
ms.date: 11/22/2017
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
ms.openlocfilehash: e5b4164cf1f1355ab9a0d2f350aa5b3b5ce411e0
ms.sourcegitcommit: f4c0d7bc4b617688c643101a34062db90014851a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2017
ms.locfileid: "25550763"
---
# <a name="configure-the-feature-pack"></a>Configurar el feature pack

## <a name="overview"></a>Información general

[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]utiliza paquetes de características para proporcionar una integración más estrecha con Azure, mejoras y características. Estos paquetes de características extienden la funcionalidad en áreas clave, como la implementación, seguridad, análisis, en tiempo de ejecución y copia de seguridad. 

> [!NOTE]
> Los paquetes de características están disponibles con las ediciones Enterprise y Developer de [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] cuando: 
> 
> - Usar con Software Assurance (SA), o
> - Ejecutando [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] en Azure con un contrato Enterprise
> 
> Los paquetes de características no están disponibles para cualquier otro [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] edition o cualquier otro [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] versión. 

## <a name="download-and-install"></a>Descargue e instale

Los paquetes de características son acumulativos. Por lo que al instalar el feature pack de 2, también obtendrá las características y actualizaciones en feature pack 1.

* Descargue el [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 2 de](https://aka.ms/bts2016fp2).

* Descargue el [!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [Feature Pack 1 de](https://www.microsoft.com/download/details.aspx?id=55100).

#### <a name="install"></a>Install

1. Ejecute el programa de instalación como administrador.
2. En **bienvenida**, seleccione **siguiente**. 
3. Acepte el contrato de licencia y seleccione **Siguiente**. 
4. Continúe con la instalación. Durante la instalación, pueden abrir varias ventanas de comandos y se cierre. Cuando haya finalizado, deberá **finalizar**.

Se crea un registro de instalación en `C:\ProgramData\Microsoft\E-Business Servers Updates\Updates\Uninstall4014788-FP2\setup.log`.

>[!TIP]
> Para obtener instrucciones completas sobre la instalación, consulte el [instalación paso a paso de Feature Pack](https://blog.sandro-pereira.com/2017/04/27/microsoft-biztalk-server-2016-feature-pack-1-step-by-step-installation/) entrada de blog.

## <a name="feature-pack-2-updates"></a>Actualizaciones de características Pack 2

#### <a name="expose-soap-endpoints-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[Exponer los extremos SOAP con administración de API](../core/connect-to-azure-api-management.md)

Analizando la integración de administración de API realizada con Feature Pack 1, ahora puede exponer un WCF-BasicHTTP ubicación de recepción como un extremo SOAP mediante la consola de administración de BizTalk Server. 

#### <a name="use-the-event-hub-adapterevent-hubs-adaptermd"></a>[Usar el adaptador de concentrador de eventos](event-hubs-adapter.md)

Enviar mensajes de BizTalk a los centros de eventos de Azure y recibir mensajes desde los centros de eventos de Azure a BizTalk Server. Al configurar las propiedades de transporte, puede iniciar sesión fácilmente en su cuenta de Azure y seleccionar automáticamente el espacio de nombres de los centros de eventos de Azure y centro de eventos.

#### <a name="backup-to-azure-blob-accountcorehow-to-configure-the-backup-biztalk-server-jobmd"></a>[Copia de seguridad para la cuenta de blobs de Azure](../core/how-to-configure-the-backup-biztalk-server-job.md)
El trabajo de copia de seguridad de BizTalk Server realiza una copia de seguridad de los archivos de registro y las bases de datos de BizTalk. Al configurar este trabajo del Agente SQL, puede especificar una cuenta de almacenamiento de blobs de Azure dentro de las propiedades del trabajo. Esto le ofrece otra opción para copia de seguridad de los datos, en lugar de usar un disco físico local. 

#### <a name="multi-machine-deployment-using-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[Implementación en varios equipos mediante VSTS](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)
Uso de grupos de implementación, puede implementar las aplicaciones en varios servidores de BizTalk. También puede establecer el nombre de la aplicación en el proyecto de aplicación y la instalación de la aplicación especificando el servidor de administración.

[Grupos de implementación](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index) proporciona información detallada sobre cómo hacerlo en VSTS.  

#### <a name="use-service-bus-premiumcoresb-messaging-adaptermd"></a>[Usar Premium de Bus de servicio](../core/sb-messaging-adapter.md)

El adaptador de Bus de servicio admite Premium de Bus de servicio, incluido el envío de mensajes a colas con particiones y temas. [Niveles de mensajes estándares y Premium de Bus de servicio](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-premium-messaging) detalles más información acerca de Premium de Bus de servicio. 

#### <a name="use-named-instances-with-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[Usar las instancias con nombre con Application Insights](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)
Al habilitar el análisis y escriba la clave de Application Insights, es posible recibir el error: 

```
Group settings were not applied. (A database failure occurred due to database connectivity problems.)
```

Esto sucede cuando se usa SQL instancias con nombre. Esto se corrigió en este feature pack; Puede usar instancias predeterminadas SQL y SQL las instancias con nombre. 

#### <a name="tls-12-support"></a>Soporte de TLS 1.2

TLS 1.2 es totalmente compatible en BizTalk Server, incluidos todos los adaptadores y todos los aceleradores. Puede deshabilitar SSL, TLS 1.0 y 1.1 de TLS en el servidor BizTalk Server. 

Información de clave: 

* Los sistemas externos comunicarse con BizTalk también necesitan admitir TLS 1.2
* Cualquier código personalizado, como los functoids, necesite actualizarse para admitir TLS 1.2

[Descripción del protocolo TLS/SSL](https://support.microsoft.com/kb/3155464) describe cómo configurar un entorno de TLS 1.2. 

#### <a name="use-latest-newtonsoft-json"></a>Usar JSON Newtonsoft más reciente 
Newtonsoft es un marco JSON para. NET. En este feature pack se incluye compatibilidad con la versión 10.0.3. [Descargar v. 10.0.3](https://www.nuget.org/packages/Newtonsoft.Json/10.0.3) directamente de NuGet. 


## <a name="feature-pack-1-updates"></a>Actualizaciones de características Pack 1

#### <a name="send-tracking-data-to-application-insightscoresend-tracking-data-to-azure-application-insights-using-biztalk-servermd"></a>[Enviar datos de diagnóstico a Application Insights.](../core/send-tracking-data-to-azure-application-insights-using-biztalk-server.md)

Enviar datos de seguimiento a Azure Application Insights para usar sus características, como el análisis, aprendizaje automático, diagnósticos y mucho más. 

#### <a name="configure-the-operational-data-feed-using-power-bicoreconfigure-the-operational-data-feed-for-power-bi-with-biztalk-servermd"></a>[Configurar la fuente con Power BI de datos operativos](../core/configure-the-operational-data-feed-for-power-bi-with-biztalk-server.md)

Enviar datos de seguimiento a Power BI con oData. Por ejemplo, obtener una representación visual de los datos de seguimiento de los puertos y orquestaciones. 

#### <a name="connect-to-the-management-rest-apis-in-biztalkcoreinstall-and-configure-the-management-rest-apis-in-biztalk-servermd"></a>[Conectarse a la administración de API de REST de BizTalk](../core/install-and-configure-the-management-rest-apis-in-biztalk-server.md)

Use las API de REST para administrar de forma remota los artefactos de BizTalk, incluidos los contratos, las instancias suspendidas, dado de baja orquestaciones y mucho más.

#### <a name="configure-advanced-schedulingcoreconfigure-the-time-zone-and-recurrence-scheduling-in-biztalk-servermd"></a>[Configurar la programación avanzada](../core/configure-the-time-zone-and-recurrence-scheduling-in-biztalk-server.md)

Habilitar avanzadas de programación en sus ubicaciones de recepción. Por ejemplo, establecer la zona horaria o establecer una ventana de servicio de periodicidad para un día determinado en un mes específico.

#### <a name="configure-automatic-deployments-with-vstscoreconfigure-automatic-deployment-with-visual-studio-team-services-in-biztalkmd"></a>[Configurar implementaciones automáticas con VSTS](../core/configure-automatic-deployment-with-visual-studio-team-services-in-biztalk.md)  

Usar Visual Studio Team Services (VSTS) para implementar automáticamente las soluciones o actualizar las aplicaciones existentes. VSTS se comunica con un agente instalado en el [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)].

#### <a name="connect-to-sql-server-always-encrypted-columns-with-biztalk-servercoreconnect-to-sql-server-always-encrypted-columns-with-biztalk-servermd"></a>[Conectarse a SQL Server Always Encrypted columnas con BizTalk Server](../core/connect-to-sql-server-always-encrypted-columns-with-biztalk-server.md)  

Utilice el adaptador de WCF-SQL para consultar columnas cifradas de una base de datos Always Encrypted en SQL Server.

#### <a name="integrate-with-api-managementcoreconnect-to-azure-api-managementmd"></a>[Integrar con administración de API](../core/connect-to-azure-api-management.md)

Dentro de su servicio de administración de API de Azure, puede crear y exponer una API como WSDL y usar el URI para un extremo SOAP de BizTalk.  