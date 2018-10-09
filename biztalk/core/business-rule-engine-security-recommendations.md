---
title: Recomendaciones de seguridad del motor de reglas de negocio | Microsoft Docs
ms.custom: ''
ms.date: 09/27/2018
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, business rules
- Business Rules Framework, security
- business rules, security
ms.assetid: d5df1cd0-112a-4c72-b95d-cbcd1bc6a2c3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41815d53b31b2f0bf0ebf3e5626a61d76470ac4c
ms.sourcegitcommit: c1e83b63ae34bd586e6e0ccc914640efdf96bd4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48423920"
---
# <a name="business-rule-engine-security-recommendations"></a>Recomendaciones de seguridad del motor de reglas de negocios
El motor de reglas de negocios es el componente en tiempo de ejecución del marco de trabajo de reglas de negocios. El marco de trabajo de reglas de negocios permite conectar reglas de gran riqueza semántica, declarativas y muy legibles con cualquier objeto de negocios (componentes .NET), documento XML o tabla de base de datos. Para obtener más información sobre el marco de trabajo de la regla de negocios, vea [Creating and Using Business Rules](../core/creating-and-using-business-rules.md). Para obtener más información sobre el motor de reglas de negocios, vea [motor de reglas](../core/rule-engine.md).  
  
 No hay ningún grupo de usuarios de Windows para el motor de reglas de negocios, solo cuentas individuales. BizTalk Server restringe el acceso a los recursos del motor de reglas de negocios con dos roles del servidor SQL Server:  
  
 El rol RE_Admin_Users del servidor SQL Server está destinada a aquellos usuarios que necesitan realizar tareas administrativas en el motor de reglas de negocios, como la implementación de reglas. Entre los miembros del rol RE_Admin_Users del servidor SQL Server se incluyen los administradores de BizTalk.  
  
 El grupo RE_Host_Users está destinado a todos los demás usuarios del motor de reglas de negocios que no necesitan derechos de usuario administrativos y que realizan tareas tales como la lectura y ejecución de reglas. Entre los miembros del rol RE_Host_Users se incluyen la función BizTalk_Host_Users. Para implementar permisos en el motor de reglas de negocios de forma independiente de los permisos de BizTalk Server, puede usar los roles del servidor SQL Server. Para obtener más información acerca de los permisos mínimos necesarios para usar el motor de reglas de negocios, vea [derechos de usuario mínimos de seguridad](../core/minimum-security-user-rights.md). Es recomendable seguir estas directrices para proteger e implementar el motor de reglas de negocios en su entorno.  
  
-   BizTalk Server proporciona la cuenta que utilizó para instalar el inicio de sesión del servicio de actualización como derechos de servicio y la agrega al rol RE_Host_Users del servidor SQL Server en la base de datos del motor de reglas de negocios. Si la cuenta que utiliza para la instalación no es la misma que la que va a utilizar para ejecutar el servicio de actualización, debe quitar la cuenta de instalación del rol RE_Host_Users del servidor de SQL Server.  

-   Si no usa la misma cuenta con otra cuenta de servicio de host de BizTalk, también agregar la cuenta de servicio RuleEngine a BTS_HOST_USERS en BizTalkMgmtDb y BizTalkMsgBoxDb.

-   Si utiliza el componente de servicio de actualización, deberá instalarlo en todos los equipos de tiempo de ejecución de BizTalk. Para recuperar una regla de la base de datos del motor de reglas, el servicio de actualización suplanta al autor de la llamada al servicio.  
  
-   De forma predeterminada, todos los hosts de BizTalk tienen el mismo nivel de acceso a los artefactos del motor de reglas. No hay segregación de seguridad por host. Puede configurar la seguridad por directivas mediante las API del motor de reglas. Para obtener más información acerca de cómo configurar la seguridad por directivas, consulte [Business Framework: las reglas de seguridad](../core/business-rules-framework-security.md).  
  
## <a name="see-also"></a>Vea también  
 [Puertos de los servidores de procesamiento](../core/ports-for-the-processing-servers.md)
