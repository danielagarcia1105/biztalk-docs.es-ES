---
title: Usar para la recuperación ante desastres de trasvase de registros de servidor BizTalk Server | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5d65015c-de53-4590-b644-5c2f66f763db
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16f2cf9e1d8b717ff42536ef9c0dba79132b9663
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22302300"
---
# <a name="using-biztalk-server-log-shipping-for-disaster-recovery"></a>Uso de recuperación ante desastres de trasvase de registros de servidor BizTalk Server
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]implementa la base de datos en espera funciones mediante el uso de la base de datos de trasvase de registros. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]trasvase de registros automatiza la copia de seguridad y restauración de archivos de registro de transacciones y de base de datos, lo que permite un servidor en espera reanudar el procesamiento de base de datos en caso de que se produce un error en el servidor de base de datos de producción.  
  
## <a name="how-log-shipping-works"></a>Cómo funciona de trasvase de registros  
 El [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] trabajos del agente utilizados por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para el trasvase de registros sincronizar datos entre el servidor de origen utilizados en la producción y el servidor de destino que se usa como paso intermedio de espera cada 15 minutos de forma predeterminada (es decir, cada vez que se ejecuta el trabajo de copia de seguridad de BizTalk Server).  
  
## <a name="using-log-shipping-for-disaster-recovery"></a>Usar el trasvase de registros para la recuperación ante desastres  
 Haga lo siguiente cuando se usa [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] trasvase para recuperación ante desastres de registros:  
  
-   Siga los pasos descritos en el tema [lista de comprobación: aumentar la disponibilidad con recuperación ante desastres](../technical-guides/checklist-increasing-availability-with-disaster-recovery.md) para aumentar la disponibilidad de una producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entorno mediante la recuperación ante desastres.  
  
-   Compruebe que los servidores de recuperación ante desastres tienen la capacidad para administrar la carga de producción.  
  
     Asegúrese de que los servidores en espera tienen el mismo o similares recursos disponibles (CPU/memoria/disco) como los servidores de producción.  
  
-   Asegúrese de que los detalles de su rutina de recuperación ante desastres están bien documentados.  
  
     Documente cada paso de la preparación de la recuperación ante desastres y la implementación en detalle. Ante desastres pocas veces plenos cuando resulte práctico por lo que se supone que las partes responsables de implementar el procedimiento de recuperación ante desastres están iniciando su primer día de trabajo y a realizar esto por primera vez.  
  
-   Como parte de regular pruebas, práctica conmutación por error en el sitio de recuperación ante desastres, especialmente como nuevo de BizTalk se colocan las aplicaciones en producción.  
  
     Realizar pruebas como parte de la prueba normal y el mantenimiento para asegurarse de que puede realizar sin problemas de conmutación por error.  
  
## <a name="see-also"></a>Vea también  
 [Recuperación ante desastres](../technical-guides/disaster-recovery.md)