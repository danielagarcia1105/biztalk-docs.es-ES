---
title: "Cómo establecer las credenciales para la aplicación afiliada con la utilidad de cliente | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [SSO applications], configuring credentials
- SSOClient [SSO], configuring credentials
- applications [SSO], credentials
ms.assetid: 454b6257-3538-40be-840c-00172a2c1dce
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 31ba167bc35d01907166bb6610720e03be654c4d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a>Cómo establecer las credenciales para la aplicación afiliada con la utilidad de cliente
Utilice este comando para establecer las credenciales para un usuario para que éste tenga acceso a una aplicación específica. Este comando también habilita automáticamente la asignación.  
  
 Este comando no muestra la contraseña conforme la escribe.  
  
 Si ya existe la asignación de usuario, este comando establecerá las credenciales para la asignación existente. Si no ha creado la asignación de usuario, el sistema SSO le preguntará el Id. de usuario para la aplicación.  
  
### <a name="to-set-credentials-for-the-affiliate-application-using-the-client-utility"></a>Para establecer las credenciales de la aplicación afiliada con la utilidad de cliente  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssoclient – setcredentials \<nombre de aplicación >**, donde  **\<nombre de aplicación >** es la aplicación específica para el que desea establecer las credenciales.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4.  Cuando se solicitan las credenciales de usuario, escriba la contraseña de usuario para esta aplicación.  
  
5.  Si no ha creado la asignación de usuario, el sistema SSO le preguntará el Id. de usuario para la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)   
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)