---
title: Supervisar el uso de espacio de disco | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ac68022-a9c5-4eb9-8854-cd1ee849282b
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ae87de0b00e70ae03a30dd8ef20ede4a972388d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22298596"
---
# <a name="monitoring-disk-space-usage"></a><span data-ttu-id="5de63-102">Supervisar el uso de espacio en disco</span><span class="sxs-lookup"><span data-stu-id="5de63-102">Monitoring Disk Space Usage</span></span>
<span data-ttu-id="5de63-103">Como parte del proceso de supervisión de preparación operativa de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], supervisar el uso de espacio en disco como sigue:</span><span class="sxs-lookup"><span data-stu-id="5de63-103">As part of the monitoring process for operational readiness of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], monitor the disk space usage as follows:</span></span>  
  
-   <span data-ttu-id="5de63-104">**Determinar el disco espacio necesario.**</span><span class="sxs-lookup"><span data-stu-id="5de63-104">**Determine the disk space required.**</span></span>  
  
     <span data-ttu-id="5de63-105">Al usar archivo o MSMQ enviar / ubicaciones de recepción, asegúrese de que hay espacio suficiente dar cabida a las interrupciones de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de los sistemas de recepción.</span><span class="sxs-lookup"><span data-stu-id="5de63-105">When using File or MSMQ send / receive locations, ensure that there is ample disk space available to accommodate outages of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] or of the receiving systems.</span></span> <span data-ttu-id="5de63-106">Por ejemplo, si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] es escribir archivos en un recurso compartido en una red SAN y el sistema receptor está inactivo durante dos días, determinar si hay suficiente espacio en disco para permitir que los archivos en cola.</span><span class="sxs-lookup"><span data-stu-id="5de63-106">For example, if [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is writing files to a share on a SAN and the receiving system is down for two days, determine whether there is enough disk space to allow the files to queue up.</span></span>  
  
-   <span data-ttu-id="5de63-107">**Limpiar periódicamente el directorio de archivos de copia de seguridad de BizTalk Server.**</span><span class="sxs-lookup"><span data-stu-id="5de63-107">**Clean up the BizTalk Server backup files directory periodically.**</span></span>  
  
     <span data-ttu-id="5de63-108">Puede realizar esta limpieza utilizando una secuencia de comandos que se llama desde un trabajo del Agente SQL Server.</span><span class="sxs-lookup"><span data-stu-id="5de63-108">You can perform this cleanup using a script called from a SQL Server Agent job.</span></span>  
  
-   <span data-ttu-id="5de63-109">**Limpiar periódicamente el directorio de archivos de archivo de base de datos de seguimiento de BizTalk.**</span><span class="sxs-lookup"><span data-stu-id="5de63-109">**Clean up the BizTalk Tracking database archive files directory periodically.**</span></span>  
  
-   <span data-ttu-id="5de63-110">**Asegúrese de que hay suficiente espacio en disco disponible para acomodar la base de datos de BizTalk Server mayor (.mdf) y los archivos de registro (.ldf) de transacciones durante las horas pico del flujo de datos.**</span><span class="sxs-lookup"><span data-stu-id="5de63-110">**Ensure that there is sufficient disk space available to accommodate larger BizTalk Server database (.mdf) and transaction log (.ldf) files during times of peak data flow.**</span></span>