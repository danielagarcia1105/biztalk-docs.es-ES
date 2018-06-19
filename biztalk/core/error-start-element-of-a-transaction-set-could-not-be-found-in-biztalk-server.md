---
title: Detectado un error tras procesar conjuntos de transacciones porque no se encontró el elemento de inicio de un conjunto de transacciones | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d5380aee-1632-4cdf-98a1-aff87574ce4f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 224b08046d1733aa8426909d7dddac4b10e48c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241812"
---
# <a name="error-encountered-after-processing-transaction-sets-because-the-start-element-of-a-transaction-set-could-not-be-found"></a><span data-ttu-id="c89f8-102">Se detectó un error tras procesar conjuntos de transacciones porque no se encontró el elemento de inicio de un conjunto de transacciones</span><span class="sxs-lookup"><span data-stu-id="c89f8-102">Error encountered after processing Transaction Set(s) because the Start element of a Transaction set could not be found</span></span>
## <a name="details"></a><span data-ttu-id="c89f8-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c89f8-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c89f8-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c89f8-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c89f8-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c89f8-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c89f8-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c89f8-106">Event ID</span></span>|-|  
|<span data-ttu-id="c89f8-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c89f8-107">Event Source</span></span>|<span data-ttu-id="c89f8-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c89f8-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="c89f8-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c89f8-109">Component</span></span>|<span data-ttu-id="c89f8-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c89f8-110">EDI Engine</span></span>|  
|<span data-ttu-id="c89f8-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c89f8-111">Symbolic Name</span></span>|<span data-ttu-id="c89f8-112">InvalidEfactBiboXmlFormat</span><span class="sxs-lookup"><span data-stu-id="c89f8-112">InvalidEfactBiboXmlFormat</span></span>|  
|<span data-ttu-id="c89f8-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c89f8-113">Message Text</span></span>|<span data-ttu-id="c89f8-114">Se detectó un error tras procesar {0} conjunto(s) de transacciones.</span><span class="sxs-lookup"><span data-stu-id="c89f8-114">Error encountered after processing {0} Transaction Set(s).</span></span> <span data-ttu-id="c89f8-115">No se pudo encontrar el elemento de inicio de un conjunto de transacciones.</span><span class="sxs-lookup"><span data-stu-id="c89f8-115">Start element of a Transaction set could not be found.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c89f8-116">Explicación</span><span class="sxs-lookup"><span data-stu-id="c89f8-116">Explanation</span></span>  
 <span data-ttu-id="c89f8-117">Este evento de error,  indica que la canalización de recepción de EDI no pudo procesar un conjunto de transacciones entrante porque la canalización de recepción no encontró el encabezado ST o UNH.</span><span class="sxs-lookup"><span data-stu-id="c89f8-117">This Error/Warning/Information event indicates that the EDI receive pipeline could not process an incoming transaction set because the receive pipeline could not find the ST or UNH header.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c89f8-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c89f8-118">User Action</span></span>  
 <span data-ttu-id="c89f8-119">Para resolver este error, póngase en contacto con el remitente del intercambio y pídale que se asegure de que el conjunto de transacciones con error comience por un segmento ST01 o UNH 1.</span><span class="sxs-lookup"><span data-stu-id="c89f8-119">To resolve this error, contact the sender of the interchange, and have them ensure that the transaction set in error begins with an ST01 or UNH1 segment.</span></span>