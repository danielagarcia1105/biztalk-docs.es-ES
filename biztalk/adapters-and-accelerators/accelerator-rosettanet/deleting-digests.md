---
title: Eliminar resúmenes | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, digests
- messages, digests
- digests
- databases, deleting digests
- maintaining databases, deleting digests
ms.assetid: bcc7cb11-2f6a-4996-ad50-040d41993e09
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fefa59a7638b7dc4627d5d7a019d753b4f6290b1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206748"
---
# <a name="deleting-digests"></a><span data-ttu-id="91cb3-102">Eliminación de resúmenes</span><span class="sxs-lookup"><span data-stu-id="91cb3-102">Deleting Digests</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="91cb3-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] almacena resúmenes para los mensajes salientes, para que pueda validar el contenido de señal.</span><span class="sxs-lookup"><span data-stu-id="91cb3-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores digests for outgoing messages, so it can validate them against signal content.</span></span> <span data-ttu-id="91cb3-104">Sin embargo, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no elimina los resúmenes de después de la validación.</span><span class="sxs-lookup"><span data-stu-id="91cb3-104">However, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] does not delete the digests after validation.</span></span> <span data-ttu-id="91cb3-105">Periódicamente, puede que desee eliminar estos resúmenes para mantener el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="91cb3-105">Periodically, you may want to delete these digests to maintain system performance.</span></span>  
  
## <a name="when-and-how-to-delete-digests"></a><span data-ttu-id="91cb3-106">Cuándo y cómo eliminar resúmenes</span><span class="sxs-lookup"><span data-stu-id="91cb3-106">When and How to Delete Digests</span></span>  
 <span data-ttu-id="91cb3-107">Resúmenes de se almacenan en la tabla MessageDigestHelper de la base de datos BTARNDATA.</span><span class="sxs-lookup"><span data-stu-id="91cb3-107">Digests are stored in the MessageDigestHelper table of the BTARNDATA database.</span></span> <span data-ttu-id="91cb3-108">Periódicamente, puede que desee eliminar estos resúmenes de la tabla mediante el uso de un procedimiento almacenado que elimina solo los resúmenes que tienen más de un período determinado.</span><span class="sxs-lookup"><span data-stu-id="91cb3-108">Periodically, you may want to delete these digests from the table by using a stored procedure that deletes only those digests that are older than a certain period.</span></span> <span data-ttu-id="91cb3-109">La tabla MessageDigestHelper contiene un `TimeCreated` propiedad que puede usar para este propósito.</span><span class="sxs-lookup"><span data-stu-id="91cb3-109">The MessageDigestHelper table contains a `TimeCreated` property that you can use for this purpose.</span></span>  
  
 <span data-ttu-id="91cb3-110">Crear un procedimiento almacenado con la siguiente instrucción SQL (como modificado para sus fines) y ejecute el procedimiento almacenado para eliminar resúmenes anteriores.</span><span class="sxs-lookup"><span data-stu-id="91cb3-110">Create a stored procedure with the following SQL statement (as modified for your purposes), and run the stored procedure to delete old digests.</span></span> <span data-ttu-id="91cb3-111">Esta declaración de ejemplo elimina todos los resúmenes de más de siete días:</span><span class="sxs-lookup"><span data-stu-id="91cb3-111">This sample statement deletes all digests more than seven days old:</span></span>  
  
```  
delete from MessageDigestHelper where datediff(day, TimeCreated, getutcdate()) > 7  
```  
  
> [!NOTE]
>  <span data-ttu-id="91cb3-112">El procedimiento almacenado debe incluir una llamada a `getutcdate`, no `getdate`, ya que todos los [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] bases de datos utilizan la hora UTC (hora Universal coordinada).</span><span class="sxs-lookup"><span data-stu-id="91cb3-112">The stored procedure must include a call to `getutcdate`, not `getdate`, because all [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] databases use UTC (Universal Time Coordinate) time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91cb3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="91cb3-113">See Also</span></span>  
 [<span data-ttu-id="91cb3-114">Mantener bases de datos BTARN</span><span class="sxs-lookup"><span data-stu-id="91cb3-114">Maintaining BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)