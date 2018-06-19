---
title: Cómo administrar la sincronización de contraseña | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], managing
- managing [SSO], disabling features
- managing [SSO], enabling features
- Password Synchronization [SSO], SSOMANAGE command line utility
- SSO database, SSOMANAGE command line utility
- managing, Password Synchronization [SSO]
- SSO database, database settings
- SSOMANAGE command line utility
ms.assetid: 033e63f2-e5b0-4400-99c3-145679d9b84e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ce76f2ca16cca44af1658983c49d11f6931e931
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972658"
---
# <a name="how-to-manage-password-synchronization"></a>Cómo administrar la sincronización de contraseña
El Complemento MMC o la utilidad de línea de comandos SSOMANAGE se utiliza para habilitar o deshabilitar las características de SSO, así como para mostrar la configuración de la base de datos de SSO.  
  
### <a name="to-manage-features-or-display-settings-using-the-mmc-snap-in"></a>Para administrar características o mostrar la configuración utilizando el Complemento MMC  
  
1.  Haga clic con el botón secundario en la base de datos o característica adecuada.  
  
2.  Haga clic en el elemento de menú que proceda.  
  
### <a name="to-enable-sso-features-using-the-command-line"></a>Para habilitar las características de SSO utilizando la línea de comandos  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage-habilitar** y presione ENTRAR.  
  
### <a name="to-disable-sso-features-using-the-command-line"></a>Para deshabilitar las características de SSO utilizando la línea de comandos  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage-deshabilitar** y presione ENTRAR.  
  
### <a name="to-display-current-database-settings-using-the-command-line"></a>Para mostrar la configuración de la base de datos utilizando la línea de comandos  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage - displaydb** y presione ENTRAR.  
  
## <a name="see-also"></a>Vea también  
 [Sincronización de contraseñas](../core/password-synchronization2.md)