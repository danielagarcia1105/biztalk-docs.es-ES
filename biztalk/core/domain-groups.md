---
title: Grupos de dominio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: domain groups
ms.assetid: 9adc090e-e18c-46b6-b985-49b200d42966
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 52fc5cc05718aa6d9e0ca89bc48467052fb916a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="domain-groups"></a>Grupos de dominio
BizTalk Server admite cuentas de grupo de dominio y de usuario en configuraciones de uno y de varios equipos. Para configuraciones de varios equipos, debe observar los requisitos mencionados en esta sección y en el apartado Consideraciones para crear un entorno multiservidor de la Guía de instalación. Para obtener más información, consulte [Introducción a la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5).  
  
-   Si utiliza grupos de dominio para la configuración de BizTalk Server, debe crear los grupos manualmente antes de configurar BizTalk Server. El Administrador de configuración no puede crear grupos de dominio.  
  
-   Después de crear grupos de dominio o cuentas de usuario, agregar cuentas de usuario a los grupos adecuados según las afiliaciones de grupo en [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
-   Use  **\<DomainName >\\< nombre de usuario\>**  al especificar la información de cuenta de dominio en el Administrador de configuración.  
  
-   BizTalk Server necesita cuentas de dominio en todos los escenarios de clúster. No puede utilizar cuentas locales con un servidor SQL Server o un servidor de SSO (servidor secreto principal) agrupados.  
  
-   El Administrador de instalación y configuración de BizTalk Server debe ser miembro de los siguientes grupos: los administradores de SSO (sólo al configurar el servidor secreto principal); Administradores locales; función de SQL Server sysadmin; Administradores OLAP.  
  
> [!NOTE]
>  Puede crear el grupo de dominio automáticamente si especifica un grupo de dominio durante la configuración de los grupos de administradores de SSO y de administradores de aplicaciones afiliadas de SSO y tiene los privilegios suficientes para hacerlo. Si no tiene privilegios suficientes, asegúrese de que esos grupos ya existen.  
  
## <a name="see-also"></a>Vea también  
 [Grupos locales](../core/local-groups.md)   
 [Información general sobre la instalación de BizTalk Server 2013 y 2013 R2](http://msdn.microsoft.com/library/8041926c-cfc9-4eaf-9c28-a2c6e8015bc5)   
 [Cuentas de grupos y de usuario de Windows en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md)