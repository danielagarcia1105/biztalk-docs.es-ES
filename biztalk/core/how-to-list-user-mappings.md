---
title: Cómo enumerar asignaciones de usuario | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [SSO maps], listing maps
- maps [SSO], listing maps
ms.assetid: f9b73785-3a59-45c8-9e88-d2d16b5a46aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cef1fbe44c9c3ddbe5458a92644f9ea39534789e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36974109"
---
# <a name="how-to-list-user-mappings"></a>Cómo enumerar asignaciones de usuario
Utilice este comando para listar todas las asignaciones existentes del usuario especificado.  
  
 Para llevar a cabo esta tarea deberá ser administrador de SSO, administrador de aplicaciones, administrador afiliado de SSO o usuario.  
  
 Asignaciones de usuario habilitadas aparecen como (E) \< *dominio*\>\\*\<username\>*, mientras que deshabilita las asignaciones de usuario aparecen como (D) \< *dominio*\>\\*\<username\>*.  
  
### <a name="to-list-user-mappings-using-the-administration-utility"></a>Para listar asignaciones de usuarios con la utilidad de administración  
  
1. En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3. Realice una de las siguientes operaciones:  
  
   - Tipo **ssomanage-listmappings *\<dominio\>\\< nombre de usuario\>***  para enumerar todas las asignaciones de un usuario determinado tiene en las aplicaciones afiliadas que pertenece, dónde *\<dominio\>* es el dominio de Microsoft Windows para la cuenta de usuario y *\<username\>* es el Nombre de usuario de Windows para el que desea enumerar las asignaciones de usuario. Si el usuario es un administrador afiliado o un administrador de SSO, este comando enumerará todas las asignaciones de ese usuario en todas las aplicaciones afiliadas.  
  
      o bien  
  
   - Tipo **ssomanage-listmappings *\<nombre de la aplicación\>***  para enumerar todas las asignaciones de usuario para una aplicación determinada.  
  
      o bien  
  
   - Si es un administrador de aplicaciones, escriba **ssomanage-listmappings *\<dominio\>\\< nombre de usuario\>* *\< nombre de la aplicación\>***  para enumerar todas las asignaciones de un usuario determinado tiene en las aplicaciones afiliadas que es un administrador.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-list-user-mappings-using-the-client-utility"></a>Para listar asignaciones de usuarios con la utilidad de cliente  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo **ssoclient – listmappings** para enumerar todas las asignaciones.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo crear asignaciones de usuario](../core/how-to-create-user-mappings.md)   
 [Asignaciones de inicio de sesión único](../core/sso-mappings.md)   
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)   
 [Administración de asignaciones de usuarios](../core/managing-user-mappings.md)