---
title: Número de segmentos incluidos no coincide. | Microsoft Docs
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
ms.openlocfilehash: d0d2b91ba8ddecfe4926cbc21834b239eedc4547
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009389"
---
# <a name="number-of-included-segments-do-not-match"></a><span data-ttu-id="77eba-102">El número de segmentos incluidos no coincide.</span><span class="sxs-lookup"><span data-stu-id="77eba-102">Number of included segments do not match</span></span>
## <a name="details"></a><span data-ttu-id="77eba-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="77eba-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="77eba-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="77eba-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="77eba-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="77eba-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="77eba-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="77eba-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="77eba-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="77eba-107">Event Source</span></span>   | <span data-ttu-id="77eba-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77eba-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span> |
|    <span data-ttu-id="77eba-109">Componente</span><span class="sxs-lookup"><span data-stu-id="77eba-109">Component</span></span>    |                                       <span data-ttu-id="77eba-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="77eba-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="77eba-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="77eba-111">Symbolic Name</span></span>  |                        <span data-ttu-id="77eba-112">X12TsIncludedSegCountMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="77eba-112">X12TsIncludedSegCountMismatchDescription</span></span>                        |
|  <span data-ttu-id="77eba-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="77eba-113">Message Text</span></span>   |                        <span data-ttu-id="77eba-114">El número de segmentos incluidos no coincide.</span><span class="sxs-lookup"><span data-stu-id="77eba-114">Number of included segments do not match</span></span>                        |
  
## <a name="explanation"></a><span data-ttu-id="77eba-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="77eba-115">Explanation</span></span>  
 <span data-ttu-id="77eba-116">Este evento de error,  indica que el número de segmentos del conjunto de transacciones del intercambio X12 no es igual al número del finalizador del conjunto de transacciones (campo SE01).</span><span class="sxs-lookup"><span data-stu-id="77eba-116">This Error/Warning/Information event indicates that the number of segments in the transaction set of the X12 interchange does not equal the number in the transaction set trailer (SE01 field).</span></span> <span data-ttu-id="77eba-117">Esto tiene lugar cuando el intercambio se conserva y se suspende al producirse un error.</span><span class="sxs-lookup"><span data-stu-id="77eba-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="77eba-118">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="77eba-118">User Action</span></span>  
 <span data-ttu-id="77eba-119">Para resolver este error, asegúrese de que el número que aparece en el campo SE01 del finalizador de intercambio es el mismo que el número de segmentos del conjunto de transacciones y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="77eba-119">To resolve this error, make sure that the number in the SE01 field of the interchange trailer is the same as the number of segments in the transaction set, and then resend the interchange.</span></span>