---
title: Cómo actualizar la configuración de utilidad de administración de BAM tras realizar una copia de seguridad y restaurar | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7b27062b-546f-4030-983b-15d793912690
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa7d8e91ab82cc74f2af2ca0c12f79cdb0a8fcbe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970085"
---
# <a name="how-to-update-the-bam-management-utility-configuration-after-a-backup-and-restore"></a>Cómo actualizar la configuración de la utilidad de administración de BAM tras realizar una copia de seguridad y restaurar
Cuando la combinación de nombre de servidor\base de datos cambia debido a un cambio en el entorno de BizTalk Server, como en la copia de seguridad y la secuencia de restauración, debe actualizar el archivo de configuración de la utilidad de administración de BAM (bm.exe.config) para reflejar estos cambios de nombres.  
  
### <a name="to-update-the-bam-management-configuration-file-a-after-backup-and-restore"></a>Para actualizar el archivo de configuración de la administración de BAM tras realizar una copia de seguridad y restaurar  
  
1. Abra el archivo bm.exe.config con el Bloc de notas haciendo **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config y, a continuación, haga clic en **Aceptar**.  
  
2. Localice la sección appSettings en el archivo y cambie los siguientes valores:  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="oldServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
3. en  
  
   ```  
   <!-- Default server and database for bm.exe. -->  
   <add key="DefaultServer" value="newServerName" />  
   <add key="DefaultDatabase" value="BAMPrimaryImport" />  
   ```  
  
4. Guarde el archivo.  
  
## <a name="see-also"></a>Vea también  
 [Administración de bases de datos de BAM](../core/managing-bam-databases.md)