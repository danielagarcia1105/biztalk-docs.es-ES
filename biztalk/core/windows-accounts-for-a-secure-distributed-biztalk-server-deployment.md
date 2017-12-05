---
title: "Cuentas de Windows para una implementación distribuida segura de BizTalk Server | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, Windows groups
- user accounts, naming conventions
- user accounts
- access control, Windows groups
- security, access control
- architecture, security
- security, Windows accounts
- administrator accounts
- user accounts, administrators
- architecture, large distributions
ms.assetid: 2a0893ef-8bfb-481b-b024-7f7d6e2a6f09
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04c7e6e28cc0deb83eaa7868c6c4ee17da8bc563
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="windows-accounts-for-a-secure-distributed-biztalk-server-deployment"></a>Cuentas de Windows para una implementación distribuida segura de BizTalk Server
Para obtener información completa sobre la arquitectura del sistema para la implementación de BizTalk Server, vea [arquitecturas de servidor de BizTalk de ejemplo](../core/sample-biztalk-server-architectures.md).  
  
 Esta sección contiene recomendaciones para crear cuentas y grupos de Windows en un entorno distribuido de BizTalk Server. Los nombres de las cuentas y los grupos son sugerencias que se basan en sus funciones. Puede elegir el nombre de estos grupos y cuentas. Para obtener más información sobre arquitecturas distribuidas de BizTalk Server, vea [arquitectura distribuida grande](../core/large-distributed-architecture.md).  
  
## <a name="windows-groups-for-a-secure-distributed-biztalk-server-deployment"></a>Grupos de Windows para una implementación distribuida segura de BizTalk Server  
 La siguiente lista describe los grupos de Windows que se recomienda que el administrador del dominio cree en el controlador de dominio de la capa de datos.  
  
-   Administradores de SSO  
  
-   Administradores afiliados de SSO  
  
-   Administradores de servidor BizTalk Server  
  
-   Operadores de servidor BizTalk Server  
  
 Para obtener información completa acerca de los grupos de Windows que utiliza BizTalk Server, vea [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
 Además de los grupos de dominio anteriores, en la tabla siguiente se enumeran los grupos adicionales específicos de la implementación segura para que el administrador del dominio los cree en el controlador de dominio de la capa de datos.  
  
|Nombre de grupo (recomendado)|Finalidad|  
|------------------------------|-------------|  
|Usuarios de host de procesamiento 1|Grupo para las instancias de host de un host concreto en curso que se utiliza para procesar mensajes. Cree un grupo para cada host In-Process que utilice para procesar mensajes en el entorno de BizTalk Server.|  
|Usuarios de host de envío de BizTalk 1|Grupo para la instancia de host de un host In-Process concreto que se utiliza para enviar mensajes. Cree un grupo para cada host In-Process que utilice para enviar mensajes en el entorno de BizTalk Server.|  
|Usuarios de host de recepción de BizTalk 1|Grupo para la instancia de host de un host In-Process concreto que se utiliza para recibir mensajes. Cree un grupo para cada host In-Process que utilice para recibir mensajes en el entorno de BizTalk Server.|  
|Usuarios de host de seguimiento de BizTalk|Grupo del host de BizTalk dedicado al seguimiento.|  
|Usuarios de SOAP de BizTalk|Grupo de las instancias de host del host aislado que se utiliza para el adaptador de SOAP.|  
|Usuarios de HTTP de BizTalk|Grupo de las instancias de host de los hosts aislado que se utilizan para el adaptador de HTTP.|  
  
 El administrador del dominio debe crear los siguientes grupos en el controlador de dominio del dominio de interfaces de servicio:  
  
-   Usuarios del portal de SAE de BizTalk  
  
## <a name="windows-user-or-service-accounts-for-a-secure-distributed-biztalk-server-deployment"></a>Cuentas de usuario o de servicio de Windows para una implementación distribuida segura de BizTalk Server  
 La siguiente tabla enumera las cuentas que se recomienda que el administrador del dominio cree en el controlador de dominio del dominio de datos. El administrador del dominio debe asegurarse de que las cuentas formen parte de los grupos indicados.  
  
 Para obtener información completa acerca de las cuentas de usuario que utiliza BizTalk Server, vea [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
|Nombre de cuenta (ejemplo)|Tipo|Miembro del grupo|  
|------------------------------|----------|---------------------|  
|Administrador de SSO|Usuario|Administradores de SSO|  
|Servicio SSO|ssNoVersion|Administradores de SSO|  
|Secreto principal de SSO|ssNoVersion|Administradores de SSO|  
|Administrador de BizTalk|Usuario|Administradores de BizTalk<br /><br /> Administradores afiliados de SSO|  
|Operador de BizTalk|Usuario|Operadores de BizTalk|  
|Procesamiento de BizTalk 1|ssNoVersion|Usuarios de host de procesamiento 1|  
|2 de procesamiento de BizTalk **Nota:** puede crear varias cuentas para cada host de procesamiento en su entorno.|ssNoVersion|Usuarios de host de procesamiento 1|  
|Seguimiento de BizTalk|ssNoVersion|Usuarios de host de seguimiento de BizTalk|  
|Adaptador de SOAP|ssNoVersion|Usuarios de SOAP de BizTalk|  
|adaptador de HTTP|ssNoVersion|Usuarios de HTTP de BizTalk|  
|Servicio de actualización de motor de reglas|ssNoVersion||  
|Installation|Usuario|Administradores de SSO (sólo para configurar el servidor secreto principal).<br /><br /> Administradores locales<br /><br /> Función de SQL Server sysadmin<br /><br /> Administrador de OLAP|  
|Grupo de aplicaciones de SAE|ssNoVersion|IIS_WPG|  
|Administración de SAE|ssNoVersion|IIS_WPG|  
|Notificación de SAE|ssNoVersion|SQLServer2005NotificationServicesUser$\<**NombreDeEquipo**\>|  
  
 La siguiente tabla enumera las cuentas que se recomienda que el administrador del dominio cree en el controlador de dominio del dominio corporativo.  
  
|Nombre de cuenta|Tipo|  
|------------------|----------|  
|Administrador de SharePoint|Usuario|  
|Credencial de sitio de SharePoint|Usuario|  
  
## <a name="see-also"></a>Vea también  
 [Arquitectura distribuida de gran tamaño](../core/large-distributed-architecture.md)   
 [Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)   
 [Grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [Arquitecturas de ejemplo de BizTalk Server](../core/sample-biztalk-server-architectures.md)