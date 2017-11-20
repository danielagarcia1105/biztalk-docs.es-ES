---
title: Detectado un error tras procesar conjuntos de transacciones porque DocType sin definir. | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a323658c-77d8-4059-aa15-d88c08e5450d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 874b0229eecdd5fe9c046f69789c4708b9280031
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-after-processing-transaction-sets-because-doctype-was-not-set"></a><span data-ttu-id="c016c-102">Se detectó un error tras procesar conjunto(s) de transacciones porque DocType está sin definir</span><span class="sxs-lookup"><span data-stu-id="c016c-102">Error encountered after processing Transaction Set(s) because DocType was not set</span></span>
## <a name="details"></a><span data-ttu-id="c016c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c016c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c016c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c016c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c016c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c016c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c016c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c016c-106">Event ID</span></span>|-|  
|<span data-ttu-id="c016c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c016c-107">Event Source</span></span>|<span data-ttu-id="c016c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c016c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="c016c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c016c-109">Component</span></span>|<span data-ttu-id="c016c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c016c-110">EDI Engine</span></span>|  
|<span data-ttu-id="c016c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c016c-111">Symbolic Name</span></span>|<span data-ttu-id="c016c-112">DocTypeNotSet</span><span class="sxs-lookup"><span data-stu-id="c016c-112">DocTypeNotSet</span></span>|  
|<span data-ttu-id="c016c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c016c-113">Message Text</span></span>|<span data-ttu-id="c016c-114">Se detectó un error tras procesar {0} conjunto(s) de transacciones.</span><span class="sxs-lookup"><span data-stu-id="c016c-114">Error encountered after processing {0} Transaction Set(s).</span></span> <span data-ttu-id="c016c-115">DocType sin definir.</span><span class="sxs-lookup"><span data-stu-id="c016c-115">DocType was not set</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c016c-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="c016c-116">Explanation</span></span>  
 <span data-ttu-id="c016c-117">Este evento de error,  indica que la canalización de recepción EDI no pudo procesar un conjunto de transacciones entrante porque ST01 (para intercambios X12) o UNH2.1 (para intercambios EDIFACT) no estaba configurado para el conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="c016c-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming transaction set because ST01 (for an X12 interchange) or UNH2.1 (for an EDIFACT interchange) was not set for the transaction set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c016c-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c016c-118">User Action</span></span>  
 <span data-ttu-id="c016c-119">Para resolver este error, compruebe que el segmento ST01 o UNH1 para el conjunto de transacciones con error está configurado en un tipo de documento válido.</span><span class="sxs-lookup"><span data-stu-id="c016c-119">To resolve this error, verify that the ST01 or UNH1 segment for the transaction set in error is set to a valid document type.</span></span>