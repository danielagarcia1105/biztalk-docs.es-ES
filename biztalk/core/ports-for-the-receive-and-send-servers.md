---
title: "Puertos para los servidores de envío y recepción | Documentos de Microsoft"
ms.custom: 
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection strings
- servers, sending
- ports, servers
- servers, receiving
- BizTalk Server, service accounts
- SSO, service accounts
ms.assetid: 19cafe74-6676-4779-8ced-de0841dba19f
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04ddda71d04cf784f07cf8e0783775d7ae91e6d5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ports-for-the-receive-and-send-servers"></a>Puertos para los servidores de envío y recepción
Para obtener información completa acerca de cómo proteger la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 La tabla siguiente contiene la lista de puertos que debe configurar para que los servidores de envío y recepción tengan acceso a los servicios que necesitan. El firewall en el que tiene que abrir los puertos dependerá de que el servidor de destino forme parte de la arquitectura. Debe abrir estos puertos tanto al tráfico entrante como al tráfico saliente.  
  
|Contexto de servicio o aplicación|Servidor de destino|Servicio de destino|Puerto|Protocolo|Reason|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|Cuenta de servicio de BizTalk|Recurso compartido de archivos<br /><br /> Recurso compartido de Página principal de documentos EDI|Servidor de envío y recepción|445|TCP|Recuperar y descargar archivos en la ubicación de archivos del adaptador de archivo|  
|Cuenta de servicio de BizTalk|Servidor FTP|Servicio FTP|20|TCP|Para que el adaptador de FTP recupere y descargue los archivos en el servidor FTP|  
|Cuenta de servicio de BizTalk|Servidor FTP|Servicio FTP|21|TCP|Para que el adaptador de FTP recupere y descargue los archivos en el servidor FTP|  
|Cuenta de servicio de BizTalk|Servidor POP3 Server|Servicio POP3|110|TCP|Para que el adaptador de POP3 recupere correo electrónico en el servidor POP3|  
|Cuenta de servicio de BizTalk|Servidor de procesamiento|Message Queue Server de Windows|1801|TCP|Para que el adaptador de BizTalk para Message Queue reciba y envíe mensajes al tiempo de ejecución de BizTalk.|  
|Cadena de conexión|Destino del adaptador SQL|SQL Server|1433|TCP|Recuperar y enviar mensajes de las bases de datos que utiliza el adaptador SQL|  
|Cadena de conexión|Destino del adaptador SQL|DTC|135|TCP|Transacción de conexión a SQL Server para el adaptador SQL|  
|Cadena de conexión|Destino del adaptador SQL|DTC|50000-50200|TCP|Puertos RPC secundarios para el adaptador de SQL **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Cuenta de servicio de BizTalk|SMTP o Exchange|SMTP|25|TCP|Para que el adaptador SMPT se conecte al servidor SMTP|  
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
|Usuario conectado|Base de datos de análisis de BAM|OLAP|2383 (SQL Server 2005 Analysis Services)|TCP|Para actualizar y recuperar información de la base de datos de análisis de SAE|  
|Usuario conectado|Base de datos de análisis de BAM|Sistema de archivos de servidor OLAP|445|TCP|Para crear el archivo de datos OLAP (.mdb) en el equipo remoto|  
|Usuario conectado|Base de datos de análisis de BAM|OLAP|2725|TCP|Para la recuperación de datos para el análisis (informes de tabla dinámica®)|  
|Usuario conectado|Base de datos de análisis de BizTalk|OLAP|2383 (SQL Server 2005 Analysis Services)|TCP|Para crear y configurar la base de datos de análisis de BizTalk **Nota:** los servidores de procesamiento necesario para conectarse a esta base de datos sólo cuando se ejecuta el Administrador de configuración de BizTalk.|  
|Usuario conectado|Base de datos de análisis de BizTalk|Sistema de archivos de servidor OLAP|445|TCP|Para crear el archivo de datos OLAP (.mdb) en el equipo remoto **Nota:** los servidores de procesamiento necesario para conectarse a esta base de datos sólo cuando se ejecuta el Administrador de configuración de BizTalk.|  
|Usuario conectado|Base de datos de análisis de BizTalk|OLAP|2725|TCP|Crear y configurar la base de datos y recuperar datos para el análisis (informes de tabla dinámica)|  
|Cuenta de servicio de inicio de sesión único (SSO)|Servidor secreto principal|RPC|135|TCP|Transacción de conexión a SQL Server para que el servicio SSO se conecte al servidor secreto principal|  
|Cuenta de servicio de inicio de sesión único (SSO)|Servidor secreto principal|RPC secundario|50000-50200|TCP|Puertos RPC secundarios para que el servicio SSO se conecte al servidor secreto principal. **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Cuenta de servicio de una instancia de host de BizTalk|Base de datos de cuadro de mensajes|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
|Cuenta de servicio de una instancia de host de BizTalk|Base de datos de administración de BizTalk|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
|Cuenta de servicio de una instancia de host de BizTalk|base de datos de SSO|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
|Cuenta de servicio de una instancia de host de BizTalk|Base de datos de seguimiento|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de nomenclatura de servidores](../core/server-naming-conventions.md)   
 [Recomendaciones de seguridad del adaptador HTTP](../core/http-adapter-security-recommendations.md)   
 [Recomendaciones de seguridad del adaptador SOAP](../core/soap-adapter-security-recommendations.md)   
 [Recomendaciones de seguridad del adaptador de FTP](http://msdn.microsoft.com/library/ea7c0577-9d72-4d63-94e7-8f649c6e713f)   
 [Recomendaciones de seguridad del adaptador de SMTP](../core/smtp-adapter-security-recommendations.md)   
 [Recomendaciones de seguridad del adaptador de archivo](http://msdn.microsoft.com/library/fe4d51c0-b697-457b-bf27-f1cf6965d954)   
 [Arquitectura distribuida de gran tamaño con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md)   
 [Puertos necesarios para el servidor BizTalk Server](../core/required-ports-for-biztalk-server.md)