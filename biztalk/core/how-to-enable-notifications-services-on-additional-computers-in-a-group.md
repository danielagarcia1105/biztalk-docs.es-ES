---
title: "Cómo habilitar servicios de notificación en más equipos en un grupo | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 571d6b45-b0cc-47f2-bed3-7c6f3e70decc
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9787c5ac1371f6743285a151e5666d12b592a300
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-enable-notifications-services-on-additional-computers-in-a-group"></a>Cómo habilitar servicios de notificación en equipos adicionales en un grupo
Al ejecutar BAM en un entorno de varios equipos, debe habilitar Notification Services en cada equipo en el que va a ejecutar la utilidad de administración de BAM para implementar una actividad.  
  
 Considere el caso siguiente:  
  
-   Grupo A consta de los siguientes equipos:  
  
    -   El equipo 1 se utiliza como equipo de administración de BAM.  
  
    -   El equipo 2 aloja las tablas de importación principal (PIT) y la base de datos de esquema de estrella de BAM.  
  
    -   El equipo 3 aloja las bases de datos de archivo y análisis de BAM.  
  
    -   El equipo 4 aloja la base de datos de alertas de BAM.  
  
    -   El equipo 5 aloja el resto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] las bases de datos.  
  
-   Grupo B:  
  
    -   El equipo 6 se utiliza como equipo de administración de BAM en el que todas las bases de datos se comparten con el grupo A.  
  
 Para poder implementar una actividad en las bases de datos en un grupo desde el equipo en el grupo B, primero debe registrar los servicios de notificación con el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] hospeda los servicios de notificación. Si no se registra, aparecerá el siguiente error:  
  
 Deploying Alert… (Implementando alerta...) ERROR: Error en la implementación de BAM.  
  
 Las alertas no se implementaron.  
  
 Se produjo una excepción en el destino de la invocación.  
  
 No se encontraron las entradas de Registro de la instancia especificada de Notification Services.  
  
### <a name="to-register-notifications-services-additional-computers"></a>Procedimiento para registrar equipos adicionales de servicios de notificaciones  
  
1.  En el equipo del grupo adicional, haga clic en **iniciar**, seleccione **todos los programas**, haga clic en **Microsoft SQL Server 2005**, haga clic en **deherramientasdeconfiguración**y, a continuación, haga clic en **comandos de Notification Services**.  
  
2.  En el símbolo del sistema, escriba: **nscontrol register - nombre \<NS prefijo nombre elegido en config\> -server \<sql server de ns db\>**. Esto permite que los servicios de notificación inicien sesión en la base de datos correcta (nscontrol mantiene esta información en el Registro del equipo de servicio).  
  
## <a name="see-also"></a>Vea también  
 [Cambiar la configuración de tiempo de ejecución BAM](../core/changing-bam-runtime-settings.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)