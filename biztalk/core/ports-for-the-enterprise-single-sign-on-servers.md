---
title: "Puertos para la empresa solo servidores de inicio de sesión | Documentos de Microsoft"
ms.custom: 
ms.date: 2016-01-07
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, SSO
- SSO
ms.assetid: 30eb99f9-02cb-43c9-b038-d7bd898e3a7a
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c0335a6a09cb8d323261c2d8357cc3d5b929b61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="ports-for-the-enterprise-single-sign-on-servers"></a>Puertos para los servidores de inicio de sesión único de la empresa
Para obtener información completa acerca de cómo proteger la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 En la tabla siguiente, se enumeran los puertos que necesitan los servidores de inicio de sesión único (SSO) empresarial del dominio de procesamiento para tener acceso al servidor secreto principal y a la base de datos de SSO. Debe abrir estos puertos tanto al tráfico entrante como al tráfico saliente.  
  
|Contexto de servicio o aplicación|Servidor de destino|Servicio de destino|Puerto|Protocolo|Razón|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|Usuario conectado|base de datos de SSO|SQL Server|1433|TCP|Crear y conectarse a la base de datos de SSO.|  
|Cuenta de servicio de inicio de sesión único (SSO)|Servidor secreto principal|Servicio de inicio de sesión único (SSO)|135|TCP|Transacción de conexión a SQL Server para que el servicio SSO recupere la clave secreta principal del servidor secreto principal|  
|Cuenta de servicio de inicio de sesión único (SSO)|Servidor secreto principal|Servicio de inicio de sesión único (SSO)|50000-50200|TCP|Puertos RPC secundarios que se utilizan para recuperar la clave secreta del servidor secreto principal. **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
  
 La tabla siguiente contiene la lista de puertos que debe configurar para que el servidor secreto principal de inicio de sesión único (SSO) empresarial obtenga acceso a los servicios que necesita. El firewall en el que tiene que abrir los puertos dependerá de que el servidor de destino forme parte de la arquitectura. Debe abrir estos puertos tanto al tráfico entrante como al tráfico saliente.  
  
|Contexto de servicio o aplicación|Servidor de destino|Servicio de destino|Puerto|Protocolo|Razón|  
|------------------------------------|------------------------|-------------------------|----------|--------------|------------|  
|Usuario conectado|base de datos de SSO|SQL Server|1433|TCP|Crear y conectarse a la base de datos de SSO.|  
|Cuenta de servicio de inicio de sesión único (SSO)|Servidores de procesamiento|Servicio de inicio de sesión único (SSO)|135|TCP|Transacción de conexión a SQL Server para que el servicio SSO recupere la clave secreta principal del servidor secreto principal|  
|Cuenta de servicio de inicio de sesión único (SSO)|Servidores de procesamiento|Servicio de inicio de sesión único (SSO)|50000-50200|TCP|Puertos RPC secundarios que se utilizan para recuperar la clave secreta del servidor secreto principal. **Nota:** puede que necesite abrir más puertos RPC secundarios según la carga del servidor.|  
  
## <a name="see-also"></a>Vea también  
 [Convenciones de nomenclatura de servidores](../core/server-naming-conventions.md)   
 [Recomendaciones de seguridad SSO](../core/sso-security-recommendations.md)   
 [Arquitectura distribuida de gran tamaño con servicios de trabajadores de información](../core/large-distributed-architecture-with-information-worker-services.md)   
 [Puertos necesarios para el servidor BizTalk Server](../core/required-ports-for-biztalk-server.md)