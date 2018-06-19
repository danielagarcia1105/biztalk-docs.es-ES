---
title: Depuración y el archivo de datos de seguimiento | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14094fda-3fd9-4d45-9bbb-cd9377c2cbad
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94a2560bc8a57a8f60bf2d1ebcddf68b62fd178a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302940"
---
# <a name="purging-and-archiving-tracking-data"></a>Depuración y el archivo de datos de seguimiento
Es importante configurar y habilitar el trabajo DTA Purge and Archive SQL Agent. Este trabajo archiva y purga los datos antiguos de la base de datos de seguimiento de BizTalk (DTA). Esto es esencial para un correcto [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sistema. Una base de datos de seguimiento grande empezarán a afectar al rendimiento del host de seguimiento y los demás procesos que consulta la base de datos de seguimiento. Si no se purgan los datos de seguimiento de la base de datos de seguimiento, la base de datos siguen creciendo a.  
  
## <a name="guidelines-for-using-the-dta-purge-and-archive-job"></a>Directrices para usar la DTA purgar y archivar trabajo  
  
-   **Asegúrese de que el trabajo DTA Purge and Archive SQL Agent está correctamente configurado, habilitado y se completan correctamente.**  
  
     Este trabajo no está habilitado de forma predeterminada porque primero debe configurarlo para que incluya un directorio donde se pueden escribir los archivos de almacenamiento.  
  
-   **Si solo necesita purgar los datos antiguos y no necesita archivarla en primer lugar y, después, cambiar el código SQL el trabajo del agente para llamar al procedimiento almacenado "dtasp_PurgeTrackingDatabase".**  
  
     Esto omite el paso de archivo y solo realiza la purga. Para obtener más información acerca de este procedimiento almacenado y cambiar el trabajo del Agente SQL para utilizarla, vea ["How to purgar datos desde el BizTalk seguimiento Database"](http://go.microsoft.com/fwlink/?LinkId=153817) (http://go.microsoft.com/fwlink/?LinkId=153817).  
  
-   **Asegúrese de que el trabajo está capacitado para purgar los datos de seguimiento de velocidad a la que se generan el seguimiento de los datos entrantes.**  
  
     Es aceptable para el trabajo obtener durante las horas pico de carga, pero siempre debe ser capaz de ponerse al día. Si el trabajo de purga se queda atrás y nunca es capaz de ponerse al día, siguen creciendo a la base de datos de seguimiento y rendimiento finalmente se verá afectado negativamente.  
  
-   **Revise la purga condicional y purga incondicional parámetros para garantizar que se mantiene datos durante el período de tiempo óptimo.**  
  
     Para obtener más información acerca de estos parámetros, consulte ["Archivado y purga el seguimiento de base de datos BizTalk"](http://go.microsoft.com/fwlink/?LinkId=153816) (http://go.microsoft.com/fwlink/?LinkId=153816).  
  
-   **Si necesita mantener el seguimiento de guardar los archivos, asegúrese de que tiene un proceso en su lugar para restaurar y utilizarlos correctamente.**  
  
## <a name="see-also"></a>Vea también  
 [Lista de comprobación: Configurar SQL Server](~/technical-guides/checklist-configuring-sql-server.md)