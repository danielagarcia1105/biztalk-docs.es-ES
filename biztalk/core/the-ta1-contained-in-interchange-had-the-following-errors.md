---
title: "El TA1 contenido en el intercambio contenía los errores siguientes | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e2d63fe9-63ef-44b3-8cb9-45a7abf8d0e4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 03bd7486d25e2c94fc809e6dc50c43359c152b70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="the-ta1-contained-in-interchange-had-the-following-errors"></a><span data-ttu-id="261b4-102">El TA1 contenido en el intercambio presentaba los errores siguientes</span><span class="sxs-lookup"><span data-stu-id="261b4-102">The TA1 contained in interchange had the following errors</span></span>
## <a name="details"></a><span data-ttu-id="261b4-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="261b4-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="261b4-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="261b4-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="261b4-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="261b4-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="261b4-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="261b4-106">Event ID</span></span>|-|  
|<span data-ttu-id="261b4-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="261b4-107">Event Source</span></span>|<span data-ttu-id="261b4-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="261b4-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="261b4-109">Componente</span><span class="sxs-lookup"><span data-stu-id="261b4-109">Component</span></span>|<span data-ttu-id="261b4-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="261b4-110">EDI Engine</span></span>|  
|<span data-ttu-id="261b4-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="261b4-111">Symbolic Name</span></span>|<span data-ttu-id="261b4-112">X12TA1Error</span><span class="sxs-lookup"><span data-stu-id="261b4-112">X12TA1Error</span></span>|  
|<span data-ttu-id="261b4-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="261b4-113">Message Text</span></span>|<span data-ttu-id="261b4-114">El {0} TA1 contenido en el intercambio con Id. '{1}', Id. de remitente '{2}', Id. de destinatario '{3}' contenía los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="261b4-114">The {0} TA1 contained in interchange with id '{1}', sender id '{2}', receiver id '{3}' had the following errors:</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="261b4-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="261b4-115">Explanation</span></span>  
 <span data-ttu-id="261b4-116">Este evento de error, advertencia o información indica que la canalización de recepción no pudo procesar la confirmación TA1 entrante debido a la condición de error indicada.</span><span class="sxs-lookup"><span data-stu-id="261b4-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming TA1 acknowledgment because of the indicated error condition.</span></span> <span data-ttu-id="261b4-117">Esto puede indicar que la confirmación no se ajusta a TA1Schema.</span><span class="sxs-lookup"><span data-stu-id="261b4-117">This may indicate that the acknowledgment does not conform to the TA1Schema.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="261b4-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="261b4-118">User Action</span></span>  
 <span data-ttu-id="261b4-119">Para resolver este error, pida al remitente de la confirmación que resuelva el problema que presenta la confirmación, que se asegure de que ésta se ajusta a TA1Schema y que vuelva a enviar la confirmación.</span><span class="sxs-lookup"><span data-stu-id="261b4-119">To resolve this error, have the sender of the acknowledgment resolve the issue with the acknowledgment, ensuring that the acknowledgment conforms to the TA1Schema, and then resend the acknowledgment.</span></span>