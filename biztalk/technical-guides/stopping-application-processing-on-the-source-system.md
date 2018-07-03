---
title: Detener procesamiento de aplicaciones en el sistema de origen | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cde5fc62-4bc2-4ef0-81bc-c7d39ff36cb6
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c92fe07371be2abb44c314eb77eb38c6c853bebe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982461"
---
# <a name="stopping-application-processing-on-the-source-system"></a>Detener procesamiento de aplicaciones en el sistema de origen
Se debe detener el procesamiento de la aplicación cuando el origen [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores en tiempo de ejecución pueden seguir participar en procesamiento de documentos mediante los servidores de base de datos existente. En este escenario, actividad de procesamiento debe detenerse para que se pueda completar una operación de restauración coherentes.  
  
 Para detener el procesamiento de la aplicación en el sistema de origen, asegúrese de que no hay conexiones abiertos entre la producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en tiempo de ejecución y el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Siga estos pasos para detener el procesamiento de la aplicación en la producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en tiempo de ejecución:  
  
1. Deshabilitar todas las ubicaciones de recepción en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos del grupo de BizTalk. Tome nota de todos los recibir ubicaciones que están deshabilitadas para que estas ubicaciones de recepción pueden habilitarse de nuevo más tarde. Esto detendrá [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del procesamiento de mensajes entrantes.  
  
2. Detener todas las instancias de host desde que se ejecutan en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos del grupo. Esto puede hacerse desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Tome nota de todas las instancias de host que se detuvieron para que estas instancias de host se pueden reiniciar más tarde.  
  
3. Todos los detenga [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] relacionados con los trabajos del agente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
4. Si BAM está en uso, deshabilite cualquier BAM cubo datos y actualización mantenimiento paquetes SSIS. Esto puede hacerse mediante el uso de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio.  
  
5. Detener los servicios de análisis en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Esto puede hacerse, detenga todas las instancias de MSSQLServerOLAPService en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos donde está instalado Analysis Services.  
  
6. Detenga cualquier otra [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios en el Administrador de servicios que pueden estar ejecutándose en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos del grupo, por ejemplo, el servicio de inicio de sesión único de Enterprise y el servicio de actualización de motor de reglas. Tome nota de los servicios que se detienen para que puede reiniciar más tarde.  
  
7. Cierre todas las aplicaciones que se conectan a la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Esto incluye las instancias de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)], y cualquier otro instala aplicaciones de BizTalk.  
  
8. Compruebe que no hay ninguna actividad de base de datos generada por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Use [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio para ver qué procesos están conectados a la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Esto puede hacerse mediante la expansión **administración** y haga doble clic en **Monitor de actividad** en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio. A continuación, haga clic para seleccionar **información del proceso**. O bien usar los procedimientos almacenados del sistema **sp_who** o **sp_who2** para identificar las conexiones abiertas en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Si hay algún proceso conectado, buscarlos y finalícelas normalmente. o como último recurso, haga clic en cada proceso en el **información del proceso** panel [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio y haga clic en **Terminar proceso** para terminar la conexión.  
  
9. Procesamiento de la base de datos adicionales se puede producir en las bases de datos de la aplicación. Si estas bases de datos se restaurará, asegúrese de que todo el procesamiento se ha detenido.  
  
## <a name="see-also"></a>Vea también  
 [Restauración del grupo de BizTalk](../technical-guides/restoring-the-biztalk-group.md)