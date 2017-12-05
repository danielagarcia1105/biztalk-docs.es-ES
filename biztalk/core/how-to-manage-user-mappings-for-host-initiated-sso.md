---
title: "Cómo administrar las asignaciones de usuario para el Host para SSO iniciado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- maps, host initiated SSO
- host initiated SSO, user maps
ms.assetid: 6b05249e-da35-475b-9c23-5eb556013d57
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a0bf65bdb3de30d5b701946215b5c7ae7d40d828
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-manage-user-mappings-for-host-initiated-sso"></a>Cómo administrar las asignaciones de usuario para el Host para SSO iniciado
Utilice los procedimientos siguientes para crear asignaciones, definir credenciales y habilitar o deshabilitar asignaciones.  
  
### <a name="to-manage-user-mappings-for-host-initiated-sso-using-the-mmc-snap-in"></a>Para administrar asignaciones de usuarios para SSO iniciado por host utilizando el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, el complemento MMC de ENTSSO, expanda la **Enterprise Single Sign-On** nodo.  
  
3.  En el panel de ámbito, haga clic en **aplicaciones afiliadas**.  
  
4.  En el panel de detalles, haga clic con el botón secundario en la aplicación afiliada, y después seleccione la opción de menú apropiada, según la acción que desee llevar a cabo.  
  
### <a name="to-create-mappings-in-host-initiated-sso-using-the-command-line"></a>Crear asignaciones en SSO iniciado por host utilizando la línea de comandos  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage – createmappings \<archivo de asignación\>**, donde **archivo de asignación >** es el nombre del archivo xml.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
     A continuación se muestra un ejemplo de archivo de asignaciones:  
  
    ```  
    <SSO>  
      <mapping>  
        <windowsDomain>DomainName</windowsDomain>  
        <windowsUserId>UserA</windowsUserId>  
        <externalApplication>SSOApplication</externalApplication>  
    <externalUserId>ExternalUserID that corresponds to UserA</externalUserId>  
      </mapping>  
    </SSO>  
  
    ```  
  
 Cuando la característica Validar contraseña está habilitada en la aplicación afiliada, es necesario definir las credenciales tal como se describe a continuación:  
  
#### <a name="to-set-credentials-for-individual-type-affiliate-applications-using-the-command-line"></a>Para definir las credenciales para aplicaciones afiliadas de tipo individual utilizando la línea de comandos  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage - setcredentials \<nombre de la cuenta de Windows\> \<nombre de la aplicación\>**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
#### <a name="to-set-credentials-for-host-group-type-affiliate-applications-using-the-command-line"></a>Para definir las credenciales para aplicaciones afiliadas de tipo grupo de hosts utilizando la línea de comandos  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage - setcredentials \<nombre de cuenta externa\> \<nombre de la aplicación\>**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
#### <a name="to-enable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a>Para habilitar las asignaciones de las aplicaciones afiliadas de tipo individual mediante la línea de comandos  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage - enablemapping \<nombre de la cuenta de Windows\> \<nombre de la aplicación\>**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a>Para deshabilitar las asignaciones para aplicaciones afiliadas de tipo individual utilizando la línea de comandos  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage - disablemapping \<nombre de la cuenta de Windows\> \<nombre de la aplicación\>**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
#### <a name="to-enable-mappings-for-host-group-type-affiliate-applications-using-the-command-line"></a>Para habilitar las asignaciones para aplicaciones afiliadas de tipo grupo de hosts utilizando la línea de comandos  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage - enablemapping \<nombre de cuenta externa\> \<nombre de la aplicación\>**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
#### <a name="to-disable-mappings-for-individual-type-affiliate-applications-using-the-command-line"></a>Para deshabilitar las asignaciones para aplicaciones afiliadas de tipo individual utilizando la línea de comandos  
  
1.  En el menú **Inicio** , haga clic en **Ejecutar**.  
  
2.  En el **ejecutar** cuadro de diálogo, escriba **cmd**y, a continuación, haga clic en **Aceptar**.  
  
3.  En la línea de comandos, vaya al directorio de instalación de inicio de sesión único empresarial. El valor predeterminado es \<unidad\>: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage - disablemapping \<nombre de cuenta externa\> \<nombre de la aplicación\>**.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [SSO iniciado por host](../core/host-initiated-sso.md)