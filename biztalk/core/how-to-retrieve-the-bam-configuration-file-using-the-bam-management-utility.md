---
title: Cómo recuperar el archivo de configuración de BAM mediante la utilidad de administración de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67ce5e0c-467a-486c-8eec-217a2a26d7b4
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4277e6b088ed136021b898e26204a63dc782a895
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008517"
---
# <a name="how-to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>Cómo recuperar el archivo de configuración de BAM mediante la utilidad de administración de BAM
Los administradores y programadores pueden utilizar la herramienta de administración de BAM para recuperar la configuración actual de la infraestructura de BAM. La configuración recuperada se puede utilizar para migrar una instalación de BAM a un servidor nuevo o se puede modificar y utilizar para actualizar una instalación de BAM existente.  
  
## <a name="prerequisites"></a>Requisitos previos  
 A continuación se exponen algunos requisitos previos para realizar el procedimiento de este tema:  
  
-   Bases de datos de BAM configuradas  
  
-   Permisos para leer la base de datos de importación principal de BAM  
  
### <a name="to-retrieve-the-bam-configuration-file-using-the-bam-management-utility"></a>Para recuperar el archivo de configuración de BAM mediante la utilidad de administración de BAM  
  
1. Abra un símbolo del sistema como sigue: haga clic en **iniciar**, haga clic en **ejecutar**, tipo **cmd**y, a continuación, haga clic en **Aceptar**.  
  
2. Desplácese a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking.  
  
3. Escriba lo siguiente en el símbolo del sistema de línea de comandos: **bm get-config - FileName:\<archivo de salida\>**, donde \< *archivo de salida* \> se sustituye por el nombre de su archivo de configuración de BAM. Presione **ENTRAR**.  
  
## <a name="see-also"></a>Vea también  
 [Utilidad de administración de BAM](../core/bam-management-utility.md)