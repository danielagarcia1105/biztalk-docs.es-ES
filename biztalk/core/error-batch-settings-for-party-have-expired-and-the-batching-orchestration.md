---
title: La configuración de lote para la entidad ha caducado y la orquestación por lotes está finalizando | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a2f272b6-4da2-4736-8d61-ce48359f36dd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 471d42035f0c8c279fd25e8bb5ba480f7e0f962a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990061"
---
# <a name="the-batch-settings-for-party-have-expired-and-the-batching-orchestration-is-being-terminated"></a><span data-ttu-id="697c8-102">La configuración de lotes de la entidad ha caducado y la orquestación de procesamiento por lotes está finalizando</span><span class="sxs-lookup"><span data-stu-id="697c8-102">The batch settings for party have expired and the batching orchestration is being terminated</span></span>
## <a name="details"></a><span data-ttu-id="697c8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="697c8-103">Details</span></span>  
  
|                 |                                                                                                                                                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="697c8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="697c8-104">Product Name</span></span>   |                                                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                                   |
| <span data-ttu-id="697c8-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="697c8-105">Product Version</span></span> |                                                              [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                                               |
|    <span data-ttu-id="697c8-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="697c8-106">Event ID</span></span>     |                                                                                           -                                                                                           |
|  <span data-ttu-id="697c8-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="697c8-107">Event Source</span></span>   |                                                <span data-ttu-id="697c8-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="697c8-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>                                                 |
|    <span data-ttu-id="697c8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="697c8-109">Component</span></span>    |                                                                                    <span data-ttu-id="697c8-110">Motor de procesamiento por lotes</span><span class="sxs-lookup"><span data-stu-id="697c8-110">Batching Engine</span></span>                                                                                    |
|  <span data-ttu-id="697c8-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="697c8-111">Symbolic Name</span></span>  |                                                                                 <span data-ttu-id="697c8-112">BatchSettingsExpired</span><span class="sxs-lookup"><span data-stu-id="697c8-112">BatchSettingsExpired</span></span>                                                                                  |
|  <span data-ttu-id="697c8-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="697c8-113">Message Text</span></span>   | <span data-ttu-id="697c8-114">La configuración de lotes para la entidad {0} han expirado y la orquestación por lotes está finalizando.</span><span class="sxs-lookup"><span data-stu-id="697c8-114">The batch settings for party {0} have expired and the batching orchestration is being terminated.</span></span> <span data-ttu-id="697c8-115">No se generarán más lotes hasta que se haya habilitado el procesamiento por lotes para esta entidad</span><span class="sxs-lookup"><span data-stu-id="697c8-115">Further batches will not be generated till the batching is activated for this party</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="697c8-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="697c8-116">Explanation</span></span>  
 <span data-ttu-id="697c8-117">Esta advertencia indica que la instancia de orquestación por lotes se ha desactivado por haberse alcanzado el final del intervalo de activación.</span><span class="sxs-lookup"><span data-stu-id="697c8-117">This Warning indicates that the batching orchestration instance has been deactivated because the end of the activation range has been reached.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="697c8-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="697c8-118">User Action</span></span>  
 <span data-ttu-id="697c8-119">Para resolver este error, realice al procedimiento siguiente para reiniciar el proceso por lotes:</span><span class="sxs-lookup"><span data-stu-id="697c8-119">To resolve this error, restart the batching process by doing the following:</span></span>  
  
1.  <span data-ttu-id="697c8-120">Abra la consola de administración de BizTalk Server y vaya a la página Configuración de creación de lotes de intercambio del cuadro de diálogo Propiedades de EDI.</span><span class="sxs-lookup"><span data-stu-id="697c8-120">Open the BizTalk Server Administration Console, and move to the Interchange Batch Creation Settings Page of the EDI Properties dialog box.</span></span>  
  
2.  <span data-ttu-id="697c8-121">Restablecer los criterios de finalización y, a continuación, reinicie la orquestación, haga clic en **iniciar**.</span><span class="sxs-lookup"><span data-stu-id="697c8-121">Reset the end criteria, and then restart the orchestration by clicking **Start**.</span></span>  
  
3.  <span data-ttu-id="697c8-122">Si la fecha y hora de inicio es anterior a la hora al hacer clic en **iniciar**, haga clic en **Sí** para actualizar la fecha y hora de inicio a la fecha y hora actual.</span><span class="sxs-lookup"><span data-stu-id="697c8-122">If the Start datetime is prior to the time when you clicked **Start**, click **Yes** to update the Start datetime to the current datetime.</span></span>