---
title: Cómo identificar cuellos de botella en la base de datos de seguimiento | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9b72e726-6225-47a0-8e1d-0f5a9cf745d3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc63ae8f673b25c4acbd2f7c066c38f2cb58d914
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011021"
---
# <a name="how-to-identify-bottlenecks-in-the-tracking-database"></a><span data-ttu-id="0fe55-102">Cómo identificar cuellos de botella en la base de datos de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0fe55-102">How to Identify Bottlenecks in the Tracking Database</span></span>
<span data-ttu-id="0fe55-103">Para identificar cuellos de botella en la base de datos de seguimiento de BizTalk (BizTalkDTADb), realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="0fe55-103">To identify bottlenecks in the BizTalk Tracking (BizTalkDTADb) database, perform the following steps:</span></span>  
  
1. <span data-ttu-id="0fe55-104">Asegúrese de que servicio del Agente SQL está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="0fe55-104">Ensure that the SQL-Agent Service is running.</span></span>  
  
2. <span data-ttu-id="0fe55-105">Asegúrese de que el trabajo de archivo y purga esté en ejecución y que se esté realizando correctamente.</span><span class="sxs-lookup"><span data-stu-id="0fe55-105">Ensure that the Archive/Purge Job is running and completing successfully.</span></span>  
  
3. <span data-ttu-id="0fe55-106">Asegúrese de que se ejecuta el trabajo TrackedMessages_Copy_BizTalkMsgBoxDB y se complete correctamente.</span><span class="sxs-lookup"><span data-stu-id="0fe55-106">Ensure that the TrackedMessages_Copy_BizTalkMsgBoxDB Job is running and completing successfully.</span></span>  
  
4. <span data-ttu-id="0fe55-107">Compruebe que hay suficiente espacio disponible en disco para los archivos DTADb y para el crecimiento de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="0fe55-107">Verify that sufficient free disk space is available for the DTADb archives and database growth.</span></span>  
  
5. <span data-ttu-id="0fe55-108">Usar un host dedicado para el seguimiento y medir el contador de rendimiento de longitud de cola de Host con la carga.</span><span class="sxs-lookup"><span data-stu-id="0fe55-108">Use a dedicated host for tracking and measure the Host Queue Length performance counter when under load.</span></span>  
  
6. <span data-ttu-id="0fe55-109">Compruebe el contador de rendimiento de tamaño de tabla de cola de impresión para una tendencia en aumento con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="0fe55-109">Check the Spool Table size performance counter for an increasing trend over time.</span></span>  
  
7. <span data-ttu-id="0fe55-110">Comprobación de la duración de ejecución del trabajo de archivo y purga de largos tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0fe55-110">Check the Archive/Purge job execution duration for long execution times.</span></span>  
  
8. <span data-ttu-id="0fe55-111">Compruebe la capacidad de respuesta del disco (disco en segundos por contador de rendimiento de lectura/escritura) en el disco que hospeda la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="0fe55-111">Check disk responsiveness (Disk Seconds per Read/Write performance counter) on the disk hosting the BizTalk Tracking database.</span></span>  
  
   <span data-ttu-id="0fe55-112">Se recomienda encarecidamente que ajuste el valor de los parámetros siguientes del dtasp_PurgeTrackingDatabase invocada por el trabajo DTA Purge and Archive o dtasp_backupandpurgetrackingdatabase por:</span><span class="sxs-lookup"><span data-stu-id="0fe55-112">We strongly recommend tuning down the value of the following parameters of the dtasp_BackupAndPurgeTrackingDatabase or dtasp_PurgeTrackingDatabase invoked by the DTA Purge and Archive job:</span></span>  
  
- <span data-ttu-id="0fe55-113">@nLiveHours tinyint — cualquiera instancias completadas anteriores a (horas) + (días) se eliminarán junto con todos los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="0fe55-113">@nLiveHours tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="0fe55-114">Valor predeterminado es 0 horas.</span><span class="sxs-lookup"><span data-stu-id="0fe55-114">Default is 0 hours.</span></span>  
  
- <span data-ttu-id="0fe55-115">@nLiveDays tinyint — cualquiera instancias completadas anteriores a (horas) + (días) se eliminarán junto con todos los datos asociados.</span><span class="sxs-lookup"><span data-stu-id="0fe55-115">@nLiveDays tinyint — Any completed instance older than the (live hours) + (live days) will be deleted along with all associated data.</span></span> <span data-ttu-id="0fe55-116">El intervalo predeterminado es 1 día.</span><span class="sxs-lookup"><span data-stu-id="0fe55-116">Default interval is 1 day.</span></span>  
  
- <span data-ttu-id="0fe55-117">@nHardDeleteDays tinyint — todos los datos (incluso si incompletos) anteriores se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="0fe55-117">@nHardDeleteDays tinyint — All data (even if incomplete) older than this will be deleted.</span></span> <span data-ttu-id="0fe55-118">El intervalo de tiempo especificado para HardDeleteDays debería ser superior a la ventana de actividad de los datos.</span><span class="sxs-lookup"><span data-stu-id="0fe55-118">The time interval specified for HardDeleteDays should be greater than the live window of data.</span></span> <span data-ttu-id="0fe55-119">La ventana de actividad de datos es el intervalo de tiempo durante el cual se desea conservar los datos de seguimiento en la base de datos de seguimiento de BizTalk (BizTalkDTADb).</span><span class="sxs-lookup"><span data-stu-id="0fe55-119">The live window of data is the interval of time for which you want to maintain tracking data in the BizTalk Tracking (BizTalkDTADb) database.</span></span> <span data-ttu-id="0fe55-120">Todo lo que sea anterior a este intervalo cumplirá los requisitos para ser objeto de archivo en el siguiente archivo y, posteriormente, de purga.</span><span class="sxs-lookup"><span data-stu-id="0fe55-120">Anything older than this interval is eligible to be archived at the next archive and then purged.</span></span> <span data-ttu-id="0fe55-121">Valor predeterminado es 30 días.</span><span class="sxs-lookup"><span data-stu-id="0fe55-121">Default is 30 days.</span></span>  
  
  <span data-ttu-id="0fe55-122">Estos parámetros se deben establecer con arreglo a las directivas de retención de datos en un entorno de producción, mientras que una pruebas de laboratorio de rendimiento se recomienda que use valores como sigue:</span><span class="sxs-lookup"><span data-stu-id="0fe55-122">These parameters should be set in accordance with data retention policies in a production environment, whereas in a performance lab tests we recommend that you use values as follows:</span></span>  
  
  <span data-ttu-id="0fe55-123">declarar @dtLastBackup conjunto datetime @dtLastBackup = GetUTCDate()</span><span class="sxs-lookup"><span data-stu-id="0fe55-123">declare @dtLastBackup datetime set @dtLastBackup = GetUTCDate()</span></span>  
  <span data-ttu-id="0fe55-124">exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup</span><span class="sxs-lookup"><span data-stu-id="0fe55-124">exec dtasp_PurgeTrackingDatabase 1, 0, 1, @dtLastBackup</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fe55-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="0fe55-125">See Also</span></span>  
 [<span data-ttu-id="0fe55-126">Cuellos de botella en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="0fe55-126">Bottlenecks in the Database Tier</span></span>](../technical-guides/bottlenecks-in-the-database-tier.md)