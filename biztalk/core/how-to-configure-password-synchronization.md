---
title: Cómo configurar la sincronización de contraseña | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Password Synchronization [SSO], replay files
- Password Synchronization [SSO], maximum age
- SSOCONFIG command line utility
- Password Synchronization [SSO], SSOCONFIG command line utility
- Password Synchronization [SSO], configuring
- configuring, Password Synchronization [SSO]
ms.assetid: 04000dfc-02b9-4d50-babe-8bc8a07a33b7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2e8348cdf78db3e95ed75e5d83e6ea53bdffdee
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25968914"
---
# <a name="how-to-configure-password-synchronization"></a>Cómo configurar la sincronización de contraseña
La utilidad de línea de comandos SSOCONFIG se utiliza para establecer la configuración de la sincronización de contraseñas.  
  
### <a name="to-specify-the-directory-for-replay-files"></a>Para especificar el directorio para archivos de reproducción  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssoconfig - replayfiles \<directorio de archivos de reproducción\> &#124; - predeterminado** y presione ENTRAR.  
  
> [!NOTE]
>  Los archivos de reproducción no se eliminan al cambiar la cuenta de servicio. Si se cambia esta cuenta, será necesario eliminar los archivos de reproducción de forma manual.  
  
#### <a name="to-display-or-change-maximum-password-synchronization-age"></a>Para mostrar o cambiar la antigüedad máxima de la sincronización de contraseñas  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssoconfig - syncage \<antigüedad máxima de contraseña en horas\>**  y presione ENTRAR.  
  
> [!NOTE]
>  La utilidad SSOCONFIG usa la hora del equipo de SQL Server como la hora del sistema. Téngalo en cuenta al utilizar cualquier comando relacionado con la hora.  
  
## <a name="see-also"></a>Vea también  
 [Sincronización de contraseñas](../core/password-synchronization2.md)