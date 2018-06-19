---
title: Número de segmentos incluidos no coincide. | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c868de02-fda7-4d84-be50-2c08cde0450c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01878c11c8464968b31a7f34ff75b5b494309f90
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263420"
---
# <a name="number-of-included-segments-do-not-match"></a><span data-ttu-id="c7933-102">El número de segmentos incluidos no coincide.</span><span class="sxs-lookup"><span data-stu-id="c7933-102">Number of included segments do not match</span></span>
## <a name="details"></a><span data-ttu-id="c7933-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="c7933-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="c7933-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="c7933-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="c7933-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="c7933-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="c7933-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="c7933-106">Event ID</span></span>|-|  
|<span data-ttu-id="c7933-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="c7933-107">Event Source</span></span>|<span data-ttu-id="c7933-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7933-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="c7933-109">Componente</span><span class="sxs-lookup"><span data-stu-id="c7933-109">Component</span></span>|<span data-ttu-id="c7933-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="c7933-110">EDI Engine</span></span>|  
|<span data-ttu-id="c7933-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="c7933-111">Symbolic Name</span></span>|<span data-ttu-id="c7933-112">X12TsIncludedSegCountMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="c7933-112">X12TsIncludedSegCountMismatchDescription</span></span>|  
|<span data-ttu-id="c7933-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="c7933-113">Message Text</span></span>|<span data-ttu-id="c7933-114">El número de segmentos incluidos no coincide.</span><span class="sxs-lookup"><span data-stu-id="c7933-114">Number of included segments do not match</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="c7933-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="c7933-115">Explanation</span></span>  
 <span data-ttu-id="c7933-116">Este evento de error,  indica que el número de segmentos del conjunto de transacciones del intercambio X12 no es igual al número del finalizador del conjunto de transacciones (campo SE01).</span><span class="sxs-lookup"><span data-stu-id="c7933-116">This Error/Warning/Information event indicates that the number of segments in the transaction set of the X12 interchange does not equal the number in the transaction set trailer (SE01 field).</span></span> <span data-ttu-id="c7933-117">Esto tiene lugar cuando el intercambio se conserva y se suspende al producirse un error.</span><span class="sxs-lookup"><span data-stu-id="c7933-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c7933-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="c7933-118">User Action</span></span>  
 <span data-ttu-id="c7933-119">Para resolver este error, asegúrese de que el número que aparece en el campo SE01 del finalizador de intercambio es el mismo que el número de segmentos del conjunto de transacciones y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="c7933-119">To resolve this error, make sure that the number in the SE01 field of the interchange trailer is the same as the number of segments in the transaction set, and then resend the interchange.</span></span>