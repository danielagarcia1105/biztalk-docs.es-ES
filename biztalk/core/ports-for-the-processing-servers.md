---
title: Puertos para los servidores de procesamiento | Documentos de Microsoft
ms.custom: 
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- servers, processing
- ports, processing servers
ms.assetid: 0207b68f-8769-4674-aadc-b3a67b6f210b
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4539a17ae95f02c17c754ddcf44882911d805b5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ports-for-the-processing-servers"></a>Puertos de los servidores de procesamiento
Para obtener información completa acerca de cómo proteger la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 La tabla siguiente contiene la lista de puertos que debe configurar para que los servidores de procesamiento tengan acceso a los servicios necesarios. El firewall en el que tiene que abrir los puertos dependerá de que el servidor de destino forme parte de la arquitectura. Debe abrir estos puertos tanto al tráfico entrante como al tráfico saliente.  
  
|Contexto de servicio o aplicación|Servidor de destino|Servicio de destino|Puerto|Protocolo|Razón|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|Usuario conectado|Base de datos de administración de BizTalk|SQL Server|1433|TCP|Crear y configurar la base de datos de administración de BizTalk|  
|Usuario conectado|Base de datos de administración de BizTalk|DTC|135|TCP|Transacción de conexión a SQL Server para crear, configurar y actualizar la base de datos|  
|Usuario conectado|Base de datos de administración de BizTalk|DTC|50000-50200|TCP|Puertos RPC secundarios **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Usuario conectado|Base de datos de cuadro de mensajes|SQL Server|1433|TCP|Crear y configurar la base de datos de cuadro de mensajes|  
|Usuario conectado|Base de datos de cuadro de mensajes|DTC|135|TCP|Transacción de conexión a SQL Server para crear el host|  
|Usuario conectado|Base de datos de cuadro de mensajes|DTC|50000-50200|TCP|Puertos RPC secundarios **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Cuenta de servicio de SSO|base de datos de SSO|SQL Server|1433|TCP|Para que el inicio de sesión único (SSO) empresarial se conecte a la base de datos de SSO|  
|Usuario conectado|base de datos de SSO|DTC|135|TCP|Transacción de conexión a SQL Server para conectarse a la base de datos de SSO|  
|Usuario conectado|base de datos de SSO|DTC|50000-50200|TCP|Puertos RPC secundarios **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Usuario conectado|Base de datos de seguimiento|SQL Server|1433|TCP|Crear y configurar la base de datos de seguimiento|  
|Usuario conectado|Base de datos de seguimiento|DTC|135|TCP|Transacción de conexión a SQL Server|  
|Usuario conectado|Base de datos de seguimiento|DTC|50000-50200|TCP|Puertos RPC secundarios **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Usuario conectado|Base de datos del motor de reglas de negocios|SQL Server|1433|TCP|Crear y configurar la base de datos del motor de reglas de negocios|  
|Usuario conectado|Base de datos del motor de reglas de negocios|DTC|135|TCP|Transacción de conexión a SQL Server para crear, configurar y actualizar la base de datos|  
|Usuario conectado|Base de datos del motor de reglas de negocios|DTC|50000-50200|TCP|Puertos RPC secundarios **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Usuario conectado|Base de datos de análisis de BAM|OLAP|2393|TCP|Para actualizar y recuperar información de la base de datos de análisis de SAE|  
|Usuario conectado|Base de datos de análisis de BAM|Sistema de archivos de servidor OLAP|445|TCP|Para crear el archivo de datos OLAP (.mdb) en el equipo remoto|  
|Usuario conectado|Base de datos de análisis de BAM|OLAP|2725|TCP|Para la recuperación de datos para el análisis (informes de tabla dinámica)|  
|Usuario conectado|Base de datos de análisis de BizTalk|OLAP|2393|TCP|Para crear y configurar la base de datos de análisis de BizTalk **Nota:** los servidores de procesamiento necesitan para conectarse a esta base de datos sólo cuando se ejecuta el Administrador de configuración de BizTalk.|  
|Usuario conectado|Base de datos de análisis de BizTalk|Sistema de archivos de servidor OLAP|445|TCP|Para crear el archivo de datos OLAP (.mdb) en el equipo remoto **Nota:** los servidores de procesamiento necesitan para conectarse a esta base de datos sólo cuando se ejecuta el Administrador de configuración de BizTalk.|  
|Usuario conectado|Base de datos de análisis de BizTalk|OLAP|2725|TCP|Crear y configurar la base de datos y recuperar datos para el análisis (informes de tabla dinámica)|  
|Cuenta de servicio de inicio de sesión único (SSO)|Servidor secreto principal|RPC|135|TCP|Transacción de conexión a SQL Server para que el servicio SSO se conecte al servidor secreto principal|  
|Cuenta de servicio de inicio de sesión único (SSO)|Servidor secreto principal|RPC secundario|50000-50200|TCP|Puertos RPC secundarios para que el servicio SSO se conecte al servidor secreto principal. **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Cuenta de servicio de una instancia de host de BizTalk|Base de datos de cuadro de mensajes|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
|Cuenta de servicio de una instancia de host de BizTalk|Base de datos de administración de BizTalk|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
|Cuenta de servicio de una instancia de host de BizTalk|base de datos de SSO|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
|Cuenta de servicio de una instancia de host de BizTalk|Base de datos de seguimiento|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de nomenclatura de servidores](../core/server-naming-conventions.md)   
 [Recomendaciones de seguridad en tiempo de ejecución de BizTalk Server](../core/biztalk-server-runtime-security-recommendations.md)   
 [Recomendaciones de seguridad de motor de reglas de negocios](../core/business-rule-engine-security-recommendations.md)   
 [Arquitectura distribuida de gran tamaño con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md)   
 [Puertos necesarios para el servidor BizTalk Server](../core/required-ports-for-biztalk-server.md)