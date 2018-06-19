---
title: Cómo crear asignaciones de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb91879c-73f4-4e9e-9e5b-534f48cd5584
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 89fd7ab2ca83d23a37944447997becd2d3f008c2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250968"
---
# <a name="how-to-create-user-mappings"></a>Cómo crear asignaciones de usuario
Use la **createmappings** comando para crear una o varias asignaciones de usuario, como se especifica en el archivo XML. A continuación, se muestra un archivo XML de ejemplo.  
  
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
  
 Si se ha cambiado la cuenta de usuario, deberá utilizar este comando para crear una asignación para la nueva cuenta de usuario. También debería quitar la asignación de usuarios antigua. Para obtener más información acerca de cómo quitar una asignación, vea [cómo eliminar asignaciones de usuario](../esso/how-to-delete-user-mappings.md).  
  
 Después de crear una asignación de usuarios, debe habilitarla para poder usar esta asignación en el sistema de inicio de sesión único (SSO). Para obtener más información, consulte [cómo habilitar una asignación de usuarios](../esso/how-to-enable-a-user-mapping.md).  
  
> [!IMPORTANT]
>  Las asignaciones de usuarios solo admiten grupos de dominio.  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a>Para crear asignaciones de usuarios con la utilidad de administración  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssomanage –createmappings <mappings file name>`, donde  *\<asignaciones de nombre de archivo >* es el nombre del archivo que contiene las asignaciones de usuario que desea crear.  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a>Para crear asignaciones de usuarios con la utilidad de cliente  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssoclient –setcredentials <application name >`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada que desea crear una asignación para el usuario.  
  
## <a name="see-also"></a>Vea también  
 [Asignaciones de SSO](../esso/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../esso/managing-affiliate-applications.md)   
 [Administración de asignaciones de usuarios](../esso/managing-user-mappings.md)