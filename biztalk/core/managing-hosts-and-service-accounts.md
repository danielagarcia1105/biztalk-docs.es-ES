---
title: Administración de Hosts y las cuentas de servicio | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, managing
- managing [user accounts]
- service accounts, security
- managing [hosts], security
- security, hosts
- managing [Windows groups]
- hosts, security
- security, service accounts
- Windows groups, managing
- user accounts, managing
ms.assetid: 25797571-f1f9-42a4-8fff-5b03076bbe36
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0099e683fba7c5f4e2400ad2f9ce005928b0a2aa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262388"
---
# <a name="managing-hosts-and-service-accounts"></a>Administrar hosts y cuentas de servicio
Después de configurar BizTalk Server, tendrá que administrar grupos de Windows y cuentas de usuario. En esta sección se proporciona información acerca de cómo administrar estas cuentas para BizTalk Server.  
  
> [!NOTE]
>  Para una instalación multiservidor de BizTalk Server, tendrá que utilizar un grupo global de dominio. Para una instalación de un solo servidor de BizTalk Server, podrá utilizar un grupo global de dominio o un grupo local.  
  
 Para realizar las tareas siguientes, tendrá que ser un administrador de Windows:  
  
-   Crear un grupo de Windows de host  
  
-   Crear cuentas de servicio para cada instancia de host  
  
-   Agregar cuentas de servicio al grupo de Windows de host  
  
-   Modificar el grupo de Windows asociado al host  
  
 Para una lista completa y una descripción de los grupos y sus cuentas de usuarios afiliados en BizTalk Server, vea [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
 Para obtener más información de derechos de usuario mínimos de seguridad para tareas administrativas, consulte [derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo crear servicio cuentas para nuevos Hosts e instancias de Host](../core/how-to-create-service-accounts-for-new-hosts-and-host-instances.md)  
  
-   [Cómo cambiar contraseñas y cuentas de servicio](../core/how-to-change-service-accounts-and-passwords.md)