---
title: Administración de seguridad de BizTalk Server | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, security
- security, user accounts
- security, passwords
- certificates, security
- security, certificates
- security, BizTalk Server
- passwords, security
- user accounts, security
ms.assetid: adc89b0a-9846-4c99-b0fc-a32fc56ed769
caps.latest.revision: 31
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7486a23d5d606a1347c60b2971ebed66c354946
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000053"
---
# <a name="managing-biztalk-server-security"></a>Administración de seguridad de BizTalk Server
El mantenimiento de un entorno seguro de Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] requiere la administración de cuentas, certificados y contraseñas. Para ayudar a garantizar la seguridad de los documentos empresariales que controla BizTalk Server, los administradores de BizTalk Server administran las siguientes cuentas y certificados:  
  
- **Grupo de administradores de BizTalk Server**. Los usuarios que van a realizar tareas administrativas mediante la consola de administración de BizTalk Server o el Instrumental de administración de Microsoft Windows (Windows Management Instrumentation, WMI) deben tener concedidos los privilegios adecuados en Microsoft SQL Server y en Microsoft Windows. Para obtener más información acerca de los privilegios para realizar tareas administrativas, consulte [derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md).  
  
   Para obtener información sobre cómo agregar usuarios al grupo de administradores de BizTalk Server o quitar usuarios del grupo Administradores de BizTalk Server, vea [cómo administrar el grupo de administradores de BizTalk Server](../core/how-to-manage-the-biztalk-server-administrators-group.md).  
  
   Para obtener más información acerca de Enterprise Single Sign-On, vea [SSO utilizando](../core/using-sso.md).  
  
- **Grupo de operadores de BizTalk Server**. El operador de BizTalk Server tiene una función con pocos privilegios, ya que sólo tiene acceso para supervisar y solucionar problemas de acciones.  
  
   Los miembros del grupo de operadores de BizTalk Server pueden realizar las siguientes acciones:  
  
  - Ver el estado del servicio y el flujo de mensajes.  
  
  - Iniciar o detener aplicaciones.  
  
  - Iniciar o detener orquestaciones.  
  
  - Iniciar o detener puertos de envío o grupos de puertos de envío.  
  
  - Habilitar o deshabilitar ubicaciones de recepción. Los cambios no se hacen efectivos hasta el próximo intervalo de actualización de la caché de 60 segundos, que es el intervalo predeterminado. El intervalo de actualización de la caché se establece en el nivel de grupo de BizTalk Server.  
  
  - Finalizar y reanudar las instancias de servicios.  
  
    Los miembros del grupo de operadores de BizTalk Server no pueden realizar las siguientes acciones:  
  
  - Modificar la configuración de BizTalk Server.  
  
  - Ver las propiedades de contexto del mensaje que estén clasificadas como información que se pueda identificar personalmente o los cuerpos de los mensajes.  
  
  - Modificar el transcurso del enrutamiento de mensajes, como la eliminación de suscripciones del sistema en ejecución o la agregación de suscripciones nuevas a éste, así como la capacidad para publicar mensajes en el tiempo de ejecución de BizTalk Server.  
  
  > [!NOTE]
  >  Si un usuario que es miembro del grupo de operadores de BizTalk Server también es administrador local en los equipos que ejecutan BizTalk Server, puede obtener acceso a los datos más allá de la función del grupo de operadores en estos equipos. Para obtener más información, consulte [derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md).  
  
  > [!NOTE]
  >  Si desea permitir que un usuario miembro del grupo de operadores de BizTalk Server supervise servidores BizTalk remotos, éste debe ser miembro también del grupo local de administradores en los equipos remotos.  
  
- **Hosts y cuentas de servicio**. En la creación de un host y de las instancias de host asociadas, debe proporcionar el grupo de Windows del host y las credenciales de cuentas de servicio de cada instancia de host. Debe asegurarse de que las cuentas de servicio de instancia de host son miembros del grupo de Windows para el host.  
  
- **Certificados de firma**. Se especifican los certificados de firma (certificados de clave privada) para el grupo de BizTalk. Son opcionales y un administrador de BizTalk Server puede cambiarlos en cualquier momento.  
  
  Para obtener información más completa acerca de las cuentas de Windows que utiliza BizTalk Server, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Procedimientos recomendados para administrar grupos y cuentas de usuario de Windows](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)  
  
-   [Procedimientos recomendados para la administración de certificados](../core/best-practices-for-managing-certificates1.md)  
  
-   [Administración de cuentas de usuario y grupos de Windows](../core/managing-windows-groups-and-user-accounts.md)