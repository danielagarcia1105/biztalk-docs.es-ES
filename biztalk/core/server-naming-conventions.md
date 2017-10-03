---
title: Convenciones de nomenclatura del servidor | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- architecture, naming conventions
- naming conventions, servers
- installation, naming conventions
ms.assetid: 98989c15-51d7-4a67-b054-abe6993a98a6
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a54e61a9ec37754158697a57a3f310d9edb90ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="server-naming-conventions"></a>Convenciones de nomenclatura de servidores
Para obtener información completa sobre la arquitectura del sistema para la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 En la tabla siguiente se describe los servidores en el diagrama en el tema [arquitectura distribuida de gran tamaño](../core/large-distributed-architecture.md)y sus funciones.  
  
|Nombre del servidor en el diagrama|Función|Description|  
|----------------------------|--------------|-----------------|  
|FW4|Firewall|Servidor de Forefront Threat Management Gateway (TMG) 2010 entre Internet y la red perimetral.|  
|HTTP (recepción)|Servidor web|Servidor Web que recibe mensajes del adaptador de HTTP. Este servidor no tiene componentes de BizTalk Server instalados, tiene páginas ASP .NET que transmiten los mensajes al dominio de interfaces de servicio Puede usar un proxy inverso de FW4 a FW3 en lugar de las páginas ASP.NET. Si usa un proxy inverso, no necesitará este servidor.|  
|Intercambio (envío o recepción)|Servidor de correo|Servidor de correo que utiliza BizTalk Server para enviar y recibir mensajes SMTP El adaptador de POP3 lee los mensajes recibidos|  
|FTP (envío o recepción)|Servidor web|Representa el protocolo de transferencia de archivos (FTP) desde el que BizTalk envía y recibe mensajes. Puede ser un servidor remoto.|  
|SQL|SQL Server|Servidor con base de datos de SQL Server que utiliza el adaptador SQL.|  
|Archivo|Servidor de archivos|Servidor que tiene un directorio de archivo desde el cual el adaptador de archivos en el dominio de interfaces de servicio coloca y recoge archivos.|  
|FW3|Firewall|Interfaces de servidor de Forefront Threat Management Gateway (TMG) 2010 protege el servicio de dominio de la red perimetral y el dominio corporativo.|  
|Procesamiento|Servidor de procesamiento|Este servidor procesa mensajes. Contiene el tiempo de ejecución de BizTalk Server, el motor de reglas de negocios y el servicio de inicio de sesión único (SSO) empresarial. En este servidor se encuentran los ensamblados de BizTalk, las instancias de host, las orquestaciones, los esquemas y las asignaciones. Un servidor de procesamiento puede tener instancias de distintos hosts.|  
|Controlador de recepción<br /><br /> (host aislado)|Servidor de envío o recepción|Servidor de BizTalk Server dedicado a la recepción de mensajes de los adaptadores de HTTP y SOAP. Un servidor de envío o recepción puede tener instancias de distintos hosts.|  
|Controlador de recepción<br /><br /> (host In-Process)|Servidor de envío o recepción|Servidor BizTalk Server dedicado a la recepción de mensajes desde los adaptadores de SQL, FTP, EDI, archivo, POP3 y Message Queue Server de BizTalk. Un servidor de envío o recepción puede tener instancias de distintos hosts.|  
|Controlador de envío|Servidor de envío o recepción|Servidor de BizTalk Server dedicado a enviar mensajes para todos los adaptadores. Un servidor de envío o recepción puede tener instancias de los distintos hosts que se utilizan para enviar mensajes.|  
|FW2|Firewall|Servidor de Forefront Threat Management Gateway (TMG) 2010 protege el dominio de servicios de las interfaces de servicio y los dominios corporativos (servicios de operaciones).|  
|Host de seguimiento|Servidor de seguimiento|Servidor que contiene la instancia de host de BizTalk que se emplea para realizar el seguimiento.|  
|Herramientas de administración|Servidor de administración|Servidor que contiene el tiempo de ejecución de BizTalk Server, la consola de administración de BizTalk y las herramientas de implementación.|  
|Servidor secreto principal|Servidor secreto principal|Servidor SSO que administra la clave secreta principal de todo el entorno. No hay más componentes de BizTalk Server en este equipo.|  
|FW1|Firewall|Servidor de Forefront Threat Management Gateway (TMG) 2010 protege el dominio de datos y las interfaces de servicio y los dominios de servicios.|  
|Cuadro de mensajes 1<br /><br /> Cuadro de mensajes 2<br /><br /> Cuadro de mensajes "n"|Servidor de datos|Servidor SQL que contiene las bases de datos de cuadro de mensajes. Puede haber un servidor SQL para cada base de datos de cuadro de mensajes.|  
|SSO|Servidor de datos|Servidor SQL Server que contiene la base de datos de SSO, que utiliza el inicio de sesión único (SSO) empresarial para almacenar en formato cifrado los Id. de usuario y las credenciales para iniciar sesión en otros sistemas, así como para almacenar en formato cifrado la información de configuración para los adaptadores que utiliza BizTalk Server.|  
|Copia de seguridad o restauración para envío de registros|Servidor de datos|Servidor SQL Server usado para restaurar las copias de seguridad de bases de datos generadas por las bases de datos de BizTalk Server.|  
|Análisis de BizTalk|Servidor de datos|Servidor de análisis que contiene la base de datos de análisis de BizTalk.|  
  
 En la tabla siguiente describe los servidores adicionales en el diagrama en el tema [arquitectura de distribuida de gran tamaño con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md) y sus funciones en comparación con el diagrama en el tema [grande Arquitectura distribuida](../core/large-distributed-architecture.md).  
  
|Nombre del servidor|Función|Description|  
|-----------------|--------------|-----------------|  
|Portal de BAM|Portal de BAM|Servidor que contiene el Portal de SAE. Los usuarios empresariales finales utilizan el portal de SAE para obtener acceso a las bases de datos de SAE a fin de supervisar los indicadores clave de rendimiento y otros datos sobre su proceso empresarial.|  
|Servicio de notificación<br /><br /> Configuración de Windows SharePoint Services<br /><br /> Contenido de Windows Sharepoint Services.<br /><br /> Esquema de estrella de BAM<br /><br /> Importación principal de SAE<br /><br /> Archivo de BAM<br /><br /> Análisis de SAE (OLAP)|Servidor de datos IW|Servidor SQL Server que contiene las bases de datos usadas por Supervisión de la actividad económica (BAM). Puede utilizar varios servidores SQL para estas bases de datos.|  
|Clientes IW|Clientes IW|Equipos cliente que los trabajadores de la información usan para Supervisión de la actividad económica (BAM).|  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura distribuida de gran tamaño](../core/large-distributed-architecture.md)   
 [Arquitectura distribuida de gran tamaño con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md)   
 [Arquitecturas de BizTalk Server de ejemplo](../core/sample-biztalk-server-architectures.md)