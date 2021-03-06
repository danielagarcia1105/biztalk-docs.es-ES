---
title: Cómo habilitar y deshabilitar Host SSO iniciado por | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host initiated SSO, disabling
- disabling, host initiated SSO
- enabling, host initiated SSO
- host initiated SSO, enabling
ms.assetid: a11d314a-6ff9-4d0a-89c3-c412541c2cec
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f187572f671328c77576749b1bf8f3564f025005
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979325"
---
# <a name="how-to-enable-and-disable-host-initiated-sso"></a>Cómo habilitar y deshabilitar Host SSO iniciado por
De forma predeterminada, el inicio de sesión único iniciado por host no se encuentra habilitado en el sistema de inicio de sesión único, y debe habilitarlo el administrador de SSO.  
  
### <a name="to-enable-host-initiated-sso-using-the-mmc-snap-in"></a>Para habilitar el SSO iniciado por host con el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **sistema**y, a continuación, haga clic en **propiedades**.  
  
4.  Haga clic en el **opciones** ficha.  
  
5.  Seleccione el **SSO iniciado por host Enable** cuadro y haga clic en **Aceptar**.  
  
### <a name="to-enable-host-initiated-sso-using-the-command-line"></a>Para habilitar el SSO iniciado por host con la línea de comandos  
  
1. En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2. En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3. En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4. Tipo **ssomanage-habilitar hisso**.  
  
   > [!NOTE]
   >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
   El SSO se deshabilita en todo el sistema de SSO y se desactivan todas las operaciones relacionadas con el SSO iniciado por host.  
  
#### <a name="to-disable-host-initiated-sso-using-the-mmc-snap-in"></a>Para deshabilitar el SSO iniciado por host con el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito del complemento MMC de ENTSSO, expanda el **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **sistema**y, a continuación, haga clic en **propiedades**.  
  
4.  Haga clic en el **opciones** ficha.  
  
5.  Desactive el **SSO iniciado por host Enable** cuadro y haga clic en **Aceptar**.  
  
#### <a name="to-disable-host-initiated-sso-using-the-command-line"></a>Para deshabilitar el SSO iniciado por host con la línea de comandos  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo **ssomanage-deshabilitar hisso** según corresponda.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [SSO iniciado por host](../core/host-initiated-sso.md)