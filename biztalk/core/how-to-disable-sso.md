---
title: "Cómo deshabilitar SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- disabling, SSO
- SSO, disabling
- managing [SSO], disabling
ms.assetid: 0fe4f87a-d7c2-4af6-afee-1065bc4a5285
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c8069ffb291b64d832a1d3ce483e7ab09be655f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-disable-sso"></a>Cómo deshabilitar SSO
Se puede deshabilitar la totalidad del sistema de inicio de sesión único utilizando el Complemento MMC o la línea de comandos.  
  
 Habrá un breve retraso hasta que se deshabiliten todos los servidores de inicio de sesión único, puesto que efectúan un sondeo de la base de datos de SSO para la obtención de la información global más reciente.  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-mmc-snap-in"></a>Para deshabilitar el inicio de sesión único empresarial con el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **System**y, a continuación, haga clic en **deshabilitar**.  
  
### <a name="to-disable-enterprise-single-sign-on-using-the-command-line"></a>Para deshabilitar el inicio de sesión único empresarial con la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage – disablesso**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo habilitar SSO](../core/how-to-enable-sso.md)   
 [Uso de SSO](../core/using-sso.md)