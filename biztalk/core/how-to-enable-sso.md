---
title: "Cómo habilitar SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications [SSO], creating
- SSO, enabling
- maps [SSO], creating
- managing [SSO], enabling
- SSO, maps
- SSO, applications
- creating, applications [SSO]
- managing [SSO], creating affiliate applications
ms.assetid: dda89d15-6b70-4c40-b658-2f6cbdd545c8
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a843c0f6cdea32ba5218140069163058fcd42442
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-sso"></a>Cómo habilitar SSO
Puede habilitar todo el sistema de inicio de sesión único (SSO) empresarial mediante el Complemento MMC o la línea de comandos.  
  
 Tras ejecutar el comando de habilitación, se produce un pequeño retraso antes de que se habiliten todos los servidores de inicio de sesión único, ya que cada uno sondea la base de datos de SSO en busca de la información global más actualizada.  
  
 Si desea configurar las asignaciones y aplicaciones afiliadas en el sistema de SSO, debe crear una aplicación afiliada. Cuando el administrador afiliado de SSO crea una aplicación afiliada, un administrador de aplicación puede realizar cambios en ella, y los usuarios de la aplicación (usuarios finales) pueden crear sus propias asignaciones. Para obtener más información, consulte [administrar aplicaciones afiliadas](../core/managing-affiliate-applications.md) y [administración de asignaciones de usuario](../core/managing-user-mappings.md).  
  
### <a name="to-enable-the-sso-system-using-the-mmc-snap-in"></a>Para habilitar el sistema de SSO con el Complemento MMC  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  Haga clic en **System**y, a continuación, haga clic en **habilitar**.  
  
### <a name="to-enable-the-sso-system-using-the-command-line"></a>Para habilitar el sistema de SSO con la línea de comandos  
  
1.  Haga clic en **iniciar**, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage – enablesso**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-enable-sso-to-create-affiliate-applications-and-mappings"></a>Para habilitar SSO para crear aplicaciones afiliadas y asignaciones  
  
1.  Inicie sesión como administrador de SSO o administrador afiliado de SSO en el servidor de SSO o en un equipo que posea los subservicios de administración SSO de SSO.  
  
2.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
3.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad\>*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage - enablesso** para habilitar el servicio de Enterprise Single Sign-On.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
5.  Inicie sesión como administrador afiliado de SSO  
  
6.  Tipo de **ssomanage - createapps  *\<archivo de la aplicación\>***  para crear una aplicación afiliada, donde \<archivo de la aplicación\> es el archivo XML que contiene las definiciones de las aplicaciones afiliadas.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Cómo establecer el servidor de SSO](../core/how-to-set-the-sso-server.md)   
 [Cómo deshabilitar SSO](../core/how-to-disable-sso.md)   
 [Cómo actualizar la base de datos SSO](../core/how-to-update-the-sso-database.md)   
 [Uso de SSO](../core/using-sso.md)