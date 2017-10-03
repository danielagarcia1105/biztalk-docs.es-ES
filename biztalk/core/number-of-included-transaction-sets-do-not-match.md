---
title: "Número de conjuntos de transacciones incluidos no coincide. | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: db958803-4667-4558-81a6-70c62d6fe8bf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16a28544757c3e9ae75dd7230673c4526fc2c8f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="number-of-included-transaction-sets-do-not-match"></a><span data-ttu-id="f1c9c-102">El número de conjuntos de transacciones incluidos no coincide.</span><span class="sxs-lookup"><span data-stu-id="f1c9c-102">Number of included transaction sets do not match</span></span>
## <a name="details"></a><span data-ttu-id="f1c9c-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="f1c9c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f1c9c-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="f1c9c-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f1c9c-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="f1c9c-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f1c9c-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="f1c9c-106">Event ID</span></span>|-|  
|<span data-ttu-id="f1c9c-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="f1c9c-107">Event Source</span></span>|<span data-ttu-id="f1c9c-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1c9c-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="f1c9c-109">Componente</span><span class="sxs-lookup"><span data-stu-id="f1c9c-109">Component</span></span>|<span data-ttu-id="f1c9c-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="f1c9c-110">EDI Engine</span></span>|  
|<span data-ttu-id="f1c9c-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="f1c9c-111">Symbolic Name</span></span>|<span data-ttu-id="f1c9c-112">X12FaNumberOfTsMismatchDescription</span><span class="sxs-lookup"><span data-stu-id="f1c9c-112">X12FaNumberOfTsMismatchDescription</span></span>|  
|<span data-ttu-id="f1c9c-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="f1c9c-113">Message Text</span></span>|<span data-ttu-id="f1c9c-114">El número de conjuntos de transacciones incluidos no coincide.</span><span class="sxs-lookup"><span data-stu-id="f1c9c-114">Number of included transaction sets do not match</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f1c9c-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="f1c9c-115">Explanation</span></span>  
 <span data-ttu-id="f1c9c-116">Este evento de error, advertencia o información indica que el número de conjuntos de transacciones del grupo del intercambio X12 no es igual al número del finalizador de grupo (campo GE01).</span><span class="sxs-lookup"><span data-stu-id="f1c9c-116">This Error/Warning/Information event indicates that the number of transaction sets in the group of the X12 interchange does not equal the number in the group trailer (GE01 field).</span></span> <span data-ttu-id="f1c9c-117">Esto tiene lugar cuando el intercambio se conserva y se suspende al producirse un error.</span><span class="sxs-lookup"><span data-stu-id="f1c9c-117">This occurs when the interchange is preserved and the interchange is suspended on an error.</span></span> <span data-ttu-id="f1c9c-118">(El mensaje de error no se envía si el intercambio se conserva y los conjuntos de transacciones se suspenden al producirse un error o bien si el intercambio se divide.)</span><span class="sxs-lookup"><span data-stu-id="f1c9c-118">(The error message is not posted if the interchange is preserved and the transaction sets are suspended on an error, or if the interchange is split.)</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f1c9c-119">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="f1c9c-119">User Action</span></span>  
 <span data-ttu-id="f1c9c-120">Para resolver este error, asegúrese de que el número que aparece en el campo GE01 del finalizador de grupo es el mismo que el número de conjuntos de transacciones del intercambio y vuelva a enviar el intercambio.</span><span class="sxs-lookup"><span data-stu-id="f1c9c-120">To resolve this error, make sure that the number in the GE01 field of the group trailer is the same as the number of transaction sets in the group of the interchange, and then resend the interchange.</span></span>