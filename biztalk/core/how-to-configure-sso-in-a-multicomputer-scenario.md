---
title: "Cómo configurar SSO en un escenario de varios equipos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, SSO
- SSO database, clustering
- clustering, Master Secret server
- SSO, configuring
- configuring, Master Secret server
- Master Secret server, clustering
- clustering, SSO database
- Master Secret server, configuring
- SSO, multiple computers
ms.assetid: 4511a03d-96f2-45f0-9891-e8b3e253499c
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45bfa58c1fc11a76109f56938b8e1b43790935f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-sso-in-a-multicomputer-scenario"></a>Cómo configurar SSO en un escenario de varios equipos
Esta sección contiene instrucciones para configurar el inicio de sesión único (SSO) empresarial en un escenario de tres equipos.  
  
 En el caso siguiente, el equipo A es el servidor secreto principal, el equipo B es el servidor de inicio de sesión único y el equipo C contiene la base de datos de SSO. El equipo B puede actuar como un servidor en tiempo de ejecución, como un servidor de administración (los subservicios administrativos de SSO utilizan este servidor para administrar la base de datos de SSO) o como un servidor de asignación (los subservicios administrativos y de cliente de SSO utilizan este servidor para administrar asignaciones).  
  
 Si desea agregar más servidores de SSO a su entorno, siga los pasos para configurar el equipo B. Todos los servidores nuevos de SSO señalarán a la base de datos de SSO existente y no pueden ser el servidor secreto principal.  
  
> [!NOTE]
>  Se recomienda configurar el servidor secreto principal en un equipo diferente del servidor de inicio de sesión único y de la base de datos de SSO.  
  
### <a name="to-configure-the-master-secret-server-and-create-the-sso-database-on-computer-a"></a>Para configurar el servidor secreto principal y crear la base de datos de SSO en el equipo A  
  
1.  Lleve a cabo una instalación personalizada de BizTalk Server e instale únicamente el componente del servidor secreto principal de inicio de sesión único empresarial.  
  
2.  Ejecute el Asistente para configuración para configurar SSO en el servidor secreto principal. En el **pregunta** , seleccione la opción de **crear un nuevo sistema SSO**.  
  
3.  En el **las cuentas de Windows** página, especifique las credenciales de cuenta de servicio para el servicio SSO. Esta cuenta debe pertenecer a la cuenta de grupo de administradores de SSO.  
  
4.  En el **las configuraciones de base de datos** página, especifique la ubicación de SQL Server (equipo C) y el nombre de la base de datos SSO (SSODB).  
  
5.  Especifique las opciones para hacer una copia de seguridad del secreto principal.  
  
6.  Complete la configuración.  
  
### <a name="to-configure-the-sso-server-on-computer-b"></a>Para configurar el servidor de SSO en el equipo B  
  
1.  Instale el inicio de sesión único empresarial en el equipo B.  
  
    > [!NOTE]
    >  Puede ser un equipo de BizTalk Server o de Host Integration Server, un servidor Web o un servidor de SSO (componentes de tiempo de ejecución de SSO).  
  
2.  Ejecute el Asistente para configuración para configurar SSO. En el **pregunta** , seleccione la opción de **unir un sistema SSO existente**.  
  
3.  En el **las cuentas de Windows** página, especifique las credenciales de cuenta de servicio para el servicio SSO. Esta cuenta debe pertenecer a la cuenta de grupo de administradores de SSO.  
  
4.  En el **las configuraciones de base de datos** página, seleccione la ubicación de SQL Server (equipo C) y el nombre de la base de datos SSO (SSODB).  
  
## <a name="see-also"></a>Vea también  
 [Cómo agrupar el servidor secreto principal](../core/how-to-cluster-the-master-secret-server1.md)   
 [Instalación de SSO](../core/installing-sso.md)