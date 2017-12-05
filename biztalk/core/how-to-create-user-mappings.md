---
title: "Cómo crear asignaciones de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps [SSO], creating
- managing [SSO maps], creating user maps
ms.assetid: c2e9f0db-920b-4d89-8e1e-5dc92805fd23
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019adf0cd41c643ac77790c96a3450bb967ddd6b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-user-mappings"></a>Cómo crear asignaciones de usuario
Utilice este comando para crear una o más asignaciones de usuarios, según se especifica en el archivo XML. A continuación, se muestra un archivo XML de ejemplo.  
  
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
  
 Si se ha cambiado la cuenta de usuario, deberá utilizar este comando para crear una asignación para la nueva cuenta de usuario. También debería quitar la asignación de usuarios antigua. Para obtener más información acerca de cómo quitar una asignación, vea [cómo eliminar asignaciones de usuario](../core/how-to-delete-user-mappings.md).  
  
 Si ha creado una asignación de usuarios y desea utilizarla en el sistema de SSO, primero deberá habilitarla. Para obtener más información, consulte [cómo habilitar una asignación de usuarios](../core/how-to-enable-a-user-mapping.md).  
  
> [!IMPORTANT]
>  Las asignaciones de usuarios solo admiten grupos de dominio.  
  
### <a name="to-create-user-mappings-using-the-administration-utility"></a>Para crear asignaciones de usuarios con la utilidad de administración  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage – createmappings  *\<asignaciones de nombre de archivo\>***, donde  *\<asignaciones de nombre de archivo\>*  es el nombre del archivo que contiene las asignaciones de usuarios que desea crear.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-create-user-mappings-using-the-client-utility"></a>Para crear asignaciones de usuarios con la utilidad de cliente  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssoclient – setcredentials  *\<nombre de la aplicación \>*** , donde  *\<nombre de la aplicación \>*  es el nombre de aplicación afiliada que desea crear una asignación para el usuario.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Asignaciones de SSO](../core/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)   
 [Administración de asignaciones de usuarios](../core/managing-user-mappings.md)