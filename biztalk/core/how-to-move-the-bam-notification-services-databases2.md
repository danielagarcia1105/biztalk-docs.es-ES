---
title: Cómo mover la notificación de BAM servicios Databases2 | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Notification Services Application database [BAM]
- Notification Services Instance database [BAM]
- migrating, Notification Services database [BAM]
ms.assetid: 4b7f3397-65c9-4c71-8374-8764f4c2e2e3
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 639a326878cd425a951581711c08a0a53127035b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254268"
---
# <a name="how-to-move-the-bam-notification-services-databases"></a>Cómo mover las bases de datos de servicios de notificación de BAM
Este procedimiento se puede utilizar para mover las bases de datos de servicios de notificación de BAM a otro servidor.  
  
> [!NOTE]
>  Es preciso mover conjuntamente la base de datos de la aplicación de servicios de notificación de BAM (BAMAlertsApplication) y la base de datos de instancias de servicios de notificación de BAM (BAMAlertsNSMain).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Para llevar a cabo este procedimiento, debe haber iniciado sesión con una cuenta que sea miembro de la función fija de servidor sysadmin de SQL Server.  
  
### <a name="to-move-the-bam-notification-services-databases"></a>Para mover las bases de datos de servicios de notificación de BAM  
  
1.  Obtenga una copia del archivo .xml utilizado para restaurar BAM:  
  
    1.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
    2.  En el símbolo del sistema, desplácese al directorio siguiente:  
  
         **%SystemDrive%\Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**   
  
    3.  En el símbolo del sistema, escriba:  
  
        ```  
        Bm.exe get-config –filename:BAMConfiguration.xml  
        ```  
  
        > [!NOTE]
        >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
2.  En el símbolo del sistema, escriba:  
  
    ```  
    Net stop NS$BamAlerts  
    ```  
  
3.  Siga las instrucciones en libros en pantalla de SQL Server realizar la copia de seguridad de la base de datos en el servidor anterior.  
  
4.  Copie las bases de datos de servicios de notificación de BAM en el nuevo servidor SQL.  
  
5.  Siga las instrucciones en Libros en pantalla de SQL Server para la creación de una copia de seguridad de una base de datos en el servidor nuevo.  
  
6.  Edite el archivo BAMConfiguration.xml y cambie el valor de ServerName en la sección Alert DeploymentUnit al nombre del nuevo servidor.  
  
7.  Guarde el archivo BAMConfiguration.xml y ciérrelo.  
  
8.  Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
9. En el símbolo del sistema, desplácese al directorio siguiente:  
  
     **%SystemDrive%\Program Files\Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **\Tracking**   
  
10. En el símbolo del sistema, escriba:  
  
    ```  
    bm.exe update-config -FileName:BAMConfiguration.xml  
    ```  
  
    > [!NOTE]
    >  En un sistema que admita el Control de cuentas de usuario (UAC), es posible que deba ejecutar la herramienta con privilegios administrativos.  
  
11. Actualice las referencias a las bases de datos de servicios de notificación de BAM. Para obtener más información, consulte [cómo actualizar referencias a las bases de datos de servicios de notificación de BAM](../core/how-to-update-references-to-the-bam-notification-services-databases.md).  
  
## <a name="see-also"></a>Vea también  
 [Mover bases de datos de servidor BizTalk Server](../core/moving-biztalk-server-databases.md)