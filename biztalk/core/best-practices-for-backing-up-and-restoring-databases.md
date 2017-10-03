---
title: "Prácticas recomendadas para realizar copias de seguridad y restaurar bases de datos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- best practices, maintaining
- restoring, best practices
- best practices, backing up
- backing up, restoring
- backing up, best practices
- maintaining, best practices
- best practices, restoring
ms.assetid: 649ca56b-3cc1-49ad-9f74-ba1521e65ee1
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2543f09c5118e58bd18ea2add113811fb733d884
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="best-practices-for-backing-up-and-restoring-databases"></a><span data-ttu-id="eaab9-102">Prácticas recomendadas para realizar copia de seguridad y restaurar las bases de datos</span><span class="sxs-lookup"><span data-stu-id="eaab9-102">Best Practices for Backing Up and Restoring Databases</span></span>
<span data-ttu-id="eaab9-103">Revise las siguientes prácticas recomendadas para garantizar la posibilidad de llevar a cabo una copia de seguridad de las bases de datos de BizTalk Server, así como de restaurarlas.</span><span class="sxs-lookup"><span data-stu-id="eaab9-103">Review the following best practices to help ensure that you can backup and restore your BizTalk Server databases.</span></span>  
  
-   <span data-ttu-id="eaab9-104">**Desarrollar la copia de seguridad y estrategias de restauración y se prueban.**</span><span class="sxs-lookup"><span data-stu-id="eaab9-104">**Develop backup and restore strategies and test them.**</span></span>  
  
     <span data-ttu-id="eaab9-105">Con un buen plan, es posible recuperar los datos con rapidez si se pierden a causa de un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="eaab9-105">With a good plan, you can quickly recover your data if it is lost due to hardware failure.</span></span>  
  
-   <span data-ttu-id="eaab9-106">**Administrar espacio en disco y archivar archivos de copia de seguridad anteriores.**</span><span class="sxs-lookup"><span data-stu-id="eaab9-106">**Manage disk space and archive previous backup files.**</span></span>  
  
     <span data-ttu-id="eaab9-107">El trabajo de copia de seguridad de BizTalk Server no elimina archivos de copia de seguridad obsoletos, por lo que la administración de este tipo de archivos resulta necesaria para conservar espacio en disco.</span><span class="sxs-lookup"><span data-stu-id="eaab9-107">The Backup BizTalk Server job does not delete outdated backup files, so you need to manage those backup files to conserve disk space.</span></span> <span data-ttu-id="eaab9-108">Después de crear una nueva copia de seguridad completa de las bases de datos, debería mover los archivos de copia de seguridad obsoletos a un dispositivo de almacenamiento de archivado para recuperar espacio en el disco principal.</span><span class="sxs-lookup"><span data-stu-id="eaab9-108">After you have created a new full backup of your databases, you should move the outdated backup files onto an archival storage device to reclaim space on the primary disk.</span></span>  
  
-   <span data-ttu-id="eaab9-109">**No almacene las copias de seguridad en el mismo equipo o disco que copia de seguridad.**</span><span class="sxs-lookup"><span data-stu-id="eaab9-109">**Do not store backups on the same computer or disk that you are backing up.**</span></span>  
  
     <span data-ttu-id="eaab9-110">Debe especificar un equipo o un disco para la copia de seguridad distinto del equipo en el que se encuentren los datos originales.</span><span class="sxs-lookup"><span data-stu-id="eaab9-110">You should specify a computer or disk for your backup that is different from the computer with the original data.</span></span> <span data-ttu-id="eaab9-111">De lo contrario, perderá todos los datos si se produce un error de hardware.</span><span class="sxs-lookup"><span data-stu-id="eaab9-111">Otherwise, you will lose all of your data if the hardware fails.</span></span>  
  
-   <span data-ttu-id="eaab9-112">**Conservar copias.**</span><span class="sxs-lookup"><span data-stu-id="eaab9-112">**Retain copies.**</span></span>  
  
     <span data-ttu-id="eaab9-113">Conserve al menos tres copias de los medios.</span><span class="sxs-lookup"><span data-stu-id="eaab9-113">Keep at least three copies of the media.</span></span> <span data-ttu-id="eaab9-114">Conserve, como mínimo, una copia fuera de las instalaciones, en un entorno sometido a un control adecuado.</span><span class="sxs-lookup"><span data-stu-id="eaab9-114">Keep at least one copy off-site in a properly controlled environment.</span></span>  
  
-   <span data-ttu-id="eaab9-115">**Realizar restauraciones de prueba.**</span><span class="sxs-lookup"><span data-stu-id="eaab9-115">**Perform trial restorations.**</span></span>  
  
     <span data-ttu-id="eaab9-116">Efectúe una restauración de prueba al menos una vez al mes para comprobar que la copia de seguridad de los archivos se realiza correctamente.</span><span class="sxs-lookup"><span data-stu-id="eaab9-116">Perform a trial restoration at least once a month to verify that your files were properly backed up.</span></span> <span data-ttu-id="eaab9-117">La restauración de prueba puede revelar problemas de hardware que no se detectan al comprobar que el software funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="eaab9-117">A trial restoration can uncover hardware problems that do not show up when you verify that your software is functioning properly.</span></span> <span data-ttu-id="eaab9-118">No espere a que se produzca un error del disco duro para ver si es posible restaurar el sistema y las bases de datos.</span><span class="sxs-lookup"><span data-stu-id="eaab9-118">Do not wait until your hard disk fails to see if you can restore your system and databases.</span></span>  
  
-   <span data-ttu-id="eaab9-119">**Proteger los dispositivos y medios.**</span><span class="sxs-lookup"><span data-stu-id="eaab9-119">**Secure devices and media.**</span></span>  
  
     <span data-ttu-id="eaab9-120">Proteja los dispositivos de almacenamiento y los medios de copia de seguridad.</span><span class="sxs-lookup"><span data-stu-id="eaab9-120">Secure both the storage device and the backup media.</span></span> <span data-ttu-id="eaab9-121">Una persona puede obtener acceso a los datos de un medio robado si los restaura en un servidor del que sea administrador.</span><span class="sxs-lookup"><span data-stu-id="eaab9-121">It is possible for someone to access the data from a stolen medium by restoring the data to another server for which they are an administrator.</span></span>  
  
-   <span data-ttu-id="eaab9-122">**Proceso de restauración y supervisar la copia de seguridad.**</span><span class="sxs-lookup"><span data-stu-id="eaab9-122">**Monitor the backup and restore process.**</span></span>  
  
     <span data-ttu-id="eaab9-123">Para asegurarse de que el proceso de restauración y de copia de seguridad se realiza correctamente, debería supervisar los trabajos del Agente SQL Server utilizados para realizar una copia de seguridad del servidor BizTalk Server y su restauración.</span><span class="sxs-lookup"><span data-stu-id="eaab9-123">To ensure that the backup and restore process was successful, you should monitor the SQL Server Agent jobs used to backup and restore BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaab9-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="eaab9-124">See Also</span></span>  
 [<span data-ttu-id="eaab9-125">Copia de seguridad y restaurar las bases de datos de servidor BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="eaab9-125">Backing Up and Restoring the BizTalk Server Databases</span></span>](../core/backing-up-and-restoring-the-biztalk-server-databases.md)