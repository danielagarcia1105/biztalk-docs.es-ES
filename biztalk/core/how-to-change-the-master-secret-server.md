---
title: "Cómo cambiar el servidor secreto principal | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, promoting
- managing [Master Secret server], promoting servers
- managing [SSO], promoting servers
- SSO, Master Secret server
- modifying, Master Secret server
- Master Secret server, changing
ms.assetid: 44a786ca-4645-44a8-b33e-d0019f0aeca9
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4676db07025b4395d58df7c24252769ba65ecfb4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-master-secret-server"></a>Cómo cambiar el servidor secreto principal
Después de configurar el servidor secreto principal y la base de datos de SSO, podrá cambiar el servidor secreto principal siempre que el original haya fallado y no pueda recuperarse. Para cambiar el servidor secreto principal, deberá promover un servidor de SSO para convertirlo en servidor secreto principal.  
  
### <a name="to-change-the-master-secret-server-using-the-mmc-snap-in"></a>Para cambiar el servidor secreto principal utilizando el Complemento MMC  
  
1.  En el **iniciar** menú, haga clic en **todos los programas**, haga clic en **Microsoft Enterprise Single Sign-On**y, a continuación, haga clic en **administración de SSO**.  
  
2.  En el panel de ámbito, haga clic en **System**y, a continuación, haga clic en **propiedades**. El maestro de servidor secreto se muestra en el **General** pestaña de la **propiedades del sistema** cuadro de diálogo.  
  
3.  Haga clic en **cambio** para seleccionar un nuevo patrón servidor secreto.  
  
    > [!IMPORTANT]
    >  Cuando se utiliza el complemento MMC para cambiar el servidor secreto principal, la operación debe llevarse a cabo en éste. No es posible cambiar el servidor secreto principal que utiliza el complemento de MMC desde un equipo que no sea el servidor secreto principal.  
  
4.  Inicie sesión en el nuevo servidor secreto principal para restaurar el secreto principal en el Registro del nuevo servidor secreto principal.  
  
5.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
6.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
7.  Reinicie el nuevo servidor secreto principal.  
  
8.  Tipo de **ssoconfig – restoreSecret \<Restaurar archivo >**, donde  **\<Restaurar archivo >** es la ruta de acceso y nombre del archivo donde se almacena el secreto principal.  
  
     El secreto principal se almacena en el Registro en la siguiente ubicación:  
  
     HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\ENTSSO\SSOSS  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
### <a name="to-promote-a-single-sign-on-server-to-master-secret-server-using-the-command-line"></a>Para promover un servidor de SSO a servidor secreto principal utilizando la línea de comandos  
  
1.  Cree un archivo XML que incluya el nombre del servidor de SSO que desea promover a servidor secreto principal. Por ejemplo,  
  
    ```  
    <sso>  
      <globalInfo>  
         <secretServer>SSO Server name</secretServer>  
      </globalInfo>  
    </sso>  
    ```  
  
    > [!IMPORTANT]
    >  Para cambiar el servidor secreto principal desde un equipo que no sea este servidor, asegúrese de que el archivo XML especificado contenga únicamente el nombre del servidor secreto principal. En concreto, no debe contener la etiqueta XML de los administradores de SSO o **ssomanage - updatedb** se producirá un error en la operación.  
  
2.  En el **iniciar** menú, haga clic en **ejecutar**y, a continuación, escriba **cmd**.  
  
3.  En el símbolo del sistema, vaya al directorio de instalación de inicio de sesión único empresarial. El directorio de instalación predeterminado es  *\<unidad >*: \Program Files\Common Files\Enterprise Single Sign-On.  
  
4.  Tipo de **ssomanage-updatedb** \< **archivo de actualización**>, donde \< **archivo de actualización**> es el nombre del archivo XML se crea en el paso 1.  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
5.  Reinicie el servidor secreto principal.  
  
6.  Tipo de **ssoconfig – restoresecret \<Restaurar archivo >**, donde  **\<Restaurar archivo >** es la ruta de acceso y nombre del archivo donde se almacena el secreto principal.  
  
     El secreto principal se almacena en el Registro en la siguiente ubicación:  
  
     HKEY_LOCAL_MACHINESOFTWAREMicrosoftENTSSOSSOSS  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
## <a name="see-also"></a>Vea también  
 [Servidor secreto principal](../core/master-secret-server.md)   
 [Cómo agrupar el servidor secreto principal](../core/how-to-cluster-the-master-secret-server1.md)   
 [Cómo actualizar la base de datos SSO](../core/how-to-update-the-sso-database.md)   
 [Uso de SSO](../core/using-sso.md)