---
title: Cómo actualizar los equipos en tiempo de ejecución | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 576a7065-04b6-436c-acf9-28c8d6e40107
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fff5c5ec4c965b9dbdaaf5d876ca0943a32be96
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36993301"
---
# <a name="how-to-update-the-runtime-computers"></a>Cómo actualizar los equipos en tiempo de ejecución
El sistema de destino [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en tiempo de ejecución están configurados con la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Asistente de configuración como parte del grupo de BizTalk de producción que se ejecutan en el entorno de producción. Cuando se restaura el grupo de BizTalk de producción en el entorno de recuperación ante desastres, se debe actualizar la configuración en cada [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipo de tiempo de ejecución para que apunte a la recuperación ante desastres [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] instancias cuando intenta conectarse a los datos restaurados grupo de BizTalk de producción. Después de restaura el grupo de BizTalk en el sistema de destino, use el procedimiento siguiente para actualizar la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en tiempo de ejecución.  
  
### <a name="to-update-the-biztalk-server-runtime-computers"></a>Para actualizar los equipos en tiempo de ejecución de BizTalk Server  
  
1. Copie el archivo SampleUpdateInfo.xml editado en el directorio de BizTalk Server\Schema\Restore en cada servidor BizTalk server de 32 bits \Program Files\Microsoft o en el directorio \Program archivos (x86) \Microsoft BizTalk Server\Bins32\Schema\Restore cada BizTalk de 64 bits servidor en el sistema de destino.  
  
2. En cada servidor BizTalk server, abra un símbolo del sistema. Haga clic en **Inicio**, **Ejecutar…** y escriba **cmd**. Finalmente, haga clic en **Aceptar**.  
  
   > [!NOTE]  
   >  En los equipos de 64 bits, debe abrir un símbolo del sistema de 64 bits.  
  
3. En la línea de comandos, vaya a \Program Files\Microsoft BizTalk Server\Schema\Restore (en equipos de 32 bits) o a \Program archivos (x86) \Microsoft BizTalk Server\Bins32\Schema\Restore (en equipos de 64 bits) y escriba este comando:  
  
   ```  
   cscript UpdateRegistry.vbs SampleUpdateInfo.xml  
   ```  
  
4. Habilitar y reiniciar todas las instancias de Host de BizTalk y todos los demás servicios de BizTalk en los servidores de BizTalk en el sistema de destino.  
  
5. Reinicie WMI en cada servidor BizTalk server en el sistema de destino. Haga clic en **iniciar**, haga clic en **ejecutar**, tipo **services.msc**y, a continuación, haga clic en **Aceptar**. En el **servicios** MMC complemento, contextual **Instrumental de administración de Windows** y seleccione **reiniciar**.  
  
6. En cada servidor BizTalk server, abra el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **grupo de BizTalk**y, a continuación, seleccione **quitar**.  
  
7. Haga clic en **administración de BizTalk Server 2010**, seleccione **conectar a grupo existente**, seleccione la instancia de base de datos de SQL Server y el nombre que corresponde a la base de datos de administración de BizTalk para la base de datos el grupo de BizTalk y, a continuación, haga clic en **Aceptar**.  
  
   > [!NOTE]
   >  Después de actualizar el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en tiempo de ejecución, es posible que también deberá actualizar el **nombre del servidor de SSO** tal como se muestra en el **propiedades del grupo** disponibles en el cuadro de diálogo el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Consola de administración. Para actualizar el **nombre del servidor de SSO**, inicie el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic para expandir [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administración, haga clic en el **grupo de BizTalk** nodo y seleccione **Propiedades** para mostrar el **General** pestaña de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. A continuación, en el **nombre del servidor de SSO** cuadro de texto, escriba el nombre del servidor Enterprise Single Sign-On que utilizará este equipo para tener acceso a la información de configuración para los adaptadores y haga clic en **Aceptar**. Éste es el nombre del servidor de SSO utilizado para establecer la conexión con la base de datos de SSO.  
  
8. Reinicie los siguientes servicios de Windows en cada servidor en tiempo de ejecución de BizTalk server:  
  
   -   Servicio de inicio de sesión único empresarial  
  
   -   Servicio de actualización de motor de reglas  
  
   -   Instancias de Host de BizTalk  
  
## <a name="see-also"></a>Vea también  
 [Recuperación de los equipos en tiempo de ejecución](../technical-guides/recovering-the-runtime-computers.md)