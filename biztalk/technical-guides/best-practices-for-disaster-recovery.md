---
title: "Procedimientos recomendados para la recuperación ante desastres | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: afbb0a57-0d31-4a2f-847c-02b40361c0ed
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1e988055205203c5c4bc7a4d9d6e84706414967c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-disaster-recovery"></a>Prácticas recomendadas para la recuperación ante desastres
Para obtener información sobre los procedimientos recomendados para la recuperación ante desastres para [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], consulte [prácticas recomendadas para la copia de seguridad y restauración](http://go.microsoft.com/fwlink/?LinkId=151391) (http://go.microsoft.com/fwlink/?LinkId=151391) en [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda.  
  
 **Crear una copia de seguridad y plan de restauraciones**  
  
-   Asegúrese de que el plan de copia de seguridad especifica lo siguiente:  
  
    -   El equipo en el que se almacenarán las copias de seguridad.  
  
    -   Los programas que se utilizarán para realizar una copia de seguridad del sistema.  
  
    -   Los equipos de los que desea realizar una copia de seguridad.  
  
    -   La programación en la que se realizará la copia de seguridad.  
  
    -   La ubicación fuera del sitio donde se archivarán las copias de seguridad.  
  
 **Mantener un registro escrito de todos los cambios en el sistema BizTalk Server**  
  
-   Asegúrese de anotar todos los cambios que se han aplicado al sistema, como Service Packs, revisiones y QFE. Esto es fundamental para que el sistema se restaure del modo más parecido posible al que existía antes de que se produjera el error en el hardware.  
  
 **Implementar las siguientes medidas para ayudar a prevenir o minimizar el efecto de un desastre**  
  
-   Tenga disponibles las actualizaciones de software y firmware.  
  
-   Procure que todos los discos de software se encuentren disponibles y se pueda tener acceso a ellos con facilidad.  
  
-   Disponga de un plan para supervisar los servidores de forma proactiva. Esto es muy importante, ya que las instancias de orquestación en un host con errores no se pueden recuperar un segundo host hasta 10 minutos.  
  
-   Mantenga registros del hardware.  
  
-   Mantenga registros del software.  
  
 **Implementar la tolerancia a errores en su organización en el nivel de hardware o software**  
  
-   La implementación de clústeres y la matriz redundante de discos independientes (RAID) posibilita que el sistema pueda recuperarse de un error en el hardware.  
  
 **Archivar los medios de copia de seguridad de forma regular en una ubicación segura**  
  
-   Cree una programación para archivar los medios de copia de seguridad de forma periódica y mantenga los archivos en una ubicación segura y fuera del sitio. Con este procedimiento, se asegura la disponibilidad de una copia de seguridad para cuando resulte necesaria.  
  
 **Comprobar la integridad de las copias de seguridad y que se producen sin errores**  
  
-   Supervise todos los trabajos de copia de seguridad y asegúrese de que finalizan sin errores.  
  
 **Mantener hardware idéntico de repuesto disponible**  
  
-   La existencia de hardware idéntico de repuesto disponible, se garantiza que puede reemplazar rápidamente hardware defectuoso para desarrollar y ejecutar más rápidamente.  
  
 **Documentar y probar los procedimientos de recuperación**  
  
-   La prueba de recuperación ante desastres debería llevarse a cabo antes de ejecutar el sistema en la fase de producción. Al tener planes y llevar a cabo pruebas de versiones preliminares, se asegura de que el personal de IT pueda recuperar los sistemas de BizTalk Server.  
  
 **Entrenar su personal de TI en los procedimientos de recuperación ante desastres**  
  
-   Asegúrese de que el personal de IT cuenta con los conocimientos adecuados para recuperar el sistema si fuera necesario.  
  
 **Practicar la restauración de una copia de seguridad en un entorno de prueba**  
  
-   Practique la recuperación del sistema BizTalk Server en un entorno de prueba para asegurarse de que puede restaurarlo en el entorno de producción si se produce un fallo.  
  
## <a name="see-also"></a>Vea también  
 [Recuperación ante desastres](../technical-guides/disaster-recovery.md)