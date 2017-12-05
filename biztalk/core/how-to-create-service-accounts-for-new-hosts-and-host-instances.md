---
title: "Cómo crear servicio cuentas para nuevos Hosts e instancias de Host | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Configuration Manager, service accounts
- Windows groups, service accounts
- Configuration Manager
- service accounts, Windows groups
- hosts, service accounts
- service accounts, hosts
- service accounts, Configuration Manager
- service accounts, creating
- creating, service accounts
ms.assetid: cef97f4a-8db1-41b6-9614-608c2fbf59a9
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5d4887d78466340b12b95ed43d27523955ab0689
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-service-accounts-for-new-hosts-and-host-instances"></a>Cómo crear cuentas de servicio para nuevos hosts y nuevas instancias de host
El administrador de configuración configura los grupos de Windows y las cuentas de usuario necesarios al instalar y configurar BizTalk Server en un único equipo.  
  
 Es necesario crear manualmente cuentas de usuario y grupos de Windows, y agregar aquéllas a éstas en un entorno de dominio antes de ejecutar al administrador de configuración. Para obtener más información, consulte [grupos de dominio](../core/domain-groups.md).  
  
 Debe realizar el siguiente procedimiento antes de crear un nuevo host o una nueva instancia de host.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión como miembro del grupo de administradores de dominio o del grupo de administradores.  
  
### <a name="to-create-service-accounts-for-new-hosts-or-host-instances"></a>Para crear cuentas de servicio para nuevos hosts y nuevas instancias de host  
  
1.  Cree un grupo de Windows de host para el nuevo host que se va a crear. Para obtener más información acerca de cómo crear un nuevo host, consulte [cómo crear un nuevo Host](../core/how-to-create-a-new-host.md).  
  
2.  Cree cuentas de servicio para cada una de las instancias de host que se van a agregar al nuevo host. Para obtener más información acerca de cómo crear una nueva instancia de host, consulte [cómo agregar una instancia de Host](../core/how-to-add-a-host-instance.md).  
  
3.  Agregue cuentas de servicio al grupo de Windows de host según resulte necesario. Para obtener información acerca de los grupos de Windows a la que debe agregar la cuenta de servicio, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
4.  Utilice el grupo de Windows y la cuenta de servicio al crear el host y la instancia de host.  
  
    > [!NOTE]
    >  No se especifica \< *nombre_equipo*\>\ como el prefijo en el programa de instalación de un único equipo con los grupos locales.  
  
    > [!NOTE]
    >  Si se utiliza un grupo de dominio, debe especificar \< *nombre NetBIOS del dominio*\>\ como el prefijo para el nombre de grupo de Windows de host. Por ejemplo, CONTOSO\btssvc.  
  
## <a name="see-also"></a>Vea también  
 [Administración de Hosts y las cuentas de servicio](../core/managing-hosts-and-service-accounts.md)   
 [Administrar la seguridad de servidor BizTalk Server](../core/managing-biztalk-server-security.md)   
 [Cómo administrar el grupo de administradores de BizTalk Server](../core/how-to-manage-the-biztalk-server-administrators-group.md)   
 [Procedimientos recomendados para administrar grupos y cuentas de usuario de Windows](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)