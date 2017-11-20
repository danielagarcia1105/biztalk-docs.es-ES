---
title: Mantener las tablas de base de datos sin repudio | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- databases, purging
- databases, non-repudiation database
- maintaining databases, purging
- purging databases
- databases, maintaining
- non-repudiation, database
ms.assetid: 29222510-325b-4cd7-854b-6f548a63fd08
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 182172eccddcaad684f35335708dce6027fb111f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="maintaining-the-non-repudiation-database-tables"></a><span data-ttu-id="afddd-102">Mantener las tablas de base de datos sin repudio</span><span class="sxs-lookup"><span data-stu-id="afddd-102">Maintaining the Non-Repudiation Database Tables</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="afddd-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] almacena los mensajes para fines sin repudio en las tablas MessageStorageIn y MessageStorageOut de la base de datos BTARNArchive.</span><span class="sxs-lookup"><span data-stu-id="afddd-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores messages for non-repudiation purposes in the MessageStorageIn and MessageStorageOut tables of the BTARNArchive database.</span></span> <span data-ttu-id="afddd-104">Muchos mensajes en estas tablas pueden afectar al rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="afddd-104">Many messages in these tables can affect system performance.</span></span> <span data-ttu-id="afddd-105">Puede que desee mantener estas tablas de base de datos sin repudio periódicamente purgar y archivar los mensajes de dichas tablas, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="afddd-105">You may want to maintain these non-repudiation database tables by periodically purging and archiving messages from these tables, as appropriate.</span></span>  
  
## <a name="routine-database-maintenance"></a><span data-ttu-id="afddd-106">Mantenimiento rutinario de la base de datos</span><span class="sxs-lookup"><span data-stu-id="afddd-106">Routine Database Maintenance</span></span>  
 <span data-ttu-id="afddd-107">Cuando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] recibe un mensaje, se guarda siempre el mensaje en la tabla MessageStorageIn y se establece inicialmente la **ToBePurged** campo a "1", que indica que el mensaje no requieren un sin repudio.</span><span class="sxs-lookup"><span data-stu-id="afddd-107">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] receives a message, it always saves the message in the MessageStorageIn table and initially sets the **ToBePurged** field to "1", which indicates that the message does not require non-repudiation.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="afddd-108">a continuación, descifra y descodifica el mensaje para determinar cuál es el acuerdo.</span><span class="sxs-lookup"><span data-stu-id="afddd-108"> then decrypts and decodes the message to determine what the agreement is.</span></span> <span data-ttu-id="afddd-109">Después de descifrar y descodificación, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] examina el acuerdo para ver si debe guardar el mensaje para fines sin repudio.</span><span class="sxs-lookup"><span data-stu-id="afddd-109">After decrypting and decoding, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] examines the agreement to see whether it must save the message for non-repudiation purposes.</span></span> <span data-ttu-id="afddd-110">Si es así, Establece el **ToBePurged** campo en "0" y rellene los demás campos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="afddd-110">If so, it sets the **ToBePurged** field to "0" and fills in the other fields of the message.</span></span> <span data-ttu-id="afddd-111">Si no es así, deja el **ToBePurged** campo como "1" y no rellene los demás campos del mensaje.</span><span class="sxs-lookup"><span data-stu-id="afddd-111">If not, it leaves the **ToBePurged** field as "1" and does not fill in the other fields of the message.</span></span>  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="afddd-112">no elimina automáticamente los mensajes con el **ToBePurged** campo establecido en "1".</span><span class="sxs-lookup"><span data-stu-id="afddd-112"> does not automatically delete messages with the **ToBePurged** field set to "1".</span></span> <span data-ttu-id="afddd-113">Además, no archiva mensajes guardados para sin repudio a otras tablas.</span><span class="sxs-lookup"><span data-stu-id="afddd-113">In addition, it does not archive messages saved for non-repudiation to other tables.</span></span> <span data-ttu-id="afddd-114">Estos dos conjuntos de mensajes pueden acumular en la tabla MessageStorageIn y afectar al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="afddd-114">These two sets of messages can build up in the MessageStorageIn table and affect performance.</span></span> <span data-ttu-id="afddd-115">Como parte del mantenimiento rutinario en la base de datos, puede que desee hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="afddd-115">As part of routine maintenance on the database, you may want to do the following:</span></span>  
  
-   <span data-ttu-id="afddd-116">Ejecutar un procedimiento almacenado que contiene el código SQL siguiente instrucción que se va a todos los eliminar mensajes en la tabla MessageStorageIn cuyos **ToBePurged** campo no es igual a "0":</span><span class="sxs-lookup"><span data-stu-id="afddd-116">Run a stored procedure containing the following SQL statement to delete all messages in the MessageStorageIn table whose **ToBePurged** field is not equal to "0":</span></span>  
  
    ```  
    delete MessageStorageIn where ToBePurged <> 0  
    ```  
  
-   <span data-ttu-id="afddd-117">Después de un período adecuado (puede determinar qué directiva de empresa), ejecutar un procedimiento almacenado para archivar los mensajes sin repudio para una base de datos sin conexión que no afectará al rendimiento.</span><span class="sxs-lookup"><span data-stu-id="afddd-117">After an appropriate period (which company policy may dictate), run a stored procedure to archive non-repudiation messages to an offline database that will not affect performance.</span></span> <span data-ttu-id="afddd-118">Este período se puede determinar mediante el **TimeCreated** campo en la tabla MessageStorageIn.</span><span class="sxs-lookup"><span data-stu-id="afddd-118">You can determine this period by using the **TimeCreated** field in the MessageStorageIn table.</span></span> <span data-ttu-id="afddd-119">Una vez transcurrido el período sin repudio para un mensaje, puede eliminar el mensaje de la base de datos de archivo mediante la siguiente instrucción SQL (lo que elimina los mensajes que tienen más de siete días):</span><span class="sxs-lookup"><span data-stu-id="afddd-119">After the non-repudiation period for a message has expired, you can delete the message from the archive database by using the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
    ```  
    delete <archive table name> where datediff(d, TimeCreated, GetUTCDATA())>7  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="afddd-120">El **TimeCreated** campo en la tabla MessageStorageIn está en formato UTC.</span><span class="sxs-lookup"><span data-stu-id="afddd-120">The **TimeCreated** field in the MessageStorageIn table is in UTC.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="afddd-121">No debe eliminar un mensaje entrante que es menos de una hora de antigüedad.</span><span class="sxs-lookup"><span data-stu-id="afddd-121">You should not delete an incoming message that is less than one hour old.</span></span>  
  
 <span data-ttu-id="afddd-122">Cuando [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] envía un mensaje saliente, que tiene acceso al acuerdo sin repudio.</span><span class="sxs-lookup"><span data-stu-id="afddd-122">When [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] sends an outgoing message, it has access to the non-repudiation agreement.</span></span> <span data-ttu-id="afddd-123">Si el contrato requiere sin repudio, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] guarda el mensaje en la tabla MessageStorageOut.</span><span class="sxs-lookup"><span data-stu-id="afddd-123">If the agreement requires non-repudiation, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves the message in the MessageStorageOut table.</span></span> <span data-ttu-id="afddd-124">De lo contrario, no se guarda el mensaje en la tabla.</span><span class="sxs-lookup"><span data-stu-id="afddd-124">If not, it does not save the message in the table.</span></span> <span data-ttu-id="afddd-125">Esto significa que no hay ninguna necesidad de un **ToBePurged** campo en esta tabla.</span><span class="sxs-lookup"><span data-stu-id="afddd-125">This means that there is no need for a **ToBePurged** field in this table.</span></span> <span data-ttu-id="afddd-126">El mantenimiento solo requerido para la tabla MessageStorageOut consiste en archivar mensajes sin repudio para una base de datos sin conexión después de un período adecuado y eliminar todos los mensajes después de su período sin repudio ha expirado.</span><span class="sxs-lookup"><span data-stu-id="afddd-126">The only maintenance required for the MessageStorageOut table is to archive non-repudiation messages to an offline database after an appropriate period, and to delete each message after its non-repudiation period has expired.</span></span> <span data-ttu-id="afddd-127">Puede hacerlo con la siguiente instrucción SQL (lo que elimina los mensajes que tienen más de siete días):</span><span class="sxs-lookup"><span data-stu-id="afddd-127">You can do so with the following SQL statement (which deletes messages that are older than seven days):</span></span>  
  
```  
delete MessageStorageOut where datediff(d, TimeCreated, GetUTCDATA())>7  
```  
  
## <a name="see-also"></a><span data-ttu-id="afddd-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="afddd-128">See Also</span></span>  
 <span data-ttu-id="afddd-129">[Procesamiento de mensajes RNIF](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span><span class="sxs-lookup"><span data-stu-id="afddd-129">[RNIF Message Processing](../../adapters-and-accelerators/accelerator-rosettanet/rnif-message-processing.md) </span></span>  
 [<span data-ttu-id="afddd-130">Administrar la configuración, certificados, las bases de datos y seguridad</span><span class="sxs-lookup"><span data-stu-id="afddd-130">Manage configuration, certificates, databases, and security</span></span>](manage-configuration-certificates-databases-security.md)