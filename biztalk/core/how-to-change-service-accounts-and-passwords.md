---
title: "Cómo cambiar contraseñas y cuentas de servicio | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dff53d6b-c262-4b66-b822-1c61f54ae105
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77ce9dc143765f9db49c5880da4fa4202e26c0f3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-service-accounts-and-passwords"></a>Cómo cambiar contraseñas y cuentas de servicio
Por lo general, tras configurar BizTalk Server, las organizaciones requieren cambiar las contraseñas o las cuentas de servicio mediante directivas de cuentas, como la directiva de contraseñas o la de bloqueo de cuentas. Para obtener más información acerca de las directivas de cuenta, vea el sitio Web de Microsoft TechNet en [http://go.microsoft.com/fwlink/?LinkId=62172](http://go.microsoft.com/fwlink/?LinkId=62172).  
  
 Al cambiar contraseñas o cuentas de servicio, debe hacer lo siguiente:  
  
1.  Crear una cuenta nueva de servicio o cambiar la contraseña de cuentas existentes.  
  
2.  Asegurarse de que la cuenta de servicio sea miembro de los grupos de Windows necesarios. Para obtener información acerca de los grupos de dominio o local a la que debe agregar la cuenta de servicio, consulte [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).  
  
    > [!NOTE]
    >  En un entorno de grupo de dominio, utilice la consola Usuarios y equipos de Active Directory. En un entorno de grupo local, utilice la consola Administración de equipos.  
  
3.  Lleve a cabo las siguientes tareas en función del tipo de cuenta de servicio.  
  
    |Cuenta o servicio|Cómo cambiar cuentas de usuario|Tareas necesarias después de cambiar cuentas de usuario|Cómo cambiar contraseñas|Tareas necesarias después de cambiar contraseñas|  
    |------------------------|---------------------------------|-------------------------------------------------|-----------------------------|---------------------------------------------|  
    |Servicio de inicio de sesión único empresarial en el servidor secreto principal|1.  Asegúrese de que ha realizado una copia de seguridad del secreto principal. Para obtener más información, consulte [cómo volver la seguridad del secreto principal](../core/how-to-back-up-the-master-secret.md).<br />2.  Cambie la cuenta de servicio mediante la consola Servicios.<br />3.  Restaure el secreto principal. Para obtener más información, consulte [cómo restaurar el secreto principal](../core/how-to-restore-the-master-secret.md).|Reinicie el servicio.|Cambie la contraseña de la cuenta mediante la consola Servicios.|Reinicie el servicio.|  
    |Servicio de inicio de sesión único (SSO) empresarial|Cambie la cuenta de servicio mediante la consola Servicios.|Reinicie el servicio.|Cambie la contraseña de la cuenta mediante la consola Servicios.|Reinicie el servicio.|  
    |Instancia de Host de BizTalk|Cambie la cuenta de servicio mediante la consola de administración de BizTalk Server.|Reinicie la instancia de host de BizTalk.|Cambie la contraseña de la cuenta mediante la consola Servicios o la consola de administración de BizTalk Server.|Reinicie la instancia de host de BizTalk.|  
    |Instancia de host aislado de BizTalk y el grupo de aplicaciones correspondiente que aloja el adaptador de recepción SOAP|1.  Cambie la cuenta de servicio mediante la consola de administración de BizTalk Server.<br />2.  Cambiar la cuenta del grupo de aplicaciones mediante la consola de administración de IIS **Nota:** la cuenta de servicio para el grupo de aplicaciones debe coincidir con la cuenta de servicio para un host aislado correspondiente.|1.  Cambie la cuenta de servicio del grupo de aplicaciones correspondiente mediante la consola de administración de IIS.<br />2.  Reinicie el grupo de aplicaciones mediante la consola de administración de IIS.|Cambie la contraseña de la cuenta bajo la que se ejecuta el grupo de aplicaciones. mediante la consola de administración de IIS **Nota:** no es necesario cambiar la contraseña en la consola de administración de BizTalk Server después de cambiar la contraseña.|1.  Cambie la contraseña de la cuenta en la que se ejecuta el grupo de aplicaciones correspondiente mediante la consola de administración de IIS.<br />2.  Reinicie el grupo de aplicaciones mediante la consola de administración de IIS.|  
    |Servicio de actualización de motor de reglas|Cambie la cuenta de servicio mediante la consola Servicios o Administrador de configuración.<br /><br /> El Administrador de configuración reinicia el servicio automáticamente.|Si utiliza la consola de servicios, debe reiniciar manualmente el servicio.|Cambie la contraseña de la cuenta mediante la consola Servicios o Administrador de configuración.<br /><br /> El Administrador de configuración reinicia el servicio automáticamente.|Si utiliza la consola Servicios, debe reiniciar el servicio manualmente.|  
    |Servicio de notificación de BAM|1.  Agregue la cuenta nueva al servidor SQL en el que se instaló el servicio de notificación de BAM.<br />2.  Conceda los privilegios a la cuenta nueva. Para obtener más información acerca de los privilegios necesarios, vea [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md)<br />3.  Cambie la cuenta de servicio mediante la consola Servicios.|Reinicie el servicio.|Cambiar la contraseña de la cuenta mediante la consola de servicios|Reinicie el servicio.|  
    |Servicio Web de administración de BAM|1.  Agregue la nueva cuenta para el servidor SQL server apropiado y conceda los privilegios en [grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md).<br />2.  Cambie la cuenta de usuario mediante el Administrador de configuración.||Cambie la contraseña de la cuenta de usuario mediante el Administrador de configuración.||  
    |Grupo de aplicaciones de BAM|Cambie la cuenta de servicio del grupo de aplicaciones mediante la consola Administrador de configuración.<br /><br /> El Administrador de configuración recicla el grupo de aplicaciones automáticamente.||Cambie la contraseña de la cuenta mediante el Administrador de configuración.<br /><br /> El Administrador de configuración recicla el grupo de aplicaciones automáticamente.||  
  
 El procedimiento siguiente describe cómo cambiar contraseñas y cuentas de servicio mediante el Administrador de configuración.  
  
### <a name="to-change-service-accounts-and-passwords-using-configuration-manager"></a>Para cambiar contraseñas y cuentas de servicio mediante el Administrador de configuración  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]y, a continuación, haga clic en **configuración de BizTalk Server**.  
  
2.  En el **configuración de Microsoft BizTalk Server**, haga clic en **vista**, haga clic en **las cuentas de servicio**y, a continuación, cambiar las cuentas de servicio y las contraseñas en el  **Las cuentas de servicio** cuadro de diálogo. Para obtener más información acerca de Configuration Manager, consulte [importar y exportar la configuración de BizTalk Server](../install-and-config-guides/import-and-export-biztalk-server-configuration.md).  
  
    > [!NOTE]
    >  El Administrador de configuración no proporciona un lugar centralizado para llevar el control de varios equipos. Si instala Microsoft BizTalk Server en varios equipos, debe cambiar las cuentas de servicio y las contraseñas en cada equipo en tiempo de ejecución.  
  
## <a name="see-also"></a>Vea también  
 [Grupos de Windows y cuentas de usuario en BizTalk Server](../core/windows-groups-and-user-accounts-in-biztalk-server.md)   
 [Configuración de BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)   
 [Administrar la seguridad de servidor BizTalk Server](../core/managing-biztalk-server-security.md)   
 [Prácticas recomendadas para administrar las cuentas de usuario y grupos de Windows](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)   
 [Administración de Hosts y las cuentas de servicio](../core/managing-hosts-and-service-accounts.md)