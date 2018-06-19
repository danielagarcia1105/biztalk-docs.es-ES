---
title: Puertos para el servidor de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking server
- ports, tracking server
ms.assetid: 4b4913a4-7d8d-4fd0-a116-ba868c4ad7da
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 975f5e42c800a6d4ae4015108afa2650b2c7f626
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266356"
---
# <a name="ports-for-the-tracking-server"></a>Puertos para el servidor de seguimiento
Para obtener información completa acerca de cómo proteger la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 La tabla siguiente contiene la lista de puertos que debe configurar para que el servidor de seguimiento tenga acceso a los servicios necesarios. El firewall en el que tiene que abrir los puertos dependerá de que el servidor de destino forme parte de la arquitectura. Debe abrir estos puertos tanto al tráfico entrante como al tráfico saliente.  
  
|Contexto de servicio o aplicación|Servidor de destino|Servicio de destino|Puerto|Protocolo|Razón|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|Usuario conectado|Base de datos de administración de BizTalk|SQL Server|1433|TCP|Crear y configurar la base de datos de administración de BizTalk|  
|Usuario conectado|Base de datos de administración de BizTalk|DTC|135|TCP|Transacción de conexión a SQL Server para actualizar y recuperar información de la base de datos|  
|Usuario conectado|Base de datos de administración de BizTalk|DTC|50000-50200|TCP|Puertos RPC secundarios **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Usuario conectado|base de datos de SSO|SQL Server|1433|TCP|Para que el servicio SSO se conecte a la base de datos de SSO|  
|Usuario conectado|Base de datos de importación principal de BAM|SQL Server|1433|TCP|Validar la base de datos de importación principal de SAE. El host de seguimiento se conecta a esta base de datos durante el tiempo de ejecución.|  
|Usuario conectado|Base de datos de esquema de estrella de SAE|SQL Server|1433||Actualizar y recuperar información de la base de datos. **Nota:** el host de seguimiento se conecta a esta base de datos sólo cuando se ejecuta el Administrador de configuración de BizTalk para crear un nuevo grupo de BizTalk desde este servidor.|  
|Usuario conectado|Base de datos de análisis de BAM|OLAP|445|TCP|Crear el archivo de datos OLAP (.mdb) en el equipo remoto. **Nota:** el host de seguimiento se conecta a esta base de datos sólo cuando se ejecuta el Administrador de configuración de BizTalk para crear un nuevo grupo de BizTalk desde este servidor.|  
|Usuario conectado|Base de datos de análisis de BAM|OLAP|2383 (SQL Server 2005 Analysis Services)||Para crear y configurar la base de datos de análisis de BAM **Nota:** seguimiento el host se conecta a esta base de datos sólo cuando se ejecuta el Administrador de configuración de BizTalk para crear un nuevo grupo de BizTalk desde este servidor.|  
|Usuario conectado|Base de datos de análisis de BAM|OLAP|2725|TCP|Para la recuperación de datos para el análisis (informes de tabla dinámica) **Nota:** seguimiento el host se conecta a esta base de datos sólo cuando se ejecuta el Administrador de configuración de BizTalk para crear un nuevo grupo de BizTalk desde este servidor.|  
|Usuario conectado|Base de datos de seguimiento|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos|  
|Usuario conectado|Base de datos de cuadro de mensajes|SQL|1433|TCP|Actualizar y recuperar información de la base de datos|  
|Usuario conectado|Base de datos de cuadro de mensajes|DTC|135|TCO|Transacción de conexión a SQL Server|  
|Usuario conectado|Base de datos de cuadro de mensajes|DTC|50000-50200||Puertos RPC secundarios|  
|Usuario conectado|Base de datos de archivo SAE|SQL Server|1433|TCP|Para actualizar y recuperar la información de la base de datos **Nota:** seguimiento el host se conecta a esta base de datos sólo cuando se ejecuta el Administrador de configuración de BizTalk para crear un nuevo grupo de BizTalk desde este servidor.|  
|Cuenta de servicio de SSO|base de datos de SSO|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos|  
|Cuenta de servicio de SSO|Servidor secreto principal|Servicio de clave secreta principal|135|TCP|Transacción de conexión a SQL Server para que el servicio SSO se conecte al servidor secreto principal|  
|Cuenta de servicio de SSO|Servidor secreto principal|RPC secundario|50000-50200|TCP|Puertos RPC secundarios para que el servicio SSO se conecte al servidor secreto principal|  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de nomenclatura de servidores](../core/server-naming-conventions.md)   
 [Consideraciones de seguridad para el seguimiento de datos de instancias y mensajes](../core/security-considerations-for-message-and-instance-data-tracking.md)   
 [Arquitectura distribuida de gran tamaño con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md)   
 [Puertos necesarios para el servidor BizTalk Server](../core/required-ports-for-biztalk-server.md)   
 [Información general sobre la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)