---
title: Archivar y purgar la base de datos de seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7014cf31-86e8-4829-8055-056442329009
caps.latest.revision: 37
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3556618df02c7a8c9df5d0d55c27eb69ed91eae2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000861"
---
# <a name="archive-and-purge-the-biztalkdtadb-database"></a>Archivar y purgar la base de datos BizTalkDTADb

## <a name="overview"></a>Información general
Puesto que BizTalk Server procesa cada vez más datos en el sistema, el tamaño de la base de datos de seguimiento de BizTalk (BizTalkDTADb) continúa aumentando. Un crecimiento descontrolado reduce el rendimiento del sistema y puede dar lugar a errores en el Servicio de descodificación de datos de seguimiento (TDDS). Además de los datos de seguimiento general, se pueden acumular también los mensajes controlados en la base de datos de cuadro de mensajes, lo que daría lugar a un rendimiento pobre del disco.  
  
BizTalk Server automatiza ambos procesos mediante el trabajo DTA Purge and Archive. Archivar y purgar los datos de la base de datos de seguimiento de BizTalk permite mantener el sistema en buen estado y tener los datos de seguimiento archivados para usarlos en el futuro. Puesto que los archivos de la base de datos de seguimiento de BizTalk se acumulan con el tiempo y consumen espacio en disco, se recomienda moverlos con regularidad a un recurso de almacenamiento secundario.  
  
 Cuando se purgan datos de la base de datos de seguimiento de BizTalk, el trabajo DTA Purge and Archive purga distintos tipos de información de seguimiento, como, por ejemplo, datos de seguimiento del motor de reglas, información de eventos de orquestación, así como de instancia de servicio y de mensaje.  
  
 La antigüedad de un registro de datos de seguimiento se basa en la hora en la que se insertaron los datos en la base de datos de seguimiento de BizTalk. El trabajo DTA Purge and Archive utiliza la marca de tiempo para comprobar continuamente si el registro es anterior a la ventana de actividad de datos. Después de cada período de ventana de actividad, la base de datos de seguimiento de BizTalk se archiva y se crea un archivo de almacenamiento nuevo. Todos los datos de seguimiento completados que sean anteriores al período de ventana activa se purgan en cada intervalo de trabajo del Agente SQL Server especificado por la programación de trabajo.  
  
 BizTalk Server utiliza los conceptos de purga condicional y purga incondicional. La purga condicional se utiliza para purgar instancias completadas, mientras que la purga incondicional se utiliza únicamente para purgar instancias que no se han completado.  
  
## <a name="soft-purge"></a>Purga condicional
  
 En el trabajo DTA Archive and Purge, la suma de los parámetros LiveHours y LiveDays es la ventana de actividad de los datos que desea mantener en el entorno de BizTalk Server. Se purgan todos los datos asociados con una instancia completada anterior a esta ventana de actividad de datos. De forma predeterminada, el trabajo DTA Archive and Purge no se encuentra habilitado. Primero, es preciso configurar el trabajo y habilitarlo.  
  
 Por ejemplo, puede configurar el trabajo DTA Purge and Archive para ejecutarse cada 20 minutos y establecer actividad = 1 y LiveDays = 0. La primera vez que este trabajo del Agente SQL Server ejecuta (T0), toma una copia de seguridad de la base de datos de seguimiento mediante la creación de un archivo y se guarda una entrada en la base de datos con esta marca de tiempo. Un archivo correcto resulta necesario para purgar datos de seguimiento. Si el archivo se ha realizado correctamente, se purgan todos los datos asociados con las instancias que se completaron hace más de una hora. Cada vez que se ejecuta el trabajo, se purgan los datos completados hace más de una hora. En la tercera ejecución (después de una hora), se crea un nuevo archivo que contiene los datos de todas las instancias que se insertaron en la base de datos de seguimiento durante el último período de una hora.  
  
 Así es cómo se configuraría el archivo y purga paso en el trabajo DTA Purge and Archive para que coincida con el ejemplo:  
  
```  
exec dtasp_BackupAndPurgeTrackingDatabase  
1, --@nLiveHours 1,   
0, --@nLiveDays   
1, --@nHardDeleteDays   
‘\\server\backup’, --@nvcFolder   
null, --@nvcValidatingServer   
0 --@fForceBackup Soft purge process  
```  
  
 La marca de tiempo de la última copia de seguridad se almacena en la base de datos de seguimiento de BizTalk y garantiza que los datos tan sólo se purgan si se encuentran en el archivo anterior. Para obtener mayor confiabilidad, los archivos se superponen durante, aproximadamente, 10 minutos. En la siguiente ilustración, basada en el ejemplo anterior, se muestra el proceso de purga condicional. Tenga en cuenta que las tareas de archivo y purga no siempre ocurren al mismo tiempo.  
  
 **Proceso de purga**  
  
 ![Proceso de purga](../core/media/archivingandpurging.gif "archivingandpurging")  
  
## <a name="hard-purge"></a>Purga incondicional
  
 Puesto que la purga condicional tan sólo purga los datos asociados con instancias completadas, si tuviera un alto número de instancias en bucle cuya ejecución se produjese de manera indefinida, la base de datos de seguimiento crecería y estas instancias nunca se podrían purgar. La fecha de la purga incondicional permite que se purgue toda la información anterior al intervalo especificado, a excepción de la información que indica la existencia de un servicio. Establezca la purga incondicional utilizando el <strong>@nHardDeleteDays</strong> parámetro en el archivo y purga el paso en el trabajo de purga de DTA Archive and. La configuración de purga incondicional debe ser siempre superior a la configuración de purga condicional. En otras palabras, <strong>@nHardDeleteDays</strong> debe ser mayor que la suma de <strong>@nLiveHours</strong> y <strong>@nLiveDays</strong>.  
  
 Archivar y purgar incluye las características que se describen en la siguiente tabla:  
  
|Característica|Descripción|  
|-------------|-----------------|  
|Purga incondicional|Permite configurar un intervalo de tiempo para purgar la información de instancias no completadas anteriores a la fecha especificada.|  
|Copiar mensajes controlados en la base de datos de seguimiento|La opción CopyTrackedMessageToDTA permite copiar directamente mensajes de los que se ha efectuado un seguimiento de los servidores de cuadro de mensajes a la base de datos de seguimiento de BizTalk. Esto resulta necesario para purgar datos mediante el trabajo DTA Purge and Archive.|  
|Validación de archivos|Permite configurar de forma opcional un servidor de base de datos secundario para validar los archivos conforme se crean.|  
|Compatibilidad de seguimiento con varias versiones de base de datos de seguimiento de BizTalk|Archivos de base de datos permite usar seguimiento admite con BizTalk Server.|  
|Reducción de datos de seguimiento|Reduce notablemente la cantidad de datos de seguimiento almacenados sin reducir la información de seguimiento generada. Esto da lugar a un crecimiento más lento de la base de datos de seguimiento.|  
|Operaciones de seguimiento más rápidas, importante optimización de los esquemas de base de datos|Permite usar tareas de seguimiento para buscar mensajes e instancias de servicio en bases de datos de gran tamaño; esta característica se ha optimizado notablemente.|  
  
> [!NOTE]
>  Si están surgiendo problemas de rendimiento que se solucionan de manera momentánea mediante la purga de la base de datos de seguimiento de BizTalk, y desea configurar BizTalk para que no recopile más información de seguimiento, considere la posibilidad de desactivar el seguimiento global. Consulte [desactivar el seguimiento Global](../core/how-to-turn-off-global-tracking.md).  
  
## <a name="next-steps"></a>Pasos siguientes
  
-   [Lista de comprobación: archivar y limpiar la base de datos de seguimiento de BizTalk](../core/checklist-archiving-and-purging-the-biztalk-tracking-database.md)  
  
-   [Configurar el rol BTS_BACKUP_USERS para archivar y depurar datos de la base de datos de seguimiento de BizTalk](../core/configure-bts_backup_users-role-to-archive-and-purge-from-tracking-database.md)  
  
-   [Configurar el trabajo DTA Purge and Archive](../core/how-to-configure-the-dta-purge-and-archive-job.md)  
  
-   [Depurar datos de la base de datos de seguimiento de BizTalk](../core/how-to-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [Depurar datos manualmente de la base de datos de seguimiento de BizTalk](../core/how-to-manually-purge-data-from-the-biztalk-tracking-database.md)  
  
-   [Habilitar la validación automática de archivos](../core/how-to-enable-automatic-archive-validation.md)  
  
-   [Copiar mensajes de los que se ha realizado un seguimiento en la base de datos de seguimiento de BizTalk](../core/how-to-copy-tracked-messages-into-the-biztalk-tracking-database.md)  
  
-   [Mejorar el rendimiento del proceso de archivo y depuración](../core/improving-the-performance-of-the-archiving-and-purging-process.md)  
  
-   [Desactivar el seguimiento global](../core/how-to-turn-off-global-tracking.md)