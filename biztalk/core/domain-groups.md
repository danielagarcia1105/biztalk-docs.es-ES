---
title: Grupos de dominio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9adc090e-e18c-46b6-b985-49b200d42966
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2944ce83df75ed724c9a7acafeee119b40cacafb
ms.sourcegitcommit: 7b64c823fa8d7fa8b10b163613311be69b861017
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2018
ms.locfileid: "39625872"
---
# <a name="domain-groups-in-biztalk"></a>Grupos de dominio de BizTalk
BizTalk Server admite cuentas de grupo de dominio y de usuario en configuraciones de uno y de varios equipos. Para configuraciones de varios equipos, debe observar los requisitos mencionados en esta sección y en el apartado Consideraciones para crear un entorno multiservidor de la Guía de instalación. Para obtener más información, consulte el [Introducción a la instalación](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md).  
  
## <a name="before-you-begin"></a>Antes de comenzar
-   Si utiliza grupos de dominio para la configuración de BizTalk Server, debe crear los grupos manualmente antes de configurar BizTalk Server. El Administrador de configuración no puede crear grupos de dominio.  
  
-   Después de crear grupos de dominio o cuentas de usuario, agregue las cuentas de usuario a los grupos adecuados según las afiliaciones de grupo en [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
-   Use **\<DomainName\>\\< nombre de usuario\>** al especificar la información de cuenta de dominio en el Administrador de configuración.  
  
-   BizTalk Server necesita cuentas de dominio en todos los escenarios de clúster. No puede utilizar cuentas locales con un servidor SQL Server o un servidor de SSO (servidor secreto principal) agrupados.  
  
-   El Administrador de instalación y configuración de BizTalk Server debe ser miembro de los siguientes grupos: los administradores de SSO (sólo al configurar el servidor secreto principal); Administradores locales; rol de SQL Server sysadmin; Administradores de OLAP.  
  
> [!NOTE]
>  Puede crear el grupo de dominio automáticamente si especifica un grupo de dominio durante la configuración de los grupos de administradores de SSO y de administradores de aplicaciones afiliadas de SSO y tiene los privilegios suficientes para hacerlo. Si no tiene privilegios suficientes, asegúrese de que esos grupos ya existen.  
  
## <a name="see-also"></a>Vea también  
 [Grupos locales](../core/local-groups.md)   
 [Introducción a la instalación](../install-and-config-guides/biztalk-server-what-s-new-installation-configuration-and-upgrade.md)   
 [Cuentas de grupos y de usuario de Windows en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md)
