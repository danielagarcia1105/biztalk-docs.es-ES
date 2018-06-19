---
title: Cómo eliminar una aplicación afiliada | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec290d38-0220-4bf2-b596-2d6453e51c8d
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: d0632f7e4217cb9bbccd2ee604688f22eb6de348
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250984"
---
# <a name="how-to-delete-an-affiliate-application"></a>Cómo eliminar una aplicación afiliada
Use el complemento MMC o la **deleteapps** comando para eliminar la aplicación afiliada especificada de la base de datos de credenciales.  
  
> [!IMPORTANT]
>  Cuando se elimina una aplicación afiliada, el sistema SSO elimina automáticamente todas las asignaciones asociadas a dicha aplicación.  
  
> [!IMPORTANT]
>  Para realizar esta tarea debe ser administrador de SSO o administrador afiliado de SSO.  
  
### <a name="to-delete-an-affiliate-application-using-the-mmc-snap-in"></a>Para eliminar una aplicación afiliada con el Complemento MMC  
  
1.  Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento de MMC, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en la aplicación afiliada y, a continuación, haga clic en **eliminar**.  
  
### <a name="to-delete-an-affiliate-application-using-the-command-line"></a>Para eliminar una aplicación afiliada con la línea de comandos  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssomanage –deleteapp <application name>`, donde  *\<nombre de aplicación >* es el nombre de la aplicación afiliada que desea quitar de la base de datos de credenciales.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md)   
 [Cómo habilitar una aplicación afiliada](../esso/how-to-enable-an-affiliate-application.md)   
 [Administrar asignaciones de usuario](../esso/managing-user-mappings.md)   
 [Administración de aplicaciones afiliadas](../esso/managing-affiliate-applications.md)