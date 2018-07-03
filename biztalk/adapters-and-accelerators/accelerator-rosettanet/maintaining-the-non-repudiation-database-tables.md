---
title: Mantenimiento de las tablas de base de datos sin repudio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- databases, purging
- databases, non-repudiation database
- maintaining databases, purging
- purging databases
- databases, maintaining
- non-repudiation, database
ms.assetid: 29222510-325b-4cd7-854b-6f548a63fd08
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ceea893a49512167242eb6552e6a23c5a84cd18
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966229"
---
# <a name="maintaining-the-non-repudiation-database-tables"></a><span data-ttu-id="01213-102">Mantenimiento de las tablas de base de datos sin repudio</span><span class="sxs-lookup"><span data-stu-id="01213-102">Maintaining the Non-Repudiation Database Tables</span></span>
<span data-ttu-id="01213-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] almacena los mensajes para fines sin repudio en las tablas MessageStorageIn y MessageStorageOut de la base de datos BTARNArchive.</span><span class="sxs-lookup"><span data-stu-id="01213-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores messages for non-repudiation purposes in the MessageStorageIn and MessageStorageOut tables of the BTARNArchive database.</span></span> <span data-ttu-id="01213-104">Muchos mensajes en estas tablas pueden afectar al rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="01213-104">Many messages in these tables can affect system performance.</span></span> <span data-ttu-id="01213-105">Desea mantener estas tablas de base de datos sin repudio periódicamente purgar y archivar los mensajes de dichas tablas, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="01213-105">You may want to maintain these non-repudiation database tables by periodically purging and archiving messages from these tables, as appropriate.</span></span>  
  
## <a name="routine-database-maintenance"></a><span data-ttu-id="01213-106">Mantenimiento rutinario de la base de datos</span><span class="sxs-lookup"><span data-stu-id="01213-106">Routine Database Maintenance</span></span>  
 <span data-ttu-id="01213-107">Cuando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] recibe un mensaje, siempre se guarda el mensaje en la tabla MessageStorageIn y se establece inicialmente el **ToBePurged** campo "1", lo que indica que el mensaje no requieren un sin repudio.</span><span class="sxs-lookup"><span data-stu-id="01213-107">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receives a message, it always saves the message in the MessageStorageIn table and initially sets the **ToBePurged** field to "1", which indicates that the message does not require non-repudiation.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="01213-108"> a continuación, descifra y descodifica el mensaje para determinar cuál es el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="01213-108"> then decrypts and decodes the message to determine what the agreement is.</span></span> <span data-ttu-id="01213-109">Después de descifrado y la descodificación, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] examina el contrato para ver si debe guardar el mensaje para fines sin repudio.</span><span class="sxs-lookup"><span data-stu-id="01213-109">After decrypting and decoding, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] examines the agreement to see whether it must save the message for non-repudiation purposes.</span></span> <span data-ttu-id="01213-110">Si es así, Establece la **ToBePurged** campo "0" y rellene los demás campos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="01213-110">If so, it sets the **ToBePurged** field to "0" and fills in the other fields of the message.</span></span> <span data-ttu-id="01213-111">Si no, abandona el **ToBePurged** campo como "1" y no rellene los demás campos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="01213-111">If not, it leaves the **ToBePurged** field as "1" and does not fill in the other fields of the message.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="01213-112"> no se elimina automáticamente los mensajes con el **ToBePurged** campo establecido en "1".</span><span class="sxs-lookup"><span data-stu-id="01213-112"> does not automatically delete messages with the **ToBePurged** field set to "1".</span></span> <span data-ttu-id="01213-113">Además, no archiva mensajes guardados para el no rechazo a otras tablas.</span><span class="sxs-lookup"><span data-stu-id="01213-113">In addition, it does not archive messages saved for non-repudiation to other tables.</span></span> <span data-ttu-id="01213-114">Estos dos conjuntos de mensajes pueden acumular en la tabla MessageStorageIn y afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="01213-114">These two sets of messages can build up in the MessageStorageIn table and affect performance.</span></span> <span data-ttu-id="01213-115">Como parte del mantenimiento rutinario en la base de datos, puede hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="01213-115">As part of routine maintenance on the database, you may want to do the following:</span></span>  
  
-   <span data-ttu-id="01213-116">Ejecutar un procedimiento almacenado que contiene el código SQL siguiente instrucción para eliminar todos los mensajes en la tabla MessageStorageIn cuyos **ToBePurged** campo no es igual a "0":</span><span class="sxs-lookup"><span data-stu-id="01213-116">Run a stored procedure containing the following SQL statement to delete all messages in the MessageStorageIn table whose **ToBePurged** field is not equal to "0":</span></span>  
  
    ```  
    delete MessageStorageIn where ToBePurged <> 0  
    ```  
  
-   <span data-ttu-id="01213-117">Después de un período adecuado (puede dictar qué directiva de empresa), ejecute un procedimiento almacenado para archivar los mensajes de rechazo a una base de datos sin conexión que no afectará al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="01213-117">After an appropriate period (which company policy may dictate), run a stored procedure to archive non-repudiation messages to an offline database that will not affect performance.</span></span> <span data-ttu-id="01213-118">Este período se puede determinar mediante el **TimeCreated** campo en la tabla MessageStorageIn.</span><span class="sxs-lookup"><span data-stu-id="01213-118">You can determine this period by using the **TimeCreated** field in the MessageStorageIn table.</span></span> <span data-ttu-id="01213-119">Una vez transcurrido el período de rechazo de un mensaje, puede eliminar el mensaje de la base de datos de archivo mediante el uso de la siguiente instrucción SQL (lo que elimina los mensajes que tienen más de siete días):</span><span class="sxs-lookup"><span data-stu-id="01213-119">After the non-repudiation period for a message has expired, you can delete the message from the archive database by using the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
    ```  
    delete <archive table name> where datediff(d, TimeCreated, GetUTCDATA())>7  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="01213-120">El **TimeCreated** campo en la tabla MessageStorageIn está en formato UTC.</span><span class="sxs-lookup"><span data-stu-id="01213-120">The **TimeCreated** field in the MessageStorageIn table is in UTC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01213-121">No debe eliminar un mensaje entrante que tiene menos de un hora de antigüedad.</span><span class="sxs-lookup"><span data-stu-id="01213-121">You should not delete an incoming message that is less than one hour old.</span></span>  
  
 <span data-ttu-id="01213-122">Cuando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía un mensaje saliente, tiene acceso al acuerdo sin repudio.</span><span class="sxs-lookup"><span data-stu-id="01213-122">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sends an outgoing message, it has access to the non-repudiation agreement.</span></span> <span data-ttu-id="01213-123">Si el contrato requiere sin repudio, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] guarda el mensaje en la tabla MessageStorageOut.</span><span class="sxs-lookup"><span data-stu-id="01213-123">If the agreement requires non-repudiation, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves the message in the MessageStorageOut table.</span></span> <span data-ttu-id="01213-124">Si no es así, no guarda el mensaje en la tabla.</span><span class="sxs-lookup"><span data-stu-id="01213-124">If not, it does not save the message in the table.</span></span> <span data-ttu-id="01213-125">Esto significa que no hay ninguna necesidad de un **ToBePurged** campo en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="01213-125">This means that there is no need for a **ToBePurged** field in this table.</span></span> <span data-ttu-id="01213-126">El mantenimiento solo necesario para la tabla MessageStorageOut consiste en archivar los mensajes de rechazo a una base de datos sin conexión tras un período adecuado, y eliminar cada mensaje después de su período de no repudio ha expirado.</span><span class="sxs-lookup"><span data-stu-id="01213-126">The only maintenance required for the MessageStorageOut table is to archive non-repudiation messages to an offline database after an appropriate period, and to delete each message after its non-repudiation period has expired.</span></span> <span data-ttu-id="01213-127">Puede hacerlo con la siguiente instrucción SQL (lo que elimina los mensajes que tienen más de siete días):</span><span class="sxs-lookup"><span data-stu-id="01213-127">You can do so with the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
```  
delete MessageStorageOut where datediff(d, TimeCreated, GetUTCDATA())>7  
```  
  
## <a name="see-also"></a><span data-ttu-id="01213-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="01213-128">See Also</span></span>  
 <span data-ttu-id="01213-129">[Procesamiento de mensajes RNIF](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="01213-129">[RNIF Message Processing](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span></span>  
 [<span data-ttu-id="01213-130">Administrar la configuración, certificados, bases de datos y seguridad</span><span class="sxs-lookup"><span data-stu-id="01213-130">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)