---
title: Puertos para el servidor del Portal de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: df67c31c-a7a3-4bff-9374-0d8a0cf0ad21
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adfa47415c1e367941203d20533c5e3ac3f431da
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266468"
---
# <a name="ports-for-the-bam-portal-server"></a>Puertos para el servidor del portal de BAM
Para obtener información completa acerca de cómo proteger la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 La tabla siguiente contiene la lista de puertos que debe configurar para que el sitio Web del portal de BAM tenga acceso a los servicios necesarios. El firewall en el que tiene que abrir los puertos dependerá de que el servidor de destino forme parte de la arquitectura. Debe abrir estos puertos tanto al tráfico entrante como al tráfico saliente.  
  
|Contexto de servicio o aplicación|Servidor de destino|Servicio de destino|Puerto|Protocolo|Razón|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|Usuario conectado|Base de datos de administración de BizTalk|SQL Server|1433|TCP|Para crear y configurar la base de datos|  
|Usuario conectado|Base de datos de administración de BizTalk|DTC|135|TCP|Transacción de conexión a SQL Server para crear, configurar y actualizar la base de datos|  
|Usuario conectado|Base de datos de administración de BizTalk|DTC|50000-50200|TCP|Puertos RPC secundarios para crear y conectarse a esta base de datos **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Grupo de aplicaciones|Clientes de entrada|HTTP(S)|80 o 443|TCP|Para el tráfico entrante para el sitio Web|  
|Usuario conectado|Base de datos de cuadro de mensajes|SQL Server|1433|TCP|Para crear y configurar la base de datos|  
|Usuario conectado|Base de datos de cuadro de mensajes|DTC|135|TCP|Transacción de conexión a SQL Server para crear, configurar y actualizar la base de datos|  
|Usuario conectado|Base de datos de cuadro de mensajes|DTC|50000-50200|TCP|Puertos RPC secundarios **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Cuenta de servicio de SSO|base de datos de SSO|SQL Server|1433|TCP|Para conectar a la base de datos de SSO|  
|Usuario conectado|Base de datos de seguimiento|SQL Server|1433|TCP|Para crear y configurar la base de datos|  
|Usuario conectado|Base de datos del motor de reglas de negocios|SQL Server|1433|TCP|Para crear y configurar la base de datos|  
|Usuario conectado|Base de datos del motor de reglas de negocios|DTC|135|TCP|Transacción de conexión a SQL Server para crear, configurar y actualizar la base de datos|  
|Usuario conectado|Base de datos del motor de reglas de negocios|DTC|50000-50200|TCP|Puertos RPC secundarios **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Usuario conectado|Base de datos de análisis de BAM|OLAP|2393|TCP|Para crear y configurar la base de datos|  
|Usuario conectado|Base de datos de análisis de BAM|Sistema de archivos de servidor OLAP|445|TCP|Crear el archivo de datos OLAP (.mdb) en el equipo remoto|  
|Usuario conectado|Base de datos de análisis de BAM|OLAP|2725|TCP|Actualizar y recuperar información de la base de datos|  
|Cuenta de servicio de SSO|base de datos de SSO|SQL Server|1433|TCP|Para que el servicio SSO actualice y recupere información de la base de datos|  
|Cuenta de servicio de SSO|Servidor secreto principal|Servidor secreto principal|135|TCP|Transacción de conexión a SQL Server para que el servicio SSO se conecte al servidor secreto principal|  
|Servicio SSO|Servidor secreto principal|RPC secundario|50000-50200|TCP|Puertos RPC secundarios para que el servicio SSO se conecte al servidor secreto principal. **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Instancia de host de BizTalk|Base de datos de cuadro de mensajes|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
|Instancia de host de BizTalk|Base de datos de administración de BizTalk|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
|Instancia de host de BizTalk|base de datos de SSO|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
|Instancia de host de BizTalk|Base de datos de seguimiento|SQL Server|1433|TCP|Actualizar y recuperar información de la base de datos durante las operaciones de tiempo de ejecución|  
|Usuario del grupo de aplicaciones de BAM|Servicios de notificación de BAM|SQL Server|1433|TCP|Para obtener acceso a la base de datos de servicios de notificación de BAM|  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de nomenclatura de servidores](../core/server-naming-conventions.md)   
 [Consideraciones de seguridad para el Portal de BAM](../core/security-considerations-for-the-bam-portal.md)   
 [Arquitectura distribuida de gran tamaño con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md)   
 [Puertos necesarios para el servidor BizTalk Server](../core/required-ports-for-biztalk-server.md)