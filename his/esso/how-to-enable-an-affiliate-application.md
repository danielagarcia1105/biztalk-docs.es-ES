---
title: Cómo habilitar una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 051bc35f-55e6-4811-9559-b1bb66a570ce
caps.latest.revision: ''
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 53dcd9886bc808f84b112146971a6f9519c404e2
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="how-to-enable-an-affiliate-application"></a>Cómo habilitar una aplicación afiliada
Puede usar el complemento MMC o la **enableapp** comando para habilitar la aplicación afiliada especificada.  
  
### <a name="to-enable-an-affiliate-application-using-the-mmc-snap-in"></a>Para habilitar una aplicación afiliada con el Complemento MMC  
  
1.  Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en la aplicación afiliada y, a continuación, haga clic en **habilitar**.  
  
### <a name="to-enable-an-affiliate-application-using-the-command-line"></a>Para habilitar una aplicación afiliada desde la línea de comandos  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssomanage –enableapp <application name>`, donde \< *nombre de la aplicación*> es el nombre de la aplicación afiliada que desea habilitar.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md)   
 [Cómo crear una aplicación afiliada](../esso/how-to-create-an-affiliate-application.md)   
 [Administrar asignaciones de usuario](../esso/managing-user-mappings.md)   
 [Administración de aplicaciones afiliadas](../esso/managing-affiliate-applications.md)