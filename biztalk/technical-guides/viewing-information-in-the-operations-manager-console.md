---
title: "Ver la información en la consola de Operations Manager | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6acdf425-4c36-4d89-9493-81b33481fe6d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 687932839c379ed9589a51baae0ae8562f4af705
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="viewing-information-in-the-operations-manager-console"></a>Ver información en la consola de Operations Manager
Usar las vistas proporcionadas con el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack para conocer la disponibilidad actual, la configuración, el estado y el rendimiento de su entorno de BizTalk Server. Una vista puede contener una larga lista de objetos. Para buscar un objeto o grupo de objetos específico, puede usar los botones Ámbito, Búsqueda y Buscar de la barra de herramientas de Operations Manager. Para obtener más información, vea los temas de administración de supervisión datos mediante ámbito, búsqueda y busque el tema en la Ayuda de Operations Manager 2007 R2\2012.  
  
 Las siguientes vistas aparecen directamente en  **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  nodo en el panel de supervisión de la consola del operador.  
  
-   **Vistas de aplicación**: Administrador de BizTalk A está interesado en supervisar el estado y el estado de varios artefactos de BizTalk Server y las aplicaciones, como orquestaciones puertos de envío, ubicaciones de recepción y así sucesivamente.  
  
-   **Vistas de implementación**: un administrador de TI empresarial está interesado en supervisar el estado y el estado de las diversas implementaciones de enterprise los equipos que hospedan SQL Server bases de datos, equipos que hospedan el servicio SSO, los equipos de la instancia de host, IIS, Servicios de red y así sucesivamente.  
  
## <a name="application-views"></a>Vistas de aplicación  
 Vistas de aplicación contienen los elementos descritos en la tabla siguiente.  
  
### <a name="elements"></a>Elementos  
  
|Nombre de vista|Description|  
|---------------|-----------------|  
|Vista de estado de la aplicación|Se trata de una vista de panel que muestra el estado de una aplicación de BizTalk. El estado de aplicación de BizTalk depende del estado de sus artefactos como orquestaciones, grupo de puertos de envío, puerto de envío, puerto de recepción y ubicación de recepción que lo componen. El panel de vista de detalles proporciona las propiedades de la aplicación de BizTalk hospedada.|  
|Vista de estado de grupo|Se trata de una vista de panel que muestra el estado de un grupo de BizTalk. El estado de un grupo de BizTalk depende del estado de host de BizTalk y aplicaciones de BizTalk. El panel de vista de detalles proporciona las propiedades del grupo de BizTalk.|  
|Vista de estado de host|Se trata de una vista de panel que muestra el estado de un host de BizTalk. El estado de un host de BizTalk depende del estado de las instancias de las aplicaciones alojadas de BizTalk. El panel de vista de detalles proporciona las propiedades del host de BizTalk.|  
  
#### <a name="application-artifacts-views"></a>Vistas de artefactos de aplicaciones  
 Vistas de artefactos de aplicaciones contienen los elementos descritos en la tabla siguiente.  
  
### <a name="elements"></a>Elementos  
  
|Nombre de vista|Description|  
|---------------|-----------------|  
|Vista de estado de orquestaciones|Muestra el estado de configuración y en tiempo de ejecución de la orquestación para la aplicación hospedada.|  
|Vista de estado de la ubicación de recepción|Muestra el estado en tiempo de ejecución y configuración de ubicación de recepción para la aplicación hospedada.|  
|Vista de estado de puertos de recepción|Muestra el estado en tiempo de ejecución y configuración de puertos de recepción para la aplicación hospedada.|  
|Vista de estado de grupos de puertos de envío|Muestra el estado de configuración y en tiempo de ejecución del grupo de puertos de envío para la aplicación hospedada.|  
|Vista de estado del puerto de envío|Muestra el estado en tiempo de ejecución y configuración de puerto de envío para la aplicación hospedada.|  
  
## <a name="deployment-views"></a>Vistas de implementación  
 Vistas de implementación contienen los elementos descritos en la tabla siguiente.  
  
### <a name="elements"></a>Elementos  
  
|Nombre de vista|Description|  
|---------------|-----------------|  
|Vista de estado de implementación|Se trata de una vista de panel que muestra el estado de un grupo de implementación de BizTalk. El estado del grupo de implementación de BizTalk depende del estado de los componentes de servidor en tiempo de ejecución que lo componen como rol de BAM, rol de motor de reglas, función de tiempo de ejecución de BizTalk y Host de BizTalk. El panel de vista de detalles proporciona las propiedades del grupo de implementación de BizTalk.|  
|Vista de estado de hosts|Se trata de una vista de panel que muestra el estado de un host de BizTalk. El estado de un host de BizTalk depende del estado de las instancias de las aplicaciones alojadas de BizTalk. El panel de vista de detalles proporciona las propiedades del host de BizTalk.|  
|Vista de estado del rol de motor de reglas|Se trata de una vista de panel que muestra el estado de un servicio de motor de reglas que se ejecuta en los servidores en tiempo de ejecución. El panel de vista de detalles proporciona las propiedades de los servidores en tiempo de ejecución que tienen instalado el servicio de motor de reglas.|  
|Vista de estado de la función en tiempo de ejecución|Se trata de una vista de panel que muestra el estado de los servidores en tiempo de ejecución que tienen instalado el servicio de motor de reglas en tiempo de ejecución. El estado de una función de tiempo de ejecución de BizTalk depende del estado de sus componentes, como el servicio SSO, base de datos de administración, base de datos de cuadro de mensaje, base de datos SSO y base de datos de seguimiento. El panel de vista de detalles proporciona las propiedades de los servidores en tiempo de ejecución.|  
  
### <a name="bam-component-views"></a>Vistas de componente BAM  
  
### <a name="elements"></a>Elementos  
  
|Nombre de vista|Description|  
|---------------|-----------------|  
|Vista de estado de alertas de BAM|Muestra la vista de estado del componente de alertas de BAM de BizTalk.|  
|Vista de estado de análisis de BAM|Muestra la vista de estado del componente de análisis de BAM de BizTalk.|  
|Vista de rendimiento de BAM|El panel Leyenda muestra el contador de rendimiento de BAM.|  
|Vista de estado de Portal de BAM|Muestra la vista de estado de portal de BAM.|  
|Vista de estado de tiempo de ejecución de BAM|Muestra la vista de estado de tiempo de ejecución BAM.|  
  
#### <a name="bam-alerts"></a>Alertas de BAM  
  
### <a name="elements"></a>Elementos  
  
|Nombre de vista|Description|  
|---------------|-----------------|  
|Vista de estado de alertas de BAM|Muestra una lista de alertas de BAM de BizTalk que es un servicio de notificación y genera cualquiera de los servicios críticos no están disponible.|  
  
##### <a name="runtime-component-views"></a>Vistas de componentes en tiempo de ejecución  
  
### <a name="elements"></a>Elementos  
  
|Nombre de vista|Description|  
|---------------|-----------------|  
|Vista de estado de servicio de aplicación|Muestra el estado de todas las instancias de host en un grupo de BizTalk.|  
|Vista de estado de rendimiento del cuadro de mensaje|El panel Leyenda muestra el contador de rendimiento para tamaño de los datos de seguimiento de cuadro de mensaje.|  
|Vista de rendimiento de los adaptadores de mensajería|El panel Leyenda muestra el contador de rendimiento de Bytes recibidos de adaptador de recepción de MSMQ.|  
|Vista de rendimiento de mensajería|El panel Leyenda muestra el contador de rendimiento para ubicaciones de recepción activas.|  
|Vista de rendimiento de orquestación|El panel Leyenda muestra el contador de rendimiento para orquestaciones ejecutables.|  
|Vista de uso de recursos de servidor|El panel Leyenda muestra el contador de rendimiento de tiempo de inactividad de porcentaje de disco físico.|  
  
###### <a name="runtime-alerts"></a>Alertas en tiempo de ejecución  
  
### <a name="elements"></a>Elementos  
  
|Nombre de vista|Description|  
|---------------|-----------------|  
|Vista de alertas de núcleo|Muestra las alertas de núcleo de BizTalk.|  
|Vista de alertas de mensajería|Muestra las alertas de mensajería de BizTalk.|