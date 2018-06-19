---
title: Puertos para el servidor de administración | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, administration server
- administration server
ms.assetid: dc0094b2-5ba2-4b8f-84aa-b6232be358ee
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd44158d721f8b6d247b51073e9f9e77ea7f6deb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22265476"
---
# <a name="ports-for-the-administration-server"></a>Puertos para el servidor de administración
Para obtener información completa acerca de cómo proteger la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 La tabla siguiente contiene la lista de puertos que debe configurar para que el servidor de administración tenga acceso a los servicios necesarios. El firewall en el que tiene que abrir los puertos dependerá de que el servidor de destino forme parte de la arquitectura. 
  
|Servidor de destino|Servicio de destino|Puerto|Protocolo|Reason|  
|---|---|---|---|---|  
|Base de datos de administración de BizTalk|SQL Server|1433|TCP|Para crear, configurar y obtener acceso a información en la base de datos de administración de BizTalk.|  
|Base de datos de administración de BizTalk|DTC|135|TCP|Transacción de conexión a SQL Server para actualizar la base de datos|  
|Base de datos de administración de BizTalk|DTC|50000-50200|TCP|Puertos RPC secundarios **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Base de datos de importación principal de BAM|SQL Server|1433|TCP|Comprobar que la base de datos de importación principal de SAE existe con la consola de administración de BizTalk (o WMI)|  
|Base de datos de administración de BizTalk|SQL Server|1433|TCP|Ver los datos de configuración e instalar las instancias de host con la consola de administración de BizTalk (o WMI)|  
|Base de datos de administración de BizTalk|DTC|135|TCP|Transacción de conexión a SQL Server para crear y actualizar un host con la consola de administración de BizTalk (o WMI)|  
|Base de datos de administración de BizTalk|DTC|50000-50200|TCP|Puertos RPC secundarios para crear un host mediante la consola de administración de BizTalk (o WMI) **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Base de datos de cuadro de mensajes|SQL Server|1433|TCP|Crear un host con la consola de administración de BizTalk (o WMI)|  
|Base de datos de cuadro de mensajes|DTC|135|TCP|Transacción de conexión a SQL Server para crear y actualizar un host con la consola de administración de BizTalk (o WMI)|  
|Base de datos de cuadro de mensajes|DTC|50000-50200|TCP|Puertos RPC secundarios para crear un host mediante la consola de administración de BizTalk (o WMI) **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Servidor de procesamiento|WMI/RPC|135|TCP|Transacción de conexión a SQL Server para agregar un nuevo servidor al grupo con la consola de administración de BizTalk (o WMI)|  
|Servidor de procesamiento|WMI/RPC|50000-50200|TCP|Puertos RPC secundarios para agregar un nuevo servidor al grupo mediante la consola de administración de BizTalk (o WMI) **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Servidor de procesamiento|Bloque de mensajes del servidor (SMB)|445|TCP|Utilizado para tener acceso a recursos compartidos de archivos. También puede resultar necesario para instalar una instancia de host mediante la consola de administración de BizTalk (o WMI).|  
|Base de datos del motor de reglas de negocios|SQL Server|1433|TCP|Implementar reglas de negocios utilizando el Asistente para implementar el motor de reglas de negocios.|  
|Base de datos del motor de reglas de negocios|DTC|135|TCP|Transacción de conexión a SQL Server para implementar reglas de negocios utilizando el Asistente para implementar el motor de reglas de negocios.|  
|Base de datos del motor de reglas de negocios|DTC|50000-50200|TCP|Puertos RPC secundarios para implementar reglas de negocios utilizando el Asistente para implementar el motor de reglas de negocios. **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
|Base de datos de administración de BizTalk|SQL Server|1433|TCP|Implementar un ensamblado|  
|Base de datos de seguimiento|SQL Server|1433|TCP|Implementar un ensamblado|  
|Servidor IIS|IIS|1164|TCP|Para habilitar la implementación de la aplicación de BizTalk empaquetar HTTP o puertos de servicio Web hospedado en el servidor IIS en un archivo MSI.|  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de nomenclatura de servidores](../core/server-naming-conventions.md)   
 [Recomendaciones de seguridad de implementación de aplicaciones](../core/application-deployment-security-recommendations.md)   
 [Consideraciones de seguridad para el seguimiento de datos de instancias y mensajes](../core/security-considerations-for-message-and-instance-data-tracking.md)   
 [Arquitectura distribuida de gran tamaño con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md)   
 [Puertos necesarios para el servidor BizTalk Server](../core/required-ports-for-biztalk-server.md)