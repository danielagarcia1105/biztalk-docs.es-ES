---
title: Cómo deshabilitar una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a7df6e78-6d18-443d-82dc-4351c20a8c4e
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 6bae89d2a05ec34095e0fa2ac3feafc7b88b894e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250928"
---
# <a name="how-to-disable-an-affiliate-application"></a>Cómo deshabilitar una aplicación afiliada
Use el complemento MMC o la **disableapp** comando para deshabilitar la aplicación afiliada especificada.  
  
### <a name="to-disable-an-affiliate-application-using-the-mmc-snap-in"></a>Para deshabilitar una aplicación afiliada con el Complemento MMC  
  
1.  Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en la aplicación afiliada y, a continuación, haga clic en **deshabilitar**.  
  
### <a name="to-disable-an-affiliate-application-using-the-command-line"></a>Para deshabilitar una aplicación afiliada desde la línea de comandos  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssomanage –disableapp <application name>`, donde \< *nombre de la aplicación*> es el nombre de la aplicación afiliada que desea deshabilitar.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md)   
 [Cómo habilitar una aplicación afiliada](../esso/how-to-enable-an-affiliate-application.md)   
 [Administrar asignaciones de usuario](../esso/managing-user-mappings.md)   
 [Administración de aplicaciones afiliadas](../esso/managing-affiliate-applications.md)