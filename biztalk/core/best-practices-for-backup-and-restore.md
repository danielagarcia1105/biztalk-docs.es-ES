---
title: "Procedimientos recomendados para copias de seguridad y restauración | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aaf721ba-50ce-4334-b86d-e856b54d3486
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23657dcc843744741d6315b6a8c18ca3d35e1fe4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-backup-and-restore"></a>Prácticas recomendadas para efectuar copias de seguridad y restauraciones
-   **Crear una copia de seguridad y plan de restauraciones**  
  
     Asegúrese de que el plan de copia de seguridad especifica lo siguiente:  
  
    -   El equipo en el que se almacenarán las copias de seguridad.  
  
    -   Los programas que se utilizarán para realizar una copia de seguridad del sistema.  
  
    -   Los equipos de los que desea realizar una copia de seguridad.  
  
    -   La programación en la que se realizará la copia de seguridad.  
  
    -   La ubicación fuera del sitio donde se archivarán las copias de seguridad.  
  
-   **Mantener un registro escrito de todos los cambios en el sistema BizTalk Server**  
  
     Asegúrese de anotar todos los cambios que se han aplicado al sistema, como Service Packs, revisiones y QFE. Esto es fundamental para que el sistema se restaure del modo más parecido posible al que existía antes de que se produjera el error en el hardware.  
  
-   **Implementar las siguientes medidas para ayudar a prevenir o minimizar el efecto de un desastre:**  
  
    -   Tenga disponibles las actualizaciones de software y firmware.  
  
    -   Tenga preparados todos los discos de instalación del software. Incluye el software del sistema (por ejemplo, unidades especializadas) y el software de aplicaciones (por ejemplo, BizTalk Server).  
  
    -   Disponga de un plan para supervisar los servidores de forma proactiva. Esta medida es muy importante, ya que las instancias de orquestación en un host con errores no puede recuperarlas un segundo host hasta que no transcurran diez minutos.  
  
    -   Mantenga registros del hardware.  
  
    -   Mantenga registros del software.  
  
-   **Implementar la tolerancia a errores en su organización en el nivel de hardware o software**  
  
     La implementación de clústeres y la matriz redundante de discos independientes (RAID) posibilita que el sistema pueda recuperarse de un error en el hardware.  
  
-   **Archivar los medios de copia de seguridad de forma regular en una ubicación segura**  
  
     Cree una programación para archivar los medios de copia de seguridad de forma periódica y mantenga los archivos en una ubicación segura y fuera del sitio. Con este procedimiento, se asegura la disponibilidad de una copia de seguridad para cuando resulte necesaria.  
  
-   **Comprobar la integridad de las copias de seguridad y que se producen sin errores**  
  
     Supervise todos los trabajos de copia de seguridad y asegúrese de que finalizan sin errores.  
  
-   **Mantener hardware idéntico de repuesto disponible**  
  
     Al tener disponible un hardware idéntico de repuesto se asegura poder reemplazar con rapidez el hardware defectuoso y comenzar a trabajar con él sin dilación.  
  
-   **Documentar y probar los procedimientos de recuperación**  
  
     Lo ideal sería que se ejecutara la prueba de recuperación ante desastres, antes de ejecutar el sistema en producción. Al tener planes y llevar a cabo pruebas de versiones preliminares, se asegura de que el personal de IT pueda recuperar los sistemas de BizTalk Server. Generalmente significa que debe intentar de forma periódica restaurar la copia de seguridad del sistema en el hardware real que usará.  
  
-   **Entrenar su personal de TI en los procedimientos de recuperación ante desastres**  
  
     Asegúrese de que el personal de IT cuenta con los conocimientos adecuados para recuperar el sistema si fuera necesario.  
  
-   **Practicar la restauración de copia de seguridad en un entorno de prueba**  
  
     Practique la recuperación del sistema BizTalk Server en un entorno de prueba para asegurarse de que puede restaurarlo en el entorno de producción si se produce un fallo.  
  
## <a name="see-also"></a>Vea también  
 [Copia de seguridad y restauración de BizTalk Server](../core/backing-up-and-restoring-biztalk-server.md)