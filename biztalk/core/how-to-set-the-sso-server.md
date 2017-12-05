---
title: "Cómo establecer el servidor de SSO | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- servers, selecting [SSO]
- SSO, selecting servers
- managing [SSO], selecting servers
- SSOManage [SSO]
ms.assetid: a0b0176d-b426-4ab1-8a7e-1f96f4214683
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7dab9df7b5444b437f12737c37036b592a70aad
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-set-the-sso-server"></a>Cómo establecer el servidor de SSO
Cada vez que utilice ssomanage, en primer lugar debe seleccionar al usuario para el servidor de inicio de sesión único con el que desea establecer la conexión.  
  
 Puede hacerlo de una de las maneras siguientes:  
  
-   Los usuarios pueden seleccionarse a sí mismos para el servidor de inicio de sesión único correcto.  
  
-   Un administrador de equipo local del servidor de inicio de sesión único puede seleccionar a todos los miembros de la cuenta de usuarios de inicio de sesión único en este servidor.  
  
### <a name="to-set-the-enterprise-single-sign-on-server-using-the-mmc-snap-in"></a>Para establecer el servidor de inicio de sesión único empresarial con el Complemento MMC  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el complemento MMC en el **raíz de consola**, haga clic en **Enterprise Single Sign-On**y haga clic en **seleccione**.  
  
3.  Desplácese al servidor correspondiente.  
  
4.  Si es necesario, seleccione la **establecer servidor de SSO para todos los usuarios** casilla de verificación.  
  
5.  Haga clic en **Aceptar**.  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-a-single-user-using-the-command-line"></a>Para establecer el servidor de inicio de sesión único empresarial para un solo usuario con la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage – server \<el nombre del servidor SSO\>**, donde  **\<el nombre del servidor SSO\>**  es el nombre del equipo del servidor de inicio de sesión único en el usuario va a conectar.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-set-the-enterprise-single-sign-on-server-for-all-users-using-the-command-line"></a>Para establecer el servidor de inicio de sesión único empresarial para todos los usuarios con la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage – serverall \<el nombre del servidor SSO\>**, donde  **\<el nombre del servidor SSO\>**  es el nombre de equipo único inicio de sesión del servidor de todos los señalarán a los miembros de la cuenta de usuarios de inicio de sesión único.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-determine-the-enterprise-single-sign-on-server-to-which-a-user-is-connected-using-the-command-line"></a>Para determinar el servidor de inicio de sesión único empresarial al que se conecta un usuario con la línea de comandos  
  
1.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
2.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  **\<unidad\>**: \Program Files\Common Files\Enterprise Single Sign-On.  
  
3.  Tipo de **ssomanage – showserver**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
> [!NOTE]
>  Este comando muestra la configuración del usuario actual (y la de otros usuarios, si los hubiera).  
  
## <a name="see-also"></a>Vea también  
 [Cómo habilitar SSO](../core/how-to-enable-sso.md)   
 [Cómo deshabilitar SSO](../core/how-to-disable-sso.md)   
 [Cómo mostrar la información de la base de datos SSO](../core/how-to-display-the-sso-database-information.md)   
 [Uso de SSO](../core/using-sso.md)