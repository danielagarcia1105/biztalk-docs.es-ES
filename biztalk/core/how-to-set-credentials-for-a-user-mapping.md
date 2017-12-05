---
title: "Cómo establecer las credenciales para una asignación de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], credentials
- managing [SSO maps], configuring credentials
ms.assetid: 75b29114-56b6-4db0-8666-61cf6c675401
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4853499dbfd85cd5114212e37f4d22770d64a22
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-credentials-for-a-user-mapping"></a>Cómo establecer las credenciales para una asignación de usuario
Utilice este comando para establecer credenciales para que un usuario tenga acceso a una aplicación específica.  
  
 Este comando no muestra la contraseña conforme la escribe.  
  
 Si la asignación de usuario existe ya, este comando establece las credenciales para esa asignación. Si no ha creado la asignación de usuario, el sistema SSO le preguntará el Id. de usuario para la aplicación.  
  
### <a name="to-set-credentials-for-a-user-mapping"></a>Para establecer credenciales para una asignación de usuario  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage – setcredentials \<dominio\>\\< nombre de usuario\> \<applicationname\>**, donde  **\< dominio\>**  es el dominio de Windows para la cuenta de usuario  **\<nombre de usuario\>**  es el nombre de usuario de Windows, y  **\<applicationname \>**  es la aplicación específica para el que desea establecer las credenciales.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
4.  Cuando el sistema SSO le pida las credenciales de usuario, escriba la contraseña de usuario para esta aplicación.  
  
5.  Si no ha creado la asignación de usuario, el sistema SSO le preguntará el Id. de usuario para la aplicación.  
  
### <a name="to-set-credentials-for-a-user-mapping-from-the-client-utility"></a>Para establecer credenciales para una asignación de usuario desde la utilidad de cliente  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssoclient - setcredentials \<nombre de la aplicación\>**, donde  **\<nombre de la aplicación\>**  es el nombre de la aplicación afiliada ¿desea quitar la asignación de usuario.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear asignaciones de usuario](../core/how-to-create-user-mappings.md)   
 [Asignaciones de SSO](../core/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)   
 [Administración de asignaciones de usuarios](../core/managing-user-mappings.md)