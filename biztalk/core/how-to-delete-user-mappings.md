---
title: Cómo eliminar asignaciones de usuario | Microsoft Docs
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
ms.openlocfilehash: 034f587d8c7d87f5fa6aa7e5e33ca4ef147d9f9b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014389"
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
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo <strong>ssomanage-deletemappings  *\<nombre del archivo de asignaciones\></strong><em>, donde \<</em> nombre del archivo de asignaciones* \> es el nombre del archivo que contiene las asignaciones de usuarios que desea eliminar.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-delete-a-specific-user-mapping-using-the-administration-utility"></a>Para eliminar una asignación de usuario específica con la utilidad de administración  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo **ssomanage-deletemapping  *\<dominio\>*\\*\<username\> *   *\<nombre de la aplicación\>**<em>, donde *\<dominio\></em> es el dominio de Windows para la cuenta de usuario *\< nombre de usuario\>* es el nombre de usuario de Windows y \<* nombre de la aplicación* \> es la aplicación específica para el que desea quitar la asignación de usuario.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-delete-a-user-mapping-using-the-client-utility"></a>Para eliminar una asignación de usuario con la utilidad de cliente  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo ** ssoclient-deletemapping *\<nombre de la aplicación\>**<em>, donde *\<nombre de la aplicación\></em>  es el nombre de la aplicación afiliada que desea quitar el asignación de usuario.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Asignaciones de inicio de sesión único](../core/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)   
 [Administración de asignaciones de usuarios](../core/managing-user-mappings.md)