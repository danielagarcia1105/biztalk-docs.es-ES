---
title: "Detener el proceso en el sistema de origen de la aplicación | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cde5fc62-4bc2-4ef0-81bc-c7d39ff36cb6
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70fe980e3f29e2bd4cf13aa2b74a1923126fcec2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="stopping-application-processing-on-the-source-system"></a>Detener el proceso en el sistema de origen de la aplicación
Procesamiento de la aplicación debe detenerse cuando el origen de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servidores en tiempo de ejecución son todavía puede participar en procesamiento de documentos mediante los servidores de base de datos existente. En este escenario, actividad de procesamiento se debe detener para que se pueda completar una operación de restauración coherentes.  
  
 Para detener el procesamiento de la aplicación en el sistema de origen, no Asegúrese de que no hay ninguna conexión abierta entre la producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en tiempo de ejecución y el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Siga estos pasos para detener el procesamiento de la aplicación en producción [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos en tiempo de ejecución:  
  
1.  Deshabilitar todas las ubicaciones de recepción en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos del grupo de BizTalk. Hacer que los reciba una nota de todas las ubicaciones que se deshabilitan para que estas ubicaciones de recepción pueden habilitarse de nuevo más tarde. Este comando detiene [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] del procesamiento de mensajes entrantes.  
  
2.  Detener todas las instancias de host no se ejecuten en la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos del grupo. Esto puede hacerse desde el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración. Tome nota de todas las instancias de host que se detuvieron para que estas instancias de host se pueden reiniciar más tarde.  
  
3.  Todos los detenga [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] relacionadas con trabajos del agente [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos.  
  
4.  Si BAM está en uso, deshabilite cualquier BAM cubo datos y actualización paquetes SSIS de mantenimiento. Esto puede hacerse mediante el uso de [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio.  
  
5.  Detener Analysis Services en el [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Esto puede hacerse por detener todas las instancias de MSSQLServerOLAPService en la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos donde está instalado Analysis Services.  
  
6.  Detener cualquier otro [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servicios en el Administrador de servicios que pueden estar ejecutándose en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] equipos del grupo, por ejemplo, el servicio de inicio de sesión único de empresa y el servicio de actualización de motor de reglas. Tome nota de los servicios que se detienen para que se pueden reiniciar más tarde.  
  
7.  Cierre todas las aplicaciones que se conectan a la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Esto incluye las instancias de la [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, [!INCLUDE[btsVStudio2008](../includes/btsvstudio2008-md.md)], y cualquier otro instalado ya las aplicaciones de BizTalk.  
  
8.  Compruebe que no hay ninguna actividad de base de datos generada por [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. Use [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio para ver qué procesos están conectados a la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Esto puede hacerse mediante la expansión **administración** y haga doble clic en **Monitor de actividad** en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio. A continuación, haga clic para seleccionar **información del proceso**. O bien usar los procedimientos almacenados del sistema **sp_who** o **sp_who2** para identificar las conexiones abiertas a la [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] equipos que alojan [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] bases de datos. Si no hay ningún proceso conectado, buscarlos y finalizar normalmente; o como último recurso, haga clic en cada proceso en el **información del proceso** panel en [!INCLUDE[btsSQLServerNoVersion](../includes/btssqlservernoversion-md.md)] Management Studio y haga clic en **Terminar proceso** para terminar la conexión.  
  
9. Procesamiento de la base de datos adicionales se puede producir en las bases de datos de aplicación. Si estas bases de datos se restaurará, asegúrese de que todo el procesamiento se detiene.  
  
## <a name="see-also"></a>Vea también  
 [Restaurar el grupo de BizTalk](../technical-guides/restoring-the-biztalk-group.md)