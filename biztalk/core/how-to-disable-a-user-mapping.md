---
title: Cómo deshabilitar una asignación de usuario | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, maps
- managing [SSO maps], disabling
- maps [SSO], disabling
ms.assetid: 9b6eaff2-674b-49f7-8d5c-3e040a7dc7f8
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b17ab68356d5d39f3f839f736261d4a7ef79c78
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-disable-a-user-mapping"></a>Cómo deshabilitar una asignación de usuario
Puede deshabilitar una asignación de usuarios cuando desee desactivar todas las operaciones que están asociadas a una asignación determinada. Debe deshabilitar una asignación de usuarios antes de que pueda quitarla.  
  
 Cuando se deshabilita una asignación de usuarios, aparecerá como (D) *\<dominio\>\\< nombre de usuario\>* al enumerar las asignaciones de usuario.  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a>Para deshabilitar una asignación de usuarios con la utilidad de administración  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo **ssomanage-disablemapping  *\<dominio\>*\\*\<nombre de usuario\> \<nombre de la aplicación\>***, donde *\<dominio\>* es el dominio de Windows para la cuenta de usuario y *\<nombre de usuario\>* es el nombre de usuario de Windows para que desea deshabilitar las credenciales y *\<nombre de la aplicación\>* es el nombre de la aplicación afiliada que desea quitar la asignación de usuario.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a>Para deshabilitar una asignación de usuarios con la utilidad de cliente  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo ** ssoclient – disablemapping *\<nombre de la aplicación\>***, donde *\<nombre de la aplicación\>* es el nombre de la aplicación afiliada que desea quitar la asignación de usuario.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Asignaciones de SSO](../core/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)   
 [Administración de asignaciones de usuarios](../core/managing-user-mappings.md)