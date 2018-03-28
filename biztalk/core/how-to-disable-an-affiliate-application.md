---
title: Cómo deshabilitar una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- disabling, applications
- managing [SSO applications], disabling
- applications [SSO], disabling
ms.assetid: febf1687-f0d0-4f87-b462-23535bbddf6d
caps.latest.revision: ''
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09efa7dd00f563b8b02469909d2105d443438e95
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-disable-an-affiliate-application"></a>Cómo deshabilitar una aplicación afiliada
Puede utilizar el Complemento MMC o la línea de comandos para deshabilitar la aplicación afiliada especificada.  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a>Para deshabilitar una aplicación afiliada con el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en la aplicación afiliada y, a continuación, haga clic en **deshabilitar**.  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a>Para deshabilitar una aplicación afiliada desde la línea de comandos  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo **ssomanage-disableapp *\<nombre de la aplicación\>***, donde \<*nombre de la aplicación* \> es el nombre de la aplicación afiliada ¿desea deshabilitar.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)   
 [Cómo habilitar una aplicación afiliada](../core/how-to-enable-an-affiliate-application.md)   
 [Administrar asignaciones de usuario](../core/managing-user-mappings.md)   
 [Administración de aplicaciones afiliadas](../core/managing-affiliate-applications.md)