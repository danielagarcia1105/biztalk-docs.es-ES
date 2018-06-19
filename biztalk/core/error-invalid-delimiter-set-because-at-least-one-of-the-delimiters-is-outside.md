---
title: Conjunto de delimitadores no válido porque al menos uno de los delimitadores está fuera del intervalo permitido | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c1286559-765b-4728-945d-cf3386e1ba06
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c70722adc1a099d340b862d38574b44391954aa4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241460"
---
# <a name="invalid-delimiter-set-because-at-least-one-of-the-delimiters-is-outside-the-allowed-range"></a><span data-ttu-id="db3a2-102">Grupo de delimitadores no válido porque al menos uno de los delimitadores está fuera del intervalo permitido</span><span class="sxs-lookup"><span data-stu-id="db3a2-102">Invalid delimiter set because at least one of the delimiters is outside the allowed range</span></span>
## <a name="details"></a><span data-ttu-id="db3a2-103">Detalles</span><span class="sxs-lookup"><span data-stu-id="db3a2-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="db3a2-104">Nombre del producto</span><span class="sxs-lookup"><span data-stu-id="db3a2-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="db3a2-105">Versión del producto</span><span class="sxs-lookup"><span data-stu-id="db3a2-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="db3a2-106">Identificador del evento</span><span class="sxs-lookup"><span data-stu-id="db3a2-106">Event ID</span></span>|-|  
|<span data-ttu-id="db3a2-107">Origen del evento</span><span class="sxs-lookup"><span data-stu-id="db3a2-107">Event Source</span></span>|<span data-ttu-id="db3a2-108">EDI de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db3a2-108">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI</span></span>|  
|<span data-ttu-id="db3a2-109">Componente</span><span class="sxs-lookup"><span data-stu-id="db3a2-109">Component</span></span>|<span data-ttu-id="db3a2-110">Motor EDI</span><span class="sxs-lookup"><span data-stu-id="db3a2-110">EDI Engine</span></span>|  
|<span data-ttu-id="db3a2-111">Nombre simbólico</span><span class="sxs-lookup"><span data-stu-id="db3a2-111">Symbolic Name</span></span>|<span data-ttu-id="db3a2-112">DelimiterOutOfRange</span><span class="sxs-lookup"><span data-stu-id="db3a2-112">DelimiterOutOfRange</span></span>|  
|<span data-ttu-id="db3a2-113">Texto del mensaje</span><span class="sxs-lookup"><span data-stu-id="db3a2-113">Message Text</span></span>|<span data-ttu-id="db3a2-114">Grupo de delimitadores {0} no válido; al menos uno de los delimitadores está fuera del intervalo permitido de 0 a 127.</span><span class="sxs-lookup"><span data-stu-id="db3a2-114">Invalid delimiter set {0}, atleast one of the delimiters is outside the allowed range of 0 through 127</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="db3a2-115">Explicación</span><span class="sxs-lookup"><span data-stu-id="db3a2-115">Explanation</span></span>  
 <span data-ttu-id="db3a2-116">Este evento de error,  indica que la canalización de recepción no pudo procesar el intercambio entrante, pues uno o varios separadores del intercambio estaban fuera del intervalo de valores del conjunto de caracteres ASCII.</span><span class="sxs-lookup"><span data-stu-id="db3a2-116">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming interchange because one or more separators in the interchange was outside the range of values in the ASCII character set.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="db3a2-117">Acción del usuario</span><span class="sxs-lookup"><span data-stu-id="db3a2-117">User Action</span></span>  
 <span data-ttu-id="db3a2-118">Para resolver este error, asegúrese de que cada separador del intercambio se encuentra en el conjunto de caracteres ASCII y vuelva a enviar el mensaje.</span><span class="sxs-lookup"><span data-stu-id="db3a2-118">To resolve this error, make sure that each separator in the interchange is in the ASCII character set, and then have the interchange resent.</span></span>