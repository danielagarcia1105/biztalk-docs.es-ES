---
title: Cómo habilitar servicios de notificación en equipos adicionales en un grupo | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 571d6b45-b0cc-47f2-bed3-7c6f3e70decc
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fd8a1a49be2416fb8b7fe5d160dd5228a95e94f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36983397"
---
# <a name="how-to-enable-notifications-services-on-additional-computers-in-a-group"></a>Cómo habilitar servicios de notificación en equipos adicionales en un grupo
Al ejecutar BAM en un entorno de varios equipos, debe habilitar Notification Services en cada equipo en el que se ejecutará la utilidad de administración de BAM para implementar una actividad.  
  
 Considere el caso siguiente:  
  
- Grupo A consta de los siguientes equipos:  
  
  - El equipo 1 se utiliza como equipo de administración de BAM.  
  
  - El equipo 2 aloja las tablas de importación principal (PIT) y la base de datos de esquema de estrella de BAM.  
  
  - El equipo 3 aloja las bases de datos de archivo y análisis de BAM.  
  
  - El equipo 4 aloja la base de datos de alertas de BAM.  
  
  - El equipo 5 aloja el resto de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
- Grupo B:  
  
  -   El equipo 6 se utiliza como equipo de administración de BAM en el que todas las bases de datos se comparten con el grupo A.  
  
  Para poder implementar una actividad en las bases de datos en un grupo desde el equipo del grupo B, primero debe registrar los servicios de notificación con el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] hospeda los servicios de notificación. Si no se registra, aparecerá el siguiente error:  
  
  Deploying Alert… (Implementando alerta...) ERROR: Error de la implementación de BAM.  
  
  Las alertas no se implementaron.  
  
  Se produjo una excepción en el destino de la invocación.  
  
  No se encontraron las entradas de Registro de la instancia especificada de Notification Services.  
  
### <a name="to-register-notifications-services-additional-computers"></a>Procedimiento para registrar equipos adicionales de servicios de notificaciones  
  
1.  En el equipo del grupo adicional, haga clic en **iniciar**, apunte a **todos los programas**, haga clic en **Microsoft SQL Server 2005**, haga clic en **deherramientasdeconfiguración**y, a continuación, haga clic en **línea de comandos de Notification Services**.  
  
2.  En el símbolo del sistema, escriba: **nscontrol register - nombre \<NS prefijo elegida en config\> -server \<del servidor sql ns db\>**. Esto permite que los servicios de notificación inicien sesión en la base de datos correcta (nscontrol mantiene esta información en el Registro del equipo de servicio).  
  
## <a name="see-also"></a>Vea también  
 [Cambiar la configuración de BAM en tiempo de ejecución](../core/changing-bam-runtime-settings.md)   
 [Utilidad de administración de BAM](../core/bam-management-utility.md)