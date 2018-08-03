---
title: Cómo deshabilitar una asignación de usuario | Microsoft Docs
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e49f524337fffde9261af4aa2cd64c75e307ccb
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36972637"
---
# <a name="how-to-disable-a-user-mapping"></a>Cómo deshabilitar una asignación de usuarios
Puede deshabilitar una asignación de usuarios cuando desee desactivar todas las operaciones que están asociadas a una asignación determinada. Debe deshabilitar una asignación de usuarios antes de que pueda quitarla.  
  
 Cuando se deshabilita una asignación de usuario, aparecerá como (D) *\<dominio\>\\< nombre de usuario\>* al enumerar las asignaciones de usuario.  
  
### <a name="to-disable-a-user-mapping-using-the-administration-utility"></a>Para deshabilitar una asignación de usuarios con la utilidad de administración  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo **ssomanage-disablemapping  *\<dominio\>*\\*\<username\> \<nombre de la aplicación\>**  <em>, donde *\<dominio\></em>  es el dominio de Windows para la cuenta de usuario y *\<username\>* es el Nombre de usuario de Windows para el que desea deshabilitar las credenciales, y *\<nombre de la aplicación\>* es el nombre de la aplicación afiliada que desea quitar la asignación de usuario.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-disable-a-user-mapping-using-the-client-utility"></a>Para deshabilitar una asignación de usuarios con la utilidad de cliente  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Tipo ** ssoclient-disablemapping *\<nombre de la aplicación\>**<em>, donde *\<nombre de la aplicación\></em>  es el nombre de la aplicación afiliada que desea quitar el asignación de usuario.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Asignaciones de inicio de sesión único](../core/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)   
 [Administración de asignaciones de usuarios](../core/managing-user-mappings.md)