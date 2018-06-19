---
title: Eliminar datos adjuntos huérfanos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- maintaining databases, deleting orphaned attachments
- databases, deleting orphaned attachments
- attachments
ms.assetid: 38280464-9c9d-4890-9fc5-4b8031dd3f88
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7660182793cc82ac938f0dd25011a7c4ad7d7e9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209996"
---
# <a name="deleting-orphan-attachments"></a><span data-ttu-id="a50fd-102">Eliminar datos adjuntos huérfanos</span><span class="sxs-lookup"><span data-stu-id="a50fd-102">Deleting Orphan Attachments</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="a50fd-103">[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] almacena los datos adjuntos de los mensajes recibidos.</span><span class="sxs-lookup"><span data-stu-id="a50fd-103"> [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] stores attachments for received messages.</span></span> <span data-ttu-id="a50fd-104">En ciertas circunstancias, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] guarda los datos adjuntos, pero elimina el mensaje asociado de la tabla MessagesToLOB, lo que da lugar a un archivo adjunto huérfano.</span><span class="sxs-lookup"><span data-stu-id="a50fd-104">In certain circumstances, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] saves the attachment, but deletes the associated message from the MessagesToLOB table, resulting in an orphan attachment.</span></span> <span data-ttu-id="a50fd-105">Esto puede ocurrir cuando se envía un mensaje que incluya un archivo adjunto y tiene un manifiesto que no es válido, por ejemplo, un manifiesto en qué NumberOfAttachments = 0.</span><span class="sxs-lookup"><span data-stu-id="a50fd-105">This can occur when you submit a message that has an attachment and has a manifest that is not valid, for example, a manifest in which NumberOfAttachments = 0.</span></span> <span data-ttu-id="a50fd-106">Periódicamente, puede que desee eliminar datos adjuntos de huérfanos para mantener el rendimiento del sistema.</span><span class="sxs-lookup"><span data-stu-id="a50fd-106">Periodically, you may want to delete orphan attachments to maintain system performance.</span></span>  
  
## <a name="how-to-delete-orphan-attachments"></a><span data-ttu-id="a50fd-107">Cómo eliminar datos adjuntos huérfanos</span><span class="sxs-lookup"><span data-stu-id="a50fd-107">How to Delete Orphan Attachments</span></span>  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="a50fd-108">almacena los datos adjuntos en la tabla de datos adjuntos de la base de datos BTARNDATA.</span><span class="sxs-lookup"><span data-stu-id="a50fd-108"> stores attachments in the Attachments table of the BTARNDATA database.</span></span> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]<span data-ttu-id="a50fd-109">almacena los mensajes asociados en la tabla MessagesToLOB.</span><span class="sxs-lookup"><span data-stu-id="a50fd-109"> stores the associated messages in the MessagesToLOB table.</span></span> <span data-ttu-id="a50fd-110">Datos adjuntos huérfanos se produce cuando los datos adjuntos tienen un `outMessageID` propiedad que no se corresponde con el `MessageID` propiedad de un mensaje en la tabla MessagesToLOB.</span><span class="sxs-lookup"><span data-stu-id="a50fd-110">An orphan attachment results when the attachment has an `outMessageID` property that does not correspond to the `MessageID` property of a message in the MessagesToLOB table.</span></span>  
  
 <span data-ttu-id="a50fd-111">Periódicamente, puede que desee eliminar datos adjuntos de la tabla mediante un procedimiento almacenado que elimina solo los datos adjuntos que no tienen un mensaje correspondiente en la tabla MessagesToLOB.</span><span class="sxs-lookup"><span data-stu-id="a50fd-111">Periodically, you may want to delete attachments from the table by using a stored procedure that deletes only those attachments that do not have a corresponding message in the MessagesToLOB table.</span></span> <span data-ttu-id="a50fd-112">Es un ejemplo de la instrucción SQL para el procedimiento almacenado:</span><span class="sxs-lookup"><span data-stu-id="a50fd-112">A sample SQL statement for the stored procedure is:</span></span>  
  
```  
delete from attachments where outMessageID not in (select messageid from messagestolob)  
```  
  
 <span data-ttu-id="a50fd-113">Además, se recomienda que elimine los datos adjuntos que son anteriores a un período determinado y no requieren una investigación más.</span><span class="sxs-lookup"><span data-stu-id="a50fd-113">Additionally, it is recommended that you delete attachments that are older than a certain period, and do not require any more investigation.</span></span> <span data-ttu-id="a50fd-114">La tabla de datos adjuntos contiene un `TimeCreated` propiedad que puede usar para eliminar antiguos archivos adjuntos.</span><span class="sxs-lookup"><span data-stu-id="a50fd-114">The Attachments table contains a `TimeCreated` property that you can use to delete old attachments.</span></span> <span data-ttu-id="a50fd-115">Este proceso es similar al proceso utilizado para eliminar resúmenes anteriores.</span><span class="sxs-lookup"><span data-stu-id="a50fd-115">This process is similar to the process used to delete old digests.</span></span> <span data-ttu-id="a50fd-116">Para una instrucción SQL de ejemplo para un procedimiento almacenado que elimina el antiguos resúmenes, consulte [eliminar resúmenes](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md).</span><span class="sxs-lookup"><span data-stu-id="a50fd-116">For a sample SQL statement for a stored procedure that deletes old digests, see [Deleting Digests](../../adapters-and-accelerators/accelerator-rosettanet/deleting-digests.md).</span></span>  
  
 <span data-ttu-id="a50fd-117">También se recomienda que se puede indizar los datos adjuntos y MessagestoLOB tablas en las columnas respectivas de MessageID.</span><span class="sxs-lookup"><span data-stu-id="a50fd-117">It is also recommended that you index the Attachments and MessagestoLOB tables on the respective MessageID columns.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a50fd-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="a50fd-118">See Also</span></span>  
 [<span data-ttu-id="a50fd-119">Mantener bases de datos BTARN</span><span class="sxs-lookup"><span data-stu-id="a50fd-119">Maintaining BTARN Databases</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/maintaining-btarn-databases.md)