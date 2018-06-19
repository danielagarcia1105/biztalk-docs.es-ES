---
title: Configuración del motor y parámetros de ajuste de reglas | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- troubleshooting, registry keys
- registry keys
- Business Rules Engine, registry keys
- troubleshooting, business rules
- validating, business rules
- business rules, validating
ms.assetid: cb0bcffe-bbc6-4495-84d2-2a822c3413b3
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e6d2acc5b70f7a2be120db5159f893922135a429
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270340"
---
# <a name="rule-engine-configuration-and-tuning-parameters"></a>Parámetros de configuración y ajuste del motor de reglas
La siguiente tabla contiene una lista de claves del Registro que puede ser útil para la validación y solución de problemas de la configuración. Estas claves del registro se almacenan en **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\BusinessRules\3.0**.  
  
 Con la excepción de las primeras tres claves aparecen, estas claves están diseñadas para permitir a los productos y no a los usuarios, para personalizar el motor de reglas. Todas ellas se crean en el momento de la instalación; sin embargo, no se proporciona ninguna interfaz para configurar estos valores.  
  
 Las definiciones de las columnas de la tabla son las siguientes:  
  
-   **Nombre**. Nombre de la clave del Registro.  
  
-   **Descripción**. Descripción breve sobre la ubicación o utilización de la clave.  
  
-   **Configuración predeterminada**. Valor devuelto si la clave no existe.  
  
-   **Instalación predeterminada**. Valor configurado por BizTalk Server al instalar el motor de reglas.  
  
|Nombre|Description|Configuración predeterminada|Instalación predeterminada|  
|----------|-----------------|--------------------|---------------------|  
|InstallPath|Ubicación de los archivos BRE que se usa en el momento de la configuración.|(null)|C:\Archivos de programa\Archivos comunes\Microsoft BizTalk (o C:\Archivos de programa (x86)\Archivos comunes\Microsoft BizTalk en un sistema operativo de 64 bits)|  
|DatabaseServer|Servidor de bases de datos utilizado|(cadena vacía)|Nombre del servidor de bases de datos especificado durante la configuración de BRE.|  
|DatabaseName|Nombre de la base de datos que se va a utilizar.|(cadena vacía)|Nombre de la base de datos especificada durante la configuración de BRE. Normalmente, es BizTalkRuleEngineDb|  
|PubSubAdapterAssembly|Nombre de ensamblado del adaptador de pub/sub.|Microsoft.RuleEngine|Microsoft.RuleEngine|  
|PubSubAdapterClass|Nombre de clase del adaptador de pub/sub.|Microsoft.RuleEngine.PubSubAdapter|Microsoft.RuleEngine.PubSubAdapter|  
|DeploymentDriverAssembly|Nombre de ensamblado del controlador de implementación.|Microsoft.RuleEngine|Microsoft.BizTalk.RuleEngineExtensions|  
|DeploymentDriverClass|Nombre de clase del controlador de implementación.|Microsoft.RuleEngine.RuleSetDeploymentDriver|Microsoft.BizTalk.RuleEngineExtensions.RuleSetDeploymentDriver|  
|TrackingInterceptorAssembly|Nombre de ensamblado del interceptor de seguimiento|(cadena vacía)|Microsoft.BizTalk.RuleEngineExtensions|  
|TrackingInterceptorClass|Nombre de clase del interceptor de seguimiento|(cadena vacía)|Microsoft.BizTalk.RuleEngineExtensions.RuleSetTrackingInterceptor|  
|TranslationTimeout|Tiempo máximo en milisegundos que se puede utilizar para traducir un conjunto de reglas. **Nota:** Esto puede reemplazarse en forma de conjunto de reglas mediante la propiedad RuleSetConfiguration).|60000 (1 minuto)|60000|  
|UpdateServiceName|Nombre del servicio de actualización que utiliza .NET Remoting para localizar el servicio.|RemoteUpdateService|RemoteUpdateService|  
|UpdateServiceHost|Equipo que hospeda el servicio de actualización que utiliza .NET remoting para localizar el servicio. **Nota:** el servicio actualmente restringe los mensajes entrantes al mismo equipo solo.|localhost|localhost|  
|UpdateServicePort|Número de puerto de TCP utilizado por el servicio de actualización que utiliza .NET Remoting para localizar el servicio.|3132|3132|  
|CacheEntries|Número máximo de conjuntos de reglas que el servicio de actualización almacena en caché.|32|32|  
|CacheTimeout|Tiempo en segundos para que venzan las entradas en la caché de servicio de actualización.|3600 (1 hora)|3600|  
|PollingInterval|Tiempo en segundos para que el servicio de actualización compruebe si hay actualizaciones en SqlRuleStore.|60 (1 minuto)|60|  
|SqlTimeout|Valor de tiempo de espera de los comandos SQL que tienen acceso al almacén de reglas SQL. El valor de esta clave se interpreta de la siguiente manera:<br /><br /> < 0 - Utiliza el valor predeterminado de .NET (30 segundos)<br /><br /> = 0 - Tiempo de espera ilimitado<br /><br /> > 0 - Tiempo máximo antes de que se agote el tiempo de espera de una consulta|-1|-1|  
  
 También puede agregar una clave del registro denominada StaticSupport, tal y como se mencionó en [invocar miembros estáticos de una clase](../core/invoking-static-members-of-a-class.md).  
  
 Los valores del Registro son globales para todas las aplicaciones que alojan una instancia de motor de reglas. Puede anular estos valores del Registro a nivel de aplicación mediante el uso del archivo de configuración de la aplicación. Para las aplicaciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], la aplicación de host es BTSNTSvc.exe y el archivo de configuración es BTSNTSvc.exe.config, que podrá encontrar en el directorio de instalación de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  Deberá especificar en el archivo de configuración de la aplicación los valores de los parámetros de configuración que desee anular, tal como se muestra a continuación:  
  
```  
<configuration>  
    <configSections>  
        <section name="Microsoft.RuleEngine" type="System.Configuration.SingleTagSectionHandler" />  
    </configSections>  
    <Microsoft.RuleEngine  
        UpdateServiceHost="localhost"  
        UpdateServicePort="3132"  
        UpdateServiceName="RemoteUpdateService"  
        CacheEntries="32"  
        CacheTimeout="3600"  
        PollingInterval="60"  
        TranslationTimeout="3600"  
        CachePruneInterval="60"  
        DatabaseServer="(localhost)"  
        DatabaseName="BizTalkRuleEngineDb"  
        SqlTimeout="-1"  
        StaticSupport="1"  
    />  
</configuration>  
```