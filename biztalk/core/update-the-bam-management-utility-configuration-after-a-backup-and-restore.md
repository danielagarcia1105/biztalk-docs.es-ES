---
title: "Cómo actualizar la configuración de utilidad de administración de BAM después de una copia de seguridad y restauración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7b27062b-546f-4030-983b-15d793912690
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf316e7275b3db47b02a7f09ed5d2a66571c4de1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-update-the-bam-management-utility-configuration-after-a-backup-and-restore"></a><span data-ttu-id="14864-102">Cómo actualizar la configuración de la utilidad de administración de BAM tras realizar una copia de seguridad y restaurar</span><span class="sxs-lookup"><span data-stu-id="14864-102">How to Update the BAM Management Utility Configuration After a Backup and Restore</span></span>
<span data-ttu-id="14864-103">Cuando la combinación de nombre de servidor\base de datos cambia debido a un cambio en el entorno de BizTalk Server, como en la copia de seguridad y la secuencia de restauración, debe actualizar el archivo de configuración de la utilidad de administración de BAM (bm.exe.config) para reflejar estos cambios de nombres.</span><span class="sxs-lookup"><span data-stu-id="14864-103">When the server\database name combination changes as the result of a change in your BizTalk Server environment such as a backup and restore sequence, you must update the BAM management utility configuration file (bm.exe.config) to reflect these name changes.</span></span>  
  
### <a name="to-update-the-bam-management-configuration-file-a-after-backup-and-restore"></a><span data-ttu-id="14864-104">Para actualizar el archivo de configuración de la administración de BAM tras realizar una copia de seguridad y restaurar</span><span class="sxs-lookup"><span data-stu-id="14864-104">To update the BAM management configuration file a after backup and restore</span></span>  
  
1.  <span data-ttu-id="14864-105">Abra el archivo bm.exe.config con el Bloc de notas haciendo clic en **iniciar**, haga clic en **ejecutar**, escriba notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="14864-105">Open the bm.exe.config file using Notepad by clicking **Start**, clicking **Run**, typing notepad [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]tracking\bm.exe.config, and then clicking **OK**.</span></span>  
  
2.  <span data-ttu-id="14864-106">Localice la sección appSettings en el archivo y cambie los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="14864-106">Locate the appSettings section in the file and change the following values:</span></span>  
  
    ```  
    <!-- Default server and database for bm.exe. -->  
    <add key="DefaultServer" value="oldServerName" />  
    <add key="DefaultDatabase" value="BAMPrimaryImport" />  
    ```  
  
3.  <span data-ttu-id="14864-107">en</span><span class="sxs-lookup"><span data-stu-id="14864-107">to</span></span>  
  
    ```  
    <!-- Default server and database for bm.exe. -->  
    <add key="DefaultServer" value="newServerName" />  
    <add key="DefaultDatabase" value="BAMPrimaryImport" />  
    ```  
  
4.  <span data-ttu-id="14864-108">Guarde el archivo.</span><span class="sxs-lookup"><span data-stu-id="14864-108">Save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14864-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="14864-109">See Also</span></span>  
 [<span data-ttu-id="14864-110">Administrar bases de datos BAM</span><span class="sxs-lookup"><span data-stu-id="14864-110">Managing BAM Databases</span></span>](../core/managing-bam-databases.md)