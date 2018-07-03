---
title: Trabajar con el archivo de definición de actividad de seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- tracking, activity definition file
- activity definition file
- activity definition file, about activity definition file
- tracking, managing views
- activity definition file, activity fields
ms.assetid: 0592a844-aad7-4054-b1e7-344f1086f0b1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0be795daa7e08707c113d8230dc8d324bc71f951
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991917"
---
# <a name="working-with-the-tracking-activity-definition-file"></a>Trabajar con el archivo de definición de actividad de seguimiento
El archivo de definición de actividad contiene información sobre el seguimiento de las actividades de proceso y el mensaje en Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]. [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Este archivo se usa para administrar los datos de seguimiento de BizTalk actividad de supervisión económica (BAM). El archivo de definición es un archivo XML (Tracking.xml) que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala en el \< *unidad*\>: \Program Files\Microsoft Acelerador de BizTalk 2013 para RosettaNet \BAMTracking carpeta. Las actividades definidas en Tracking.xml pueden ser suficientes para sus fines.  
  
 Para obtener más información sobre el seguimiento de actividades, vistas y tablas, consulte [mejorada de seguimiento](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md). Para obtener más información acerca de SAE, vea "actividad de supervisión económica (BAM)" en la Ayuda de BizTalk Server.  
  
## <a name="managing-tracking-views"></a>Administrar vistas de seguimiento  
 No utilice el Editor de perfiles de seguimiento de BizTalk con [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] de seguimiento. Los puntos de seguimiento no son personalizables; No cambie las definiciones de actividad. Sin embargo, puede administrar la implementación y las vistas BAM. Para ello, modifica un [!INCLUDE[btsExcel](../../includes/btsexcel-md.md)] (Tracking.xls) de la hoja de cálculo que [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] programa de instalación instala en el \< *unidad*\>: \Program Files\Microsoft BizTalk 2013 Accelerator for menú Carpeta BAMTracking. Para obtener más información, consulte "Administración de seguimiento vistas" a continuación.  
  
 Si las vistas definidas en Tracking.xml no son suficientes para satisfacer sus necesidades, puede definir vistas diferentes de la información de seguimiento en BAM, como se indica a continuación.  
  
#### <a name="to-create-different-tracking-views"></a>Para crear vistas de seguimiento diferente  
  
1. Haga clic en **Inicio**y, a continuación, haga clic en **Ejecutar**. Escriba **cmd** en el cuadro de texto Abrir del cuadro de diálogo Ejecutar y, a continuación, haga clic en **Aceptar**. En el cuadro de diálogo de línea de comandos, escriba el código siguiente para anular la implementación de tracking.xml, a continuación, haga clic en **Aceptar**:  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm remove-all  -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2013 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
2. En [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Explorer, desplácese a  *\<unidad\>*: \Program Files\Microsoft BizTalk 2013 Accelerator for RosettaNet \BAM de seguimiento. Haga doble clic en Tracking.xls.  
  
3. Crear una nueva vista en la actividad económica. Para obtener información acerca de cómo hacerlo, consulte "Administración de la actividad económica" en la Ayuda de BizTalk Server.  
  
4. Haga clic en **BAM**y, a continuación, haga clic en **exportar XML**. Mover a la ubicación deseada, escriba un nombre de archivo (que no sea Tracking.xml) y, a continuación, haga clic en **guardar**.  
  
   > [!IMPORTANT]
   >  Al definir nuevas vistas de seguimiento en un archivo XLS de seguimiento y exportar un archivo XML desde el archivo XLS de seguimiento, algunos de los nuevos nombres de campo pueden modificarse ligeramente. Corregir este problema mediante la comprobación de los campos en su personalizados de seguimiento de archivos XML en el campo tracking.xml estándar instalado el programa de instalación de BTARN.  
  
5. Implementar el nuevo archivo XML de seguimiento. Para ello, haga clic en **iniciar**y, a continuación, haga clic en **ejecutar**. Escriba **cmd** en el cuadro de texto Abrir del cuadro de diálogo Ejecutar y, a continuación, haga clic en **Aceptar**. En el cuadro de diálogo de línea de comandos, escriba el código siguiente para implementar el nuevo archivo de seguimiento, a continuación, haga clic en **Aceptar**. Se recomienda cambiar el nombre del archivo XML de seguimiento para que no sobrescriba el archivo de tracking.xml predeterminado.  
  
   ```  
   cd %ProgramFiles%\Microsoft BizTalk Server 2013\Tracking  
   bm.exe deploy-all -DefinitionFile:"%ProgramFiles%\Microsoft BizTalk 2030 Accelerator for RosettaNet\BAMTracking\<filename\>.xml"  
   ```  
  
   La información de seguimiento en BAM no incluye el contenido del mensaje, ya que se almacena en un [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] base de datos.  
  
   Puede administrar la implementación de seguimiento mediante el uso de la empresa actividad supervisión de utilidad de administración de BAM. Para obtener más información acerca de esta utilidad, vea "Utilizando el negocio actividad supervisión de utilidad de administración" en la Ayuda de BizTalk Server.  
  
## <a name="activity-fields"></a>Campos de actividad  
 Los campos de la actividad de mensaje en el archivo de definición de actividad son los siguientes:  
  
- ActivityName  
  
- Categoría  
  
- ContentKey  
  
- DestinationPartyName  
  
- ErrorDescription  
  
- HasError  
  
- InReplyToMessageID  
  
- IsReceived  
  
- MessageTrackingID  
  
- NoFPipInstance  
  
- PipCode  
  
- PipInstanceID  
  
- PiPVersion  
  
- SourcePartName  
  
- Timestamp  
  
  Los campos de la actividad del proceso en el archivo de definición de actividad son los siguientes:  
  
- EndTime  
  
- InitiatorPartyName  
  
- IsInitiatorRole  
  
- PipCode  
  
- PipInstanceID  
  
- PipName  
  
- PipVersion  
  
- ResponderPartyName  
  
- StartTime  
  
- Estado  
  
## <a name="see-also"></a>Vea también  
 [Seguimiento mejorado](../../adapters-and-accelerators/accelerator-rosettanet/enhanced-tracking.md)   
 [Administrar la configuración, certificados, bases de datos y seguridad](manage-configuration-certificates-databases-security.md)