---
title: Cómo eliminar asignaciones de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82c4cdff-b82d-4cfd-8e20-220a2fe78656
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: a9d0a31c3dbc9d5980f59d9f30d20ec15f603a38
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-delete-user-mappings"></a>Cómo eliminar asignaciones de usuario
Utilice estos comandos para eliminar una o varias asignaciones de usuario, como especificó en el archivo XML. A continuación, se muestra un archivo XML de ejemplo.  
  
```  
<sso>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name1</externalApplication>   
<externalUserId>App1UserName</externalUserId>   
</mapping>  
<mapping>  
<windowsDomain>domain</windowsDomain>   
<windowsUserId>WindowsUserName</windowsUserId>   
<externalApplication>Application name2</externalApplication>   
<externalUserId>App2UserName</externalUserId>   
</mapping>  
</sso>  
```  
  
 Si un usuario no es un miembro de la cuenta de usuarios de la aplicación, o no existe en Active Directory, debe utilizar este comando para quitar la asignación de usuario de la base de datos de credenciales.  
  
 Si la cuenta de usuario ha cambiado, debe utilizar este comando para quitar la asignación de usuario antigua y luego crear una asignación de usuario nueva para la cuenta de usuario nueva. Para obtener más información acerca de cómo crear una asignación, vea [cómo crear asignaciones de usuario](../esso/how-to-create-user-mappings.md).  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a>Para eliminar asignaciones de usuarios con la utilidad de administración  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssomanage –deletemappings <mappings file name>`, donde \< *asignaciones de nombre de archivo*> es el nombre del archivo que contiene las asignaciones de usuario que desea eliminar.  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a>Para eliminar una asignación de usuario específica con la utilidad de administración  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssomanage –deletemapping <domain>\<username> <application name>`, donde  *\<dominio >* es el dominio de Windows para la cuenta de usuario  *\<nombre de usuario >* es el nombre de usuario de Windows, y \< *nombre de la aplicación*> es la aplicación específica para la que desea quitar la asignación de usuario.  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a>Para eliminar una asignación de usuario con la utilidad de cliente  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssoclient –deletemapping <application name>`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada para la que desea quitar la asignación de usuario.  
  
## <a name="see-also"></a>Vea también  
 [Asignaciones de SSO](../esso/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../esso/managing-affiliate-applications.md)   
 [Administración de asignaciones de usuarios](../esso/managing-user-mappings.md)