---
title: "Cómo habilitar una aplicación afiliada | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], enabling
- managing [SSO applications], enabling
- enabling, applications [SSO]
ms.assetid: 81c94e1b-cd3d-482e-9a78-9b1476af9e5f
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca2e0d03b233ffdf6bc0db759133062928aa22ef
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-enable-an-affiliate-application"></a>Cómo habilitar una aplicación afiliada
Utilice el Complemento MMC o la línea de comandos para habilitar la aplicación afiliada especificada.  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a>Para habilitar una aplicación afiliada con el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en la aplicación afiliada y, a continuación, haga clic en **habilitar**.  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a>Para habilitar una aplicación afiliada desde la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage-enableapp  *\<nombre de aplicación >***, donde \< *nombre de la aplicación*> es el nombre de la aplicación afiliada ¿desea habilitar.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../core/sso-affiliate-applications.md)   
 [Cómo crear una aplicación afiliada](../core/how-to-create-an-affiliate-application.md)   
 [Administrar asignaciones de usuario](../core/managing-user-mappings.md)   
 [Administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md)