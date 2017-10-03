---
title: "Trabajar con el archivo de definición de actividad de seguimiento | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tracking, activity definition file
- activity definition file
- activity definition file, about activity definition file
- tracking, managing views
- activity definition file, activity fields
ms.assetid: 0592a844-aad7-4054-b1e7-344f1086f0b1
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 751b05f28682ecc0a0230fc924cf706d0531784d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="working-with-the-tracking-activity-definition-file"></a>Trabajar con el archivo de definición de actividad de seguimiento
El archivo de definición de actividad contiene información acerca del seguimiento de la actividades de proceso y el mensaje en [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]usa este archivo para administrar los datos de seguimiento de BizTalk actividad supervisión económica (BAM). El archivo de definición es un archivo XML (Tracking.xml) que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] el programa de instalación instala en el \< *unidad*>: \Program Acelerador de BizTalk 2013 para RosettaNet \BAMTracking carpeta. Las actividades definidas en Tracking.xml pueden ser suficientes para sus fines.  
  
 Para obtener más información sobre el seguimiento de actividades, vistas y tablas, consulte [mejorada de seguimiento](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md). Para obtener más información acerca de BAM, vea "actividad supervisión económica (BAM)" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
## <a name="managing-tracking-views"></a>Administrar vistas de seguimiento  
 No utilice el Editor de perfiles de seguimiento de BizTalk con [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] de seguimiento. Los puntos de seguimiento no son personalizables; No cambie las definiciones de actividad. Sin embargo, puede administrar la implementación y vistas de BAM. Para ello, modifique un [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] (Tracking.xls) de la hoja de cálculo que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] el programa de instalación instala en el \< *unidad*>: \Program BizTalk 2013 Accelerator para RosettaNet\BAMTracking carpeta. Para obtener más información, vea "Administrar seguimiento vistas" a continuación.  
  
 Si las vistas definidas en Tracking.xml no son suficientes para satisfacer sus necesidades, puede definir vistas diferentes de la información de seguimiento en BAM como se indica a continuación.  
  
#### <a name="to-create-different-tracking-views"></a>Para crear vistas de seguimiento diferente  
  
1.  Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**. Escriba **cmd** en el cuadro de texto Abrir del cuadro de diálogo Ejecutar y, a continuación, haga clic en **Aceptar**. En el cuadro de diálogo de línea de comandos, escriba el código siguiente para anular la implementación de tracking.xml, a continuación, haga clic en **Aceptar**:  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
    bm remove-all  -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking\<filename>.xml"  
    ```  
  
2.  En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] el explorador, vaya a  *\<unidad >*: \Program BizTalk 2013 Accelerator for RosettaNet \BAM de seguimiento. Haga doble clic en Tracking.xls.  
  
3.  Crear una nueva vista de supervisión de la actividad de negocio. Para obtener información acerca de cómo hacerlo, vea "Administrar Business Activity Monitoring" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
4.  Haga clic en **BAM**y, a continuación, haga clic en **exportar XML**. Mover a la ubicación deseada, escriba un nombre de archivo (que no sean Tracking.xml) y, a continuación, haga clic en **guardar**.  
  
    > [!IMPORTANT]
    >  Al definir nuevas vistas de seguimiento en un archivo XLS de seguimiento y exportar un archivo XML desde el archivo XLS de seguimiento, algunos de los nuevos nombres de campo pueden modificarse ligeramente. Corregir esto, compruebe los campos en su archivo XML con el campo de tracking.xml estándar que se instala el programa de instalación de BTARN de seguimiento.  
  
5.  Implementar el nuevo archivo XML de seguimiento. Para ello, haga clic en **iniciar**y, a continuación, haga clic en **ejecutar**. Escriba **cmd** en el cuadro de texto Abrir del cuadro de diálogo Ejecutar y, a continuación, haga clic en **Aceptar**. En el cuadro de diálogo de línea de comandos, escriba el código siguiente para implementar el nuevo archivo de seguimiento, a continuación, haga clic en **Aceptar**. Se recomienda cambiar el nombre del archivo XML de seguimiento para que no sobrescribe el archivo de tracking.xml predeterminado.  
  
    ```  
    cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
    bm.exe deploy-all -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2030 Accelerator for RosettaNet\BAMTracking\<filename>.xml"  
    ```  
  
 La información de seguimiento en BAM no incluye el contenido del mensaje, ya que se almacena en un [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] base de datos.  
  
 Puede administrar la implementación de seguimiento mediante el uso de los negocios actividad supervisión de utilidad de administración de BAM. Para obtener más información acerca de esta utilidad, vea "Mediante el negocio actividad supervisión de administración la utilidad" en [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
## <a name="activity-fields"></a>Campos de actividad  
 Los campos de la actividad de mensaje en el archivo de definición de actividad son los siguientes:  
  
-   ActivityName  
  
-   Categoría  
  
-   ContentKey  
  
-   DestinationPartyName  
  
-   ErrorDescription  
  
-   HasError  
  
-   InReplyToMessageID  
  
-   IsReceived  
  
-   MessageTrackingID  
  
-   NoFPipInstance  
  
-   PipCode  
  
-   PipInstanceID  
  
-   PiPVersion  
  
-   SourcePartName  
  
-   Timestamp  
  
 Los campos de la actividad del proceso en el archivo de definición de actividad son los siguientes:  
  
-   EndTime  
  
-   InitiatorPartyName  
  
-   IsInitiatorRole  
  
-   PipCode  
  
-   PipInstanceID  
  
-   PipName  
  
-   PipVersion  
  
-   ResponderPartyName  
  
-   StartTime  
  
-   Estado  
  
## <a name="see-also"></a>Vea también  
 [Seguimiento mejorado](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)   
 [Administrar la configuración, certificados, las bases de datos y seguridad](manage-configuration-certificates-databases-security.md)