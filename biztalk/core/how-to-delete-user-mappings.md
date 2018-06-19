---
title: Cómo eliminar asignaciones de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maps [SSO], deleting
- managing [SSO maps], deleting user maps
ms.assetid: de511113-b0b0-4920-91dc-4c9e380fda58
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03f7c1fa75b6fe7bb4c78e18c97fccd1404f89c9
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25970666"
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
  
 Si el usuario no es miembro de la cuenta Usuarios de aplicación o si no existe en Active Directory, debería utilizar este comando para quitar la asignación de usuario de la base de datos de SSO.  
  
 Si la cuenta de usuario ha cambiado, debe utilizar este comando para quitar la asignación de usuario antigua y luego crear una asignación de usuario nueva para la cuenta de usuario nueva. Para obtener más información acerca de cómo crear una asignación, vea [cómo crear asignaciones de usuario](../core/how-to-create-user-mappings.md).  
  
### <a name="to-delete-user-mappings-using-the-administration-utility"></a>Para eliminar asignaciones de usuarios con la utilidad de administración  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo **ssomanage – deletemappings *\<asignaciones de nombre de archivo\>***, donde \<* asignaciones de nombre de archivo* \> es el nombre del archivo que contiene el asignaciones de usuarios que desea eliminar.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a>Para eliminar una asignación de usuario específica con la utilidad de administración  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de  **ssomanage-deletemapping  *\<dominio\>*\\*\<nombre de usuario\> *  *\<nombre de la aplicación\>***, donde *\<dominio\>* es el dominio de Windows para la cuenta de usuario *\<denombredeusuario\>* es el nombre de usuario de Windows, y \<* nombre de la aplicación* \> es la aplicación específica para la que desea quitar la asignación de usuario.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a>Para eliminar una asignación de usuario con la utilidad de cliente  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo ** ssoclient – deletemapping *\<nombre de la aplicación\>***, donde *\<nombre de la aplicación\>* es el nombre de la aplicación afiliada que desea quitar la asignación de usuario.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Asignaciones de SSO](../core/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)   
 [Administración de asignaciones de usuarios](../core/managing-user-mappings.md)