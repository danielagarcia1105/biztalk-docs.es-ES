---
title: Cómo identificar cuellos de botella en la base de datos de importación principal de BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0372f1f1-d892-4f7d-b6c4-e0f2b5a02f1c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 613bfa623110a4792894da71365c1a40d7856c15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37003629"
---
# <a name="how-to-identify-bottlenecks-in-the-bam-primary-import-database"></a><span data-ttu-id="a3b5d-102">Cómo identificar cuellos de botella en la base de datos de importación principal de BAM</span><span class="sxs-lookup"><span data-stu-id="a3b5d-102">How to Identify Bottlenecks in the BAM Primary Import Database</span></span>
<span data-ttu-id="a3b5d-103">Para identificar cuellos de botella en la base de datos de supervisión de la actividad económica (BAM), realice los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="a3b5d-103">To identify bottlenecks in the Business Activity Monitoring (BAM) database, perform the following steps:</span></span>  
  
1. <span data-ttu-id="a3b5d-104">Asegúrese de que el número de instancias activas no aumente.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-104">Ensure that the Active Instances count is not climbing.</span></span>  
  
2. <span data-ttu-id="a3b5d-105">Asegúrese de que servicio del Agente SQL está en ejecución.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-105">Ensure that the SQL-Agent Service is running.</span></span>  
  
3. <span data-ttu-id="a3b5d-106">Si está configurado el análisis OLAP, asegúrese de que el BAM_AN_\<activityname\> trabajo se ejecute a intervalos periódicos.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-106">If OLAP Analysis is configured, ensure that the BAM_AN_\<activityname\> job is running at periodic intervals.</span></span>  
  
4. <span data-ttu-id="a3b5d-107">Asegúrese de que BAM_DM_\<activityname\> trabajo (Mantenimiento de datos) está programado para ejecutarse a intervalos periódicos.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-107">Ensure that BAM_DM_\<activityname\> (Data Maintenance) job is scheduled to run at periodic intervals.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a3b5d-108">En la actividad de base de datos BAM de escenarios de uso elevado puede afectar al rendimiento de otras bases de datos de BizTalk Server, lo que afectará el rendimiento general de BizTalk Server.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-108">In high usage scenarios BAM database activity can impact the performance of other BizTalk Server databases, which will affect overall BizTalk Server performance.</span></span> <span data-ttu-id="a3b5d-109">En este caso, tenga en cuenta las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="a3b5d-109">In this case consider taking the following actions:</span></span>  
   > 
   > - <span data-ttu-id="a3b5d-110">Considere la posibilidad de reducir la duración de todas las actividades BAM desde el valor predeterminado (6 meses) a 1 mes o menos.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-110">Consider decreasing the duration of all BAM activities from the default value (6 months) to 1 month or less.</span></span> <span data-ttu-id="a3b5d-111">Esto reducirá el período de tiempo para que los datos BAM se mantienen en la base de datos BAMPrimaryImport antes de archivarse.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-111">This will reduce the time period for which BAM data is maintained in the BAMPrimaryImport database before being archived.</span></span> <span data-ttu-id="a3b5d-112">Use la utilidad de administración de BAM `set-activitywindow` comando para modificar la duración de las actividades de BAM.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-112">Use the BAM Management Utility `set-activitywindow` command to modify the duration of BAM activities.</span></span> <span data-ttu-id="a3b5d-113">Para obtener más información sobre la administración de actividades de la utilidad de administración de BAM Consulte comandos [comandos de administración de la actividad](http://go.microsoft.com/fwlink/?LinkId=210417) (http://go.microsoft.com/fwlink/?LinkId=210417).</span><span class="sxs-lookup"><span data-stu-id="a3b5d-113">For more information about the BAM Management Utility activity management commands see [Activity Management Commands](http://go.microsoft.com/fwlink/?LinkId=210417) (http://go.microsoft.com/fwlink/?LinkId=210417).</span></span>  
   >   -   <span data-ttu-id="a3b5d-114">Mover la base de datos de archivo de BAM a una instancia de SQL Server que no hospeda las bases de datos de BizTalk MessageBox.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-114">Move the BAM Archive database to an instance of SQL Server that does not host any BizTalk MessageBox databases.</span></span> <span data-ttu-id="a3b5d-115">Esto impedirá que estas bases de datos de la competencia por los recursos y mejorar el rendimiento general.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-115">This will prevent these databases from competing for resources and improve overall performance.</span></span>  
  
5. <span data-ttu-id="a3b5d-116">Usar un host dedicado para el seguimiento y medir el contador de rendimiento de longitud de cola de Host con la carga.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-116">Use a dedicated host for tracking and measure the Host Queue Length performance counter when under load.</span></span>  
  
6. <span data-ttu-id="a3b5d-117">Compruebe el contador de rendimiento de tamaño de tabla de cola de impresión para una tendencia en aumento con el tiempo.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-117">Check the Spool Table size performance counter for an increasing trend over time.</span></span>  
  
7. <span data-ttu-id="a3b5d-118">Comprobación de la duración de ejecución del trabajo de archivo y purga de largos tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-118">Check the Archive/Purge job execution duration for long execution times.</span></span>  
  
8. <span data-ttu-id="a3b5d-119">Compruebe la capacidad de respuesta del disco (disco en segundos por contador de rendimiento de lectura/escritura) en el disco que hospeda la base de datos de seguimiento de BizTalk.</span><span class="sxs-lookup"><span data-stu-id="a3b5d-119">Check disk responsiveness (Disk Seconds per Read/Write performance counter) on the disk hosting the BizTalk Tracking database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b5d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3b5d-120">See Also</span></span>  
 [<span data-ttu-id="a3b5d-121">Cuellos de botella en el nivel de base de datos</span><span class="sxs-lookup"><span data-stu-id="a3b5d-121">Bottlenecks in the Database Tier</span></span>](../technical-guides/bottlenecks-in-the-database-tier.md)