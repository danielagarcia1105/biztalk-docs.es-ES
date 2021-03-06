---
title: Cómo configurar las bases de datos BAM mediante la utilidad de administración de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 801338f4-b363-4f8e-b248-9c628065ded2
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6878e6aa3874384bd17f340c62421c432182f637
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001317"
---
# <a name="how-to-set-up-the-bam-databases-using-the-bam-management-utility"></a>Cómo configurar las bases de datos de BAM con la utilidad de administración de BAM
Los administradores suelen usar la utilidad de configuración de BizTalk Server para configurar las bases de datos de BAM. Puede usar la utilidad de administración de BAM (bm.exe) como método alternativo de configuración de bases de datos.  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:  
  
-   Deberá tener permisos de administrador en el servidor SQL en que residen las bases de datos BAMPrimaryImport, BAMStarSchema y BAMArchive.  
  
-   Para configurar las bases de datos de servicios de notificación de SQL, deberá tener permiso de administrador y ser miembro del grupo de administradores local, así como ser miembro de otros grupos de administradores que se hayan configurado, como el grupo de administradores de BTS.  
  
-   Deberá disponer de un archivo de configuración de BAM que contenga los datos XML con los que configurar las bases de datos.  
  
### <a name="to-set-up-the-bam-databases-using-the-bam-management-utility"></a>Para configurar las bases de datos de BAM con la utilidad de administración de BAM  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3. Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm setup-databases - ConfigFile:\<archivo de configuración\>**, donde \< *archivo de configuración* \>se sustituye por el nombre de su archivo de configuración de BAM. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)