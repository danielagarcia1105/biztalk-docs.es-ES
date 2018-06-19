---
title: Cómo borrar la caché de aplicaciones | Documentos de Microsoft
ms.custom: ''
ms.date: 11/30/2017
ms.prod: host-integration-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6a897791-d32f-46a4-8c5d-2b2161e92bd9
caps.latest.revision: 3
author: gplarsen
ms.author: hisdocs; plarsen
manager: anneta
ms.openlocfilehash: 24954e8314bc94d4570eb57acbf1d4b03bebb65b
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "30250944"
---
# <a name="how-to-clear-the-application-cache"></a>Cómo borrar la caché de aplicaciones
Use el complemento MMC o la **/purgecache** comando para quitar el contenido de la caché de credenciales (toda la información que está asociada a la aplicación afiliada) para la aplicación especificada en todos los servidores de inicio de sesión único (SSO).  
  
### <a name="to-clear-the-cache-using-the-mmc-snap-in"></a>Para borrar la caché con el Complemento MMC  
  
1.  Haga clic en **iniciar**, seleccione **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **aplicaciones afiliadas**.  
  
4.  En el panel de resultados, haga clic en la aplicación afiliada y haga clic en **desactive**.  
  
### <a name="to-clear-the-cache-using-the-command-line"></a>Para borrar la caché con la línea de comandos  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**, tipo `cmd`, y, a continuación, presione ENTRAR.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación Enterprise Single Sign-On.  
  
     El directorio de instalación predeterminado es \< *unidad*>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de `ssomanage –purgecache <application name>`, donde \< *nombre de la aplicación*> es el nombre de la aplicación afiliada que desea purgar la caché de.  
  
## <a name="see-also"></a>Vea también  
 [Aplicaciones afiliadas de SSO](../esso/sso-affiliate-applications.md)   
 [Administración de aplicaciones afiliadas](../esso/managing-affiliate-applications.md)