---
title: Cómo actualizar la configuración de utilidad de administración de BAM después de una copia de seguridad y restauración | Documentos de Microsoft
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
ms.openlocfilehash: cf316e7275b3db47b02a7f09ed5d2a66571c4de1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286676"
---
# <a name="how-to-update-the-bam-management-utility-configuration-after-a-backup-and-restore"></a>Cómo actualizar la configuración de la utilidad de administración de BAM tras realizar una copia de seguridad y restaurar
Cuando la combinación de nombre de servidor\base de datos cambia debido a un cambio en el entorno de BizTalk Server, como en la copia de seguridad y la secuencia de restauración, debe actualizar el archivo de configuración de la utilidad de administración de BAM (bm.exe.config) para reflejar estos cambios de nombres.  
  
### <a name="to-update-the-bam-management-configuration-file-a-after-backup-and-restore"></a>Para actualizar el archivo de configuración de la administración de BAM tras realizar una copia de seguridad y restaurar  
  
1.  Abra el archivo bm.exe.config con el Bloc de notas haciendo clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config y, a continuación, haga clic en **Aceptar**.  
  
2.  Localice la sección appSettings en el archivo y cambie los siguientes valores:  
  
    ```  
    <!-- Default server and database for bm.exe. -->  
    <add key="DefaultServer" value="oldServerName" />  
    <add key="DefaultDatabase" value="BAMPrimaryImport" />  
    ```  
  
3.  en  
  
    ```  
    <!-- Default server and database for bm.exe. -->  
    <add key="DefaultServer" value="newServerName" />  
    <add key="DefaultDatabase" value="BAMPrimaryImport" />  
    ```  
  
4.  Guarde el archivo.  
  
## <a name="see-also"></a>Vea también  
 [Administrar bases de datos BAM](../core/managing-bam-databases.md)