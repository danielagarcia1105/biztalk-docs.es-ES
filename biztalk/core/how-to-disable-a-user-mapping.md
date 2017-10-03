---
title: "Cómo deshabilitar una asignación de usuario | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disabling, maps
- managing [SSO maps], disabling
- maps [SSO], disabling
ms.assetid: 9b6eaff2-674b-49f7-8d5c-3e040a7dc7f8
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 417a28dd117a51d0bb1d45238f0efc96417c391a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-a-user-mapping"></a>Cómo deshabilitar una asignación de usuario
Puede deshabilitar una asignación de usuarios cuando desee desactivar todas las operaciones que están asociadas a una asignación determinada. Debe deshabilitar una asignación de usuarios antes de que pueda quitarla.  
  
 Cuando se deshabilita una asignación de usuarios, aparecerá como (D)  *\<dominio >\\< nombre de usuario\>*  al enumerar las asignaciones de usuario.  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a>Para deshabilitar una asignación de usuarios con la utilidad de administración  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de  **ssomanage-disablemapping  *\<dominio >*\\*\<nombre de usuario > \<nombre de aplicación >** *, donde  *\<dominio >* es el dominio de Windows para la cuenta de usuario y  *\<nombre de usuario >* es el nombre de usuario de Windows para el que desea deshabilitar el las credenciales, y  *\<nombre de aplicación >* es el nombre de la aplicación afiliada que desea quitar la asignación de usuario.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a>Para deshabilitar una asignación de usuarios con la utilidad de cliente  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssoclient – disablemapping  *\<nombre de aplicación >***, donde  *\<nombre de aplicación >* es el nombre de la afiliada aplicación que desea quitar la asignación de usuario.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Asignaciones de SSO](../core/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)   
 [Administrar asignaciones de usuario](../core/managing-user-mappings.md)