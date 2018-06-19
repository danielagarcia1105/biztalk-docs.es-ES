---
title: Control de acceso de grupos y cuentas de servicio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- access control, service accounts
- user accounts, default accounts
- service accounts, security
- user accounts, unsupported
- access control, groups
- service accounts, access control
- groups, access control
- groups, security
ms.assetid: 411a7bfa-6675-4d09-9e37-83e2941df3c6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9a04129427b524f0e183012ba7f10df1288327a8
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967034"
---
# <a name="access-control-for-groups-and-service-accounts"></a>Control de acceso para grupos y cuentas de servicio
Cada instancia de host de BizTalk se ejecuta bajo una cuenta de servicio creada por el usuario. Las cuentas de servicio y sus contraseñas deben proporcionarse en el momento de crear la instancia de host en un equipo. A continuación, BizTalk Server verifica que esas cuentas tienen los derechos de usuario mínimos necesarios para realizar sus tareas agregando cada una de ellas a un grupo de Windows local o de dominio que, a su vez, la agrega a la función de base de datos de SQL Server específica de ese host.  
  
 Este procedimiento ofrece las siguientes ventajas:  
  
-   Puede darse una cuenta de servicio distinta a cada instancia de host, lo que permite cambiar las contraseñas de cada instancia de host sin desconectar servidores. Pueden realizarse actualizaciones sucesivas de contraseñas sin interrumpir el servicio.  
  
    > [!NOTE]
    >  No puede utilizar la misma cuenta de servicio para hosts con autenticación de confianza y para hosts sin dicha autenticación.  
  
-   Si concede derechos de usuario de recurso al grupo local o de dominio en el nivel de Microsoft SQL Server™, puede agregar y quitar cuentas de servicio sin tener que cambiar los derechos de usuario concedidos en SQL Server, lo que le ahorrará trabajo administrativo y reducirá su costo total de propiedad.  
  
 Con el fin de garantizar que las cuentas de servicio tienen los derechos de usuario mínimos necesarios para realizar sus tareas, las funciones de base de datos de SQL Server creadas por BizTalk Server para las cuentas de servicio no son idénticas en todas las bases de datos de BizTalk Server. Para las bases de datos de seguimiento y administración, todas las cuentas de servicio de instancia de host necesitan tener acceso a los mismos objetos de SQL Server, por lo que BizTalk Server crea una sola función de base de datos de SQL Server denominada BTS_Host_User. BizTalk agrega todos los grupos de Windows creados para hosts de BizTalk a esa función de base de datos de SQL Server.  
  
 Para la base de datos de cuadro de mensajes, cada host tiene ciertos recursos dedicados. BizTalk Server crea un rol de base de datos de SQL Server por host, denominada BTS_\<*hostname*\>_usuario, y agrega el grupo de Windows para cada host en sus respectivos roles de base de datos de SQL Server con el fin de bloquear el acceso de uno recursos de host por otro host.  
  
## <a name="accounts-not-supported-by-biztalk-server"></a>Cuentas no admitidas por BizTalk Server  
 BizTalk Server no permite utilizar ninguna de las siguientes cuentas integradas de Windows:  
  
-   NT_AUTHORITY\NetworkService  
  
-   LocalSystem (Sistema local)  
  
-   NT_AUTHORITY\LocalService  
  
## <a name="see-also"></a>Vea también  
 [Control de acceso para los Roles administrativos](../core/access-control-for-administrative-roles.md)   
 [Derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md)   
 [Grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [Control de acceso y seguridad de los datos](../core/access-control-and-data-security.md)