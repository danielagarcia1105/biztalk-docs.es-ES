---
title: Configuración posterior a la base de datos Optimizations1 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 763b5358-97ed-4ada-8318-0ad07388ba89
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e89da931e7f7a007734d69dfec8921556982ec24
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36975085"
---
# <a name="post-configuration-database-optimizations"></a>Optimizaciones de configuración posterior a la base de datos
Además de seguir las recomendaciones de [optimizaciones de base de datos de configuración previa](../technical-guides/post-configuration-database-optimizations1.md), se deben seguir varios pasos para optimizar el rendimiento de la base de datos de BizTalk Server en SQL Server *después* Se ha instalado BizTalk Server y se han configurado las bases de datos de BizTalk Server. En este tema se proporciona una lista de estas optimizaciones.  
  
## <a name="pre-allocate-space-for-biztalk-server-databases-and-define-auto-growth-settings-for-biztalk-server-databases-to-a-fixed-value-instead-of-a-percentage-value"></a>Reserve espacio para las bases de datos de BizTalk Server y definir la configuración de crecimiento automático de las bases de datos de BizTalk Server en un valor fijo en lugar de un valor de porcentaje  
  
-   Crecimiento automático base de datos SQL Server es una operación de bloqueo que afecta negativamente al rendimiento de la base de datos de BizTalk Server. Por lo tanto, es importante asignar suficiente espacio para las bases de datos de BizTalk Server de antemano minimizar la aparición de crecimiento automático de base de datos.  
  
-   Crecimiento automático de base de datos debe establecerse en un número fijo de megabytes, en lugar de a un porcentaje (especificar el crecimiento del archivo **en Megabytes**). Esto debe hacerse por lo que si se produce el crecimiento automático, lo hace en forma medida, lo que reduce la probabilidad de crecimiento excesivo de la base de datos. El incremento de crecimiento por lo general debe ser mayor de 100 MB (para archivos de gran tamaño), 10 MB (para archivos mediana) o 1 MB (para archivos pequeños).  
  
-   Cuando SQL Server aumenta el tamaño de un archivo, el nuevo espacio en primer lugar debe inicializarse antes de poder usarlo. Se trata de una operación de bloqueo que implica rellenar el nuevo espacio con páginas vacías. En Windows Server 2003 o una versión posterior de SQL Server 2005 admite "inicialización instantánea de archivos". Esto puede reducir considerablemente el impacto del rendimiento de una operación de crecimiento de archivos. Para obtener más información, consulte "Inicialización de archivo de base de datos" en la documentación de SQL Server 2008 en [ http://go.microsoft.com/fwlink/?LinkId=132063 ](http://go.microsoft.com/fwlink/?LinkId=132063). En este tema proporciona los pasos para habilitar la inicialización instantánea de archivos.  
  
## <a name="move-the-backup-biztalk-server-output-directory-to-a-dedicated-lun"></a>Mover el directorio de salida de copia de seguridad de BizTalk Server a un LUN dedicado  
 Mueva el directorio de salida de copia de seguridad de BizTalk Server (copia de seguridad completa y de registro) al LUN dedicado, edite los pasos 1 y 2 (Insertar nueva ruta de salida) de la tarea de copia de seguridad BizTalk Server [BizTalkMgmtDb]. Mover el directorio de salida de copia de seguridad de BizTalk Server a un LUN dedicado reducir la contención de E/S de disco cuando se ejecuta el trabajo al escribir en un disco diferente que el trabajo esté leyendo.  
  
## <a name="verify-the-biztalk-server-sql-agent-jobs-are-running"></a>Compruebe que los trabajos del agente de SQL de BizTalk Server se está ejecutando  
 BizTalk Server incluye varios trabajos del Agente SQL Server que realizan funciones importantes para mantener los servidores operativos y en buen estado. Debe supervisar el estado de estos trabajos y asegurarse de que se ejecutan sin errores. Una de las causas más comunes de problemas de rendimiento de BizTalk Server es que los trabajos del agente de SQL de BizTalk Server no están en ejecución, lo que a su vez puede provocar que el cuadro de mensajes y el seguimiento de las bases de datos crecen sin control. Siga estos pasos para asegurarse de que los trabajos del agente de SQL de BizTalk Server se ejecutan sin problemas:  
  
 Una de las causas más comunes de problemas de rendimiento de BizTalk Server es que los trabajos del agente de SQL de BizTalk Server no están en ejecución, lo que a su vez puede provocar que el cuadro de mensajes y el seguimiento de las bases de datos crecen sin control. Siga estos pasos para asegurarse de que los trabajos del agente de SQL de BizTalk Server se ejecutan sin problemas:  
  
-   **Compruebe el servicio Agente SQL Server se está ejecutando**.  
  
-   **Compruebe los trabajos del Agente SQL Server instalados por BizTalk Server están habilitados y ejecutándose correctamente**.  
  
     Los trabajos del Agente SQL Server de BizTalk Server son cruciales, si no se están ejecutando, se degradará el rendimiento del sistema con el tiempo.  
  
-   **Compruebe que se completan los trabajos del Agente SQL Server de BizTalk Server de manera oportuna**.  
  
     Configurar Microsoft Operations Manager (MOM) 2005 o Microsoft System Center Operations Manager 2007 para supervisar los trabajos.  
  
     Debe ser consciente de las programaciones que son específicas de determinados trabajos:  
  
    -   El trabajo MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb continuamente se ejecuta de forma predeterminada. Software de supervisión debe tener esta programación en la cuenta y no generan advertencias.  
  
    -   El trabajo MessageBox_Message_Cleanup_BizTalkMsgBoxDb no está habilitado o programado, pero se inicia el trabajo MessageBox_Message_ManageRefCountLog_BizTalkMsgBoxDb cada 10 segundos. Por lo tanto, este trabajo debe no ser habilitado, programado o iniciar de forma manual.  
  
-   **Compruebe el tipo de inicio del servicio Agente SQL Server está correctamente configurado**.  
  
     Compruebe que el servicio Agente SQL Server está configurado con un **tipo de inicio** de **automática** a menos que el servicio Agente SQL Server está configurado como un recurso de clúster en un clúster de Windows Server. Si el servicio Agente SQL Server está configurado como un recurso de clúster, se debe configurar el **tipo de inicio** como **Manual** porque el servicio se administrarán mediante el servicio de clúster.  
  
## <a name="configure-purging-and-archiving-of-tracking-data"></a>Configurar la depuración y el archivo de datos de seguimiento  
 Siga estos pasos para asegurarse de que purga y el archivado de datos de seguimiento está configurado correctamente:  
  
-   Asegúrese de que el trabajo del Agente SQL "DTA Purge y Archive" está correctamente configurado, habilitado y completando correctamente. Para obtener más información, consulte "Cómo configurar la DTA purgar y archivar trabajo" en la documentación de BizTalk Server en [ http://go.microsoft.com/fwlink/?LinkId=104908 ](http://go.microsoft.com/fwlink/?LinkId=104908).  
  
-   Asegúrese de que el trabajo es capaz de purgar los datos de seguimiento tan rápido como el seguimiento de los datos entrantes se generaron. Para obtener más información, vea "Medir el rendimiento máximo sostenible de seguimiento" en la documentación de BizTalk Server 2006 R2 en [ http://go.microsoft.com/fwlink/?LinkId=104909 ](http://go.microsoft.com/fwlink/?LinkId=104909).  
  
-   Revise la purga condicional y purga incondicional parámetros para asegurarse de que mantienen los datos durante el período de tiempo óptimo. Para obtener más información, vea "Archivado y purga el seguimiento base de datos BizTalk" en la documentación de BizTalk Server en [ http://go.microsoft.com/fwlink/?LinkId=101585 ](http://go.microsoft.com/fwlink/?LinkId=101585).  
  
-   Si solo necesita purgar los datos antiguos y necesita archivarla en primer lugar, cambio el Agente SQL de trabajos para llamar al procedimiento almacenado "dtasp_PurgeTrackingDatabase." Para obtener más información, vea "Cómo purgar datos desde el BizTalk seguimiento de base de datos" en la documentación de BizTalk Server en [ http://go.microsoft.com/fwlink/?LinkId=101584 ](http://go.microsoft.com/fwlink/?LinkId=101584).  
  
## <a name="monitor-and-reduce-dtc-log-file-disk-io-contention"></a>Supervisar y reducir la contención de E/S de disco del archivo de registro DTC  
 El archivo de registro de Microsoft Distributed Transaction Coordinator (MS DTC) puede convertirse en un cuello de botella de E/S de disco en entornos con muchas transacciones. Esto es especialmente cierto cuando se utilizan los adaptadores que admiten transacciones, como MQSeries, MSMQ o SQL Server, o en un entorno de varios mensajes. Los adaptadores transaccionales usen transacciones DTC y entornos de varios mensajes usan en gran medida de transacciones de DTC. Para asegurarse de que el archivo de registro DTC no es un cuello de botella de E/S de disco, debe supervisar el uso de E/S del disco donde reside el archivo de registro DTC en los servidores de base de datos de SQL Server del disco. Si resulta excesivo uso de E/S del disco donde reside el archivo de registro DTC del disco, a continuación, considere la posibilidad de mover el archivo de registro DTC a un disco más rápido. En un entorno donde está en el clúster de SQL Server, esto no es supone un problema porque el archivo de registro ya estará en una unidad compartida, que probablemente será una unidad de SAN rápida con varios ejes. Sin embargo, todavía debe supervisar el uso de E/S de disco porque puede convertirse en un cuello de botella en entornos no agrupado o al registro de DTC archivo está en un disco compartido con otros archivos de uso intensivo del disco.  
  
 Para asegurarse de que el archivo de registro DTC no es un cuello de botella de E/S de disco, debe supervisar el uso de E/S del disco donde reside el archivo de registro DTC en los servidores de base de datos de SQL Server del disco. Si se convierte en disco, uso de E/S del disco donde reside el archivo de registro DTC excesiva, considere la posibilidad de mover el archivo de registro DTC a un disco más rápido.  
  
 En un entorno donde está en el clúster de SQL Server, esto no es supone un problema porque el archivo de registro ya estará en una unidad compartida, que probablemente será una unidad de SAN rápida con varios ejes. Sin embargo, todavía debe supervisar el uso de E/S de disco porque puede convertirse en un cuello de botella en entornos no agrupado o al registro de DTC archivo está en un disco compartido con otros archivos de uso intensivo del disco.  
  
## <a name="separate-the-messagebox-and-tracking-databases"></a>Separar el cuadro de mensajes y las bases de datos de seguimiento  
 Dado que las bases de datos de BizTalk MessageBox y seguimiento de BizTalk son los más activos, se recomienda que colocar los archivos de datos y los archivos de registro de transacciones para cada una de ellas en unidades de disco dedicados para reducir la probabilidad de problemas de contención de E/S de disco. Por ejemplo, necesitaría cuatro unidades para los archivos de base de datos de cuadro de mensajes y seguimiento de BizTalk, una para cada una de las siguientes acciones:  
  
- Archivos de datos de cuadro de mensajes  
  
- Archivos de registro de transacciones de cuadro de mensajes  
  
- Archivos de datos de seguimiento de BizTalk (DTA)  
  
- Archivos de registro de transacciones de seguimiento de BizTalk (DTA)  
  
  Separar las bases de datos de BizTalk MessageBox y seguimiento de BizTalk y separación de los archivos de base de datos y archivos de registro de transacciones en discos físicos diferentes se consideran mejores prácticas para reducir la contención de E/S de disco. Pruebe a distribuir la E/S de disco en ejes físicos tantos como sea posible. También puede reducir la contención de E/S de disco mediante la colocación de la base de datos de seguimiento de BizTalk en un servidor dedicado de SQL, sin embargo, todavía debe seguir las prácticas anteriormente con respecto a la separación de los archivos de datos y los archivos de registro de transacciones.  
  
## <a name="optimize-filegroups-for-the-biztalk-server-databases"></a>Optimizar los grupos de archivos para las bases de datos de BizTalk Server  
 Siga los pasos de [optimización de grupos de archivos para el Databases1](../technical-guides/optimizing-filegroups-for-the-databases1.md) y las notas del producto "Optimización de base de datos de BizTalk Server" en [ http://go.microsoft.com/fwlink/?LinkId=101578 ](http://go.microsoft.com/fwlink/?LinkId=101578) para crear archivos y grupos de archivos adicionales para BizTalk Bases de datos de servidor. Esto aumentará considerablemente el rendimiento de las bases de datos de BizTalk Server desde una configuración de disco único.