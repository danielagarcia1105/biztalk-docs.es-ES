---
title: "Cómo actualizar los equipos en tiempo de ejecución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 576a7065-04b6-436c-acf9-28c8d6e40107
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ca8edb4da6b59c33f87100ee3669bb2472d4350c
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-update-the-runtime-computers"></a>Cómo actualizar los equipos en tiempo de ejecución
El sistema de destino [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en tiempo de ejecución se configuran con el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Asistente de configuración como parte del grupo de BizTalk de producción ejecutan en el entorno de producción. Cuando se restaura el grupo de BizTalk de producción en el entorno de recuperación ante desastres, se debe actualizar la configuración en cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo de tiempo de ejecución para que apunte a la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias cuando intenta conectarse a la restaurada grupo de BizTalk de producción. Después de restaura el grupo de BizTalk en el sistema de destino, utilice el procedimiento siguiente para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en tiempo de ejecución.  
  
### <a name="to-update-the-biztalk-server-runtime-computers"></a>Para actualizar los equipos de tiempo de ejecución de BizTalk Server  
  
1.  Copie el archivo SampleUpdateInfo.xml editado en el directorio de BizTalk Server\Schema\Restore en cada servidor de BizTalk de 32 bits \Program o en el directorio \Program archivos (x86) \Microsoft BizTalk Server\Bins32\Schema\Restore cada BizTalk de 64 bits servidor en el sistema de destino.  
  
2.  En cada servidor BizTalk server, abra un símbolo del sistema. Haga clic en **Inicio**, **Ejecutar…**y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
    > [!NOTE]  
    >  En los equipos de 64 bits, debe abrir un símbolo del sistema de 64 bits.  
  
3.  En la línea de comandos, desplácese a \Program BizTalk Server\Schema\Restore (en equipos de 32 bits) o a \Program archivos (x86) \Microsoft BizTalk Server\Bins32\Schema\Restore (en equipos de 64 bits) y escriba el siguiente comando:  
  
    ```  
    cscript UpdateRegistry.vbs SampleUpdateInfo.xml  
    ```  
  
4.  Habilitar y reiniciar todas las instancias de Host de BizTalk y todos los demás servicios de BizTalk en los servidores de BizTalk en el sistema de destino.  
  
5.  Reinicie WMI en cada servidor de BizTalk en el sistema de destino. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **services.msc**y, a continuación, haga clic en **Aceptar**. En el **servicios** MMC complemento, contextual **Windows Management Instrumentation** y seleccione **reiniciar**.  
  
6.  En cada servidor BizTalk server, abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **grupo de BizTalk**y, a continuación, seleccione **quitar**.  
  
7.  Haga clic en **administración de BizTalk Server 2010**, seleccione **conectar a grupo existente**, seleccione la instancia de base de datos de SQL Server y el nombre que corresponde a la base de datos de administración de BizTalk para la base de datos el grupo de BizTalk y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]  
    >  Después de actualizar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en tiempo de ejecución, también debe actualizar el **nombre del servidor de SSO** como se muestra en el **propiedades del grupo de** disponibles en el cuadro de diálogo el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Consola de administración. Para actualizar la **nombre del servidor de SSO**, inicie la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic para expandir [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración, haga clic en el **grupo de BizTalk** nodo y seleccione **Propiedades** para mostrar la **General** pestaña de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. A continuación, en la **nombre del servidor de SSO** cuadro de texto, escriba el nombre del servidor Enterprise Single Sign-On que utilizará este equipo para tener acceso a la información de configuración para los adaptadores y haga clic en **Aceptar**. Éste es el nombre del servidor de SSO utilizado para establecer la conexión con la base de datos de SSO.  
  
8.  Reinicie los siguientes servicios de Windows en cada servidor de tiempo de ejecución de BizTalk server:  
  
    -   Servicio SSO empresarial  
  
    -   Servicio de actualización de motor de reglas  
  
    -   Instancias de Host de BizTalk  
  
## <a name="see-also"></a>Vea también  
 [Recuperación de los equipos en tiempo de ejecución](../technical-guides/recovering-the-runtime-computers.md)